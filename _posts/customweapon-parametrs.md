# CustomWeapon шейдер

## Шейдер для скинов из CS:GO, используется на моделях оружия и ножах

Параметры шейдера:  

**"$PREVIEW"**  
 >  Без него игра будет вылетать, всегда ставить значение на 1

**"$grungetexture"** и **"$weartexture"**  
> Текстуры износа, везде одинаковые и имеют такие стандартные значения: 
 - **"$grungetexture"** - "models\weapons\customization\shared\gun_grunge"
 - **"$weartexture"** - "models\weapons\customization\shared\paint_wear"


**"$surfacetexture"**  
 > Нормаль(**!!НЕ КАРТА НОРМАЛЕЙ ИЛИ БАМП!!**) в пространстве объекта и альфа канал Cavity.
 
Берётся из models\weapons\customization\{*weapon*}\{*weapon*}_surface, где {weapon} - название basetexture модели 


**"$maskstexture"**  
 > Маски для правильного маппинга паттернов и блеска на скинах:
 - R: анодированный,
 - G: camo2,
 - B: camo3,
 - A: черный будет закрашиватся,белый оставит исходную базовую текстуру.
 
Берётся из "models\weapons\customization{weapon}{weapon}_masks", где {weapon} - название basetexture модели    

**"$aotexture"**  
 > Ambient Occlusion. 
 
Берётся из "models\weapons\customization{weapon}{weapon}_ao", где {weapon} - название basetexture модели

**"$postexture"**  
 > Высокоточное положение в пространстве объекта, грубо говоря с помощью её движок понимает как расположить паттерн на модели.
Берётся из "models\weapons\customization{weapon}{weapon}_pos", где {weapon} - название basetexture модели
 
**"$exptexture"**  
 > Экспонента, где R: инвертированный roughness, G: metallic, B: не используется, обычно заливают чёрным цветом.
 
Берётся из "models\weapons\v_models{weapon}{weapon}_exponent", где {weapon} - название basetexture модели"


**"$WEARTEXTURETRANSFORM"** и **"$GRUNGETEXTURETRANSFORM"**   
> Трасформация текстур отвечающих за износ, по стандарту имеет такие значения: 
"scale 2.1 2.1 translate 0 0 rotate 0"


**"$basetexture"**  
 > Базовая текстура модели

**"$phongboost"**  
 > Усиление Фонга, если более понятным языком, то усиливает блеск.  
 
