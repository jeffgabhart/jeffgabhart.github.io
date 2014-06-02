---
layout: post
title: Sending and Receiving SMS Through Tropo
category: code
tags: ruby, tropo, sms
---

I wanted a [Tropo][tropo] script that could send out text messages via the REST API as well as forward text messages that were received through the Tropo phone number. This scaffold shows how I identified and handled the two cases. 

{% highlight ruby %}
if $action == "create"
  # Script called from REST API
  call "+1XXX5551212", {:network => "SMS"}
  say "Sample Message Text"
else
  # Script called from incoming SMS
  callerId = $currentCall.callerID
  text = $currentCall.initialText
  message "#{callerId} => #{text}", {:to => "+1YYY5551212", :network => "SMS"}
end
{% endhighlight %}

  [tropo]: https://www.tropo.com
