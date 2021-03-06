Yandex MapKit-Android, repackaged for gradle and maven
===
 
This is a fork from the official (and unsupported for years) YandexMapKit-Android maps library, 
simply repackaged into the AAR/Maven form and uploaded to the maven repo. No other modifications was made.

[ ![Download](https://api.bintray.com/packages/livotovlabs/maven/YandexMapKit/images/download.svg) ](https://bintray.com/livotovlabs/maven/YandexMapKit/_latestVersion)


Android 6.0 Important Information
---
Current YandexMapKit will not work on android 6.0+ due to relocated symbols bug, see the original issue here: https://github.com/yandexmobile/yandexmapkit-android/issues/201

At the moment, you cannot do anything with this, use Google Maps or OSM instead, until the issue is either fixed by Yandex or YandexMapKit 2.0 released. However, if you'll find a solution to workaround this, please let me know too :)

Usage
---

Add compile statement to your gradle file repositories and dependencies sections:

```groovy
repositories {
    maven {
        ...
        url  "http://dl.bintray.com/livotovlabs/maven"
    }
}
```

```groovy
compile ('eu.livotov.labs.android:yandexmapkit-library:2.0.0@aar') {transitive=true}
```

Enjoy and hope that one day, maybe in 2020 or 2040, Yandex will finally release their new and modern map sdk for Android :)


Below goes the original README.md from Yandex.
---

Поддержка этой версии Yandex Map Kit прекращена. Он по-прежнему работает, но исправляться будут только критические ошибки. Мы разрабатываем новую версию.

В этом репозитории находится тестовое приложение, демонстрирующее возможности Yandex Map Kit.

Как начать
------------

1.  Клонируйте репозиторий примера
    git clone https://github.com/yandexmobile/yandexmapkit-android.git
2.  В папке yandexmapkit-library находятся библиотеки ресурсы и документация для Yandex Map Kit данный  проект является library project 
3.  В папке yandexmapkit-sample находится пример приложения который зависит от проекта yandexmapkit-library
4.  Данные проекты уже настроены для работы в среде Eclipse
 1.	Импортируйте данные проекты в среду Eclipse 
 2. Проверьте в настройках проекта yandexmapkit-library  в пункте Android  что установлена  "is Library"
 3. Проверьте в настройках проекта yandexmapkit-sample в пункте  Android что есть зависимость от проекта yandexmapkit-library
5.  Подставьте свой API ключ во все  layout где  используется объект MapView
6.  Всё готово к запуску тестового проекта


Миграция с первой версии
-------------------------

1. При создании OverlayItem необходимо в конструкторе вместо объекта  Bitmap  передавать Drawable, можно воспользоваться new BitmapDrawable(you_bitmap)
2. При создании объекта BalloonItem необходимо в конструкторе передавать Context (необходимый для загрузки ресурсов)
3. Исправить использования интерфейса с OnBallonListener на OnBalloonListener и добавить новые методы из данного интерфейса
4. Исправить имя метода у BalloonItem с setOnBallonListener на setOnBalloonViewClickListener
5. Необходимо изменить логику работы интерфейса  OnBalloonListener  метода  onBallonClick  на  onBalloonViewClick


Интеграция проектов с Яндекс.Картами и Навигатором
--------------------------------------------------

Способы интеграции приложений с Яндекс.Картами для посторения маршрутов и выполнения поиска описаны на [Wiki](https://github.com/yandexmobile/yandexmapkit-android/wiki)

Дополнительная информация
---------------------------

Также у этого проекта есть:
* [Wiki](https://github.com/yandexmobile/yandexmapkit-android/wiki), в которой содержится полезная информация о Yandex Map Kit.
* JavaDoc, который находится в yandexmapkit-library/doc. В нем содержится описание классов и методов Yandex Map Kit.

Если вы хотите сообщить об ошибке или предложить идею в развитии, то напишите об этом, пожалуйста, в [Issues](https://github.com/yandexmobile/yandexmapkit-android/issues).
