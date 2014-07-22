---
layout: post
title: base16 Color Schemes
category: code
tags: windows, atom, console2, sublime-text, visual-studio
---

I spotted a nice set of color schemes called [base16][base16] and [eighties][base16-eighties] is my favorite. All you have to do is pull down the [base16-builder][base16-builder] repository and call the ruby script with the color scheme you like best.

{% highlight bash %}
git clone https://github.com/chriskempson/base16-builder.git
cd base16-builder
./base16 schemes/eighties.yml
{% endhighlight %}

After a few seconds, the output directory will contain color scheme files that are compatible with apps such as [atom][atom], [console2][console2], [sublime text][sublime-text] (textmate), [visual studio][visual-studio], and many others. 

  [atom]: https://atom.io/
  [base16]: http://chriskempson.github.io/base16
  [base16-builder]: https://github.com/chriskempson/base16-builder
  [base16-eighties]: http://chriskempson.github.io/base16/#eighties
  [console2]: http://sourceforge.net/projects/console/files/
  [sublime-text]: http://www.sublimetext.com/
  [visual-studio]: http://www.visualstudio.com/
