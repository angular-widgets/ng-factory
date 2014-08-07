{% block title -%}
# {{ pkg.name }} [![Build Status](http://img.shields.io/travis/{{ url }}.svg)](http://travis-ci.org/{{ url }})
{%- endblock %}

{% block header -%}
{{ pkg.description }}
{%- endblock %}

## Examples
{% block examples -%}
{% for module in modules -%}
{% for example in examples[module] %}
- **{{ module }}** - [{{ example.basename }}]({{ src.cwd }}/{{ module }}/docs/examples/{{ example.basename }})

``` {{ example.extname }}
{% include example.filename %}
```
{%- endfor %}
{%- endfor %}
{%- endblock %}

## Usage
{% block usage -%}
{{ ngdocs }}
{%- endblock %}

## Dependencies

Package | Version
------- | -------
{% for dependency, version in dependencies -%}
{{ dependency }} | **{{ version }}**
{% endfor %}

## Status
{% for badge in badges %}
[![{{ badge.title }}]({{ badge.image }})]({{ badge.url }})
{% endfor %}

## Contributing

Please submit all pull requests the against master branch. If your unit test contains JavaScript patches or features, you should include relevant unit tests. Thanks!

## License

{{ license }}