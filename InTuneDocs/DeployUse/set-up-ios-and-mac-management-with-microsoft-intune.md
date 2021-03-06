---
title: "Настройка управления в iOS и Mac | Microsoft Intune"
description: "Включение управления мобильными устройствами (MDM) с помощью Microsoft Intune для устройств iOS, включая устройства iPad и iPhone, а также для устройств Mac OS X."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc451224-1372-4b84-b641-cfa67cb3849b
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c880bd9dfb998355a18e78af898a96d4cee393f7
ms.openlocfilehash: 263fb9add8d30c0f98af46e46b566f15513db109


---

# Настройка управления устройствами в iOS и Mac
Инструкции по настройке устройства iOS или Mac см. [здесь](../enduser/using-your-ios-or-mac-os-x-device-with-intune.md).

Intune позволяет управлять мобильными устройствами iPad, iPhone и Mac OS X, а также предоставляет пользователям доступ к корпоративной электронной почте и приложениям. Для управления устройствами iOS и Mac с помощью Intune требуется сертификат службы push-уведомлений Apple (APNs). После добавления этого сертификата в Intune пользователи смогут установить приложение корпоративного портала для регистрации своих устройств. Или же администратор сможет настроить [управление корпоративными устройствами iOS](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

1.  **Настройка Intune**<br>
    Если это еще не сделано, подготовьтесь к управлению мобильными устройствами, [установив в качестве центра управления мобильными устройствами](prerequisites-for-enrollment.md#set-mobile-device-management-authority) службу **Microsoft Intune** и настроив MDM.

2.  **Получение запроса подписи сертификата**<br>
    Используя учетную запись с правами администратора, откройте [консоль администрирования Microsoft Intune](http://manage.microsoft.com), перейдите в меню **Администрирование** &gt; **Управление мобильными устройствами** &gt; **iOS и Mac OS X** &gt; **Отправка сертификата APNs** и щелкните **Скачать запрос на сертификат APNs**. Сохраните файл запроса на подписывание сертификата (CSR-файл) локально. CSR-файл используется для запроса сертификата отношений доверия с портала сертификатов push-уведомлений Apple.

    ![Диалоговое окно "Отправка сертификата APNs"](../media/Intune-iOS-enrollment-with-apns.png)

3.  **Получите сертификата службы push-уведомлений Apple**<br>
    Перейдите на [портал сертификатов push-уведомлений Apple](http://go.microsoft.com/fwlink/?LinkId=269844) и войдите с помощью идентификатора Apple ID вашей организации, чтобы создать сертификат APNs с помощью CSR-файла. Нажав кнопку **Отправить** на портале сертификации Push-уведомлений Apple, вы получаете JSON-файл, который нельзя использовать для APNs. Завершите скачивание, вернитесь на страницу **Сертификаты сторонних серверов** портала сертификатов Apple Push и нажмите кнопку **Скачать**.

    Загрузите сертификат APN (.pem) и сохраните файл локально. Этот идентификатор Apple ID необходимо использовать в будущем для возобновления действия сертификата APN.

4.  **Добавление сертификата APNs в Intune**<br>
    В [консоли администрирования Microsoft Intune](http://manage.microsoft.com) перейдите в меню **Администрирование** &gt; **Управление мобильными устройствами** &gt; **iOS и Mac OS X** &gt; **Отправка сертификата APNs** и щелкните **Отправить сертификат APNs**. **Перейдите** в файл сертификата (.pem) и щелкните **Открыть** , а затем введите ваш **Apple ID**. С помощью сертификата APN служба Intune может зарегистрировать устройства iOS и управлять ими, применяя политику к зарегистрированным мобильным устройствам.

5.  **Сообщите пользователям о том, как получить доступ к ресурсам компании с помощью корпоративного портала**<br>
    Вашим пользователям потребуется узнать, как зарегистрировать устройства и чего ожидать после того, как они начнут управлять ими.
    - [Что нужно сообщить конечным пользователям об использовании Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)
    - [Руководство конечного пользователя для устройств iOS и Mac](../enduser/using-your-ios-or-mac-os-x-device-with-intune.md)

Если ваша организация приобретает устройства iOS для пользователей, эти устройства также могут быть зарегистрированы для управления как [корпоративные устройства iOS](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

### См. также
[Предварительные требования для регистрации с помощью Microsoft Intune](prerequisites-for-enrollment.md)



<!--HONumber=Sep16_HO4-->


