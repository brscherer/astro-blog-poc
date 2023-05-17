# 🚀 Astro

There are five core design principles about why Astro was created

1. Content-focused: Astro was designed for content-rich websites.
2. Server-first: Websites run faster when they render HTML on the server.
3. Fast by default: It should be impossible to build a slow website in Astro.
4. Easy to use: You don’t need to be an expert to build something with Astro.
5. Fully-featured, but flexible: Over 100+ Astro integrations to choose from.

## Content Focused

Astro is fast because it's unique focus is content. It lets Astro make tradeoffs and deliver features that wouldn't make sense for app-focused web frameworks to implement

## Server First

Astro leverage server-side rendering over client-side rendering because SPA adds more complexity and harm page performance, including critical metrics like Time to Interactive (TTI)

## Fast by Default

Astro combines content focus with a server first MPA architecture, which allows making tradeoffs and deliver features other frameworks cannot.

## Easy to Use

Astro's goal is to be accessible to every web developer regardless of skill level or past experience.
It allows using any favorite UI component languages and borrowed part of its syntax from other well-known frameworks.
Because it was designed to run on the server, we don't need to care with reactivity, so all that complexity goes away.

## Fully featured, but flexible

Astro comes with everything we need to build a website, but also is UI-agnostic, which means you can bring your own UI framework such as React, Vue, Solid and other that are officially supported in Astro. We can also mix frameworks on the same page, making future migrations easier and preventing project lock-in to a single framework.


## MPA vs SPA

Multi Page Applications is routing is done in server, in each route will request a different html to server.
Single Page Application will use the same html and a js file to render html inside of this single page.

Astro is different from others MPA because you will always write Javascript, HTML and CSS, not needing to learn a new server language such as PHP, Ruby or Python.
It means you can render UI components in both server and client.
Result is a developer experience similar to modern web frameworks like Next.js with the performance advantages of a more traditional MPA architecture

SPA needs to download, parse and run an entire JS app in the browser just to render any HTML on the page and will likely need to fetch remote data that would introduce even more wait time before your page finish loading

MPA in the other hand will render all HTML on a remote server and often don't require much Javascript to run, but future page navigation won't benefit from local rendering

### Routing

MPA - every request to the server decides which HTML to render
SPA - locally runs in the browser hijacking any navigation and never goes to server

### State Management

SPA wins here because it runs in a single JS and that enables application maintain state and memory across multiple pages

## Astro Islands

Astro Islands refers to an interactive UI component on an otherwise static page of HTML.
This architectural pattern builds on Partial Hydration, leveraging this technique behind the scenes.

Astro, by default, removes all unused JS from the page, but sometimes we need client-side JS to creating interactive UI.
Instead of forcing entire page to become SPA, Astro asks you to create an island by using `client:load` in the component.
This isolates *island of interactivity* of your pure, lightweight HTML and CSS site.

This give huge performance boost since Javascript is only loaded for the individual components that need it.
Also it doesn't block the page rendering since it enables parallel loading. Every island will load in parallel and hydrate in isolation, so one doesn't affect the other.

Islands are the secret to Astro’s fast-by-default performance story!