# Бот для облегчения посылки обращений о нарушении правил парковки в ГАИ (<https://faq.rfrm.io/parking.html>)

Бот умеет прикреплять присланные фотографии к [обращению](https://mvd.gov.by/ru/electronicAppealLogin) и заполнять его вашими личными данными и информацией о нарушении. После отправлять его. Также фото нарушений отправляются в [телеграм-канал](http://t.me/parkun) и [твиттер](https://twitter.com/parkun_bot).

Работает по всей Беларуси.

Бот развернут по адресу <http://t.me/parkun_by_bot>.

Одобряются issue, pull requests и прочие привнесения. [Инструкция для разработчиков.](./docs/russian/developers_guide.md)

Спасибо за внимание.

***

## Changelog

### 2.10.3

- Кнопка города и кнопка, что все окей с адресом поменяны местами.

### 2.10.2

- Немного более строгая проверка на наличие города в адресе нарушения.

### 2.10.1

- Ускорена реакция на нажатие кнопки отправки обращения.
- Убран один шаг из процесса когда пользователю предлагается дописать населенный пункт к адресу нарушения.

### 2.10.0

- Примитивный контроль за присутствием в адресе нарушения города.
- На вводе адреса добавлена инфа о том, что дополнительную информацию можно будет ввести позже.
- Мелкие улучшения.

### 2.9.2

- Подготовка бота к деплою с помощью docker hub.

### 2.9.1

- Текст обращения дополнен указанием на то, что обращение считается информацией о проишествии.
- [Отправитель] Повышение надежности.
- Уменьшение мусорного вывода в логи бота.

### 2.9.0

- Добавлена возможность отправки обращения в конкретный район Минска. Район определяется автоматически. Как и раньше можно перевыбрать вручную.

### 2.8.1

- Исправлено отображение адреса отправителя. Теперь нет больше лишних запятых.

### 2.8.0

- Переделано меню ввода данных об отправителе нарушения. Появилась навигация по данным и возможность досрочно завершить ввод.

### 2.7.1

- Обновлен python до 3.8.2.
- Починена ошибка, когда в саммари обращения подставлялась не та дата, которая была введена.

### 2.7.0

- При введении всех данных, которые требуются для отправки обращения, пользователю теперь предлагается отправить неотправленное из-за этого обращение, если оно есть.
- При отмене какого-либо действия или при прерывании работы, собщения о возврате к работе теперь будут более прозрачные для каждого режима.

### 2.6.5

- Починено повреждение текущего вводимого обращения в момент, когда прилетает просьба ввести капчу и пользователь выбирает отменить обращение вместо ввода капчи.

### 2.6.4

- При вводе даты теперь можно время вводить через точку или запятую.
- Небольшое повышение надежности.

### 2.6.3

- Уточнены тексты некоторых сообщений от бота для большей ясности.

### 2.6.2

- Обновлены зависимости.

### 2.6.1

- Исправлен race condition при быстром добавлении фотографий нарушений.
- Примером адреса нарушения стал Брест вместо Минска.

### 2.6.0

- Новый механизм повторной отправки обращений, по идее более надежный. Бонусом возможность повторно отправить уже отправленное обращение (может быть, в случае неудачной отправки ботом).

### 2.5.0

- Теперь при вводе места нарушения бот предлагает выбрать 5 последних введенных адресов.

### 2.4.0

- Новый интерфейс для ввода даты нарушения. По умолчанию подставляется дата сегодня и остается ввести время в достаточно вольном формате.

### 2.3.1

- Исправление ошибок.
- Более надежный старт.
- Ленивые очереди в RabbitMQ чтобы они переживали рестарты (но все равно вроде не переживают).
- [Отправитель] Исправление ошибок.
- [Отправитель] Более надежный старт.
- [Отправитель] Значительно повышена скорость отправки.

### 2.3.0

- Переписана реализация стека состояний. В итоге бот немного осмысленнее сообщает об возврате в предыдущий режим.
- Хостинг telegra.ph внезапно начал иногда отдавать 500 при загрузке фото, приходится пробовать еще.
- Добавлено отображение примечания в тексте об отправке нарушения.

### 2.2.1

- [Отправитель] Много разных ухищрений, чтобы отправитель работал стабильно.
- Изменен текст приглашения для ввода капчи (в соответствии с новой капчей сайта МВД).

### 2.2.0

- [Отправитель] Изменена архитектура отправителя обращений. Отправитель теперь умеет работать с очередью обращений.
- Таймер ввода капчи перенесен в отправителя.

### 2.1.3

- Исправлена ошибка когда не удалялись временные файлы при отмене отправки обращения.

### 2.1.2

- Исправлена ошибка, когда перед постингом в канал буквы номера не заменялись на латинские.
- Обновлено Readme
- Повышена стабильность при смене языка бота или обращения
- [Отправитель] Если из ящика было взято недействительное обращение, то отправитель сходит за актуальным, а не упадет как раньше.

### 2.1.1

- [Отправитель] Повышена стабильность отправителей обращений, они теперь не бросаются отправлять два обращения одновременно.

### 2.1.0

- Добавлена возможность ввести номер телефона в личные данные.

### 2.0.10

- Починена ошибка неопределения адреса по локации.

### 2.0.9

- Добавлено [руководство для разработчика](docs/russian/developers_guide.md) паркун бота.
- Добавлено [немного про архитектуру бота](docs/russian/parkun_arch.md).
- Добавлено предупреждение о регистрозависимости капчи.
- Мелкие доработки.

### 2.0.8

- Доработки для более легкого разворачивания бота на сервере.

### 2.0.7

- Исправлена ошибка с пересохранением уже сохраненного обращения.

### 2.0.6

- Исправлена ошибка отваливающегося таймера отмены обращения.

### 2.0.5

- Добавлено притормаживание после кнопки отправить. Торжественно клянусь его когда-нибудь убрать.
- Исправление ошибок. Повышение стабильности работы бота.

### 2.0.4

- Исправление мелких ошибок.

### 2.0.3

- Обновлены ссылки на инструкцию по эксплуатации.
- Исправление мелких ошибок.

### 2.0.2

- При вводе личных данных бот теперь валидирует номер дома.
- Корпус предлагается ввести раньше дома, чтобы было понятно, что его не надо вводить вместе с домом.

### 2.0.1

- Баг когда бот не приветствовал пользователей старого бота в себе новом.

### 2.0

- Посылка обращений в ГАИ возвращена. [Подробности.](./docs/russian/parkun_2_announcement.md)

### 1.12.0

- Отключена посылка обращений. [Подробности](https://telegra.ph/Pochemu-bot-bolshe-ne-otpravlyaet-ehlektronnye-obrashcheniya-07-03).
    Вся остальная функциональность оставлена.

### 1.11.0

- При вводе личных данных теперь отображается текущее значение.
- Сообщение запроса ФИО согласовано с примером.

### 1.10.8

- Обращение дополнено требованием не выдавать персональные данные заявителя.

### 1.10.7

- Исправление письма обращения в соответствии с новым постановлением МВД от 08.01.2019 №5.
- Изменен адрес почты Гомельского УВД.

### 1.10.6

- Установлено ограничение в 10 фото на одно обращение.
- Мелкие исправления.

### 1.10.5

- Увеличение надежности при старте бота.

### 1.10.4

- Новые email для Гродненской и Витебской области.

### 1.10.3

- Была написана новая инструкция по отправке нарушений. Добавлена в раздел /help и отображается после каждой смены личных данных.

### 1.10.2

- В тело письма теперь явно добавляется email отправителя.

### 1.10.1

- В сообщение перед отправкой добавлена информация о твиттере.

### 1.10.0

- Бот теперь отправляет нарушения и в твиттер.
- Возможно починилось периодическое дублирование некоторых постов в канале при отправке обращения ботом.

### 1.9.5

- Сервер верификации адреса почты теперь получает информацию о языке бота.

### 1.9.4

- Уточнили сообщение о подтверждении ящика чтобы было понятно, что нарушение нужно вводить заново.

### 1.9.3

- Мелкие улучшения.

### 1.9.2

- Исправлена ошибка.

### 1.9.1

- Для удобства инспекторов ссылки на фото в обращении теперь озаглавлены и расположены компактно группой.
- Повышение надежности работы бота.

### 1.9.0

- Бот теперь умеет банить и разбанивать.

### 1.8.1

- В тело письма, наряду с фото нарушения, встраивается и ссылка на это фото текстом.
- На соединение для загрузки границ регионов повешен таймаут 5 сек.
- На беларуский язык переведена фраза "Не получилось подобрать адрес."
- Ускорена обработка отправленных боту фотографий.

### 1.8.0

- Беларуская мова у боце.

### 1.7.3

- Баг на айфонах. При нажатии на кнопку "Подтвердить email" отправляется много писем.

### 1.7.2

- Теперь бот шлет копию не на почтовый ящик пользователя, а файлом в чат.

### 1.7.1

- Добавлена проверка, является ли email временным, а не постоянным.

### 1.7.0

- Добавлена процедура верификации ящика электронной почты.

### 1.6.4

- Больше важного текста выделено жирным шрифтом.
- Теперь бот посылает нарушение в канал только после успешной отправки обращения по почте.

### 1.6.3

- Уточнено сообщение о необходимости посылки качественных фото, на которых хорошо видно номер и нарушение.

### 1.6.2

- Теперь обращение просит отвечать на него только по электронной почте. Чтобы спасти побольше деревьев.
- Дополнен хелп информацией о возможности ограниченного пакетного ввода нарушений.

### 1.6.1

- Мелкие улучшения.

### 1.6.0

- Добавлена возможность просмотра и изменения личной информации командой /personal_info. Команда /setup_sender удалена.

### 1.5.1

- Исправлена ошибка неработоспособности бота при некоторых сложных email адресах отправителей.

### 1.5.0

- Добавлена возможность при отправке нарушения указать примечание в письме, от отправителя письма.

### 1.4.3

- Добавлено сообщение о том, что на фото должно быть четко видно гос. номер и само нарушение.
- В процессе повышения регистра и замены латинских букв кириллицей при обработке гос. номера теперь буква "i" тоже заменяется.

### 1.4.2

- При вводе нарушения появилась возможность выбрать адрес, введенный в прошлый раз.
- Изменен способ ответа на обращения (для ответчика).

### 1.4.1

- Смена хостинга для встроенных в тело письма фоток.

### 1.4.0

- Предварительный просмотр перед отправкой теперь формируется вместо с фотографиями нарушения.
- В предварительном просмотре перед отправкой добавлена информация о публикации в канале.
- В тексте предварительного просмотра перед отправкой важная информация выделена жирным шрифтом.
- В канал теперь публикуется также гос. номер (чтобы можно было использовать поиск).

### 1.3.3

- Ошибка в шаблоне - упоминание ГУВД Мингорисполкома.

### 1.3.2

- В альбомах, посылаемых в канал, подпись устанавливается только на первое фото. В таком случае она отображается под альбомом.

### 1.3.1

- Исправлена ошибка, из-за которой бот застревал на отправке фото.

### 1.3.0

- Теперь бот пересылает фотографии, адрес нарушения и время в канал для всеобщей потехи.
- Обновлен /help.

### 1.2.0

- Добавлена возможность отправлять обращения о нарушениях по всей республике. Обращение идет в областное УВД (должны сами пересылать по районам по идее).

### 1.1.6

- В сообщение бота, что обращение успешно отправлено, добавлено предупреждение, что на mail.ru копии письма не доходят.

### 1.1.5

- Дополнен хелп про недоход писем на ящики на mail.ru.
- Дополнен хелп списком изменений.

### 1.1.4

- Прикрепленные в письме фото дополнительно встраиваются в тело письма. Некоторые почтовые ящики ГАИ не умеют прикрепленные файлы.

### 1.1.3

- Исправлен баг, когда добавлялись не все фото при добавлении их группой.

### 1.1.2

- Мелкие доработки под капотом

### 1.1.1

- Обновлен раздел /help

### 1.1.0

- Добавлена возможность отправлять запросы в ГАИ на беларуском языке.
- Исправлена редкая ошибка непоявления подтверждения отправки обращения.

### 1.0.0 Бот запущен в промышленную эксплуатацию

- исправление опечаток в шаблоне письма
- доработка логгирования

### 0.2.0

- Кнопка для переввода данных о нарушении
- Реплики бота стали более официальными

### 0.1.1

- Поправил ошибку неправильного подбора текущего времени.

### 0.1.0 Вторая тестовая версия

- Поправил и изменил много где тексты.
- Добавил команду для фидбэка.
- Сделал кнопки под сообщениями и насыпал их побольше.
- Добавил политику конфиденциальности, почитать можно по команде /help.
- Добавил возможность задавать адрес отправкой локации.
- Сделал номер телефона необязательным.

### 0.0.0 Первая тестовая версия
