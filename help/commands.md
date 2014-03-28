{% extends "/help/base.html" %}

{% block subheader %}
<a class="breadcrumb" href="/help/">Справка</a>
<span class="breadcrumb active">Команды</span>
{% endblock %}

{% block content %}

<h1>Команды</h1>

<p>Для того, чтобы общаться через Вашу программу для обмена быстрыми сообщениями, добавьте нашего робота p@point.im в свой список контактов и отправляйте ему команды.</p>

<a name="users"></a><h2>Пользователи</h2>
<p><code>reg[ister] [@]nickname</code>&nbsp;&mdash; зареристрироваться.</p>
<p><code>@nickname[+[[offset] limit]]</code>&nbsp;&mdash; информация о пользователе. <code>+</code>&nbsp;&mdash; с последними постами.</p>
<p><code>w[hoami]</code>&nbsp;&mdash; инфорация о себе.</p>
<p><code>login</code> — получить URL для входа на сайт.</p>

<a name="messaging"></a><h2>Сообщения</h2>

<a name="posts"></a><h3>Просмотр постов</h3>
<p><code>+</code>&nbsp;&mdash; последние 10 постов ленты подписок.</p>
<p><code>+5</code>&nbsp;&mdash; последние 5 постов ленты подписок.</p>
<p><code>+20 10</code>&nbsp;&mdash; последние 10 постов ленты подписок со смещением 20 постов.</p>
<p><code>*тег</code> или <code>**другой тег</code>&nbsp;&mdash; последние 10 постов с указанным тегом.</p>
<p><code>@user *тег</code> или <code>@user **другой тег</code>&nbsp;&mdash; последние 10 постов пользователя с указанным тегом.</p>
<p>При отображении постов с тегом действуют те же атрибуты количества и смещения, что и при выборке постов из ленты. Например:</p>
<p><code>@arts *point +5</code> отобразит пять последних постов @arts с тегом point.</p>
<p><code>p|pm[+[[offset] limit]]</code>&nbsp;&mdash; показать свои последние личные/закрытые посты.</p>

