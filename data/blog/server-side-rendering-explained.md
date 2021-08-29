---
title: 'Server-side Rendering explained'
date: '2020-07-14'
tags: ['javascript', 'react', 'programming']
draft: false
summary: 'How fast the browser builds your app depends on how you build it. The first thing the browser receives is an HTML document and other assets like image, CSS, javascript.'
authors: ['default']
---

### How the browser works when loading an app

How fast the browser builds your app depends on how you build it. The first thing the browser receives is an HTML document and other assets like image, CSS, javascript. Once the browser parses the HTML document it knows to go fetch CSS, images, javascript. Even though the website has the HTML it can not render the website until it’s the corresponding CSS has finished parsing. Once that’s done the browser goes ahead and renders the page. The browser is really good at this and does it really fast.

### Loading JavaScript

After the HTML document is parsed it will go ahead and download the javascript files. The amount of time it takes to download the javascript is a lot. With a slow internet connection, this could take a long time depending on the size of the javascript file explicitly if your first load is dependent on Javascript.

### Sever-side Rendering

With server-side rendering, we can generate the HTML on the server and send that down to the browser. So the user will see the HTML of your website almost immediately as the javascript app boots up in the background. This may not make your page load faster than a none server-side rendering website it does give your users something to see as the Javascript downloads in the background. This is a really nice benefit the is a cost to server-side rendering.

### Two Steps to Server-side Rendering

1. server-side rendering is not free there are time and effort that needs to take place on the server so if it takes a while to do this generation you are not going to have a fast page load.

2. Secondly have the browser has finished processing your HTML and CSS it will still need to parse and execute your Javascript and this can be really heavy on the browser’s main thread. While the user will be able to see the application it will be in this frozen state where a user can not interact with it and so it is only after the Javascript is finished parsing and executing that the application will be interactive to the user.
