# hackerspace
Ова репо го содржи статичниот сајт на хаклабот КИКА којшто е напишан со помош на [Jekyll](https://jekyllrb.com/) и [Liquid](https://shopify.github.io/liquid/).

Вебсајтот содржи мал систем за настани (следен настан, минати настани), блог и информации.

![img](https://i.imgur.com/5cBIZjp.png)


## Зошто статичен сајт и зошто не WordPress?

GitHub нуди бесплатно хостирање на статични сајтови коишто се пишувани во Jekyll. Исто,
статичните сајтови не користат backing services (на пример: датабази, мејл), при што на некој начин
се безбедни од напади од видот на SQL injection и слично.

Сајтот сервира претходно генериран HTML према клиентот и тука завршува приказната.

## Како функционира додавање настан или блог пост?

Настаните и блог-постовите се обични [Markdown](https://en.wikipedia.org/wiki/Markdown) фајлови коишто се чуваат во папките `_events` и `_posts`, соодветно.

Секој фајл во папките `_events` и `_posts` треба да ги содржи следниве два дела:
1. Детали за настанот или блог-постот од видот на: наслов, автор, датум...
2. Содржина

### Детали за настанот или блог-постот

#### За настани:

```
---
title: "Учиме да лемиме!"
author: "Некојси"
layout: "event_post"
start_date: "2019-02-01T14:00:00Z"
end_date: "2019-02-01T15:00:00Z"
---
```

#### За блог-постови:

```
---
title: "Како поминавме на НСНД19"
author: "Некојси"
layout: "blog_post"
date: "2019-01-26T14:31:01Z"
tags: "nsnd moravice"
category: "other"
---
```

### Детали + содржина
```
---
title: "Учиме да лемиме!"
author: "Некојси"
layout: "event_post"
start_date: "2019-02-01T14:00:00Z"
end_date: "2019-02-01T15:00:00Z"
---

Во петок ќе учиме да лемиме во #хаклаб! Секој што
сака да научи е добредојден. :)
```

Делот со детали може да се пишува мануелно, но е мачно, за таа цел постои [алатката](https://skopjehacklab.github.io/alatkata) којашто ќе го убрза целиот процес на креирање настан или блог-пост.

Сега кога ги имаш двата дела напишани во фајлот, следно е да му дадеш име. Името на фајлот треба да биде во следниов редослед: 

> YYYY-MM-DD-some-short-title.md

Каде што:
- YYYY - година
- MM - месец
- DD - ден

Значи:

#### Додавање на настан / блог-пост
- Креирај сметка на github
- Побарај пристап до skopjehacklab заедничкото репо
- Влези во `_events` или `_posts` папката на ова репо
- Кликни на `Create new file`
- Посети ја [алатката](https://skopjehacklab.github.io/alatkata) и копирај ги деталите
- Залепи ги деталите во фајлот и под нив напиши содржина
- Дај му име на фајлот според горенаведеното
- Напиши commit порака и commit-ни го фајлот

## Како да се снајдам наоколу?

- `_layouts` - секој настан или блог-пост има свој `layout` или распоред по кој што ќе се генерира HTML-от.
- `_includes` - овде стојат фајловите во видот на `header.html` и `footer.html` коишто ги содржи секоја страница на вебсајтот.
- `assets` - CSS, JS, слики, икони и слично.
- `blog` - изгледот на блогот и страницата која ги сортира блог постовите по лепенки и категории.
- `index.html` - главната страница
- `donations.html` - страницата за донации
- `events.html` - страницата за настани
- `faq.html` - страницата за ЧПП.
- `members.html` - страницата со информации за местото и чланарината

#### Битно

- `_posts` - овде стојат блог постовите
- `_events` - овде стојат настаните
- `_config.yml` - овде стои конфигурацијата на целиот вебсајт, мени за навигација, ЧПП, линкови, плагини и слично.

Додавање на ЧПП или нов линк во менито за навигација се врши во фајлот `_config.yml`.

## Како да пријавам баг или да додам нешто на сајтот?

Багови и грешки во вебсајтот се пријавуваат во `Issues` на ова репо. За да поправиш грешка или додадеш нешто на сајтот (ова НЕ вклучува настан и блог-пост) отвори нов Pull Request и побарај некој да го провери.
