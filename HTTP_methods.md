Домашка на вторник - изучить методы НТТР запросов 

Что такое HTTP
HTTP расшифровывается как HyperText Transfer Protocol, "протокол передачи гипертекста"
На данный момент он используется для передачи произвольных данных(изначально для передачи документов в HTML).

В основе HTTP - клиент-серверная структура передачи данных. Клиент формирует запрос(request) и отправляет на сервер; на сервере запрос обрабатывается, формируется ответ (response)  и передается клиенту.

HTTP не шифрует передаваемую информацию. Для защиты передаваемых данных используется расширение HTTPS(HyperText Transfer Protocol Secure), которое упаковывает передаваемые данные в криптографический протокол SSL или TLS.

???????????????????????????????????????????????????????????????????????????

Структура HTTP запроса
HTTP запрос состоит из 3х основных частей:
- строка запроса (request line), в ней указывается метод передачи, версия протокола HTTP к URL, к которому должен обратиться сервер;

- заголовок (message header), содержат тело сообщения, передаваемые параметры и др. сведения;??????????
- тело сообщения (entity body), могут находиться передаваемые в запросе данные.??????????
???????????????????????

HTTP Методы
Для того, чтобы указать серверу на то, какое действие мы хотим произвести с ресурсом, используются различные HTTP-методы(тип HTTP запроса), которые описывают действия с ресурсами.


Http methods
 1. GET запрашивает представление ресурса. Извлекает данные.

Примечание: Строка запроса (имя/значение) отправляется в URL ??? картинка
Синтакс кода ??? картинка

 2. POST для отправки сущностей к определенному ресурсу. Часто вызывает изменение состояния или какие-то побочные эффекты на сервере.

Примечание: Отправляемые данные содержатся в теле запроса.
Синтакс кода

 3. PUT заменяет все текущие представления ресурса данными запроса. 
 4. PATCH для частичного изменения ресурса
 5. DELETE удаляет указанный ресурс
 6. HEAD запрашивает ресурс так же как и GET, но без тела ответа.
 7. OPTIONS используется для описания параметров соединения с ресурсом.

 8. COPY создает дубликат исходного ресурса, указанного в Request-URI, в целевом ресурсе, указанном в URI в заголовке Destination. Заголовок Destination ДОЛЖЕН присутствовать. Точное поведение метода COPY зависит от типа исходного ресурса. 

Заголовок Overwrite можно задать, чтобы запретить перезапись уже существующего файла с таким именем. Значение T, по умолчанию, разрешает перезапись, значение F — запрещает.Если в каталоге /animals/ уже есть файл lion.png, то запрос из примера не будет выполнен.

Если копирование прошло успешно, возвращается следующий ответ:

HTTP/1.1 201 Created
Content-Length: 0 

 9. LINK используется для установления одной или нескольких связей между ресурсом, идентифицированным действующим URI запроса, и одним или несколькими другими ресурсами.

10. UNLINK используется для удаления одной или нескольких связей между ресурсом, идентифицированным действующим URI запроса, и другими ресурсами.

11. PURGE — это то, что происходит, когда вы выбираете объект из кеша и отбрасываете его вместе с его вариантами. Вызывается через HTTP с помощью метода PURGE.

HTTP-purge аналогична HTTP-запросу GET, за исключением того, что используется метод PURGE. На самом деле вы можете называть этот метод как угодно, но большинство людей называют это очисткой. Некоторые HTTP-серверы и системы кэширования действительно реализуют PURGE, например, Squid и Varnish:
Squid: Как удалить объект из кеша?
Varnish: Очистка и бан

12. LOCK
13. UNLOCK
14. PROPFIND
15. VIEW


Таблица кодов ответа (состояния) HTTP гиперссылка на коды


