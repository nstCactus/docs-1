---
editLink: false
helpfulVotes: false
home: true
---

# Documentation

This landing page describes the first-party learning materials in the Craftsphere and splits off into documentation for [Craft CMS](/3.x/), [Craft Commerce](/commerce/3.x/), [Craft Nitro](/nitro/), and the [Intro to Craft CMS tutorial](/getting-started-tutorial/).

## Browse Product Documentation

The **documentation** is each product’s user manual, describing its features and how to work with it. It’s for front end developers building sites, and PHP developers extending Craft or Commerce.

<div class="w-full sm:flex sm:-mx-2">
    <LinkPanel title="Craft CMS" subtitle="Flexible content management." link="/3.x/" icon="/docs/icons/craft.svg" />
    <LinkPanel title="Craft Commerce" subtitle="Custom, extensible ecommerce." link="/commerce/3.x/" icon="/docs/icons/commerce.svg" />
</div>

The documentation is organized to be read sequentially, starting with installation and core concepts it continues to build on. It ends with _Extending_ sections to be used as jumping-off points adding to or enhancing Craft or Commerce with your own code. You can jump around however you’d like, but sometimes it helps to work your way down a section in order.

In addition to the documentation, Craft CMS and Craft Commerce each have a separate **class reference** that’s generated from the source code. The class reference is more like a technical schematic, where browsing requires familiarity with the source code’s layout. The documentation frequently links to the class reference as a way to point to the exhaustive, definitive description of the subject.

### IDE Autocompletion

An advanced understanding of Craft requires reading the documentation and reading the code. One of the fastest ways to explore the code is by taking the time to set up autocompletion for your code editor.

Once you’ve configured PhpStorm properly, for example, you can click through live code like a website and get thorough, automatic suggestions for templates and queries and PHP code as you type it.

Further reading:

- [PhpStorm Settings for Craft CMS](https://github.com/craftcms/phpstorm-settings)
- [Auto-Complete Craft CMS 3 APIs in Twig with PhpStorm](https://nystudio107.com/blog/auto-complete-craft-cms-3-apis-in-twig-with-phpstorm)
- [GraphQL Schema Auto-Completion with PhpStorm](https://nystudio107.com/blog/graphql-schema-auto-completion-with-phpstorm)
- [PhpStorm can auto-complete your custom entry field handles](https://twitter.com/nystudio107/status/982268301127532544?lang=en)

## Follow the Tutorial

The tutorial is the best place to start if you’re new to Craft. It doesn’t require development experience and explains how to get started with a code editor, local development environment, and Craft CMS installation to build a simple blog.

<IconLink title="Intro to Craft CMS" subtitle="Learn the fundamentals building a simple blog." link="/getting-started-tutorial/" icon="/docs/icons/icon-tutorial.svg" />

## Clone a Starter

There’s also a starter project with Twig and Gatsby examples if you’d rather spin up a site to investigate.

<div class="w-full sm:flex sm:-mx-2">
    <LinkPanel title="Blog Starter" subtitle="craftcms/starter-blog" link="https://github.com/craftcms/starter-blog" :repo="true" />
</div>

## Visit the Knowledge Base

The Knowledge Base lives at [craftcms.com/knowledge-base](https://craftcms.com/knowledge-base).

Knowledge Base articles are more atomic, each one focusing on a topic that might augment the documentation or answer a common support question. While Knowledge Base articles share common categories and sometimes link to one another other, there’s no overarching structure like there is with the documentation.

## Explore Popular Resources

<div class="sm:flex sm:flex-wrap">
    <div class="py-1 sm:w-1/2 sm:py-0">
        <IconLink title="Knowledge Base"
            subtitle="Read support articles."
            link="https://craftcms.com/knowledge-base"
            icon="/docs/icons/icon-knowledge-base.svg"
            icon-size="large"
        />
    </div>
    <div class="py-1 sm:w-1/2 sm:py-0">
        <IconLink title="Stack Exchange"
            subtitle="Get help and help others."
            link="https://craftcms.stackexchange.com/"
            icon="/docs/icons/icon-stack-exchange.svg"
            icon-size="large"
        />
    </div>
    <div class="py-1 sm:w-1/2 sm:py-0">
        <IconLink title="Discord"
            subtitle="Meet the community."
            link="https://craftcms.com/discord"
            icon="/docs/icons/icon-discord.svg"
            icon-size="large"
        />
    </div>
    <div class="py-1 sm:w-1/2 sm:py-0">
        <IconLink title="Twitter"
            subtitle="See the latest Craft tweets."
            link="https://twitter.com/craftcms"
            icon="/docs/icons/icon-twitter.svg"
            icon-size="large"
        />
    </div>
    <div class="py-1 sm:w-1/2 sm:py-0">
        <IconLink title="CraftQuest"
            subtitle="Watch video courses."
            link="https://craftquest.io/"
            icon="/docs/icons/icon-craft-quest.svg"
            icon-size="large"
        />
    </div>
    <div class="py-1 sm:w-1/2 sm:py-0">
        <IconLink title="Craft Link List"
            subtitle="Stay in-the-know."
            link="https://craftlinklist.com/"
            icon="/docs/icons/icon-craft-link-list.svg"
            icon-size="large"
        />
    </div>
    <div class="py-1 sm:w-1/2 sm:py-0">
        <IconLink title="nystudio107 Blog"
            subtitle="Learn Craft & web dev."
            link="https://nystudio107.com/blog"
            icon="/docs/icons/icon-nystudio107.svg"
            icon-size="large"
        />
    </div>
</div>
