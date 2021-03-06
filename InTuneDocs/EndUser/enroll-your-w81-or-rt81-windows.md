---
title: "Регистрация устройства с Windows 8.1 или Windows RT 8.1 | Microsoft Intune"
description: "Описывается, как зарегистрировать устройство с Windows 8.1 или Windows RT 8.1 в Intune."
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 09/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 28984f26-1070-4f7a-877c-669a59375c0c
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: bff97f79c6e88bbf55c2c3a259891bb6206b690b
ms.openlocfilehash: ce39a013186942e3d5a2b355d1425edbed4fa769


---


# Регистрация устройства Windows 8.1 или Windows RT 8.1 в Intune

Если в вашей компании или учебном заведении используется Microsoft Intune, вы можете зарегистрировать свои устройства, чтобы получить доступ к электронной почте, файлам и другим ресурсам организации. Регистрация устройств позволяет организации обеспечить безопасность корпоративных данных. Дополнительные сведения о регистрации см. в статьях [What happens if you install the Company Portal app and enroll your device in Intune?](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows.md) (Что произойдет, если установить приложение "Корпоративный портал" и зарегистрировать устройство в Intune?) и [What your IT administrator can and can't see on your device](what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows.md) (Что ИТ-администратор может и не может видеть на вашем устройстве).


Чтобы зарегистрировать устройство Windows 8.1 или Windows RT 8.1, выполните указанные ниже действия.

1.  На устройстве последовательно выберите **Настройки** &gt; **Настройки компьютера** &gt; **Сеть** &gt; **Рабочая область**.

    ![nav-to-workplace](./media/W81-1-workplacejoin.png)

2.  Введите рабочий или учебный адрес электронной почты для идентификатора пользователя, если это необходимо, а затем выберите **Присоединиться**.

    Если идентификатор пользователя не требуется, используется адрес электронной почты, введенный при входе на это устройство.

3.  Введите пароль для рабочей или учебной электронной почты.

    ![type-password](./media/W81-2-workplacesettings_signin.png)

4.  В разделе **Turn on device management** (Включение управления устройством) нажмите **Включить**.

    ![turn-on-device-management](./media/W81-3-dev-mgt-turn-on.png)

5.  В диалоговом окне **Разрешить приложения и службы от ИТ-администратора** установите флажок **Я принимаю**, а затем нажмите **Включить**.

    ![turn-on-allow-apps-services](./media/W81-4-agree-allow-apps-services.png)

    После успешной регистрации отображается следующий экран.

    ![enrollment-complete](./media/W81-5-enrolled-done.png)

Также рекомендуется установить приложение корпоративного портала, которое позволит легко определять и скачивать приложения организации, актуальные для вас и вашей роли. В зависимости от того, как ваша компания настроила Intune, приложение корпоративного портала могло быть установлено в рамках процесса регистрации. Чтобы проверить, есть ли у вас это приложение, найдите **Корпоративный портал** в списке приложений. Если вы не видите корпоративный портал в списке приложений, выполните следующие действия для его установки.

1.  Выберите **Пуск** &gt; **Магазин**.

2.  Нажмите **Поиск** и введите **корпоративный портал**.

3.  В списке результатов нажмите **Корпоративный портал**.

4.  Нажмите **Установить** или **Бесплатно**. Отображаемый параметр зависит от того, как приложение настроено в компании.

По-прежнему нужна помощь? Обратитесь к ИТ-администратору. Его контактные данные доступны на [веб-сайте корпоративного портала](http://portal.manage.microsoft.com).




<!--HONumber=Sep16_HO3-->


