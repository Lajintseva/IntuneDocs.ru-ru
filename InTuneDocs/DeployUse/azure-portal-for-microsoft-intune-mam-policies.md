---
title: "Портал Azure для политик управления мобильными приложениями | Microsoft Intune"
description: "Создание политик управления мобильными приложениями на портале Azure. Создаваемые на портале политики могут применяться к устройствам с регистрацией в Intune или без нее."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 07/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7d6dae94-a833-40b7-9016-14ea234bb33c
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: be1ebcdf2514e45d383dd49890e0e21acf6ede44
ms.openlocfilehash: 1ddb7a30a6f23a3f3d754bd18975c50f32662578


---

# Портал Azure для политик управления мобильными приложениями Microsoft Intune
## Доступ к порталу Azure
**Портал Azure** позволяет создавать политики управления мобильными приложениями (MAM) и управлять ими.

Портал Azure поддерживает создание политик MAM для следующих приложений:
- приложения, работающие на устройствах, **зарегистрированных в службе Intune и управляемых ей**;
- приложения, работающие на устройствах, которые **не зарегистрированы** в каком-либо решении для управления мобильными устройствами;
- приложения, работающие на устройствах, которые **зарегистрированы в решении для управления мобильными устройствами стороннего производителя**.

>[!IMPORTANT]

> Если вы используете [консоль администрирования Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) для управления устройствами, то с ее помощью вы можете создать политику MAM, поддерживающую приложения на устройствах, зарегистрированных в Intune.

> В консоли администрирования Intune могут отображаться не все параметры политики MAM. Портал Azure — это новая консоль администрирования для создания политик MAM. При создании политики MAM в консоли администрирования Intune и на портале Azure политики, созданные на портале Azure, применяются к приложениям и разворачиваются для пользователей.

## Вход на портал Azure и настройка начальной страницы

1.  Перейдите на [портал Azure](https://portal.azure.com) и выполните вход с помощью своих учетных данных [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

    ![Снимок экрана со страницей входа на портал Azure](../media/AppManagement/AzurePortal_MAMSigninPage.png)

2.  После успешного входа вы увидите **панель мониторинга**. Страница **панели мониторинга** является настраиваемой.

    ![Снимок экрана с панелью мониторинга на портале Azure](../media/AppManagement/AzurePortal_MAMStartboard_NoMAM.png)

3.  В меню **Обзор** найдите пункт **Intune**.![Снимок экрана меню "Обзор" с выделенным пунктом "Intune".](../media/AppManagement/AzurePortal_MAM_Browse_Intune.png)

4.  Выберите **Intune > Управление мобильными приложениями Intune > Параметры**.

    ![Снимок экрана с колонкой "Управление мобильными приложениями Intune"](../media/AppManagement/AzurePortal_MAM_Mainblade.png)

    > [!TIP]
    > Чтобы закрепить колонку на **начальной** странице, можно использовать параметр **закрепить** в этой колонке.  Щелкните значок закрепления в **колонке управления мобильными приложениями Intune**, чтобы закрепить ее на **начальной** странице.

    ![Снимок экрана с колонкой "Управление мобильными приложениями Intune" и выделенным значком закрепления](../media/AppManagement/AzurePortal_MAM_PinBladeAction.png)

    ![Снимок экрана: панель мониторинга с закрепленным элементом "Intune"](../media/AppManagement/AzurePortal_MAM_Startboard_withMAM.png)
## Дальнейшие действия
[Подготовка к настройке политик управления мобильными приложениями](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Jul16_HO5-->

