---
layout: default
title: Contact
---
 
### Links to other places I exist online:

{% for item in site.data.links %}
* [{{item.name }}]({{ item.link }})
##### {{ item.description }}
{% endfor %}

### Contact me on: 

{% for item in site.data.contact %}
* [{{ item.platform }}]({{ item.link }}) @ {{ item.user }}
{% endfor %}


