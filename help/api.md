{% extends "/help/base.html" %}

{% block subheader %}
<a class="breadcrumb" href="/help/">Справка</a>
<span class="breadcrumb active">API</span>
{% endblock %}

{% block content %}

<p>
Ниже приведениы методы HTTP API для работы с данными Point.im.
</p>

<h1>Аутентификация</h1>

<h3>Вход</h3>
POST <code>/api/login</code>
<h4>Параметры</h4>
<p><code>login</code>&nbsp;&mdash; имя пользователя. Обязательный параметр.</p>
<p><code>password</code>&nbsp;&mdash; пароль. Обязательный параметр.</p>

<p>Далее полученный token нужно передавать в заголовках запросов:</p>
<p><code>Authorization: &lt;token&gt;</code></p>

<h3>Выход</h3>
POST <code>/api/logout</code>
<h4>Параметры</h4>
<p><code>csrf_token</code>&nbsp;&mdash; Обязательный параметр.</p>

<h1>Посты</h1>

<h3>Список последних записей в ленте</h3>
GET <code>/api/recent</code>
<h4>Параметры</h4>
<p><code>before</code>&nbsp;&mdash; идентификатор записи, от которой нужно начать выборку. Не включает запись.</p>
<p>Необходима аутентификация.</p>

<h3>Список последних записей в блоге пользователя</h3>
GET <code>/api/blog/&lt;login&gt;</code>
<h4>Параметры</h4>
<p><code>before</code>&nbsp;&mdash; идентификатор записи, от которой нужно начать выборку. Не включает запись.</p>

<h3>Список комментируемых постов</h3>
GET <code>/api/comments</code>
<h4>Параметры</h4>
<p><code>before</code>&nbsp;&mdash; идентификатор записи, от которой нужно начать выборку. Не включает запись.</p>
<p>Необходима аутентификация.</p>

<h3>Список входящих сообщений</h3>
GET <code>/api/messages</code><br/>
GET <code>/api/messages/incoming</code>
<h4>Параметры</h4>
<p><code>before</code>&nbsp;&mdash; идентификатор записи, от которой нужно начать выборку. Не включает запись.</p>
<p>Необходима аутентификация.</p>

<h3>Список исходящих сообщений</h3>
GET <code>/api/messages/outgoing</code><br/>
<h4>Параметры</h4>
<p><code>before</code>&nbsp;&mdash; идентификатор записи, от которой нужно начать выборку. Не включает запись.</p>
<p>Необходима аутентификация.</p>

<h3>Просмотр поста</h3>
GET <code>/api/post/&lt;post&gt;</code><br/>

<h1>Теги</h1>

<h3>Список тегов пользователя</h3>
GET <code>/api/tags/&lt;login&gt;</code>

<h3>Выборка постов по тегам</h3>
GET <code>/api/tags</code>
<h4>Параметры</h4>
<p><code>tag</code>&nbsp;&mdash; тег. Обязательный параметр.</p>
<p>Можно указывать несколько тегов.</p>

<h3>Выборка постов по тегам пользователя</h3>
GET <code>/api/tags/&lt;login&gt;</code>
<h4>Параметры</h4>
<p><code>tag</code>&nbsp;&mdash; тег. Обязательный параметр.</p>
<p>Можно указывать несколько тегов.</p>

<h1>Пользователи</h1>

<h3>Информация о пользователе</h3>
GET <code>/api/user/&lt;login&gt;</code>

<h3>Подписки пользователя</h3>
GET <code>/api/user/&lt;login&gt;/subscriptions</code>

<h3>Подписчики пользователя</h3>
GET <code>/api/user/&lt;login&gt;/subscribers</code>

<h3>Белый список пользователей</h3>
GET <code>/api/user/wl</code>
<p>Необходима аутентификация.</p>

<h3>Белый список пользователей</h3>
GET <code>/api/user/wl</code>
<p>Необходима аутентификация.</p>

<h1>WebSocket</h1>
<p>Для получения уведомлений о событиях можно использовать WebSocket-сервер, расположенный по адресу</p>
<p><code>ws://point.im/ws</code> или <code>wss://point.im/ws</code></p>

<p>Для аутентификации нужно передать WS-серверу сообщение вида:</p>

<p><code>Authorization: token</code>,</p>

<p>где token&nbsp;&mdash; ключ, полученный при входе через API.</p>

<h1>Прочее</h1>

<h3>Получение аватара</h3>
GET <code>/avatar/&lt;login&gt;/&lt;size&gt;</code>

<p>где size&nbsp;&mdash; размер аватара. Может быть равен 24, 40 или 80.</p>

<p>&nbsp;</p>

{% endblock %}
