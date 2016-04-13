# Класс bgFB2

PHP класс **bgFB2** преобразует HTML строку в файл [Fiction Book (fb2)](http://fictionbook.org).
Для работы требуется класс [BgClearHTML](https://github.com/VBog/BgClearHTML).

## Основная функция класса ##

`public function prepare ( (string) $content, (array) $options )`
	
Параметры:
	
`$content` - строка, содержащая HTML-разметку;
	
`$options [ $key => $value ]` - массив параметров настройки,
	
	`$opt = array(
		"title"=> *'<Название книги>'*,
		"author"=> *'<Имя автора>'*,
		"genre"=> *'<Жанр (строго из [списка](http://fictionbook.org/index.php/%D0%96%D0%B0%D0%BD%D1%80%D1%8B_FictionBook_2.1))>'*,
		"lang"=> *'<Код языка книги по ISO 639-1>'*,
		"version"=> *'<Имя автора: Фамилия Имя>'*,
		"cover"=> *'<Ссылка на изображение обложки книги (.jpg или .png)>'*,
		"publisher"=>*'<Информация об издателе>'*,
		"css"=> *'<Пользовательская таблица стилей CSS для оформления книги>'*
	);`
	
Возвращает текст в формате fb2.
	
## Функция записывает текст в файл ##

`public function save ( (string) $file,  (string) $content)`

Синоним `file_put_contents()`:

	`public function save ($file, $content) {
		$put = file_put_contents($file, $content);
		return $put;
	}`

Возвращает количество записанных байт в файл, или FALSE в случае ошибки.
