
{% assign id = include.ref-os | downcase -%}
{% assign mainpath = include.filepath -%}
{%- case id %}
{% when 'windows','macos' %}
{%- assign file-format = 'zip' %}
{% else %}
{%- assign file-format = 'tar.xz' %}
{% endcase %}
{%- if id == 'chromeos' %}
{% assign plat = 'linux' %}
{%- else %}
{% assign plat = id %}
{% endif %}
{% capture filepath -%}{{mainpath | replace: "opsys", plat}}{{file-format}} {% endcapture -%}


<div id="{{id}}-dl" class="tab-pane
  {%- if id == 'windows' %} active {% endif %}"
  role="tabpanel" aria-labelledby="{{id}}-dl-tab" markdown="1">

To download the {{include.ref-os}} 3.13 version of the Flutter SDK,
you would change the original URL from:

```terminal
https://storage.googleapis.com/{{filepath}}
```

to the mirror URL:

```terminal
https://storage.flutter-io.cn/{{filepath}}
```

</div>
