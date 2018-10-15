# Метод list
Получает список ресурсов User для указанного кластера MongoDB.
 

 
## HTTP-запрос
`GET /managed-mongodb/v1/clusters/{clusterId}/users`
 
## Path-параметры {#path_params}
 
Name | Description
--- | ---
clusterId | Обязательное поле. Идентификатор кластера, для которого нужно получить список пользователей MongoDB. Чтобы получить идентификатор кластера, используйте запрос [list](/docs/mdb/api-ref/mongodb/Cluster/list).  Максимальная длина — 50 символов.
 
## Query-параметры {#query_params}
 
Name | Description
--- | ---
pageSize | Максимальное количество результатов на странице ответа на запрос. Если количество результатов больше чем [pageSize](/docs/mdb/api-ref/mongodb/User/list#query_params), сервис вернет значение [nextPageToken](/docs/mdb/api-ref/mongodb/User/list#responses), которое можно использовать для получения следующей страницы.  Допустимые значения — от 0 до 1000 включительно.
pageToken | Токен страницы. Установите значение [pageToken](/docs/mdb/api-ref/mongodb/User/list#query_params) равным значению поля [nextPageToken](/docs/mdb/api-ref/mongodb/User/list#responses) прошлого запроса, чтобы получить следующую страницу результатов.  Максимальная длина — 100 символов.
 
## Ответ {#responses}
**HTTP Code: 200 - OK**


 
Поле | Описание
--- | ---
users | **object**<br><p>Ресурс User для MongoDB. Подробнее см. в разделе <a href="/docs/mdb/concepts">Взаимосвязь ресурсов сервиса</a>.</p> 
users.<br>name | **string**<br><p>Имя пользователя MongoDB.</p> 
users.<br>clusterId | **string**<br><p>Идентификатор кластера MongoDB, к которому принадлежит пользователь.</p> 
users.<br>permissions | **object**<br><p>Набор разрешений, предоставленных пользователю.</p> 
users.<br>permissions.<br>databaseName | **string**<br><p>Имя базы данных, к которой предоставляет доступ разрешение.</p> 
users.<br>permissions.<br>roles | **string**<br><p>Роли MongoDB базы данных databaseName, которые предоставляет разрешение.</p> 
nextPageToken | **string**<br><p>Токен для получения следующей страницы результатов в ответе. Если количество результатов больше чем <a href="/docs/mdb/api-ref/mongodb/User/list#query_params">pageSize</a>, используйте <a href="/docs/mdb/api-ref/mongodb/User/list#responses">nextPageToken</a> в качестве значения параметра <a href="/docs/mdb/api-ref/mongodb/User/list#query_params">pageToken</a> в следующем запросе списка ресурсов. Все последующие запросы будут получать свои значения <a href="/docs/mdb/api-ref/mongodb/User/list#responses">nextPageToken</a> для перебора страниц результатов.</p> 