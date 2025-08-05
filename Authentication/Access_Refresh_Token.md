###  Сравнение Access Token и Refresh Token

| Характеристика             | Access Token                            | Refresh Token                              |
|---------------------------|------------------------------------------|--------------------------------------------|
|  Назначение              | Доступ к защищённым ресурсам (API)       | Получение нового access token              |
|  Время жизни             | Короткое (5–60 минут)                    | Долгое (дни, недели)                       |
|  Используется как часто | В **каждом** запросе к API               | Только при обновлении access token         |
|  Где передаётся         | В заголовке `Authorization`             | В теле запроса или в cookie                |
|  Хранит ли инфу о юзере | Да (userID, роль, срок действия и т. д.) | Обычно нет (или просто ID токена)          |
|  Формат                 | Часто JWT                                | JWT или UUID                               |
|  Хранится на сервере?   | Нет (если stateless)                     | Часто — да (для контроля и отзыва)         |
|  Где хранится на клиенте| LocalStorage или HttpOnly Cookie         | HttpOnly Cookie (рекомендуется)            |
|  Можно ли отозвать?     | Нет (если stateless)                     | Да (если хранится на сервере)              |
|  Риски при утечке       | Ограниченный (короткий срок действия)    | Высокий (можно получить новые токены)      |

## Comparison of Access Token and Refresh Token

| Characteristic            | Access Token                                 | Refresh Token                                |
|---------------------------|-----------------------------------------------|-----------------------------------------------|
| Purpose               | Access to protected resources (API)           | Obtaining a new access token                   |
| Lifetime              | Short (5–60 minutes)                          | Long (days, weeks)                             |
| Usage frequency       | In every API request                          | Only when refreshing the access token          |
| How it is sent        | In the Authorization header                 | In the request body or in a cookie             |
| Contains user info    | Yes (user ID, role, expiration, etc.)         | Usually no (or just a token ID)                |
| Format                | Often JWT                                     | JWT or UUID                                    |
| Stored on server?     | No (if stateless)                             | Often yes (for control and revocation)         |
| Client-side storage   | LocalStorage or HttpOnly Cookie           | HttpOnly Cookie (recommended)                |
| Can it be revoked?    | No (if stateless)                             | Yes (if stored on the server)                  |
| Risk if leaked        | Limited (short lifespan)                      | High (can be used to obtain new tokens)        |
