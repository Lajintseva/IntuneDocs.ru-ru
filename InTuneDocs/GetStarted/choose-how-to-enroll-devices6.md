---
title: "Выбор способа регистрации мобильных устройств | Microsoft Intune"
description: "Выберите способ регистрации мобильных устройств в Intune, ответив на несколько простых вопросов."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 40262e47-1ab4-437d-8ca5-c89b5022f91f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
translationtype: Human Translation
ms.sourcegitcommit: 2bfba29b5b2585f276a85a8dee7e62009e41ec3f
ms.openlocfilehash: b96b970b3326b0b17f1a5f57f6d1407756c78e41


---
# Выбор способа регистрации мобильных устройств

Определить наилучший способ регистрации устройств, которыми вы управляете, помогут ответы на ряд вопросов.

## **Как вы будете управлять выделенными корпоративными устройствами?**

  > [!div class="button"]
[Программа регистрации устройств iOS >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune)  
> [!div class="button"]
[Помощник по настройке iOS >](/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune)
> [!div class="button"]
[Тег с IMEI >](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  Вы можете зарегистрировать устройства организации с выделенными пользователями следующим образом:

  - **Программа регистрации устройств Apple (DEP)** —для устройств с iOS, приобретаемых или управляемых с помощью программы DEP, можно задать профиль регистрации. При первом включении устройства оно скачает профиль DEP и зарегистрируется с его использованием.

  - **Apple Configurator на компьютере Mac**: Apple Configurator — это приложение Apple, которое выполняется на компьютере Mac. Для установки профиля регистрации на устройстве с iOS его можно подключить к компьютеру Mac с помощью USB-кабеля. Если для регистрации вы можете сбросить устройство до заводских настроек, используйте регистрацию с помощью помощника по настройке.

  - **Пометка с номером IMEI** — импортировав международные идентификаторы мобильного оборудования (IMEI) устройств компании, можно пометить эти устройства как принадлежащие компании в Intune. Это единственный способ идентифицировать выделенное (предназначенное для одного пользователя) устройство Windows или Android как корпоративное. Устройства iOS, не зарегистрированные с помощью программы регистрации устройств Apple или Apple Configurator, также можно пометить номером IMEI. Выполнив предварительную декларацию устройств (пометив их как корпоративные), можно распределять их между пользователями. Затем пользователи смогут зарегистрировать выделенные устройства как личные, установив корпоративный портал для доступа к ресурсам компании, таким как электронная почта, приложения и данные.

  > [!div class="button"]
  [< Назад](choose-how-to-enroll-devices3.md)



<!--HONumber=Sep16_HO2-->


