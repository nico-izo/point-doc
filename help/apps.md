{% extends "/help/base.html" %}

{% block subheader %}
<a class="breadcrumb" href="/help/">Справка</a>
<span class="breadcrumb active">Приложения</span>
{% endblock %}

{% block content %}
<h1>Приложения</h1>

<p>
Для того, чтобы пользоваться сервисом, Вам не нужно ничего устанавливать&nbsp;&mdash; достаточно вашего любимого Jabber-клиента или любого браузера. Ну, почти любого&nbsp;&mdash; IE 8 и ниже мы браузером не считаем:-)
</p>
<p>
Однако, некоторые программы могут помочь Вам сделать использование сервиса чуть более удобным.
</p>

<div class="clearfix">
<h2>Psi+</h2>
<a href="{{env.request.protocol}}://{{settings.domain}}/img/help/psi-plus.png"><img src="{{env.request.protocol}}://{{settings.domain}}/img/help/psi-plus-thumb.jpg" alt="Psi" class="thumb"/></a>
<p>
Популярный мультиплатформенный jabber-клиент, поддерживает XHTML-IM (XEP-0071),
что позволит Вам использовать XMPP-ссылки вместо того, чтобы вводить команды вручную.
</p>
<p>Для того, чтобы включить режим XHTML-IM, просто скажите боту <code>set xhtml on</code>.

<p><a href="http://psi-plus.com/">http://psi-plus.com/</a></p>
</div>

<div class="clearfix">
<h2>LeechCraft</h2>
<a href="{{env.request.protocol}}://{{settings.domain}}/img/help/leechcraft.png"><img src="{{env.request.protocol}}://{{settings.domain}}/img/help/leechcraft-thumb.jpg" alt="LeechCraft" class="thumb"/></a>
<p>
Мультиплатформенный модульный комбайн со встроенным jabber-клиентом, также поддерживает XHTML-IM.
</p>

<p><a href="http://leechcraft.org/">http://leechcraft.org/</a></p>
</div>

<div class="clearfix">
<h2>Emacs point.el</h2>
<a href="{{env.request.protocol}}://{{settings.domain}}/img/help/emacs-point-el.png"><img src="{{env.request.protocol}}://{{settings.domain}}/img/help/emacs-point-el-thumb.jpg" alt="Emacs point.el" class="thumb"/></a>
<p>
Для этой вундервафли от <a href="https://en.wikipedia.org/wiki/Stallman">Человека-стола</a>, претендующей на звание операционной системы, тоже есть велосипед.
</p>
<p><a href="https://github.com/rayslava/emacs-point-el">https://github.com/rayslava/emacs-point-el</a></p>
</div>

<div class="clearfix">
<h2>QIP 2012</h2>
<a href="{{env.request.protocol}}://{{settings.domain}}/img/help/qip2012.png"><img src="{{env.request.protocol}}://{{settings.domain}}/img/help/qip2012-thumb.png" alt="QIP 2012" class="thumb"/></a>
<p>
Плагин для проприетарного мультипротокольного мессенджера QIP 2012.
</p>
<p><a href="http://f.skobkin.ru/soft/qip/point/point.7z">http://f.skobkin.ru/soft/qip/point/point.7z</a></p>
</div>

{% endblock %}
