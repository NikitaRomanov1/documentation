---
sidebar_position: 20
---

# FAQ

:::info

Свой вопрос можно задать в [telegram-чате](https://t.me/feature_sliced) / [github-issues](https://github.com/feature-sliced/documentation/issues) / [github-discussions](https://github.com/feature-sliced/documentation/discussions)

:::

### Структура = Архитектура?

Архитектура - про абстракции и выстраивание связей между ними (shared/features/pages/...)

*Но без надлежащей структуры - хорошей архитектуры не сделать*

### Нужна ли мне методология только для "понимания и ясности" что происходит в проекте?

Скорее да, чем нет

*Иначе приходится читать огромные директории `components/`...*

### Нужна ли архитектура/методология начинающему разработчику?

Скорее да, чем нет

*Обычно, когда проектируешь разрабатываешь проект в одно лицо - все идет гладко. Но если появляются паузы в разработке, добавляются новые разработчики в команду - тогда-то и наступают проблемы*

### Зачем нужна еще одна методология, когда все строится на принципах?

Ответили [здесь](/docs/get-started/motivation)

### Где найти примеры применения методологии?

В открытом доступе пока есть только такие, не все до конца адаптированы до последней версии

*В ближайшее время список будет пополняться и будет вынесен в отдельный раздел*

- [Internal Examples](https://github.com/feature-sliced/examples)
- [External Examples](/examples)

*Также можно ознакомиться с [гайдами](/docs/guides/migration-from-v1) и [туториалами](/docs/get-started/tutorial/quick-start)*

### Есть ли какие-нибудь полезные ресурсы/статьи/и т.д. по FeatureSliced и связанным вещам?

<https://github.com/feature-sliced/awesome>

### Проект написан на feature-slices v1, как обновиться и стоит ли?

Ответили [здесь](/docs/guides/migration-from-v1)

### Могу ли я вкладывать страницы/фичи/сущности друг в друга?

Ответили [здесь](/docs/concepts/app-splitting#group-slices)

### Как мне работать с контекстом авторизации?

Ответили [здесь](/docs/guides/examples/viewer)

### А что с Atomic Design?

Текущая версия методологии не обязывает, но и не запрещает использовать Atomic Design вместе с feature-sliced

При этом Atomic Design [хорошо применяется](https://t.me/feature_sliced/1653) для `ui` сегмента модулей

### В чем отличие feature и entity?

- `Entity` - бизнесовая **сущность**
  - blog-post / user / order / product / ...
- `Feature` - бизнесовая фича, **действие над сущностью**
  - create-blog-post / login-by-oauth / edit-account / publish-video / ...

См. также [справочную информацию по сравнению](/docs/reference/layers/overview), [реализация viewer логики по слоям](/docs/guides/examples/viewer)

### Где хранить layout/template страниц?

Общие шаблоны для разметки лучше хранить в `shared/ui`, но бывают [разные случаи](https://github.com/feature-sliced/documentation/discussions/129)

### А будет тулкит / линтеры?

Будет, на данный момент - в разработке =)

> Пока что, для сортировки / запрета импортов можно воспользоваться
>
> - `eslint-plugin-import`
> - `eslint-plugin-simple-import-sort`
> - `eslint-plugin-boundaries`
> - `dependency-cruiser`
>
> См. [базовый пример конфига](https://gist.github.com/azinit/4cb940a1d4a3e05ef47e15aa18a9ecc5)

### Могу ли я хранить фичи используемые на одной странице прямо в директории страницы?

Методология крайне не рекомендует так делать, поскольку [каждому модулю есть соответствующее место в структуре](/docs/concepts/app-splitting)

Иначе - есть риск усложнения кодовой базы проекта

> *"Сегодня фича может использоваться только на одной странице. На следующей неделе - на трех. А через месяц - ее может не быть совсем. Мы не можем предсказывать будущее, и нужно каждый раз воздерживаться от преждевременных оптимизаций"*

*См. также пример из [quick-start](/docs/get-started/tutorial/quick-start#обычный-подход)*
