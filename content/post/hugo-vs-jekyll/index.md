---
title: "Choosing a Static Website Generator: Hugo vs. Jekyll"
date: 2020-03-23T23:37:28-07:00
draft: false
tags: ['hugo', 'jekyll']
categories: ['programming']
references: [
  'Hired.com (2019). 2020 State of Software Engineers. Retrieved from https://hired.com/state-of-software-engineers',
  'Macrae, C. (2018, January 26). Hugo vs Jekyll: Benchmarked. Retrieved from https://forestry.io/blog/hugo-vs-jekyll-benchmark/'
]
---

## What are static websites?
In simple terms, static websites are a collection of webpages that have fixed content. They are the most basic type of website and are typically considered the easiest to create.

These websites are considered the easiest to create because they have a low barrier of entry. They are usually not connected to a [backend](https://en.wikipedia.org/wiki/Data_access_layer) or a [database](https://en.wikipedia.org/wiki/Database), so the only thing that you will need to manage is the [frontend](https://en.wikipedia.org/wiki/Presentation_layer).

Given that information, static websites look essentially the same for all users (because you wouldn't have user data to customize their experience). User data, like emails and [password digests](https://en.wikipedia.org/wiki/Digest_access_authentication), need a database for storage and are considered unsafe to store in the frontend.

## Why pick a static website over a 'regular', dynamic website?
Although static websites are cool and all, why should one choose them over dynamic (a.k.a. full-stack) websites? Here are the advantages that a static website holds over a dynamic one (generally speaking):

- **Faster:** Since static websites don't have a backend or a database, all the [web hosting server](https://en.wikipedia.org/wiki/Web_hosting_service) has to do is serve the needed file. There will be no API calls to retrieve data from the database, so you're less likely to see any loading signs.

- **Cheaper:** Hosting static websites is mostly free. They can be hosted on free web hosting services such as [GitHub Pages](https://pages.github.com/), [Netlify](https://www.netlify.com/), and others. The only cost that you're likely to face is for a custom domain name, and that's optional.

- **Safer:** Since there's no backend or database, your site is less likely to be breached for private data. There's no opportunity to perform [SQL injection](https://en.wikipedia.org/wiki/SQL_injection) and similar database attacks. I think it's good practice to assume that anything stored in your static website will be available to the public.

## When should I choose a static website over a dynamic one?
You should pick to choose a static website if your website doesn't allow users to make POST, PUT, PATCH, CONNECT or DELETE [HTTP](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol) requests. In other words, you should probably choose to use a static website if your users are not going to modify any of your website's data.

## What are static website *generators*?
Static website *generators* are exactly what they sound like. They're automated processes that help you produce static websites. These technologies differentiate themselves in different ways. But the main two differentiating themes are typically speed and customization.

## Picking a static website generator
Here's a list of [the most popular static site generators](https://www.staticgen.com/). Currently, the top three are [Next.js](https://nextjs.org/), [Hugo](https://gohugo.io/), and [Nuxt.js](https://nuxtjs.org/). [Gatsby.js](https://www.gatsbyjs.org/) is a pretty popular one too.

Today, we're going to be talking about [Jekyll](https://jekyllrb.com/) and [Hugo](https://gohugo.io/), how they differ, and why you may choose one over the other. But before we go on, you may be wondering: why are we not looking at something like Next or Nuxt since they're so popular? Well, although these technologies are great, I've decided to avoid writing about them due to a few reasons, including the following:

- **They're built on top of frameworks:** Next is built on [React.js](https://reactjs.org/), and Nuxt is built on [Vue.js](https://vuejs.org/). So learning them would also mean that you're going to eventually learn the framework behind them. Hugo and Jekyll, on the other hand, are built on [Go](https://golang.org/) and [Ruby](https://www.ruby-lang.org/en/) (programming languages) respectively. So their barrier to entry is a bit lower.

- **They're often used as a part of full-stack applications:** Next and Nuxt are typically used to optimize the frontend of full-stack applications (and are kind of built for that purpose). So browsing questions about them and reading their documentation may confuse you if you plan to use them to build pure static websites [that aren't connected to a backend or database in any way]. Hugo and Jekyll, in contrast, are mostly designed to create and maintain stand-alone static websites. So getting help for them may be easier.

## Hugo vs. Jekyll: Style (themes)
You can pick a theme to build your website (rather than building it from scratch). Most themes are free and open-sourced. There are plenty of themes to choose from in both technologies.

Popular themes are sometimes available under both technologies. So if you see a theme that you like with one technology, I would suggest searching for it in the other. Here are links to theme pages for each:

- [Jekyll themes](https://jekyllrb.com/docs/themes/) (under "Pick up a theme")
- [Hugo themes](https://themes.gohugo.io/)

## Hugo vs. Jekyll: Speed
One of the main differences between Hugo and Jekyll is their speed. Looking at [this](https://forestry.io/blog/hugo-vs-jekyll-benchmark/) benchmarking test, it is said that Hugo is "... between 23 and 63 times faster than Jekyll" (Macrae, 2018) in terms of build time. This becomes more apparent as the number of pages grows. Here's a graph demonstrating the difference:


{{< figure
img="hugo-vs-jekyll-speed-graph.png" 
caption="[Source](https://forestry.io/blog/hugo-vs-jekyll-benchmark/)" 
command="Resize" 
options="700x" >}}


## Hugo vs. Jekyll: The learning curve
- **Hugo's docs are harder to follow:** As pointed out by Ben Congdon in [his blog](https://benjamincongdon.me/blog/2018/06/06/Switching-from-Jekyll-to-Hugo/), Hugo follows a [top-down engineering](https://en.wikipedia.org/wiki/Top-down_and_bottom-up_design) approach, where it tries to provide everything a user may need. While Jekyll, on the other hand, follows a [bottom-up](https://en.wikipedia.org/wiki/Top-down_and_bottom-up_design) approach where it provides minimal tools and lets you build the rest. This makes Hugo a little harder to learn. I personally found its documentation to be a little overwhelming. Jekyll's documentation was much easier to read, navigate, and follow.

- **Great communities with both:** Although Jekyll ([est. 2008](https://en.wikipedia.org/wiki/Jekyll_(software))) has been around longer than Hugo ([est. 2013](https://en.wikipedia.org/wiki/Hugo_(software))), I found both to have great communities. I didn't have trouble finding answers for either of them.

- **Programming language familiarity:** Depending on the programming languages you currently know, you may choose one technology over the other. As discussed, Jekyll is built on Ruby and Hugo is built on Go. If you're a beginner programmer, choosing Jekyll may be the easier route since Ruby is considered easier to learn than Go. If you're familiar with [statically typed programming](https://stackoverflow.com/a/1517670/7974948) languages, then Hugo may be the better option for you, as Go is statically typed.

It may be important to note that according to [this](https://hired.com/state-of-software-engineers) report by [Hired.com](https://hired.com/home), programmers experienced with Go had the most interview requests on their platform (in 2019). Here's a graph demonstrating this further:

{{< figure
img="hired-most-demand-langs.png" 
caption="[Source](https://hired.com/state-of-software-engineers)" 
command="Resize" 
options="700x" >}}

So if you are currently looking for a job (like I am), it may be worth it to look into Go, and how it may help you grow as a programmer. In case you do want to check it out, I think going through [this interactive tutorial](https://tour.golang.org/welcome/1) provided by the language's official website may be a good way to start.

## Hugo vs. Jekyll: When to use what
- **Jekyll:** I would recommend using Jekyll for building websites that don't exceed 500 pages in size (to avoid long build time). Look at [Spotify for Developers](https://developer.spotify.com/), [TwitchCon's website](https://www.twitchcon.com/), and [Sketch App's website](https://www.sketch.com/) for Jekyll generated examples. More can be found on [Jekyll's showcase page](https://jekyllrb.com/showcase/).

- **Hugo:** I would recommend Hugo for blogs, and for websites that you know are going to continue to grow in page count over time. Look at [Ben Congdon's website](https://benjamincongdon.me/), [Anna Dodson's website](https://annadodson.co.uk/), and [Pharmaseal's website](https://www.pharmaseal.co/) for Hugo generated examples. More can be found on [Hugo's showcase page](https://gohugo.io/showcase/).

If you want to look at an even deeper comparison of the two technologies, I recommend [this article](https://forestry.io/blog/hugo-and-jekyll-compared/) by [Forestry.io](https://forestry.io/).

### Thanks for reading ( ^__^ )

***

If you see something that you think needs fixing in this article, please don't hesitate to message me.

References: