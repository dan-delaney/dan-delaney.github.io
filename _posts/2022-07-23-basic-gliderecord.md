---
title: "Basic GlideRecord"
layout: post
categories: ServiceNow JavaScript GlideRecord
author: Dan Delaney
---

Testing out GitHub pages for blogging, with a basic GlideRecord query:

{% highlight javascript linenos %}
// Get all priority 1 incidents
var incGR = new GlideRecord('incident');
incGR.addQuery("priority", 1);
incGR.query();
if ( incGR.hasNext() ) {
  while ( incGR.next() ) {
    gs.print(incGR.number);
  }
}
{% endhighlight %}

