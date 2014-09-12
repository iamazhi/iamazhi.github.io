---
layout: index
---
{% include JB/setup %}

<link type="text/css" rel="stylesheet" href="{{ ASSET_PATH }}/custom/css/reflection.css"/>
<link type="text/css" rel="stylesheet" href="{{ ASSET_PATH }}/custom/css/book.css"/>
<div class="box reflection">
    {% for category in site.categories %}
        <a href="{{ BASE_PATH }}{{ site.JB.categories_path }}#{{ category[0] }}"><img src="{{ ASSET_PATH }}/custom/images/{{ category[0] }}.jpg"></a></li>
    {% endfor %}
</div>

<div class="component">
<ul class="align">
<li>
<figure class='book'>

<!-- Front -->

<ul class='hardcover_front'>
<li>
<div class="coverDesign blue">
<h1>阿智博客</h1>
<p>blog.azhibox.com</p>
</div>
</li>
<li></li>
</ul>

<!-- Pages -->

<ul class='page'>
<li></li>
<li>
<a class="btn" href="http://blog.azhibox.com" target="_blank">Go!</a>
</li>
<li></li>
<li></li>
<li></li>
</ul>

<!-- Back -->

<ul class='hardcover_back'>
<li></li>
<li></li>
</ul>
<ul class='book_spine'>
<li></li>
<li></li>
</ul>
<figcaption>
<h1><a href="http://blog.azhibox.com/index.php/Whisper#/step-1" target="_blank">成长是加，成熟是减</a></h1>
<span>Cheers to the past</span>
<p>繁华尽处，寻一无人山谷，建一木制小屋，铺一青石小路，与你晨钟暮鼓，安之若素。</p>
</figcaption>
</figure>
</li>
</ul>
</div>

