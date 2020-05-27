
{% assign person=who %}
{% include personline_tab.md short='short' %}
  
<tr>
<td>

<ul>
<li>Experiments and projects:</li>
<ul>
{% for experiment in site.experiments %}
  {% if who.experiments contains experiment.experiment %}
    <li>  <a href="{{ experiment.url }}">{{ experiment.title}}</a></li>
  {% endif %}
{% endfor %}
</ul>

<li>Technical teams:</li>

<ul>
{% for team in site.techteams %}
  {% if who.teams contains team.team %}
    <li> &nbsp; &nbsp;  <a href="{{ team.url }}">{{ team.title}}</a></li>
  {% endif %}
{% endfor %}
</ul>

<li>Software:</li>

<ul>
{% for software in site.software %}
  {% if who.software contains software.software %}
    <li> &nbsp; &nbsp;  <a href="{{ software.url }}">{{ software.title}}</a></li>
  {% endif %}
{% endfor %}
</ul>

</ul>

</td>


</tr>