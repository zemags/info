#### HLS (HTTP Live Streaming) - формат  ОТТ распространения на базе HTTP для стриминга
- плюсы
  - открытый безлицензионный формат
  - поддержка устройствами эпла
  - вставка реклама/хорошая адаптация к защите авторских прав (DRM - digital rights managment).
  - поддерживается имеющимся парком кодеров.
  - поддерживается различными приложениями и готовыми плеерами.
- минусы:
  - корпоративный стандарт. последние 10 лет он в общем-то не развивается.
  - встроенное шифрование не является полноценной DRM. для наложения DRM требуется инкапсуляция в другой формат.
  - некоторые плееры поддерживают HLS через Flash. Flash сдает позиции, уйдет и поддержка HLS такими плеерами.
  - поддержка HLS браузерами не будет расширяться


#### DASH (Dynamic Adaptive Streaming over HTTP)
- плюсы:
  - отраслевой стандарт
  - поддержка живого вещания и VOD (Video on demand)
  - Ннативная поддержка в Chrome/Android
  - поддержка кодерами
  - поддержка готовыми плеерами
- минусы:
  - нет нативной поддержки большинством браузеров
  - нет нативной поддержки в эпле хоть есть библы
  - некоторые плееры используют плагины, если плагины исчезнуть, то ВСЁ
  - проблемы с DRM, не отработана вставка рекламы

#### OTT (Over the Top) - предоставление видеоуслуг от поставщика к клиенту минуя провайдер - напрямую