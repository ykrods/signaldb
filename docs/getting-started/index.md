---
head:
- - link
  - rel: canonical
    href: https://signaldb.js.org/getting-started/
- - meta
  - name: og:type
    content: article
- - meta
  - name: og:url
    content: https://signaldb.js.org/getting-started/
- - meta
  - name: og:title
    content: Getting Started | SignalDB
- - meta
  - name: og:description
    content: Learn how to get started with SignalDB, a client-side, MongoDB-like database with real-time synchronization, TypeScript support, and blazing fast performance.
- - meta
  - name: description
    content: Learn how to get started with SignalDB, a client-side, MongoDB-like database with real-time synchronization, TypeScript support, and blazing fast performance.
- - meta
  - name: keywords
    content: getting started with SignalDB, SignalDB installation, MongoDB-like JavaScript database, TypeScript database, SignalDB collections, data persistence, local storage, real-time database, optimistic UI, JavaScript database, reactivity, frontend integration, reactive collections
---
# Getting Started

Welcome to the Getting Started Guide for SignalDB, a local-first database with signal-based reactivity and real-time synchronization. This guide will help you understand the basics of SignalDB and get you up and running quickly.

SignalDB is designed for blazing fast query performance and data persistence, while remaining framework-agnostic.

## Installation

Installing SignalDB is simple and easy. It can be installed using npm. Open your terminal and enter the following command:

```bash
  $ npm install @signaldb/core
```

## Creating Collections

Creating collections is straight forward.

```js
import { Collection } from '@signaldb/core'

const posts = new Collection()
```

but normally you want to persist your data. Persistence in SignalDB is achieved by using [persistence adapters](/data-persistence/). Choose one that fits your needs and pass it to the collection constructor. Here is an example using [`@signaldb/localstorage`](/reference/localstorage/):

```js
import { Collection } from '@signaldb/core'
import createLocalStorageAdapter from '@signaldb/localstorage'

const posts = new Collection({
  persistence: createLocalStorageAdapter('posts'),
})
```

That's all you have to do. There a also some optional configuration options you find here: [collections reference](/reference/core/collection/)


## Adding data

After you've created you first collection, you can start to add documents to it.

```js
// ...

const postId = posts.insert({ title: 'Foo', text: 'Lorem ipsum …' })
```

You created your first document in SignalDB! Check out the [data manipulation](/data-manipulation/) page to learn how to update and remove documents.

## Querying

Getting your documents back is also very easy.

```js
// ...

const cursor = collection.find({})
console.log(cursor.fetch()) // returns an array with all documents in the collection
```

You've finished the Getting Started Guide! The next steps are getting reactivity to work. Check out the [core concepts about reactivity](/core-concepts/#signals-and-reactivity-adapters) to learn how to do this.

## Next steps

Now you know the basics about SignalDB. It's time to learn how to integrate it with the framework you're using.
Take a look at our guides:
- [Angular](/guides/angular/)
- [React](/guides/react/)
- [Solid](/guides/solid-js/)
- [Svelte](/guides/svelte/)
- [Vue](/guides/vue/)


After that you might want to learn more about the [core concepts of SignalDB](/core-concepts/), how you can [query your data](/queries/) or how to [connect it to your backend](/sync/).
