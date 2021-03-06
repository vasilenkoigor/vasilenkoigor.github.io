---
layout: post
title: Не является ли TDD двойной работой и почему мы должны задуматься над тем, чтобы начать использовать TDD в своих проектах?
excerpt: "Перевод статьи из выпуска Podlodka Podcast #23"
categories: [tdd, testing]
comments: true
---

Данный пост является вольным переводом заметки на Medium [Isn’t TDD twice the work? Why should you care?](https://codeburst.io/isnt-tdd-test-driven-development-twice-the-work-why-should-you-care-4ddcabeb3df9), которая обсуждалась в 23-м выпуске [Podlodka Podcast](https://itunes.apple.com/us/podcast/podlodka-podcast/id1209828744?mt=2)

### Не является ли TDD двойной работой?

Автор отвечает на этот вопрос - “Нет”, с чем я тоже согласен.

Он ссылается на то, что при разработке без TDD - нужно время только разработку новой фичи. А с TDD нам нужно будет время заложить на тесты и разработку новой фичи. 
Но что здесь учли - так это время, необходимое для QA и фикс багов, если что-то пошло не так.

Так же, автор упоминает о замечательном [research Microsoft и IBM в попытке сравнить разработку с TDD и без](https://github.com/tpn/pdfs/blob/master/Realizing%20Quality%20Improvement%20Through%20Test%20Driven%20Development%20-%20Results%20and%20Experiences%20of%20Four%20Industrial%20Teams%20(nagappan_tdd).pdf). Результаты исследований показали, что плотность дефектов перед выпуском четырех продуктов снизилась от 40% до 90% по сравнению с аналогичными проектами, которые не использовали практику TDD. И субъективно, команды почувствовали примерно 15-35% прироста времени к разработке продукта используя TDD. 

### Почему мы должны подумать о том, чтобы начать разрабатывать по TDD?

#### TDD помогает предотвратить баги

И это не самоцель TDD, а всего лишь side-effect.
Во первых, с TDD мы имеем большое покрытие нашей кодовой базы тестами и поэтому баги вряд ли останутся незамеченными. 
Во вторых, с TDD разработчики способны поймать потенциальные баги до сборки/релиза
И в третьих, так как тесты всегда ментейнятся, то это дает гарантию качества.

#### Самодокументированный код (отличная документация)

Так как по TDD мы пишем используя паттерн “Test First”, то само собой разумеется, что тесты всегда актуальны и могут служить собой как отличная документация текущей кодовой базы.

#### С TDD вы можете предвидеть проблемы

Преимущество хорошего покрытия кода тестами сразу даст нам сразу узнать о том, что например наш кассовый флоу в проекте перестал списывать средства с банковских карт пользователей, так как данные тесты упали. Это так же могло бы значить, что кто-то допустил ошибку. Опять же, мы заметим данный баг до релиза, что значительно может сохранить нам нервы, а то и деньги.

#### TDD экономит наши деньги компании

Когда проект растет и код усложняется, то сложнее становится делать новые фичи из-за того, что одно изменение в кодовой базе может повлечь за собой баг в другом месте проекта. Но когда мы следуем TDD, мы можем быть уверенными в изменениях кодовой базы (только главное не полагаться на это на 100%, доверяй, но проверяй), а значит и QA словит меньше багов и мы сэкономим на это время и соответсвенно деньги компании.

#### Сэкономленное время можно потратить на рисерч и инновации

Из предыдущего пункта - если мы сэкономили время и деньги, то мы можем потратить все это на рисерч или на новые инновационные идеи

#### Растущий scope задач

Самым большим кошмаром менеджеров - является растущий scope задач. И этот рост может быть по разным причинам: плохо описанные задачи, неправильные требования в ТЗ, отсутствие документации и тд. Во всем этом нам так же сможет помочь TDD.

### Несколько советов из исследования Microsoft

* Интегрируйте разработку по TDD в начале нового проекта. Не останавливайтесь посередине и не утверждайте, что это все не работает. Не начинайте разработку по TDD в конце разработки проекта, когда уже дизайн проекта устоялся и большая часть кода была уже написана.
* Убедите своих разработчиков писать тесты на те баги сразу, как только они были найдены, независимо от времени
* Расскажите своему QA о том, что вы разрабатываете по TDD и чтобы они не принимали новую сборку, если упал хотя бы один тест
* Настройте CI и прогоняйте тесты в каждой сборке (тесты - как сердце всей системы)
* Считайте количество тестов, покрытие кода, найденное и пофикшенное кол-во багов, чтобы понимать то, как вам помогает TDD
