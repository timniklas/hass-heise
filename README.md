# hass-heise
Home Assistant Heise online integration

 ```
<h1><img src="https://www.heise.de/assets/heise/images/flammen.238.ltc.svg"  height="26"> Heise Security</h1>
{%- for i in range(2) %}
{%- set title = states("sensor.heiseonline_heise_security_"~ loop.index) %}
{%- set updated = state_attr("sensor.heiseonline_heise_security_"~ loop.index, "updated") %}
{%- set link = state_attr("sensor.heiseonline_heise_security_"~ loop.index, "link") %}
{%- set summary = state_attr("sensor.heiseonline_heise_security_"~ loop.index, "summary") %}
<a href="{{link}}"><b>{{title}}</b></a><br>
{{updated|as_datetime|time_since}} ago
<br/>
{%- if not loop.last %}<br>{%- endif %}
{%- endfor %}
 ```
