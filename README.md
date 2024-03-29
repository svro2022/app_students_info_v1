# App: students information <br>

> **main.py** - файл запуска программы <br>

---
## Описание

```python
Программа: Введите номер студента
Пользователь: 1
Программа: Студент Jane Snake
Программа: Знает Python, Go, Linux
Программа: Выберите специальность для оценки студента Jane Snake
Пользователь: Backend
Программа: Пригодность 50%
Программа: Jane Snake знает Python, Linux
Программа: Jane Snake не знает Docker, SQL

```

```python
Программа: Введите номер студента
Пользователь: 999
Программа: У нас нет такого студента
```

```python
Программа: Введите номер студента
Пользователь: 1
Программа: Студент Jane Snake
Программа: Знает Python, Go, Linux
Программа: Выберите специальность для оценки студента Jane Snake
Пользователь: Mobile
Программа: У нас нет такой специальности
```

### Файлы с данными для программы:

Вы можете разместить файлы в корне проекта, а можете положить их в папку data. Если так, используйте для создания путей `os.path`.

students.json

```python
[
	{ 
		"pk": 1,
		"full_name":  "Jane Snake",
		"skills": ["Python", "Go", "Linux"]
	},
	{ 
		"pk": 2,
		"full_name":  "Sheri Torres",
		"skills": ["Java", "Swify", "Fortran", "Basic"]
	},
	{ 
		"pk": 3,
		"full_name":  "Burt Stein",
		"skills": ["Planning", "Negotiation", "Management", "Sales"]
	},
	{ 
		"pk": 4,
		"full_name":  "Bauer Adkins",
		"skills": ["HTML", "CSS", "JavaScript", "React", "Node.js"]
	}
]
```

professions.json

```python
[
	{
		"pk": 1,
		"title": "Backend",
		"skills": ["Python", "Linux", "Docker", "SQL", "Flask"]
  },
	{
		"pk": 2,
		"title": "Frontend",
		"skills": ["HTML", "CSS", "React", "JavaScript"]
  },
	{
		"pk": 3,
		"title": "Testing",
		"skills": ["Windows", "MacOS", "SQL", "Jira"]
  }
]
```
---

## Реализация

При работе над программой сперва напишите полезные функции, затем протестируйте их, вызвав каждую несколько раз. Затем  перейдите к написанию основного кода программы, затем протестируйте программу, запустив несколько раз с разными данными. Не забудьте добавить комментарии к коду и докстринги к каждой функции.

**Шаг 1**

Создайте файл [utils.py](http://utils.py) или [functions.py](http://functions.py) и напишите в нем полезные функции. 

Эти функции мы будем использовать дальше в других функциях. 

| load_students() | Загружает список студентов из файла |
| --- | --- |
| load_professions() | Загружает список профессий из файла |

Когда вы написали функции – протестируйте их, вызвав несколько раз. 

**Шаг 2**

Допишите полезные функции, которые вытаскивали бы студента по номеру и профессию по названию. 

| get_student_by_pk(pk) | Получает словарь с данными студента по его pk |
| --- | --- |
| get_profession_by_title(title) | Получает словарь с инфо о профе по названию |

Когда вы написали функции – протестируйте их, вызвав несколько раз с разными аргументами.

Шаг 3

Напишите функцию `check_fitness(student, profession)`, которая получив студента и профессию, возвращала бы словарь типа:

```python
{
  "has": ["Python", "Linux"],
  "lacks": ["Docker, SQL"],
  "fit_percent": 50
}
```

Эта функция должна использовать методы множеств.

**Шаг 4** 

Допишите основной код программы по следующему алгоритму:

- получить ввод pk пользователя
- проверить существование такого пользователя.

Если такой студент есть – выведите информацию о пользователе
Если такого студента нет - завершитесь

```python
Программа: Введите номер студента
Пользователь: 1
Программа: Студент Jane Snake
Программа: Знает Python, Go, Linux
```

```python
Программа: Введите номер студента
Пользователь: 999
Программа: У нас нет такого студента
```

- Получите ввод title профессии 
Проверьте существование такой профессии
Если да – получите соответствие с помощью  `check_fitness`
Если нет – завершитесь

```python
Программа: Выберите специальность для оценки студента Jane Snake
Пользователь: Data Science
У нас нет такой специальности
```

- выведите результаты

```python
Программа: Пригодность 50%
Программа: Jane Snake знает Python, Linux
Программа: Jane Snake не знает Docker, SQL
```