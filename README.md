
## Instagram API access

Доступ к Instagram API для Android (ARM и x86) Версия 123.0.0.21.114

## Требования

* Последняя версия  JDK ([Загрузить](https://www.oracle.com/technetwork/java/javase/downloads/jdk11-downloads-5066655.html))

* Burp Suite v1.7.36 (*.jar версия) ([Загрузить](https://portswigger.net/burp/releasesarchive/community))

* Instagram APK ([ARM v117.0.0.28.123](https://www.apkmirror.com/apk/instagram/instagram-instagram/instagram-instagram-117-0-0-28-123-release/instagram-117-0-0-28-123-3-android-apk-download/)  - 
[x86 v123.0.0.21.114](https://www.apkmirror.com/apk/instagram/instagram-instagram/instagram-instagram-123-0-0-21-114-release/instagram-123-0-0-21-114-2-android-apk-download/))

***Загрузить только по указанным ссылкам, ни с Google Play или еще откуда-нибудь***

* ***Рутованый*** Android или
*виртуальный Android используя
    [Genymotion](https://www.genymotion.com/) не ниже Android 8+*,
    *виртуальный Android Genymotion x86 рутован по умолчанию*.

* ADB ([Загрузить](https://developer.android.com/studio/releases/platform-tools.html))
    *Genymotion установит ADB автоматически. Вы можете найти его `<Genymotion Installation path>/tools`*
    
## Важно!!! Выполняйте все в указанной ниже последовательности:


1. Установить Genymotion виртуальную машину и запустить ее.

2. Загрузить и установить Instagram apk на ваше устройство

3. Запустить приложение Instagram (подождать несколько секунд) и затем закрыть его.
***Необходимо запустить приложение Instagram только один раз, прежде чем начать его патчить!***

4. Загрузить файлы [ARM](https://github.com/vitaloldos/Get_Instagram_API/tree/master/arm) - [x86](https://github.com/vitaloldos/Get_Instagram_API/tree/master/x86)) и скопировать на устройство:

ARM: `adb push libliger.so /data/data/com.instagram.android/lib-superpack-zstd/libliger.so`

x86: `adb push libliger.so /data/data/com.instagram.android/lib-zstd/libliger.so`

5. Открыть еще раз приложение Instagram (подождать несколько секунд) и затем закрыть его.

6. Запустить Burp Suite с /<JDK Installation path>/bin/java -jar burpsuite_community.jar и установить в настройках Android proxy.
***Нужно установить proxy по инструкции***
*Нужно [установить Burp Suite сертификат на Android](https://distributedcompute.com/2017/12/12/tech-note-installing-burp-certificate-on-android/)*

7. Вот и все! Откройте приложение Instagram и анализируйте запросы в Burp Suite!

## Instagram Signature Key для ARM и x86

* **v117.0.0.28.123:** `a86109795736d73c9a94172cd9b736917d7d94ca61c9101164894b3f0d43bef4`
* **v123.0.0.21.114:** `8fea883900208c803efa5daebe163d3d75979be19e288368a3e34a465c0f975e`
