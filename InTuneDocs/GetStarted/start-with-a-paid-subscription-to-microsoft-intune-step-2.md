---
title: "Настройка имени личного домена | Microsoft Intune"
description: "Описывается процесс добавления имени личного домена для подписки Intune."
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 08/29/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2382f36f-13d8-4a32-81ad-6cfa604889c3
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: bf2122afc7f86d81b9d072147b19f75be2a55b51
ms.openlocfilehash: 63c0b3340a6f69e20c85abf7947c25ce88f5d826


---


# Настройка имени домена

По умолчанию Intune использует имя домена **<domain>.onmicrosoft.com**, созданное при первой подписке на службу. Если организации принадлежит личный домен, можно настроить имеющийся экземпляр Intune для использования этого имени домена вместо имени, предоставленного с подпиской.

Перед созданием учетных записей пользователей или синхронизацией учетных записей из локального каталога Active Directory настоятельно рекомендуется решить, будет ли использоваться только домен .onmicrosoft.com или нужно добавить одно или несколько настраиваемых имен доменов. Настройка домена до добавления пользователей позволяет упростить управление удостоверениями пользователей для подписки, позволив пользователям выполнять вход с учетными данными, которые они используют для доступа к другим ресурсам домена.

При оформлении подписки на облачную службу Майкрософт имеющийся экземпляр службы становится [клиентом Microsoft Azure AD](http://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant), который предоставляет службы удостоверений и каталогов для вашей облачной службы. А поскольку задачи по настройке Intune для использования имени личного домена организации не отличаются от выполняемых для клиентов Azure AD, используйте сведения и процедуры из статьи [Добавление домена](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/).

> [!TIP]
> Дополнительные сведения об использовании личного домена с облачной службой Майкрософт см. в статье [Общие сведения об именах личных доменов в Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain-concepts/).

### Дальнейшие действия
Поздравляем! Вы завершили шаг 2 *краткого руководства по Intune*.

>[!div class="step-by-step"]

>[&larr; **Вход в Intune**](.\start-with-a-paid-subscription-to-microsoft-intune-step-1.md) [**Добавление пользователей в Intune** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-3.md)  



<!--HONumber=Aug16_HO5-->


