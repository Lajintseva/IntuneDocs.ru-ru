---
title: "Профили сертификатов для доступа к ресурсам | Microsoft Intune"
description: "Защита доступа к VPN, Wi-Fi и электронной почте с помощью сертификата, устанавливаемого на каждом устройстве пользователя."
keywords: 
author: Nbigman
manager: angrobe
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8cbb8499-611d-4217-a7b4-e9b864785dd0
ms.reviewer: kmyrup
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0ced62efd04803943cbbfd8cecef907409a03c0b
ms.openlocfilehash: b5b0270468cbb1e5bbd2a3b4970329a467927cee


---

# Защита доступа к ресурсам с помощью профилей сертификатов в Microsoft Intune
При предоставлении пользователям доступа к корпоративным ресурсам через профили VPN, Wi-Fi или электронной почты можно обеспечить безопасность доступа, установив сертификат на каждом устройстве. Это работает следующим образом.

1. Настройте подходящую инфраструктуру сертификатов, как описано в статьях [Настройка инфраструктуры сертификатов для SCEP](configure-certificate-infrastructure-for-scep.md) и [Настройка инфраструктуры сертификатов для PFX](configure-certificate-infrastructure-for-pfx.md).

2. Установите корневой сертификат (или промежуточный сертификат центра сертификации (ЦС)) на каждом устройстве, чтобы оно распознавало подлинность вашего ЦС. Для этого создайте и разверните **профиль доверенного сертификата**. При его развертывании устройства, которыми вы управляете с помощью Intune, запрашивают и получают корневой сертификат. Необходимо создать отдельный профиль для каждой платформы. **Профиль доверенного сертификата** доступен для следующих платформ:
 -  Устройства iOS 8.0 и более поздней версии
 -  Mac OS X 10.9 и более поздние версии
 -  Android 4.0 и более поздней версии
 -  Windows 8.1 и более поздние версии
 -  Windows Phone 8.1 и более поздней версии

3. Создайте профили сертификатов, чтобы устройства запрашивали сертификат, используемый для проверки подлинности доступа к VPN, Wi-Fi и электронной почте, как описано в статье [Настройка профилей сертификатов Intune](configure-intune-certificate-profiles.md). Можно создать и развернуть **профиль сертификата PKCS 12 (PFX)** *или* **профиль сертификата SCEP** для устройств на следующих платформах:

  -  Устройства iOS 8.0 и более поздней версии
  -  Android 4.0 и более поздней версии
  -  Windows 10 (Desktop и Mobile) и более поздних версий

  Используйте **профиль сертификата SCEP** для устройств на следующих платформах:
    -   Mac OS X 10.9 и более поздние версии
    -   Windows Phone 8.1 и более поздней версии

Необходимо создать отдельный профиль для каждой платформы. При создании профиля необходимо сопоставить его с уже созданным **профилем доверенного корневого сертификата**.

> [!NOTE]           
> - При отсутствии центра сертификации предприятия необходимо создать его.
>- Если в зависимости от платформ устройств вы решите использовать профиль SCEP, необходимо также настроить сервер службы регистрации сертификатов для сетевых устройств (NDES).
>-  Если вы планируете использовать профили SCEP или PFX, необходимо скачать и настроить соединитель сертификатов Microsoft Intune.
>-  Сведения о настройке всех необходимых служб описаны в статьях [Настройка инфраструктуры сертификатов для SCEP](configure-certificate-infrastructure-for-scep.md) и [Настройка инфраструктуры сертификатов для PFX](configure-certificate-infrastructure-for-pfx.md).

### Дальнейшие действия
- [Настройка инфраструктуры сертификатов для SCEP](configure-certificate-infrastructure-for-scep.md)
- [Настройка инфраструктуры сертификатов для SCEP](configure-certificate-infrastructure-for-pfx.md)
- [Настройка профилей сертификатов Intune](configure-intune-certificate-profiles.md)



<!--HONumber=Sep16_HO3-->


