# Design System: Product Design Club — лендінг

> **Статус:** in-progress — токени у Figma перебудовані
> **Оновлено:** 2026-11-07
> **Figma:** [pdc → Page 2](https://www.figma.com/design/PgkeyclOnernDuZo357KaF/pdc?node-id=1087-442) (повний сайт), сторінка Components. Підсторінка менторів: [1025:1903](https://www.figma.com/design/PgkeyclOnernDuZo357KaF/pdc?node-id=1025-1903).

Source of truth для токенів. Збудовано за аудитом усіх сторінок (Page 2, 3050 шарів) і привʼязано до шарів сторінок Page 2 і Components.

## Правило

**Токен є, тільки якщо значення повторюється 3+ разів у UI.** Кольори ілюстрацій, фото, лого партнерів і мок-елементів (чат Telegram, відеодзвінок, маркі) в систему не входять. Близькі значення зведені до одного (напр. `#0A0A0A`, `#181818`, `#201D1D` → `text/primary`). Тільки цілі значення, шрифт UI — **Inter Tight**.

## Змінні у Figma

Чотири колекції, без дублів: `Primitives` (17) → `Semantic` (25, аліаси) · `Spacing` (12) · `Radius` (8). Шари привʼязані тільки до Semantic, Spacing, Radius. Primitives напряму не використовуємо.

### Primitives

| Токен | Значення |
|---|---|
| `black` / `white` | `#000000` / `#FFFFFF` |
| `ink` | `#141516` (темні кнопки) |
| `charcoal` | `#272727` (темні картки, рамки) |
| `grey/900` · `500` · `400` | `#363636` · `#6E6E6E` · `#A4A3A6` |
| `grey/300` · `200` · `100` | `#D9D9D9` · `#E0E0E0` · `#F2F6F6` |
| `lilac/50` · `lilac/900` | `#F9F5FE` · `#312740` |
| `plum/950` · `plum/700` | `#140018` (футер, темна секція) · `#32233A` |
| `ice/100` | `#DBE8FB` (текст на темному) |
| `lime/400` · `lime/100` | `#E0FF63` (зелені кнопки) · `#E0FFC7` (обведення) |

### Semantic

| Група | Токени |
|---|---|
| `text/` | `primary` (black) · `secondary` (grey/900) · `muted` (grey/500) · `disabled` (grey/400) · `inverse` (white) · `inverse-muted` (ice/100) · `accent` (lilac/900) |
| `bg/` | `page` (white) · `section` (grey/100) · `lilac` (lilac/50) · `dark` (plum/950) · `dark-raised` (charcoal) · `ink` · `black` · `highlight` (lime/400) · `disabled` (grey/300) · `hero` (lilac/100 `#EEF0F7`, фон hero підсторінок) |
| `border/` | `subtle` (grey/200) · `dark` (plum/700) · `highlight` (lime/100) · `ink` (charcoal) · `light` (white) · `inverse-soft` (ice/100) |

Прозорість (напр. білий @50%, ice @15%) лишається прозорістю шару, окремих токенів немає.

### Spacing

`space/4 · 8 · 10 · 12 · 14 · 16 · 20 · 24 · 32 · 48 · 64 · 128`. Імʼя = значення. `10` і `14` не з сітки 4, але їх ×150 і ×58 у макеті (кнопки й чіпи), тому токени. Контейнер 1184, поля 128, картки 4×281 з gap 20.

### Іконки

Колір: \`icon/primary\` (black) · \`icon/secondary\` (grey/900, дата й час) · \`icon/muted\` (mauve/400 \`#8B7E8C\`, соцмережі у футері) · \`icon/accent\` (lilac/900, Telegram) · \`icon/inverse\` (white). Розмір: \`icon-size/16 · 24 · 80\` (80 — плитка футера). Усі іконки живуть у наборі \`Icons\` у контейнері 24, колір кольорових гліфів привʼязаний до \`icon/*\`. Ширина й висота самих компонентів до змінної не привʼязані, бо тоді інстанси втрачають масштаб.

### Radius

`radius/4 · 8 · 12 · 16 · 24 · 32 · 40 · full`.

## Типографіка

Inter Tight. Heading — **Medium**, Display, Body і Caption — **Regular**. Девʼять стилів у трьох групах:

| Група | Стиль | Кегль / інтерліньяж |
|---|---|---|
| Display | `Display/L` | 56 / 100% |
| | `Display/M` | 40 / 100% (mobile 36) |
| | `Display/S` | 36 / 110% |
| Heading | `Heading/L` | 24 / 120% |
| | `Heading/M` | 20 / 120% |
| Body | `Body/L` | 18 / 130% |
| | `Body/M` | 16 / 140% |
| | `Body/S` | 14 / 140% |
| | `Caption` | 12 / 140% |

Кнопки теж на `Body/M` і `Body/S`, окремих `Label` стилів немає. Прибрані `Heading/H1` (72), `Heading/H2`, `Body/Bold`, `Label/Button`, `Label/Button S`. Шрифти ілюстрацій і мок-елементів (Montserrat, Inter, Haffer) в систему не входять.

## Border

Одна змінна `border-width/1` = 1px (×170+ у макеті), привʼязана до всіх чотирьох сторін обведення. Інші товщини (0.3, 1.5, 3.2) це масштабування ілюстрацій. Колір обведення береться з `border/*`.

## Ефекти

Стилі ефектів, колір привʼязаний до змінних `effect/*` (прозорість у самій змінній):

| Стиль | Значення | Змінна | Частота |
|---|---|---|---|
| `Ring/Dark` | 0 0 0 1.7 | `effect/ring-dark` (#252525 @40%) | ×26 |
| `Ring/Green` | 0 0 0 1.7 | `effect/ring-highlight` (#E0FF63 @40%) | ×22 |
| `Shadow/Edge Green` | 0 1.9 0 | `effect/edge-highlight` (#ADE04E) | ×13 |
| `Glass/Inner` | inner 0 0 8.8 | `effect/inner-glass` (#000 @12%) | ×7 |
| `Shadow/Card` | 0 4 16 | `effect/shadow` (#000 @35%) | ×5 |

Тінь під ілюстрацією, розмиття фону й layer blur ілюстрацій стилів не мають.

## Компоненти

Зараз у Figma **0 компонентів**. Нижче те, що реально є на сторінках (головна, ментори, поп-ап, соцпроєкти, події, база знань). Порядок створення: знизу вгору, кожен рівень збирається з попереднього. Усе прив'язується до токенів (колір, відступи, тексти), без сирих значень.

**Створено у Figma 2026-11-07** (сторінка `Components`), лише з реальних елементів макета: **Button** (28 варіантів: темна, зелена, біла, помаранчева; 4 стани; іконка опційна), **Chip** (9: зелений, фіолетовий Beta, чорний «Крок»; 3 стани), **Tag** (6: розмір L і S × Default / Hover / Active; це наявний компонент `Container` із Page 1, екземпляри не зламані). **Другий пакет (теж із реальних вузлів Page 2):** Header (рядок навігації), Nav Pill, Countdown Strip, Footer, Footer Social Tile (4 іконки × 2 стани), Icon Button (Close, Lilac × 3 стани), іконки Telegram, Close, Arrow Right. **Footer Social Tile переділано в один компонент:** 2 стани (Default, Hover) і властивість Icon (instance swap) на 4 іконки Icon/Social/Telegram, Instagram, YouTube, LinkedIn. **Бібліотека іконок:** усі іконки в контейнері 24×24, без фону, елементи масштабуються разом із контейнером. Група Icons (32: файл, папка, календар, годинник, плюс, іскра, код, плей, стрілки, шеврон, скріпка, відправити, мікрофон, камера, на весь екран, редакторські іконки, 4 соцмережі). Окремо: Stickers (hand-drawn, 10), Ornaments (3 сніжинки), Logos (8). **Єдиний стиль іконок:** Heroicons solid 24 (заливка, згладжені кути, MIT). Для 18 іконок поруч додано пару `… Solid`; телеграм, стрілки, квадратики, мікрофон лишаються власними. Футер-тайл використовує Icon/Social/* розміром 80 через instance swap. Чернетки першої спроби (Link, Avatar, Icon Button, іконки, білі чіпи) видалено. Додано: змінні `Radius`, `bg/disabled`, `text/disabled`, `lilac/50`, `lilac/900` (+ `bg/lilac`, `text/lilac`), ефекти `Shadow/Edge Green`, `Ring/Green`, `Ring/Dark`.

### 1. Атоми

| Компонент | Варіанти / стани | Де зустрічається |
|---|---|---|
| **Button** | Primary (синій), Secondary (темний `#141516`), Highlight (зелений, 3D-низ), Warm (помаранчевий); розмір S 44 / L 54; стани: default, hover, pressed, disabled; з іконкою або без | хедер, hero, картки платформи, поп-ап, CTA |
| **Icon Button** | круглий 48: close, соцмережі (Telegram, Instagram, YouTube, LinkedIn), стрілка | поп-ап, футер, каруселі |
| **Chip** | Beta (фіолетовий), «Дізнатись про ментора» (зелений 3D), напрям (темний), крок («Крок 1», чорний) | hero менторів, картка ментора, картки платформи, кроки |
| **Tag** | з іконкою Telegram: default, active; без іконки (категорія матеріалу) | фільтри менторів, база знань |
| **Link** | text link зі стрілкою, «Читати далі», акцентний синій | «Дізнатись більше», «Переглянути всі», відгуки |
| **Avatar** | розміри 24 / 32 / 46 / 92; Avatar Group з перекриттям `-12` | hero, картки, чат, відгуки |
| **Badge** | лічильник (12), мітка NEW | Telegram-картка, бенто |
| **Icon set** | 23 іконки, контейнер 24×24, без фону: Play, Telegram, Close, Arrow Right, Instagram, YouTube, LinkedIn, Cursor, Frame, Rectangle, Text, Pen, Code, Screen Share, Mic Off, Call End, Camera Off, Expand, Calendar, Clock, Pin (власна тонка, 12×20), Document (Heroicons document-text). Поруч окремий фрейм порівняння з Heroicons solid (пара є лише для Play і Close) | скрізь |
| **Divider / Level row** | рядок «рівень + число» | картка «Висока кваліфікація» |

### 2. Молекули

| Компонент | Складається з | Варіанти / стани | Де |
|---|---|---|---|
| **Nav Pill** | пункти навігації | default, hover, active | хедер |
| **Tabs** | Tab × 3 | active (чорний), inactive (лавандовий), hover | поп-ап, формати зустрічей |
| **Filter Row** | Tag × 9 | один активний | сторінка менторів |
| **Chat Bubble** | аватар + ім'я + текст | incoming, outgoing, з картинкою, typing | Telegram-картка, «Поради» |
| **Input (мок)** | поле «Повідомлення» | — | Telegram-картка (ілюстрація) |
| **FAQ Item** | питання + відповідь + іконка | closed, open | FAQ на головній і в соцпроєктах |
| **Section Heading** | заголовок + підзаголовок | по центру, зліва; з акцентним словом | усі секції |
| **Breadcrumbs** | Parent · Middle (за прапорцем) · Current + `Icon/Chevron Right` 16 | — | hero підсторінок (✅ створено) |
| **Footer Social Tile** | іконка в рамці | default, hover | футер |

### 3. Картки

| Компонент | Варіанти / стани | Де |
|---|---|---|
| **Mentor Card** | default, join («Стати ментором»); hover | сітка менторів |
| **Playing / Stamp Card** | 3 (Юрій, Ірина, Ніна), з нахилом і перспективою | hero менторів |
| **Feature Card** | dark (рівні), light (умови), black (напрями), cta | блок «Платформа» |
| **Step Card** | 1–4, з картинкою | «Як виглядає процес» |
| **Service Card** | назва + ціна + пункти + кнопка | поп-ап ментора |
| **Review Card** | прев'ю на 3 рядки + «Читати далі» | вкладка «Відгуки» |
| **Community Row** | pink, lavender, butter; hover (піднімається, показує сніжинку) | «Підійде для будь-якого рівня» |
| **Bento Card** | L, S; Фідбек, Поради, Ментори, Воркшопи, Матеріали; hover-анімація | «Фідбек, поради, ментори…» |
| **Material Card** | дата, час читання, тег, опис, кнопка | матеріали, база знань |
| **Event Card** | дата, назва, спікер, модератор | події |
| **Project Case Card** | картинка, назва, опис | соцпроєкти |
| **Org Type Row** | іконка + назва | соцпроєкти |

### 4. Секції (великі блоки)

| Компонент | З чого | Де |
|---|---|---|
| **Header** | логотип + Nav Pill + Button | всі сторінки |
| **Footer** | вордмарк, 4 Footer Social Tile, юридичний рядок | всі сторінки |
| **Countdown Strip** | текст «До наступної дизайн-кави» + таймер | головна, зверху |
| **Hero (головна)** | Section Heading, 2 Button, Avatar Group, Telegram-картка | головна |
| **Hero (підсторінка)** | Chip + заголовок + Button + Playing Card × 3 + ілюстрація | ментори |
| **Audience** | Section Heading + 3 колонки | «Для кого створений наш клуб» |
| **Bento Grid** | Bento Card × 5 | головна |
| **Meetings** | Tabs + опис + Feature Item × 3 | формати зустрічей |
| **Mentors Search** | Section Heading + Filter Row + Mentor Card × 8 | ментори |
| **Process** | Section Heading + Step Card × 4 | ментори |
| **Community** | Section Heading + Community Row × 3 + орнамент | ментори |
| **Materials** | Section Heading + Material Card × 3 | головна |
| **FAQ Section** | Section Heading + FAQ Item × 6 | головна, соцпроєкти |
| **CTA Block** | заголовок + цитата + Button | «Все головне в одній Telegram-групі» |
| **Support Marquee** | «Ми підтримуємо» + логотипи, що біжать | головна |
| **Bottom Sheet** | фото, ім'я, Tabs, контент вкладки, sticky Button | поп-ап ментора |
| **Empty State** | повідомлення + ілюстрація | «ОЙ! Щось сталось…» |

### 5. Шаблони сторінок

Home, Mentors, Social Projects, Events, Knowledge Base, Mentor Popup (оверлей). Усі на сітці 1440, поля 128, контейнер 1184.

### Порядок і межі

1. **Спершу атоми й Icon set.** Button, Chip, Tag, Link, Avatar: від них залежить усе інше.
2. **Далі молекули:** Tabs, FAQ Item, Section Heading, Chat Bubble.
3. **Картки** по частоті: Mentor Card, Step Card, Community Row, Feature Card, Service Card, Review Card.
4. **Секції** після карток: Header, Footer, Mentors Search, Process, Bottom Sheet.
5. **Не робимо компонентами:** ілюстрації, Telegram-мок, фото, логотипи партнерів, орнамент, сніжинки (це графіка, а не UI).
6. **Не більше 3–4 станів на компонент** (default, hover, pressed / active, disabled). Focus-ring не окремий стан, він береться з токена `border.focus` у коді. Матриця варіантів кожного компонента ≤ 30. **Button і Chip: два окремі компоненти.** Кожен має свої властивості (у Button: variant, size, state, icon; у Chip: variant, state), а не окремий компонент на кожен колір чи стан.

## На затвердження

1. Нейтральна шкала (10 кроків) і `green.600`. Додаткові `blue.200` / `blue.600` з минулої версії прибрав: вони не повторюються.
2. Вага H1/H2: Regular (так у макеті) чи Medium (так у Figma-стилях).
3. 4 пастельні плашки лишаємо? Мʼятну й кремову зводимо?
4. Нові стилі: `H2 S`, `H4`, `Body 3`, `Label/Button`, `Label/Button S`, `Body/Bold`.
5. Радіуси 40 → 32 і 22 / 23.6 → 24.
