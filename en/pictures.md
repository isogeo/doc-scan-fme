# Images and figures index

{% for picture in book.pictures %}
  {{ picture.nro }}. [{{ picture.list_caption }}]({{ picture.backlink }})
{% endfor %}
