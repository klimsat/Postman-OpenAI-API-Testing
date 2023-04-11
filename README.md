# Postman-OpenAI-API-Testing
В данном примере я буду использовать **GET** и **POST** запросы к **OpenAI API** в **Postman**.

## API Ключ

Во-первых,  нам необходимо зарегистрироваться на сайте OpenAI и после подтверждения номера телефона [сгенерировать ключ API](https://platform.openai.com/account/api-keys), нажав на **Create new secret key**.
![Screenshot_19](https://user-images.githubusercontent.com/25348662/231115477-df873f34-d924-497b-bcce-faa6cce90940.png)

С этим ключом API мы можем двигаться дальше.

## Postman - Коллекция и токен

Теперь нам нужен **[Postman](https://web.postman.co/)** и выполнение следующих шагов.
1. Войти в ваше рабочее пространство (Workspace).
2. Создать новую коллекцию.
3. В разделе **Authorization** напротив **Type** необходимо выбрать **Bearer Token**.
4. В поле **Token** необходимо ввести полученный вами на сайте OpenAI сгенерированный ключ.
5. Выделить в поле **Token** ваш ключ и во всплывающем окне нажать на **Set as variable**.![Screenshot_20](https://user-images.githubusercontent.com/25348662/231121743-a15f72e1-d760-4140-b7bf-39dc57e279c9.png)
6. В следующем всплывающем окне присвоить название ключу, например, **APITOKEN** и в **SKOPE** выбрать вашу действующую коллекцию.![Screenshot_21](https://user-images.githubusercontent.com/25348662/231122816-07b8249c-c34e-409c-8ca9-3fedb4b3323a.png)

## Postman - GET

Теперь мы можем обратиться с помощью **GET** запроса к OpenAI API и получить список действующих языковых моделей. Согласно [официальной документации по OpenAI API](https://platform.openai.com/docs/api-reference/authentication) мы можем сделать это с помощью голого запроса к адресу:

    https://api.openai.com/v1/models

Создаем новый запрос, выбираем **GET** тип запроса, вставляем адрес, нажимаем на **Send** и в ответном сообщения от серверной части получаем большой список всех моделей с их настройками.
![Screenshot_22](https://user-images.githubusercontent.com/25348662/231129567-191479dd-b6ed-4016-8a4c-8edb122c395a.png)

Лично меня интересует языковая модель **gpt-3.5-turbo**, так что далее буду использовать именно её.


## Postman - POST

Теперь мы попробуем пообщаться с языковой моделью **gpt-3.5-turbo** через отправку данных на сервер с помощью **POST** запроса. Согласно [официальной документации по исходящим запросам в OpenAI API](https://platform.openai.com/docs/api-reference/making-requests) мы можем сделать это с помощью запроса с к адресу:

    https://api.openai.com/v1/chat/completions
Необходимые шаги:
1. Создать новый запрос и выбирать **POST** тип запроса.
2. Ввести необходимый адрес, указанный выше.
3. Настроить тело запроса: открыть вкладку **Body**, выбрать **raw** и **JSON** формат.
4. Вставить сам код **JSON** запроса с указанием любых сообщений для ролей system и user:

```json
{
    "model": "gpt-3.5-turbo",
    "messages": [
        {
            "role": "system",
            "content": "Привет. Ты ИИ по имени Гитхазавр."
        },
        {
            "role": "user",
            "content": "Привет. Как тебя зовут?"
        }
    ],
    "max_tokens": 3000,
    "temperature": 0,
    "top_p": 1,
    "n": 1
}
```

5. Нажимаем на **Send** и получаем ответ.
![Screenshot_24](https://user-images.githubusercontent.com/25348662/231136837-900c5178-6f90-481b-b4e5-c8d67e5b578f.png)
