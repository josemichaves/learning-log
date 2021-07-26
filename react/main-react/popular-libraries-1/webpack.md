# WebPack

Webpack is a highly extensible and configurable **static module bundler** for JavaScript applications.

As shown in the illustration below, webpack goes through your application from a **root entry point**, builds a dependency graph comprising of dependencies that act directly or indirectly on the root file and produces optimized bundles of the combined modules.

![](../../../.gitbook/assets/image%20%2882%29.png)

WebPack relays in three bases:

* **Chunk** A _chunk_ refers to the code extracted from modules. This code will be stored in a _chunk file_. Chunks are commonly used when performing code-splitting with webpack.
* **Modules** _Modules_ are broken-down parts of your application which you import to perform a specific task or function. Webpack supports modules created using the ES6, CommonJS and AMD syntax.
* **Assets** The term _assets_ is frequently used within webpack and other bundlers in general. It refers to the **static files** bundled during the build process. These files could be anything from images to fonts or even video files. As you read further down the article, you will see how we use loaders to work with different asset types.



