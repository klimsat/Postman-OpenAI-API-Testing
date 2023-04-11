# Postman-OpenAI-API-Testing
В данном примере я буду использовать **GET** и **POST** запросы к **OpenAI API** в **Postman**.

## API Ключ

Во-первых,  нам необходимо зарегистрироваться на сайте OpenAI и после подтверждения номера телефона [сгенерировать ключ API](https://platform.openai.com/account/api-keys), нажав на **Create new secret key**.
![Screenshot_19](https://user-images.githubusercontent.com/25348662/231115477-df873f34-d924-497b-bcce-faa6cce90940.png)

С этим ключом API мы можем двигаться дальше.

## Postman - Коллекция и токен

Теперь нам нужен **Postman** и следующие шаги.
1. Войти в ваше рабочее пространство (Workspace).
2. Создать новую коллекцию.
3. В разделе **Authorization** напротив **Type** необходимо выбрать **Bearer Token**.
4. В поле **Token** необходимо ввести полученный вами на сайте OpenAI сгенерированный ключ.
5. Выделить в поле **Token** ваш ключ и во всплывающем окне нажать на **Set as variable**.![Screenshot_20](https://user-images.githubusercontent.com/25348662/231121743-a15f72e1-d760-4140-b7bf-39dc57e279c9.png)
6. В следующем всплывающем окне присвоить название ключу, например, **APITOKEN** и в **SKOPE** выбрать вашу действующую коллекцию.![Screenshot_21](https://user-images.githubusercontent.com/25348662/231122816-07b8249c-c34e-409c-8ca9-3fedb4b3323a.png)
