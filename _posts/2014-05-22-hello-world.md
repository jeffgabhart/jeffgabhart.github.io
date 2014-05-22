---
layout: post
title: Hello World
---
{% highlight csharp linenos %}
public class HelloWorldService : Service
{
	public object Get(HelloWorld request)
	{
		return "Hello, {0}.".Fmt(request.Name);
	}
	
	[Route("/helloworld/{name}")]
	public class HelloWorld
	{
		public string Name { get; set; }
	}
}
{% endhighlight %}
