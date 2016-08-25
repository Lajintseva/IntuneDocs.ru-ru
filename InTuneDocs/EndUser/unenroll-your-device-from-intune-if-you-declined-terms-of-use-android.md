---
title: "Отмена регистрации устройства в Intune при отказе от условий использования | Microsoft Intune"
description: "Сведения о том, как отменить регистрацию устройства Android в Intune, если вы отклонили условия использования и не можете войти в приложение корпоративного портала"
keywords: 
author: staciebarker
manager: arob98
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4278f000-0258-4de5-93a1-195b48e5061e
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 376e6c1ae229187ab8ec73390f091f1d534365dd
ms.openlocfilehash: 06e2fa597e9e4143d17e817daee7eeac8eb46bf7


---


# Отмена регистрации устройства в Intune при отказе от условий использования

Удобнее всего отменить регистрацию устройства Android, приняв условия использования, войдя в приложение корпоративного портала и отменив регистрацию в соответствии с [этими инструкциями](unenroll-your-device-from-intune-android.md). Однако если вы отклонили условия использования при попытке войти в приложение корпоративного портала, ваши дальнейшие попытки входа блокируются. Поэтому для отмены регистрации устройства воспользуйтесь этим обходным решением.

При удалении приложения корпоративного портала, помимо прочего, отменяется регистрация устройства в Intune, поэтому оно больше не сможет получать доступ к ресурсам организации.  Дополнительные сведения о том, что происходит при отмене регистрации, см. в статье [What happens if you unenroll your device from Intune?](what-happens-if-you-unenroll-your-device-from-intune-android.md) (Что происходит при отмене регистрации устройства в Intune?).

Перед удалением приложения корпоративного портала необходимо перейти к параметру **Device administrators** (Администраторы устройства) и отключить **корпоративный портал**. Конкретные действия могут немного отличаться в зависимости от используемого устройства Android.

Чтобы отменить регистрацию устройства в Intune и удалить приложение корпоративного портала, выполните следующие действия.

1.  Последовательно выберите пункты **Параметры** &gt; **Безопасность &amp; Блокировка экрана** &gt; **Администраторы устройств**.

    При выполнении этого шага регистрация устройства сразу же отменяется.

2.  Снимите флажок рядом с параметром **Корпоративный портал** или отключите его.

    Теперь можно удалить приложение корпоративного портала.

По-прежнему нужна помощь? Обратитесь к администратору ИТ (см. контактные сведения на [веб-сайте корпоративного портала](http://portal.manage.microsoft.com)) или отправьте письмо команде разработчиков Майкрософт для Android по адресу wintunedroidfbk@microsoft.com.


### См. также
[Использование устройства Android с Intune](using-your-android-device-with-intune.md)


<!--HONumber=Jul16_HO3-->

