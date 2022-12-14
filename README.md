# Чат

### Проект состоит из двух модулей:

- Server - ожидает подключения пользователей и осуществляет взаимодействие между клиентами при отправке сообщений.
- Client - подключается к серверу чата и отправляет и получает новые сообщения.

Проект создан на сборщике проектов Maven.

Файлы application.properties содержат информацию о хосте и порте, а также команде выхода из чата.
Файлы logServer.txt и logClient.txt - файлы логов. 

### Принцип работы:
Сервер ждет подключения Клиентов. Каждый клиент на сервере функционирует в качестве отдельного потока. Взаимодействие осуществляется в клиент-серверном режиме. Пользователь вводит сообщения. Сервер принимает сообщения и рассылает их всем пользователям. Для выхода из Чата пользователь вводит команду определенную в фале настроек. После отключения от Сервера Клиент завершает работу.

### Модуль Server содержит классы:
- Server - класс, отвечающий за подключение клиентов, запускает работу сервера.
- Connection - класс соединения, реализует методы приема и отправки сообщений.
- ServerLogger - записывает историю функционирования серверного приложения, запись ведется в файл.
- ServerProperties - класс осуществляет чтение настроек из файла application.properties.
- Message, MessageType,ConsoleHelper - вспомогательные классы для работы с сообщениями.

### Модуль Client содержит классы: 
- Client -  класс запускает работу клиента, работающего из консоли. Клиент, в начале своей работы, считывает из файла адрес и порт сервера, подсоединяется к указанному адресу, получает запрос имени от сервера и отправляет имя пользователя серверу, дожидается принятия имени сервером. После этого клиент обменивается текстовыми сообщениями с сервером. 
- BotClient - класс клиента-бота, работающего из консоли. Это бот, который отправляет текущее время или дату, когда получит соответствующий запрос.
- Connection - класс соединения, реализует методы приема и отправки сообщений.
- ClientLogger - записывает историю функционирования, запись ведется в файл.
- ClientProperties - класс осуществляет чтение настроек из файла application.properties.
- Message, MessageType,ConsoleHelper - вспомогательные классы для работы с сообщениями.
