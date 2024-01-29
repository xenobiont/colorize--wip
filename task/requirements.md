/\*\*

- Задание 3.
-
- Создать элемент h1 с текстом «Добро пожаловать!».
-
- Под элементом h1 добавить элемент button c текстом «Раскрасить».
-
- При клике по кнопке менять цвет каждой буквы элемента h1 на случайный.

- При каждом движении курсора по странице
- менять цвет каждой буквы элемента h1 на случайный.
  \*/

```js
/* Решение */
const title = document.createElement('h1');
const button = document.createElement('button');

button.innerText = 'Раскрасить!';

for (const letter of PHRASE) {
	const span = document.createElement('span');

	span.innerText = letter;

	title.appendChild(span);
}

document.body.prepend(title);
title.parentNode.insertBefore(button, title.nextSibling);

const letters = document.querySelectorAll('span');

const colorize = () => {
	for (const letter of letters) {
		const randomColor = getRandomColor();

		letter.style.color = randomColor;
	}
};

button.addEventListener('click', colorize);
window.addEventListener('mousemove', colorize);
```