<a name="posting"></a><h3>Отправка постов</h3>
<pre>*tag1 *tag2 *tag3 текст сообщения
</pre>
<p>или</p>
<pre>** тег с пробелами 1, тег с пробелами 2 ** текст сообщения
</pre>
<p>или</p>
<pre>** тег с пробелами 1, тег с пробелами 2
текст сообщения
</pre>
<p><code>#post_id *тег1 *тег2</code> или <code>#post_id ** тег 1, тег 2</code>&nbsp;&mdash; обновить теги.</p>
{#<p><code>upd #post_id</code>&nbsp;&mdash; update post. Only 3 updates are allowed.</p>#}
<p><code>e #post_id *тег1 *тег2 текст</code> или <code>e #post_id ** тег 1, тег 2 ** текст</code>&nbsp;&mdash; отредактировать пост.</p>
<p>Чтобы добавить пост без тегов&nbsp;&mdash; просто отправьте текст.</p>

<a name="private"></a><h3>Личные/закрытые посты</h3>
<pre>p|pm @nickname1 @nickname2 *тег1 *тег2 текст сообщения
</pre>
<p>или</p>
<pre>p|pm @nickname1 @nickname2 **тег 1, тег 2 ** текст сообщения
</pre>
<p>или</p>
<pre>p|pm ** тег 1, тег 2
текст сообщения
</pre>
<p><code>i[nvite] #post_id @nickname1 @nickname2</code>&nbsp;&mdash; пригласить пользователя в закрытый пост.</p>
<p><code>[ui|uninvite] #post_id @nickname1 @nickname2</code>&nbsp;&mdash; удалить пользователя из закрытого поста.</p>
<p><code>d #post_id</code>&nbsp;&mdash; удалить пост.</p>

<a name="comments"></a><h3>Комментарии</h3>
<p><code>#post_id</code>&nbsp;&mdash; показать пост.</p>
<p><code>#post_id+</code>&nbsp;&mdash; показать пост и последние 10 комментариев.</p>
<p><code>#post_id++</code>&nbsp;&mdash; показать пост и все комментарии.</p>
<p><code>#post_id+20</code>&nbsp;&mdash; показать пост и первые 20 комментариев.</p>
<p><code>#post_id+20 10</code>&nbsp;&mdash; показать пост и 10 комментариев, начиная с 20-го.</p>
<p><code>#post_id/comment_number</code> or <code>#post_id.comment_number</code>&nbsp;&mdash; показать комментарий.</p>
<p><code>#post_id текст</code>&nbsp;&mdash; ответить на пост.</p>
<p><code>#post_id/comment_number текст</code> или <code>#post_id.comment_number текст</code>&nbsp;&mdash; ответить на комментарий.</p>
<p><code>d #post_id/comment_number</code> or <code>d #post_id.comment_number</code>&nbsp;&mdash; удалить комментарий.</p>

<p><code>D L</code> или <code>D LAST</code>&nbsp;&mdash; удалить последний пост или комментарий.</p>

<a name="recommendations"></a><h2>Рекомендации</h2>
<p><code>! #post_id[/comment_number] [текст]</code>&nbsp;&mdash; порекомендовать пост или комментарий. Текст будет добавлен как новый комментарий.</p>
<p><strong>Обратите внимание:</strong> повторная команда удалит рекомендацию, связанный с ней комментарий также будет удалён.</p>

<a name="subscriptions"></a><h2>Подписки</h2>
<p><code>s</code> или <code>subscriptions</code>&nbsp;&mdash; посмотреть подписки.</p>
<p><code>s @nickname</code>&nbsp;&mdash; подписаться на посты и рекомендации пользователя. Если блог пользователя скрыт, ему будет отправлен запрос на добавление Вас в белый список.</p>
<p><code>s! @nickname</code>&nbsp;&mdash; подписаться на рекомендации пользователя.</p>
<p><code>s *тег</code> или <code>s **тег с пробелами</code>&nbsp;&mdash; подписаться на тег.</p>
<p><code>s @nickname *тег</code> или <code>s @nickname **тег с пробелами</code>&nbsp;&mdash; подписаться на тег пользователя.</p>
<p><code>u @nickname</code>&nbsp;&mdash; отписаться от постов и рекомендаций пользователя.</p>
<p><code>u! @nickname</code>&nbsp;&mdash; отписаться от рекомендаций пользовтеля. Подписка на его посты сохранится.</p>
<p><code>u *тег</code> или <code>u **тег с пробелами</code>&nbsp;&mdash; отписаться от тега.</p>
<p><code>u @nickname *тег</code> или <code>u @nickname **тег с пробелами</code>&nbsp;&mdash; отписаться от тега пользователя.</p>

<a name="wblists"></a><h2>Белые/чёрные списки</h2>
<p><code>wl</code> или <code>whitelist</code>&nbsp;&mdash; посмотреть содержимое белого списка.</p>
<p><code>wl @nickname</code>&nbsp;&mdash; добавить пользователя в белый список.</p>
<p><code>uwl @nickname</code>&nbsp;&mdash; удалить пользователя из белого списка.</p>

<p><code>bl</code> или <code>blacklist</code>&nbsp;&mdash; посмотреть содержимое чёрного списка.</p>
<p><code>bl @nickname</code>&nbsp;&mdash; добавить пользователя в чёрный список.</p>
<p><code>ubl @nickname</code>&nbsp;&mdash; удалить пользователя из чёрного списка.</p>

<p><code>bl *тег</code> или <code>bl **тег с пробелами</code>&nbsp;&mdash; добавить тег в чёрный список.</p>
<p><code>bl @nickname *тег</code> или <code>bl @nickname **тег с пробелами</code>&nbsp;&mdash; добавить тег пользователя в чёрный список.</p>
<p><code>ubl *тег</code> или <code>ubl **тег с пробелами</code>&nbsp;&mdash; удалить тег из чёрного списка.</p>
<p><code>ubl @nickname *тег</code> или <code>ubl @nickname **тег с пробелами</code>&nbsp;&mdash; удалить тег пользователя в чёрного списка.</p>

<a name="settings"></a><h2>Профиль</h2>
<p><code>get параметр</code>&nbsp;&mdash; посмотреть текущее значение параметра.</p>
<p><code>set password</code> или <code>set passwd</code>&nbsp;&mdash; сменить пароль.</p>
<p><code>set private on|off</code>&nbsp;&mdash; сделать блог закрытым/публичным.</p>
<p><code>set lang en</code>&nbsp;&mdash; установить язык.</p>
<p><code>set xhtml on|off</code>&nbsp;&mdash; включить/отключить сообщения в формате XHTML-IM.</p>
<p><code>set highlight on|off</code>&nbsp;&mdash; получение сообщений, в которых упомянут Ваш никнейм.</p>
{#<p><code>set user_resource on|off</code>&nbsp;&mdash; use separate resources for each user.</p>
<p><code>set post_resource on|off</code>&nbsp;&mdash; use separate resources for each post.</p>#}
<p><code>get xmpp</code> — список добавленных JID'ов.</p>
<p><code>set xmpp [+]JID</code>&nbsp;&mdash; добавить JID.</p>
<p><code>set xmpp -JID</code>&nbsp;&mdash; удалить JID.</p>
<p><code>on</code>&nbsp;&mdash; включить доставку сообщений.</p>
<p><code>off</code>&nbsp;&mdash; отключить доставку сообщений.</p>

<a name="aliases"></a><h2>Алиасы</h2></a>
<p><code>alias</code>&nbsp;&mdash; просмотреть список пользовательских и глобальных алиасов.</p>
<p><code>alias алиас</code>&nbsp;&mdash; посмотреть значение алиаса.</p>
<p><code>alias алиас = значение</code>&nbsp;&mdash; установить алиас.</p>
<p><code>unalias алиас</code>&nbsp;&mdash; удалить алиас.</p>

{% endblock %}
