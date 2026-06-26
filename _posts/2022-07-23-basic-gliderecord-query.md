---
title: "Basic GlideRecord Query"
layout: post
categories: ServiceNow JavaScript GlideRecord
---

Just testing out GitHub pages for blogging, with a basic GlideRecord query for getting a list of all Priority 1 incidents:

{% highlight javascript linenos %}
// Get all priority 1 incidents
var incGR = new GlideRecord('incident');
incGR.addQuery("priority", 1);
incGR.addActiveQuery();
incGR.query();
if ( incGR.hasNext() ) {
  while ( incGR._next() ) {
    gs.info(incGR.number);
  }
}
{% endhighlight %}

GlideAggregate example for counting the number of computers by location:

{% highlight javascript linenos %}
var ga = new GlideAggregate('cmdb_ci_computer');
ga.addAggregate('COUNT');
ga.groupBy('location');
ga.query();

while (ga.next()) {
  var location = ga.getValue('location');
  var count = ga.getAggregate('COUNT');
  gs.info('Location: ' + location + ' - Count: ' + count);
}
{% endhighlight %}