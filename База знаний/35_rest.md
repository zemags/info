#### Что такое REST?
- representational state transfer
- это архитектурный подход, определяющий как API должен выглядеть.
- этим правилам следует разраб при создании приложения
- одно из правил гласит:
- При обращении к опредленному адреасу вы должны получать определеннйы набор данных(ресурс)

#### Что такое эндпоинт?(ЕЩЕ ABC)
- эндпоинт описывают точки входа\выхода по которым можн работать с сервисом
характеризуется:
- А. адресом-addres-описывает то как мы можем найти наш сервис
- Б. байндингом -binding-описывает как оменно отправлять сообщения(по какому протоколу и формате)
- К. контрактом-contract - какие данные и действия будут доступны через этот эндпоинт

#### Что такое маршрут в структуре запроса?
- это адрес по которому отправлется ваш запрос
- структура: root-endpoit/?
    - root-endpoint это точка приема(входа\выхода) запроса на стороне сервера (API)
    - пример:конечная точка гитхаба: https://api.github.com/
- путь определяет запрашиваемый ресурс
    - пример:получить все репы юзера на гитхабе: https://api.github.com/users/ivan/repos
- последняя часть маршрута - это параметры запроса
    - использовать в запросе наборы парк ключ\значение
      - всегда наичнается  вопроса
      - каждая пара делиться & амперсандом
        - пример: ?query1=value1&query2=vaue2

#### Анатомия запроса
1. маршрут отправки
2. типа метода
3. зоголовки
4. тело(данные)

#### виды статус кодов?от 100 до 500+
- 200+ запрос успешен
- 300+ запрос перенаправлен на другой маршрут
- 400+ ошибка на стороне клиента
- 500+ ошибка на стороне сервера

#### Что такое зоголовок в запросе?
- представляют из себя пары ключ\значение
- предоставить инфу клиенту\серверу
- для аутентификации и авторизации
- итд
    - пример: "Content-type: application/json". Missing the opening ".
    - примерс курлом: curl -H "Content-Type: application/json" https://api.github.com

