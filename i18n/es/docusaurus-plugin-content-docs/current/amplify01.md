---
id: amplify-01
title: Serverless
sidebar_label: Serverless
---

# Serverless

Создание бэкенда на [AWS Amplify](https://aws.amazon.com/ru/amplify/) — это работа с бессерверной (англ. serverless) технологией, поэтому перед тем, как продолжить, мы с вами разберемся с тем, что такое бессерверные вычисления и в чем их преимущества над серверными.

Прогноз ученых мужей из университета Berkeley о том как будут развиваться бэкенд технологии:

> Предоставляя упрощенную среду программирования, бессерверные вычисления значительно упрощают использование облака, тем самым привлекая больше людей, которые могут и будут его использовать. Бессерверные вычисления включают в себя предложения FaaS и BaaS и знаменуют собой важный этап развития облачного программирования. Это избавляет от необходимости ручного управления ресурсами и их оптимизации, которые сегодняшние серверные вычисления навязывают разработчикам приложений, что походит на переход от языка ассемблера к языкам высокого уровня более четырех десятилетий назад.

> Мы прогнозируем, что использование без серверов будет стремительно расти. Мы также прогнозируем, что локальные гибридные облачные приложения со временем будут сокращаться, хотя некоторые развертывания могут сохраняться из-за нормативных ограничений и правил управления данными.

> Бессерверные вычисления станут стандартной вычислительной парадигмой в эпоху облаков, в значительной степени, заменив серверные вычисления и тем самым закрыв эру клиент-сервер.

[Cloud Programming Simplified: A Berkeley View on Serverless Computing](https://www2.eecs.berkeley.edu/Pubs/TechRpts/2019/EECS-2019-3.pdf)

## Бессерверные вычисления

Естественная для облака архитектура, которая позволяет передать большую часть операционной ответственности AWS и тем самым получить больше гибкости и инновационных возможностей. Бессерверные вычисления позволяют создавать и запускать приложения и сервисы, не беспокоясь о серверах. Они устраняют необходимость заниматься вопросами управления инфраструктурой — такими, например, как выделение серверов или кластеров, необходимых ресурсов, а также установка исправлений и обслуживание операционной системы. Их можно использовать практически для любого типа приложений или сервисов серверной части, при этом всё, что требуется для запуска и масштабирования приложения с высокой доступностью, выполняется без вмешательства клиента.

> В нашем определении, чтобы услуга считалась беcсерверной, она должна автоматически масштабироваться без необходимости явной инициализации и оплачиваться в зависимости от использования.

[Cloud Programming Simplified: A Berkeley View on Serverless Computing](https://www2.eecs.berkeley.edu/Pubs/TechRpts/2019/EECS-2019-3.pdf)

Если очень по простому, то бессерверные (Serverless) означает не физическое отсутствие серверов, а отсутствие головной боли по управлению инфраструктурой, ее обслуживания и создания.

# Преимущества бессерверной архитектуры:

В наше время существует множество способов создания приложения. Решения, которые принимаются на раннем этапе, могут и будут влиять не только на жизненный цикл приложения, но и на команды разработчиков и, в конечном счете, на компанию или организацию. В этой статье я выступаю за и излагаю способы создания ваших приложений с использованием бессерверных технологий по методологии "Модельная разработка". Каковы преимущества создания приложения таким образом, и почему бессерверность становится настолько популярной?

## Один язык программирования

С помощью современных инструментов и методологий, таких как [AWS Amplify](https://aws.amazon.com/ru/amplify/), один разработчик может использовать свой существующий набор навыков и знания единой платформы и экосистемы (например, [TypeScript](https://www.typescriptlang.org)) для создания масштабируемых приложений, в комплекте со всеми функциями, которые в прошлом потребовались бы команды высококвалифицированных бэкэнд программистов и инженеров DevOps для сборки и обслуживания.

## Меньше кода

Единственное, что имеет ценность — это функция, которую предоставляет код, а не сам код. Когда вы находите способы предоставления этих функций, одновременно ограничивая объем поддерживаемого кода и даже полностью отказываясь от кода, вы снижаете общую сложность своего приложения.
Чем меньше сложностей, тем меньше ошибок, проще для новых инженеров и в целом меньше когнитивная нагрузка для тех, кто поддерживает и добавляет новые функции.
Разработчик может подключиться к этим сервисам и реализовать функции, не зная о фактической внутренней реализации, и практически не имея внутреннего кода.

## Отсутствие необходимости управлять серверами

Не нужно выделять сервера или обслуживать их. Не требуется установка, обслуживание или администрирование программного обеспечения или среды выполнения.

## Масштабируемость

Одним из основных преимуществ отсутствия сервера является масштабируемость из коробки. При создании приложения вам не нужно беспокоиться о том, что произойдет, если ваше приложение станет чрезвычайно популярным, и вы подключите большее количество новых пользователей, и облачный провайдер справится с этим за вас.
Облачный провайдер автоматически масштабирует ваше приложение, выполняя код в ответ на каждое взаимодействие. В бессерверной функции ваш код выполняется параллельно и индивидуально обрабатывает каждый триггер (в свою очередь масштабируется с учетом размера рабочей нагрузки).
Нет необходимости беспокоиться о масштабировании ваших серверов и баз данных.

## Скорость разработки

При меньшем количестве функций скорость разработки увеличивается. Возможность быстрого развертывания типов функций, которые типичны для большинства приложений (базы данных, аутентификация, хранилище, API-интерфейсы), и при гораздо меньших предварительных затратах времени позволяет быстрее приступить к написанию основных функций и бизнес-логики для функции, которые вы хотите доставить конечному клиенту.

## Эксперименты

Если вы не тратите много времени на создание повторяющихся функций, вы можете экспериментировать легче и с меньшим риском.
При отправке новой функции вы часто оцениваете риск (время и деньги, связанные с созданием этой функции) с возможным возвратом инвестиций (ROI). Поскольку риск, связанный с испытанием новых вещей, снижается, вы можете испытать идеи, которые в прошлом, возможно, не видели свет.
Мы также можем гораздо проще протестировать различные идеи.

## Безопасность и стабильность

Поскольку услуги, на которые вы подписываетесь, являются основной компетенцией поставщика услуг, вы получаете что-то гораздо более отточенное и обычно более безопасное, чем вы могли бы создать сами.
Представьте себе компанию, основная бизнес-модель которой сосредоточена на предоставлении первичной услуги аутентификации и которая уже много лет использует ее, решая и устраняя проблемы для тысяч компаний и клиентов.
Теперь представьте, что вы пытаетесь воспроизвести такой сервис в своей собственной команде или организации. Хотя это вполне возможно и осуществимо, есть вероятность, что выбор службы, созданной и поддерживаемой людьми, единственная задача которых состоит в том, чтобы создать и поддерживать эту точную вещь, является более безопасной и надежной ставкой.
Другой основной задачей этих поставщиков услуг является просто минимальное время простоя. Это означает, что они берут на себя бремя не только создания, развертывания и обслуживания этих сервисов, но и делают все возможное, чтобы обеспечить их стабильность и устойчивость.

## Автоматический контроль доступности

Бессерверные вычисления обеспечивают встроенную высокую доступность и отказоустойчивость. Эти возможности не требуется специально проектировать, поскольку сервисы, запускающие приложение, предоставляют их по умолчанию.

## Стоимость

При традиционном подходе вы часто платите за вычислительные ресурсы независимо от того, используются они или нет. Это означает, что если вы хотите убедиться в том, что ваше приложение будет масштабироваться, вам необходимо подготовиться к самой большой рабочей нагрузке, которую вы могли бы увидеть, независимо от того, достигла ли она этого уровня. В конце концов, этот традиционный подход означал, что вы платите за неиспользованные ресурсы большую часть срока службы вашего приложения.
С бессерверными технологиями вы платите только за то, что используете. С FaaS (Function-as-a-Service) вам выставляется счет на основании количества запросов на ваши функции и времени, которое требуется для выполнения кода вашей функции. С такими управляемыми сервисами, как Amazon Rekognition, вы платите только за обработанные изображения, минуты обработки видео и т. д., Опять же, платя только за то, что вы используете.
Счет от вашего облачного провайдера — это только часть общей стоимости вашей облачной инфраструктуры, а также заработная плата. Эта стоимость уменьшается, если у вас меньше оперативных ресурсов.
Есть также затраты на разработку. Создание приложений таким способом ускоряет вывод на рынок, сокращая общее время разработки и, следовательно, стоимость разработки.
В общем вы платите за стабильную пропускную способность или время исполнения, а не за количество используемых серверов.

Подробнее о ценах [здесь](https://aws.amazon.com/ru/appsync/pricing/)

## Вывод
Сама по себе модель разделения на фронтенд и бэкенд осталось в прошлом вместе с разработчиками по фичам в эпоху serverless технологий, где фуллстэк разработчики реализуют модельную сборку приложений в разы быстрей, чем разработчики по фичам. 


<!-- ## Снипет трека на тему "Модельная разработка" 
Прослушать [здесь](https://www.dropbox.com/s/zt51wbt51s1za83/Model%20development.wav?dl=0)

Текст трека - "Модельная разработка": 

Я из классов и функций

предпочитаю функции

TC 39 

моя библия 

Реактнативный 

моя фамилия

Шести этажные рифмы

Сшибаю с ноги я

GraphQL 

мой первый класс

Подписки 

И реалтайм 

из коробки

Я новая школа

Зови OG Buda

Ru drill основал

а это фактам

Хотите слоумо?

За ваш счет легко

Right MVP solution

для ваших приложений 

Зачем писать код,

Если готовы функции?

Вызови их в коде

Кодогенерация

Атомы, 

молекулы,

темплейты, 

организмы.

Логика клиента

Отдельно от скринов

Atomic Design и вестку

В Storybook

Отдельно от 

UI Components

Изолируй бук

Я Гоша Рубчинский

На лукбуках модель

Вспомнил, кто такой

Брендан Эйх

JavaScript в кэмпе

Модельная разработка

Brad Frost сказал

Изолируй UI

Масштабируй 
бук
На других 
своих проектах
В Storybook 
меняй
Воплощая Ui

Скрины и навигация
Готов твой MVP
Когда 
Rest API
пробирается 
Я говорю 
Беги!

Модельная разработка
Стреляет мой глок
Модельная разработка
На спуске курок

2021 
Димка Реактнативный ака Server Serverlesskiy -->

## References:

[Стадии рождения новой функциональности в программном продукте](https://habr.com/ru/company/acronis/blog/250145/)

[Cоздание дизайн-систем с помощью Atomic Design](https://telegraf.design/cozdanie-dizajn-sistem-s-pomoshhyu-atomic-design/)

[Атомарный дизайн (Atomic design)](https://simpleone.ru/glossary/atomarnyj-dizajn-atomic-design/)

[GraphQL: Core Features, Architecture, Pros and Cons](https://www.altexsoft.com/blog/engineering/graphql-core-features-architecture-pros-and-cons/)

[GraphQL: A data query language](https://engineering.fb.com/core-data/graphql-a-data-query-language/)

[GraphQL](https://graphql.org/learn)


<!-- [![EnglishMoji!](/img/logo/englishmoji.png)](https://link-to.app/xvh7Ush9kl) -->
