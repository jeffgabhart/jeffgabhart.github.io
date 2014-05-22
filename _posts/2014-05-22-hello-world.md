---
layout: post
title: Hello World
category: code
tags: csharp, servicestack
---
{% highlight csharp linenos %}
public class HelloWorldService : Service
{
    public object Get(HelloWorld request)
    {
        return "Hello, {0}.".Fmt(request.Name);
    }
    
    [Route("/hello-world/{name}", "GET")]
    public class HelloWorld
    {
        public string Name { get; set; }
    }
}
{% endhighlight %}
