# Placeholder API Tests

## Запуск проекта

1.  Склонируйте репозиторий
2.  Перейдите в корневую директорию проекта через терминал и выполните команду:
    - Для Windows:
    ```shell
      ./gradlew.bat cleanTest test
    ```
    - Для Unix (Linux, MacOS):
    ```shell
      ./gradlew cleanTest test
    ```
3. Отчет Allure будет сгенерирован по следующему пути `./build/reports/allure-report/allureReport/index.html`
    > [Клик здесь](./build/reports/allure-report/allureReport/index.html), чтобы открыть отчет после выполнения тестов

## Дополнительная информация и комментарии

- Код, функционал и сообщения в проверках я писал на английском языке, с расчетом на то, что команда может быть интернациональной. 
- Комментарии к коду я писал на русском языке для улучшения восприятия проверяющим ТЗ.
- Добавил комментарий к тесту [**Try to create post with invalid data**](./src/test/kotlin/tech/themukha/placeholdertests/posts/CreatePostsTests.kt#L32) касательно того, что параметризованные тесты фейлятся.
- В параметризованных тестах использовал 2 типа источников тестовых аргументов - `ValueSource` и `MethodSource`, чтобы "показать" навыки.
- В идеале я бы везде использовал MethodSource для динамической генерации тестовых данных и уменьшения флакающих тестов.

## Тестируемые ендпоинты
> На основе [JSONPlaceholder Guide](https://jsonplaceholder.typicode.com/guide/)

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
    - [X] PATCH (частичное обновление)
    - [X] PUT (полное обновление)
    - [X] DELETE (удаление)
- `/posts/${postId}/comments`
  - Методы для тестирования:
    - [ ] GET (получение комментариев к посту)