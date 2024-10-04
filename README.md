# Placeholder API Tests

## Запуск проекта

1.  Склонируйте репозиторий
2.  Откройте проект в IntelliJ IDEA или IntelliJ Aqua
3.  Запустите тесты (PostsTest)
4.  Отчет Allure будет сгенерирован в директории `target/allure-results`

## Дополнительная информация и комментарии

- Код, функционал и сообщения в проверках я писал на английском языке, с расчетом на то, что команда может быть интернациональной. 
- Комментарии к коду я писал на русском языке для улучшения восприятия проверяющим ТЗ.
- Добавил комментарий к тесту [**Create post failure**](./src/test/kotlin/tech.themukha.placeholdertests/posts/PostsTest.kt#L39) касательно того, что параметризованные тесты фейлятся.
- В параметризованных тестах использовал 2 типа источников тестовых аргументов - `ValueSource` и `MethodSource`, чтобы "показать" навыки.
- В идеале я бы везде использовал MethodSource для динамической генерации тестовых данных и уменьшения флакающих тестов.

[//]: # (TODO: заменить строку L42 на другое значение, если изменится порядок тестов для улучшения читаемости README в ГитХабе)

## Тестируемые ендпоинты
> На основе [JSONPlaceholder Guide]()

- `/posts`
  - Методы для тестирования:
    - [X] GET (получение всех постов)
      - Параметры фильтрации:
        - [X] `id` - по id поста
        - [X] `userId` - по id пользователя
        - [X] `title` - по заголовку поста
        - [X] `body` - по телу поста
    - [X] POST (создание нового поста)
- `/posts/${postId}`
  - Методы для тестирования:
    - [X] GET (получение по ID)
    - [ ] PATCH (полное обновление)
    - [ ] PUT (частичное обновление)
    - [ ] DELETE (удаление)
- `/posts/${postId}/comments`
  - Методы для тестирования:
    - [ ] GET (получение комментариев к посту)