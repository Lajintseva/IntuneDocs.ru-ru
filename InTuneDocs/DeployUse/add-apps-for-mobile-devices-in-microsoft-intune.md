---
# required metadata

title: Добавление приложений для мобильных устройств | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f5b1f1ae-f177-450a-9af9-936a02d052e3

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Добавление приложений для мобильных устройств в Microsoft Intune

В этом разделе описывается, как добавить приложения в Intune перед их развертыванием.


> [!IMPORTANT]
> Сведения в этом разделе помогут добавить приложения, которые вы хотите развернуть на зарегистрированных устройствах и компьютерах с ОС Windows. Если вы хотите добавить приложения на компьютеры Windows, которыми вы управляете с помощью клиентского программного обеспечения Intune, см. раздел [Добавление приложений на компьютеры Windows в Microsoft Intune](add-apps-for-windows-pcs-in-microsoft-intune.md).

## Добавление приложения
В этой процедуре используется издатель ПО Intune для настройки свойств приложения и (где применимо) его отправки в облачное хранилище.

1.  В [консоли администрирования Microsoft Intune](https://manage.microsoft.com) выберите **Приложения** &gt; **Добавить приложение**, чтобы запустить издатель ПО Intune.

    > [!TIP] Перед запуском издателя может потребоваться ввести имя пользователя и пароль Intune.

2.  На странице **Установка ПО** издателя ПО в разделе **Выберите, каким образом будет предоставляться доступ к этой программе для устройств** выберите один из указанных ниже вариантов.
    - **Установщик программ** — для приложений с расширением **.msi** или **.exe** выберите один из указанных ниже вариантов.
        - **Выберите тип файла установщика программ**: указывает тип программного обеспечения, которое нужно развернуть. Например, если нужно установить приложение iOS, выберите **Пакет приложения для iOS (IPA-файл)**.
        - **Укажите расположение файлов установки ПО**: введите расположение файлов установки или нажмите кнопку **Обзор**, чтобы выбрать расположение из списка.
        - **Добавлять дополнительные файлы и вложенные папки из одной и той же папки** — только для типов файлов **установщика Windows**.<br>Для некоторых программ, использующих установщик Windows, требуются вспомогательные файлы, которые обычно находятся в одной папке с файлами установки. Выберите этот параметр, если помимо прочего требуется развернуть эти файлы.<br>Этот тип установки использует определенное пространство в облачном хранилище.

  -   **Внешняя ссылка** — для приложений, которые вы хотите создать, задав ссылку на хранилище приложений, укажите следующее.

        - **Укажите URL-адрес**: укажите один из следующих URL-адресов:
            - URL-адрес хранилища приложений для приложения, которое требуется развернуть. Например, если требуется развернуть приложение удаленного рабочего стола Microsoft для Android, укажите **https://play.google.com/store/apps/details?id=com.microsoft.rdc.android**. Чтобы найти URL-адрес приложения, используйте поисковую систему поиска для поиска страницы хранилища, содержащей приложение. Например, чтобы найти приложение удаленного рабочего стола, выполните поиск по запросу **Удаленный рабочий стол Microsoft Android**.
            - URL-адрес веб-сайта. Intune развернет на устройстве ярлык, ссылающийся на сайт (так называемый веб-клип).
            - URL-адрес приложения в Интернете. Intune развернет на устройстве ярлык, ссылающийся на приложение.
        - **Требовать, чтобы ссылка открывалась в Managed Browser (только для Android и iOS)**. При развертывании ссылки на веб-сайт или веб-приложение для пользователей они смогут открыть ее только в браузере Managed Browser Intune, который должен быть установлен на устройстве.<br>Дополнительные сведения об управляемом браузере см. в разделе [Управление доступом в Интернет с помощью политик управляемого браузера в Microsoft Intune](manage-internet-access-using-managed-browser-policies.md).<br>Этот тип установки не использует пространство в облачном хранилище.

  -   **Управляемое приложение iOS из магазина App Store** — для бесплатных приложений из магазина iTunes, которыми вы хотите управлять с помощью политик MAM, укажите следующее.

        - **Укажите URL-адрес**: введите URL-адрес хранилища приложений для приложения, которое требуется развернуть. Например, если вы хотите развернуть приложение Microsoft Work Folders для iOS, укажите **https://itunes.apple.com/us/app/work-folders/id950878067?mt=8**.<br>Этот тип установки не использует пространство в облачном хранилище.

        Например, если вы хотите развернуть на устройствах приложение Microsoft Word из магазина iTunes, страница будет выглядеть следующим образом:
        
        ![издателя программного обеспечения Intune](./media/publisher-for-mobile.png)

3.  На странице **Описание программного обеспечения** настройте следующие параметры.

    > [!TIP] В зависимости от используемого типа установщика некоторые из этих значений могут быть введены автоматически.

    - **Издатель**: введите имя издателя приложения.
    - **Имя**: введите имя приложения так, как оно будет отображаться на корпоративном портале.<br>Убедитесь, что все имена приложений являются уникальными. Если имя приложения существует два раза, пользователи корпоративного портала увидят только одно из приложений.
    - **Описание**: введите описание приложения. Оно будет отображаться для пользователей на корпоративном портале.
    - **URL-адрес страницы сведений о ПО**: доступен только в том случае, если выбран параметр **Установщик программ**. Дополнительно можно ввести URL-адрес веб-сайта со сведениями об этом приложении. Этот URL-адрес будет отображаться для пользователей на корпоративном портале.
    - **URL-адрес политики конфиденциальности**: доступен только в том случае, если выбран параметр **Установщик программ**. Дополнительно можно ввести URL-адрес веб-сайта со сведениями о политике конфиденциальности для этого приложения. Этот URL-адрес будет отображаться для пользователей на корпоративном портале.
    - **Категория** (необязательно): выберите одну из встроенных категорий приложений. Это облегчит поиск приложения при просмотре пользователями корпоративного портала.
    - **Отображать это приложение как рекомендуемое и выделить его на портале организации**: выберите этот параметр, чтобы приложение отображалось на видном месте на главной странице корпоративного портала, когда пользователи просматривают приложения.
    - **Значок** (необязательно): отправьте значок, который будет связан с приложением. Это значок, который будет отображаться с приложением при просмотре пользователями корпоративного портала.

        В этом примере вы настроили описание приложения Microsoft Word для iOS:

        ![Пример описания ПО](./media/ios-software-description.png)

4.  На странице **Требования** укажите требования, которые должны быть выполнены на компьютерах перед установкой приложения на устройство. Например, для пакета приложений для iOS можно выбрать минимальную требуемую версию iOS и тип устройства, например iPhone или iPad.

    > [!TIP] Страница **Требования** отображается только для некоторых типов приложений.

5.  Дополнительные страницы мастера отображаются при выборе типа файла **Установщик Windows**. Этот тип файлов используется при развертывании программного обеспечения на компьютеры под управлением Windows 10 или более поздней версии, которые зарегистрированы с помощью Intune.

6.  На странице **Сводка** проверьте указанные сведения. Когда вы будете готовы, нажмите кнопку **Отправить**.

7.  Чтобы завершить работу мастера, нажмите кнопку **Закрыть**.

Приложение отображается в узле **Приложения** в рабочей области **Приложения**.

## Примеры

### Развертывание приложений MSI на устройствах Windows 10
Из этого четырехминутного видеоролика вы узнаете о том, как развернуть приложения установщика Microsoft (MSI) в зарегистрированные устройства под управлением Windows 10.<br><br>

<iframe src="https://channel9.msdn.com/Series/How-to-Control-the-Uncontrolled/6--How-to-Deploy-MSI-Applications-to-Windows-10-Using-Intune-and-Mobile-Device-Management-MDM/player" width="640" height="360" allowFullScreen frameBorder="0"></iframe>

## Дальнейшие действия

После создания приложения его необходимо развернуть. Дополнительные сведения см. в статье [Развертывание приложений в Microsoft Intune](deploy-apps.md).





<!--HONumber=May16_HO4-->

