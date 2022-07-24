---
title: "Basic GlideRecord (Test Post)"
layout: post
category: servicenow
---

Basic GlideRecord:

{% highlight javascript %}
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

