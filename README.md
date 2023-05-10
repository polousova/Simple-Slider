# Simple-Slider

<h6>HTML/CSS(SCSS)/JavaScript</h6>

Простой слайдер с элементами управления и индикатором текущей страницы (точки) с переключением вручную на HTML/CSS/чистый JavaScript.
Слайдер переключается как стрелками "вперед", "назад", так и кликом по точке.
Можно добавить любое количество фотографий, код JavaScript при этом редактировать не надо.<br><br>
Используйте изображения любого размера - они будут автоматически масштабированы под размер блока слайдера. Размер изображений не является фиксированным.
Размер блока слайдера, установленный по умолчанию: 950 пикселей по ширине и 650 пикселей по высоте.<br>
Для плавной смены изображений добавлена анимация.
<hr>
<ul><h5>Добавить/удалить изображение:</h5>
  <li>В index.html найти div с классом "wrap". Добавить/удалить нужное количество div class="slider-item" с вложенным в него изображением.</li>
  <li>Оставить столько div с классом "dot" в div class="slider-dots" сколько изображений в слайдере. div с классом "dot dot-active" должен быть один и стоять первым по счету.</li>
</ul>
<ul><h5>Изменить размеры блока слайдера - редактировать файл style.scss:</h5>
  <li>Максимальная ширина слайдера 950 px задана шириной контейнера - <br>
    .slider {<br>
	&nbsp;&nbsp;&nbsp;&nbsp; max-width: 950px;<br>
	&nbsp;&nbsp;&nbsp;&nbsp; margin: 0 auto;<br>
    } <br>
   Для изменения ширины измените значение свойства max-width.
  </li>
  <li>Высота блока слайдера 600 px задана свойством height для изображения: <br>
    .slider-item img {<br>
      &nbsp;&nbsp;&nbsp;&nbsp;width: 100%;<br>
      &nbsp;&nbsp;&nbsp;&nbsp;height: 600px;<br>
      &nbsp;&nbsp;&nbsp;&nbsp;object-fit: cover;<br>
      &nbsp;&nbsp;&nbsp;&nbsp;animation-name: Appearance;<br>
      &nbsp;&nbsp;&nbsp;&nbsp;animation-duration: 1s;<br>
      &nbsp;&nbsp;&nbsp;&nbsp;animation-timing-function: cubic-bezier(.1, -.6, .2, 0);<br>
    } <br>
  Для изменения высоты измените значение свойства height.
  </li>
  <li>Свойство object-fit: cover позволяет использовать изображения различных размеров, но нужно иметь в виду, что изображения будут пропорционально масштабированы, чтобы поместиться в блок слайдера заданных размеров.</li>
</ul>
<hr>
<ul>Изменение количества слайдов и размера блока слайдера требует только редактирования HTML разметки и стилей (index.html и style.cscc файлов). Исполнение же скрипта при этом не меняется за счет двух моментов:
	<li>последний слайд, какой бы порядковый номер у него ни был, не задан жестко, а задан через свойство length псевдомассива элементов slides. Когда индекс текущего слайда становится больше длины псевдомассива, слайдер возвращается на первый слайд.<br>
	Аналогично с точками.</li>
	<li>Событие click делегировано "обертке" точек, что позволяет применять обработчик событий не к каждой точке, а к их "обертке". Мы проходим циклом for по всем точкам до последнего элемента псевдомассива dots.</li>
</ul><br>
Для подробного разбора как работает данный слайдер смотри комментарии в файле script.js.<br>
Смотри также усовершенствованную версию данного слайдера - https://github.com/polousova/Automatic-Slider.git. 