Для скинов значение брать из csgo\scripts\items\items_game.txt с помощью "ID" скина, которое можно найти на [сайте]( https://csgostash.com/)

**"$phongalbedoboost"**  
 > Усиление Альбедо Фонга.
 
Значение брать из оригинального vmt оружия


**"$phongfresnelranges"**  
 > Диапазоны Френеля Фонга.
 
Значение брать из оригинального vmt оружия


**"$basemapalphaphongmask"**  
 > Использует альфа-канал "$basetexture" как маску Фонга.

Для скинов ставить значние на **1**


**"$envmap"**  
 > 3D текстура окружения, используется для симуляции отражений на модели.
Всегда ставить значение "env_cubemap"


**"$envmapfresnel"**  
 > Добавляет эффект Френеля (наблюдение, согласно которому степень отражения, которую вы видите на поверхности, зависит от угла обзора).
 
Всегда ставить значение на 1


**"$envmaptint"**  
> Управляет интенсивностью каналов красного, зеленого и синего цвета отражения.
Можно использовать любое положительное число. По умолчанию это "[1 1 1]"означает 100% интенсивность.(спасибо https://developer.valvesoftware.com/wiki/$envmap)

Значение брать из оригинального vmt оружия


"**$phongalbedotint"**  
 > Окрашивает отражение фонга в цвет $basetexture. Величина оттенка определяется зеленым каналом $exptexture.
 
**Без $exptexture работать не будет**
Всегда ставить значение на 1


**"$phongdisablehalflambert"**
> Отключает принудительное полу-ламбертовское затенение для материалов Фонга.
Он разработан, чтобы задняя часть объекта не потеряла свою форму и не выглядела слишком плоской.

Всегда ставить значение на 1

**"$PREVIEWPHONGALBEDOTINT"**  
>  Значение брать из оригинального vmt оружия


**"$PREVIEWENVMAP"** 
>  Ставить значние на 1, если в оригинальном vmt используется $envmap

**"$WEARPROGRESS**" 
> Степень износа от 0 до 1, где 0 - износа нету, а 1 - максимальный износ(нет?)

**"$PREVIEWWEAPONOBJSCALE"** 
> Специфический масштабный коэффициент оружия для паттернов, применяемых через проекции объектного пространства(чот сложно)

Стандартное значние для скинов 1.0485


**"$PREVIEWWEAPONUVSCALE"** 
> Специфический масштабный коэффициент оружия для паттернов, применяемых через UV


**"$paintname"** 
> Название скина из csgo\scripts\items\items_game.txt, бесполезный(пока?) параметр в CSSO


**"$previewphongalbedoboost"** 
> Усиление Альбедо Фонга для скина.

Для скинов значение брать из csgo\scripts\items\items_game.txt с помощью "ID" скина, которое можно найти на [сайте]( https://csgostash.com/) (а нахуя два одинаковых значения?)


**"$painttexture"** 
>  Текстура скина или паттерн из КСГОшного pak01.dir в папке /materials/models/weapons/customization/paints/

Оригинальное название текстуры есть в csgo\scripts\items\items_game.txt, искать по "ID" скина , которое можно найти на [сайте]( https://csgostash.com/)


**"$paintstyle"** 
> Способ наложения паттерна или скина на модель.

Имеет значения: 
 + 1 = SOLID COLORS
 + 2 = HYDROGRAPHIC
 + 3 = SPRAYPAINTED
 + 4 = ANODIZED SOLID COLORS
 + 5 = ANODIZED PATTERNED
 + 6 = ANODIZED AIRBRUSHED
 + 7 = CUSTOM TEXTURE APPLIQUE
 + 8 = PATINA/ANTIQUED
 + 9 = GUNSMITH

Способ наложения есть в csgo\scripts\items\items_game.txt, искать по "ID" скина , которое можно найти на [сайте]( https://csgostash.com/)
⠀

**"$camocolor0"** 
> Цвет кастомизации 0 ( заменяет красный канал $painttexture ) 

**"$camocolor1"** 
> Цвет кастомизации 1 ( заменяет зелёный канал $painttexture )   

**"$camocolor2"** 
> Цвет кастомизации 2 ( заменяет синий канал $painttexture )

**"$camocolor3"** 
> Цвет кастомизации 3 ( заменяет альфа канал $painttexture )

 - В зависимости от $paintstyle цвета будут по разному накладыватся или воовсе будут игнорироватся
 - Это RGB параметр, по-этому он запиcывается в квадратных скобках []
Например ```"$camocolor0" "[13 53 43]"```

Значение брать из csgo\scripts\items\items_game.txt с помощью "ID" скина, которое можно найти на [сайте]( https://csgostash.com/)


**"$PATTERNTEXTURETRANSFORM"** 
> Трасформация текстуры скина.

Стандартное значение ```"center 1 1 scale 1.6 1.6 rotate 0 translate 0 0"``` , кроме scale, который находится вcsgo\scripts\items\items_game.txt с помощью "ID" скина, которое можно найти на [сайте]( https://csgostash.com/)


**"$PHONGEXPONENT"** 
> Фонг Экспонент для скина.

Значение брать из csgo\scripts\items\items_game.txt с помощью "ID" скина, которое можно найти на [сайте]( https://csgostash.com/)


**"$PHONGINTENSITY"** 
 > Интенсивность Фонга для скина.
 
 Значение брать из csgo\scripts\items\items_game.txt с помощью "ID" скина, которое можно найти на [сайте]( https://csgostash.com/). Если его там нету, то убрать параметр


**"$PREVIEWIGNOREWEAPONSCALE"** 
> 1 = игнорировать "$PREVIEWWEAPONOBJSCALE"
> 0 = применять  **"$PREVIEWWEAPONOBJSCALE"** ?(надо проверить)


## [Примеры шейдеров](https://github.com/hampta/csso-wiki/blob/master/assets/sample_vmt/ak47_olied.vmt)
