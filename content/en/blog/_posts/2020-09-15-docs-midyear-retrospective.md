---
layout: blog
title: "A Midyear Retrospective on Kubernetes Docs"
date: 2020-07-27
slug: docs-midyear-retrospective
url: /blog/2020/07/docs-midyear-retrospective
---

**Author:** Zach Corleissen, Cloud Native Computing Foundation

*Editor's note: Zach is one of the chairs for the Kubernetes documentation special interest group (SIG Docs).*

I started contributing to Kubernetes docs three years ago, at the start of the 1.8 release cycle. Kubernetes has changed a lot since then, as has the Kubernetes project itself. As with most things in 2020, the docs are in a different place now than they were in my [2019 docs review](/reviewing-2019-in-docs). This blog post is a retrospective on docs updates in 2020, a look at what's coming next, and ways for you to contribute.

This is my last blog post as a SIG Docs chair for the foreseeable future. Effective September 15th, 2020 I'm becoming a chair emeritus. It's been a powerful three years. 

## Hugo changes

In April, we updated the site's Hugo version from 0.59.1 to 0.70&mdash;a significant milestone because it brought the website current with the parser change from Black Friday to CommonMark introduced in [Hugo 0.60.0](https://gohugo.io/news/0.60.0-relnotes/). 

The parser change caused [a lot of pain](https://github.com/kubernetes/website/issues/20335), but it forced us to resolve technical debt that had plagued us since migrating from Jekyll to Hugo (which changed parsers from Kramdown to Black Friday) in [May 2018](https://kubernetes.io/blog/2018/05/05/hugo-migration/).

I'm proud of the technical and community leadership shown in this transition by SIG Docs chair Jim Angel and tech lead Tim Bannister. This was one of the moments when I knew that SIG Docs was in good hands and could handle another chair transition.

## Applying the Docsy theme

In June, we applied the [Docsy Hugo theme](https://docsy.dev) to the website. The theme significantly upgraded the site's sidebar navigation, and site visitors are happier overall with improved layouts and better formatting. 

That said, Docsy has been a [complicated success](https://github.com/kubernetes/website/issues?q=Docsy). Docsy has several non-obvious dependencies that significantly slowed our build times, especially in post-processing. We've had to delete a lot of cruft: layout-specific Javascript overriden by numerous instances of page-specific formatting, as well as a small handful of deprecated Hugo shortcodes.

I'm asked frequently whether or not I recommend Docsy for other technical docs sites. My answer: it depends. For newer projects that want to take advantage of native [Swagger support](https://www.docsy.dev/docs/adding-content/shortcodes/#swaggerui), I think Docsy is a powerful choice. Sites with  existing content (20+ pages) may run into some serious difficulties in migration. 

It's hard to predict what other sites may experience applying the Docsy theme. The Kubernetes website has years of complicated transformation in its history, and changing our site stack consequently produces unique challenges. New sites may have a much easier time working with Docsy and Hugo themes in general than we have so far, which is unsurprising. 

One piece of functionality to highlight: Hugo has a built-in [build performance tool](https://gohugo.io/troubleshooting/build-performance/) invoked at the command line: `hugo --templateMetrics`. It's helpful for diagnosing specific causes of slower builds.

## Containerizing the website

We [containerized the website](https://kubernetes.io/docs/contribute/new-content/open-a-pr/#preview-locally) for [the usual reasons](https://www.ibm.com/cloud/learn/containerization)&mdash;but also because many contributors using MacOS were experiencing open file limits (imposed by the OS and no longer configurable in Catalina) when they tried to preview the site locally. 

When building the site locally from a container in a MacOS environment, you may still encounter memory limits. (Who would have thought that SIG Docs would be performance testing containers?) But it's a lot easier to configure Docker memory usage settings--and Pull Request previews are predictably and reliably easier to compare between contributors.

## Release 1.19

The docs experience of the 1.19 release cycle deserves its own blog post. As happens in every release cycle, [something breaks](https://www.youtube.com/watch?v=_i9Qey_tRc0) in new and interesting ways. The 1.19 release was no different, but I'm pleased to say that 1.19 was one of the best docs cycles yet, thanks to the excellent leadership of [Savitha Raghunathan](https://github.com/savitharaghunathan).

After the challenges of 1.17 and 1.18, the SIG Docs chairs realized we needed to be clearer about what a docs release lead does. Part of the role involves making sure docs release successfully, yes, but the chief success metric of a docs release lead involves making sure potential problems are as visible as possible, as early as possible. Savitha did an amazing job at raising visibility on a number of potential complications before they could worse, and led her team while working to resolve them in consultation with SIG Docs leads. 

Speaking frankly: I'm not easy to impress. So when I say that Savitha impressed me with her leadership, it's one of the highest compliments I can give.

## Leadership pipeline

Need more approvers and approvers in training

1.19 had an excellent release lead
    Really deserves its own post, but Savitha R. led an amazing team

Google Season of Docs
    Accepted, projects submitted, waiting for Google to announce results on August 16th

API reference
    End goal for past 3 years
    Google Season of Docs

Analytics
    Linear growth in site visits

Future: Automatic staling
    Currently no automatic review triggers for stale content.

### Moving on

After three-plus wonderful, challenging years leading SIG Docs, I'm stepping down as SIG Docs on September 15th. This is consistent with the project values of Kubernetes, specifically that [evolution is better than stagnation](https://github.com/kubernetes/community/blob/master/values.md#evolution-is-better-than-stagnation):

> It is the duty for leaders in the Kubernetes community to find, sponsor, and promote new community members. Leaders should expect to step aside. Community members should expect to step up.

It's been a privilege to lead SIG Docs through massive scaling in site traffic, technical innovation across multiple fronts, a growing community, and an average velocity of 11,000 issues and PRs per year.

## How you can get involved

It's difficult being a big site, but awesome things are happening, and here are some specific opportunities to get involved:

- Hire technical writers
- Become a reviewer, an approver, a chair
- Contribute to a localization
