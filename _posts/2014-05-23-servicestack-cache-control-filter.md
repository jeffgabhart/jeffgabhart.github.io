---
layout: post
title: ServiceStack Cache Control Filter
category: code
tags: csharp, servicestack, cache-control
---

While testing with a Microsoft Surface, I noticed that API data was always stale. Regardless of any updates, the browser continued to show the same data as if it had never changed. 

The browser cached the original GET requests, and now any GETs to that same resource returned the data from cache. As a first attempt to address the issue, I created a request filter to set the Cache-Control header. 

{% highlight csharp linenos %}
public class NoCacheAttribute : RequestFilterAttribute
{
    public override void Execute(IHttpRequest req, IHttpResponse res, object responseDto)
    {
        res.AddHeader(HttpHeaders.CacheControl, "no-store,must-revalidate,no-cache,max-age=0");
    }
}
{% endhighlight %}

Simply add `[NoCache]` to your service or method to keep the browser from caching the resource.

In the future, I want to take a look at using ETag in conjuction with the Cache-Control header. You can vote for ETag support in ServiceStack at [UserVoice][user-voice] .

  [user-voice]: https://servicestack.uservoice.com/forums/176786-feature-requests/suggestions/4470997-add-etag-if-none-match-support-to-enable-client 'ServiceStack Feature Request - ETag'
