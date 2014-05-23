---
layout: post
title: Hello World
category: code
tags: csharp, servicestack
---
{% highlight csharp %}
public class HelloWorldService : Service
{
    public object Get(Hello request)
    {
        return "Hello, {0}.".Fmt(request.Name);
    }
    
    [Route("/hello/{name}", "GET")]
    public class Hello
    {
        public string Name { get; set; }
    }
}
{% endhighlight %}
