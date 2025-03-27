<h1>Простая рассылка по мессенджеру Telegram (PYOGRAM)</h1>

<p>ВНИМЕНИЕ! В РАССЫЛКЕ ПРИСУТСТВУЮТ НЕКОТОРЫЕ ЗАЩИТЫ ОТ БАНА, НО <ins><u>ОНИ НЕ ДАЮТ 100% ГАРАНТИИ! ОТВЕТСТВЕННОСТЬ ЗА БАН НЕ НЕСЁМ</u></ins></p>

<h2>Установка:</h2>
<p>Просто скачиваем данный репозеторий архивом и распаковывем в удобное вам место)</p>

<h2>Работа с рассылкой:</h2>
<p>После распаковыки архива, запускаем main.exe. Скрипт попросит данные API.</p><br>
<p>Эти данные можно получить по адресу <a href="https://my.telegram.org/">my.telegram.org</a></p><br>
<p>При регистрации "своего приложения по API" советую выбирать в разделе "Platform" пункты "Web", "Desktop" (почему-то с этим пунктом реже банит)</p><br>
<p>URL заполняйте по желанию, но тоже рекомендую хотя бы на заглушку в виде приёмника хука и логирования данных, простой пример:</p><br>

```
Webhook.php
```
```PHP
<?php
$data = file_get_contents("php://input");

$f = fopen("WebhookTelegram.txt", "a+");
fwrite($f, $data."\n\n\n");
fclose($f);
?>
```

<p>После регистрации приложения у вас засветятся все нужные данные для ввода!</p><br><br>

<p>Файлы message.txt и users.txt содержат в себе текст рассылки и список пользователей для рассылки</p><br>
<p>Пример users.txt:</p><br>

```
@kringgamanager3
+79999999999
@kringgadevManager
```

<p>Пример message.txt:</p><br>

```
Текст для ~~Рассылки~~!
```

<p>Обратите внимание, что в users.txt можно оставлять как номер телефона, username, так и user_id, chat_id.</p><br>
<p>Также важно упомянуть, что users.txt должен содержать данные о каждом юзере с новой строки!</p><br>
<p>Вроде как все основные моменты объяснены... Соответственно вся рассылка происходит путём запуска main.exe.</p><br>
<p>Вспомнил! При авторизации приложение создат файлы сессии и AUTH.txt, логично, что их удалять <ins><u>НИ В КОЕМ СЛУЧАЕ НЕЛЬЗЯ</u></ins>, но упомяну это тут повторно.</p><br>
<p>НИКАКИЕ ФАЙЛЫ, ЧТО СОЗДАЁТ ПРИЛОЖЕНИЕ, УДАЛЯТЬ НЕЛЬЗЯ!</p><br>
<h2>Немного о "защите"</h2>
<p>Используется сессионный вход (1 раз заходите в аккаунт, после чего он заходит автоматически).</p><br>
<p>По мимо этого между рассылками сделан интервал в 45 секунд. Моментальная отправка сообщения = моментальный бан, по этому присутствует задержка.</p>
<p>Это самые базовые принципы избежания бана, я в курсе, что их на ряд больше, но данный проект не более чем мусорная, бесплатная рассылка для личного пользования.</p>
