#### стек протоколов
- Стек протоколов — набор сетевых протоколов, для взаимодействия узлов в сети.
- Протоколы работают одновременно, нужно чтобы не возникало конфликтов или незавершённых операций.
- Каждый уровень выполняет конкретную задачу — подготовку, приём, передачу данных и последующие действия с ними.

#### Сетевая модель OSI стека (The Open Systems Interconnection model)
- Чтобы сетевые устройства могли взаимодействовать друг с другом.
- Модель определяет различные уровни взаимодействия систем.
- Каждый уровень выполняет определённые функции при таком взаимодействии.


7.**П**рикладной. тип данных - **Д**анные. доступ к сетевым службам - https, ftp, websocket. хосты, межсетевой экран.

6.**У**ровень представлений. тип данных - **Д**анные. представление и шифрование данных - ascii, jpeg, midi. хосты, межсетевой экран.

5.**С**еансовый. тип данных - **Д**анные. управление сеансом связи - l2tp, rpc. хосты, межсетевой экран.

4.**Т**ранспортный. тип данных - **С**егменты/**Д**атаграммы. прямая связь между конечными пунктами\надежность - tcp, udp, порты. хосты, межсетевой экран.

3.**С**етевой. тип данных - **П**акеты. определение маршрута, логическая адресация - ipv4, ipv6, ipsec. маршрутизатор, сетевой шлюз.

2.**К**анальный. тип данных - **Б**айты/**К**адры. физическая адресация - ppp, ethernet, 802.22, сетевая карта. сетевой мост, точка доступа.

1.**Ф**изический. тип данных -**Б**айты. работа со средой передачи, сигналами, двоичные данные. usb, оптоволокно, концентратор.


#### как происходит передача
- по сетевым уровням(стеку) объекты передают блоки данных PDU
- в блоке данных PDU есть блок служебных данных SDU
- передающий составляет данные на самом верхнем уровне стека - прикладном
- далее двигается вниз, объеденев верхний, нижный или оба создает слой N-1 PDU и так вниз до конца процесс повторяется
- приемное устройство динные с самого низкого вверъ в виде SDU

#### датаграмма
- блок информации, передаваемый протоколом через сеть без предварительного установления соединения и создания виртуального канала.