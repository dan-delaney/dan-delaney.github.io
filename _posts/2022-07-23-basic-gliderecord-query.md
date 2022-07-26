---
title: "Basic GlideRecord Query"
layout: post
categories: ServiceNow JavaScript GlideRecord
---

Testing out GitHub pages for blogging, with a basic GlideRecord query for getting a list of all Priority 1 incidents:

{% highlight javascript linenos %}
// Get all priority 1 incidents
var incGR = new GlideRecord('incident');
incGR.addQuery("priority", 1);
incGR.addActiveQuery()
incGR.query();
if ( incGR.hasNext() ) {
  while ( incGR.next() ) {
    gs.info(incGR.number);
  }
}
{% endhighlight %}

