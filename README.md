# Музыкальный плеер

Источник: видео "Уроки по JavaScript. Как сделать аудиоплеер (музыкальный проигрыватель) на JavaScript" 
https://vkvideo.ru/video-101965347_456257150?sel=19460369

1. скачать себе 2 файла из папки audiojs по ссылке:
    - либо из репозитория GitHub (https://github.com/kolber/audiojs)
    - либо с Google.Диск (https://drive.google.com/drive/folders/1YmH_sC3PCJi7OxsEQhAVKN1n8aKpNsQK?usp=sharing)
- audio.min.js
- audiojs.swf

2. в ранее скачанную папку audiojs вставляем файлы с музыкой в формате mp3 
(можно скачать по ссылке https://drive.google.com/drive/folders/1dExRuOusgpT1FVyr9LtcDDgoYThiZkES?usp=sharing)

3. создать нужные файлы в ранее скачанной папке audiojs в программе "WebStorm" для работы с JavaScript
   (скачать бесплатную версию https://www.jetbrains.com/webstorm/);
- HTML (index.html) 
- CSS (style.css) 
- JS (script.js)

4. в файле index.html:

- меняем название в строке title в разделе head - Music play

```html
<title>Music play</title>
```

- подцепляем готовый audio.min.js из папки audiojs в разделе body

```html
<script src="audio.min.js"></script>
```

5. в файле script.js пишем функцию, которая создаст проигрыватель и будет обрабатываться по нажатию

```JS
audiojs.events.ready(function(){
    var as = audiojs.createAll();
});
```

6. в файле index.html подцепляем script.js в body

```html
<script src="script.js"></script>
```

7. в файле index.html, чтобы что-то воспроизвести, нужно вставить тэг audio в body

```html
<audio src="Король и Шут - Мой Характер.mp3"></audio>
```

8. подцепить стиль css в файле index.html в head

```html
<link rel="stylesheet" href="style.css">
```

9. в файле index.html в разделе body, чтобы застилизовать сам проигрыватель. И в dev вставляем свою музыку.
Добавляем к музыке - controls, чтобы был виде проигрыватель с кнопками

```html
<div class="audiojs" classname="audiojs" id="audiojs_wrapper0">
   <audio src="Король и Шут - Мой Характер.mp3" controls></audio>
</div>
```

10. в файле style.css стилизуем сам проигрыватель - делаем больше

```css
.audiojs{
   width: 350px;
   height: 80px;
}
```

11. в файле style.css в .audiojs, чтобы цифры времени проигрывания музыки не прыгали, когда они меняются

```css
font-family: monospace;
```

12. в файле style.css в .audiojs, чтобы цифры были больше в размерах
    
```css
font-size: 73px;
```

13. в файле style.css в .audiojs добавляем цвет проигрывателя

```css
background: #373338 -webkit-gradient(linear, left top, left bottom, color-stop(0, #ff0007), color-stop(0.5, #0c00bc), color-stop(0.51, #0c00bc), color-stop(1, #444));
}
```

14. в файле style.css в .audiojs регулируем по высоте проигрыватель, чтобы он был ровно по центру

```css
text-align: center;
```

# Итог:

1. в файле audio.css

```css
.audiojs {
   width: 350px;
   height: 80px;
   font-family: monospace;
   font-size: 73px;
   background: #373338 -webkit-gradient(linear, left top, left bottom, color-stop(0, #ff0007), color-stop(0.5, #0c00bc), color-stop(0.51, #0c00bc), color-stop(1, #444));
   text-align: center;
}
```

2. в файле index.html

```html
<!DOCTYPE html>
<html lang="en">
<head>
   <meta charset="UTF-8">
   <title>Music play</title>
   <link rel="stylesheet" href="style.css">
</head>
<body>
<script src="audio.min.js"></script>
<script src="script.js"></script>
<div class="audiojs" classname="audiojs" id="audiojs_wrapper0">
   <audio src="Король и Шут - Мой Характер.mp3" controls></audio>
</div>
</body>
</html>
```

3. в файле script.js 

```JS
audiojs.events.ready(function(){
   var as = audiojs.createAll();
});
```