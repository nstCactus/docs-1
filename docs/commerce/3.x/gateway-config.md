# Gateway Configuration

Each Craft Commerce [payment gateway](payment-gateways.md) can be configured in one of several ways.

## Configuring via Control Panel

Once you’ve installed the gateway plugin, it will be available for new gateway configurations in **Commerce** → **Settings** → **Gateways**. Any gateway-specific settings will be displayed for the relevant gateway, in the exact same way Craft CMS displays relevant settings for a new field type.

At minimum, each configured gateway will need a **Name** and a **Handle**—the rest of the settings will depend on which gateway you’re using.

Even if you want to override these settings with one of the static config approaches detailed below, you’ll need to first establish gateways in the control panel so you can reference them by the `handle` you designate for each one.

## Configuring via Gateway Plugin Config

Like any Craft plugin, gateway settings can be specified via a static PHP file in the project’s `config/` directory.

If you were using the Stripe plugin, for example, you’d create `config/commerce-stripe.php` (because `commerce-stripe` is the plugin handle) and use it to return a key-value array of settings:

```php
<?php

use craft\helpers\App;

return [
    'publishableKey' => App::env('STRIPE_PUBLISHABLE_KEY'),
    'apiKey' => App::env('STRIPE_API_KEY'),
    'sendReceiptEmail' => false,
    'signingSecret' => App::env('STRIPE_SIGNING_SECRET'),
];
```

## Configuring via Dependency Injection

The config format above does not support multiple gateway configurations, so if you need to offer more than one configuration per gateway you’ll want to use dependency injection.

For example, let’s pretend we need to support two different sets of Stripe credentials because a store needs payments to go into two different accounts. We have two gateway handles: `stripeA` and `stripeB`.

Add the following to a [custom module](extend/custom-module.md)’s `init()` method:

```php
$gatewaySettings = [
    'stripeA' => [
        'apiKey' => App::env('STRIPE_API_KEY_A'),
        'publishableKey' => App::env('STRIPE_PUBLISHABLE_KEY_A'),
    ],
    'stripeB' => [
        'apiKey' => App::env('STRIPE_API_KEY_B'),
        'publishableKey' => App::env('STRIPE_PUBLISHABLE_KEY_B'),
    ],
];


Craft::$container->set(
    \craft\commerce\stripe\gateways\PaymentIntents::class,
    function($container, $params, $config) use ($gatewaySettings) {
        // Asset Volumes do this
        if (empty($config['id'])) {
            return new \craft\commerce\stripe\gateways\PaymentIntents($config);
        }

        // Merge any relevant gateway settings
        if (in_array($config['handle'], array_keys($gatewaySettings))) {
            $mergedConfig = array_merge($config, $gatewaySettings[$config['handle']]);
            return new \craft\commerce\stripe\gateways\PaymentIntents($mergedConfig);
        }
    }
);
```

## Configuring via `commerce-gateways.php`

::: warning
This configuration format has been deprecated in favor of [dependency injection](#configuring-via-dependency-injection).
:::

You can also override gateway settings in a common `config/commerce-gateways.php` file, where multiple gateway settings are returned by that gateway’s `handle`:

```php
<?php

use craft\helpers\App;

return [
    'ewayGatewayHandle' => [
        'testMode' => App::env('EWAY_TEST_MODE'),
        'apiKey' => App::env('EWAY_API_KEY'),
        'password' => App::env('EWAY_PASSWORD'),
        'CSEKey' => App::env('EWAY_CSE_KEY'),
    ],
    'paypalProGateway' => [
        'testMode' => App::env('PAYPAL_PRO_TEST_MODE'),
        'password' => App::env('PAYPAL_PRO_PASSWORD'),
        'username' => App::env('PAYPAL_PRO_USERNAME'),
        'signature' => App::env('PAYPAL_PRO_SIGNATURE'),
    ],
];
```
