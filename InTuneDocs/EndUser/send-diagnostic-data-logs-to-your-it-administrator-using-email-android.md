---
title: "Отправка журналов диагностических данных ИТ-администратору по электронной почте | Microsoft Intune"
description: 
keywords: 
author: staciebarker
manager: arob98
ms.date: 05/31/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 85c868e7-8d63-480c-9770-4e99614a5c94
ROBOTS: noindex,nofollow
ms.reviewer: arnab
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 376e6c1ae229187ab8ec73390f091f1d534365dd
ms.openlocfilehash: 30d325a9f5b920176ed5f4c9ce003564dcc6d3b5


---


# Отправка журналов диагностических данных ИТ-администратору по электронной почте

Если при работе с приложениями организации или учебного заведения или с приложением корпоративного портала на устройстве Android появляется сообщение об ошибке, вы можете отправить журналы диагностических данных, чтобы помочь ИТ-администратору выявить и исправить эту ошибку. Чтобы поместить в журналы все сведения, которые помогут ИТ-администратору выявить проблему, включите подробное ведение журналов. Дополнительные сведения о подробном ведении журналов см. [здесь](use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android.md).

Включение подробного ведения журналов

1.  Откройте приложение корпоративного портала.

2.  Последовательно выберите **Menu** (Меню) &gt; **Settings** (Настройки).

    > [!NOTE] 
    > **Меню** может быть представлено программной или аппаратной кнопкой в зависимости от используемого устройства Android.

3.  В разделе **Diagnostic Data** (Диагностические данные) нажмите **Отправить данные**.

    > [!NOTE]
    > **Только если вы используете Android 6.0 или более поздних версий:** при нажатии элемента **Отправить данные** появляется сообщение **Разрешить корпоративному порталу доступ к фото, мультимедиа и файлам на вашем устройстве?**. 

    Это сообщение вводит пользователя в заблуждение, так как **корпорация Майкрософт не осуществляет доступ к фотографиям, мультимедиа и файлам на вашем устройстве.** Текст сообщения регулируется компанией Google, поэтому корпорация Майкрософт не может изменить его.  Предоставляя доступ, вы всего лишь разрешаете устройству записывать журналы данных на свою SD-карту, что позволяет получить эти журналы с помощью USB-кабеля.

    Если запретить доступ, сообщение появится снова при следующем нажатии элемента **Отправить данные**, но отображение последующих сообщений можно отключить, установив флажок **Больше не спрашивать**.  Если пользователь захочет разрешить доступ в дальнейшем, потребуется перейти в раздел **Settings** (Настройки) &gt; **Apps** (Приложения) &gt; **Company Portal** (Корпоративный портал) &gt; **Permissions** (Разрешения) &gt; **Storage** (Хранилище) и предоставить разрешение.

4.  Следуйте инструкциям на экране, чтобы выбрать приложение электронной почты для отправки журналов ИТ-администратору. Приложение создаст сообщение электронной почты с предварительно заданным адресом, включив в него все необходимые журналы.


### См. также
[Использование устройства Android с Intune](using-your-android-device-with-intune.md)


<!--HONumber=Jul16_HO3-->

