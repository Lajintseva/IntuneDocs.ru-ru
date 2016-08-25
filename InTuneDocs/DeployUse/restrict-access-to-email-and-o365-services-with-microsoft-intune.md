---
title: "Ограничение доступа к электронной почте и службам Office 365 | Microsoft Intune"
description: "В этом разделе описывается, как использовать условный доступ, чтобы разрешать доступ к корпоративной электронной почте и данным, расположенным в SharePoint Online и других службах, только совместимым устройствам."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 06/16/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c564d292-b83b-440d-bf08-3f5b299b7a5e
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: be1ebcdf2514e45d383dd49890e0e21acf6ede44
ms.openlocfilehash: 536d34e618efdc78b3103a3b1b36f13fb784781c


---

# Ограничение доступа к электронной почте, Office 365 и другим службам с помощью Microsoft Intune
Доступ к корпоративной электронной почте и службам Office 365 можно ограничить с помощью условного доступа в Intune. Возможность условного доступа Intune позволяет ограничить доступ к корпоративной электронной почте и службам Office 365 теми устройствами, которые удовлетворяют заданным правилам.
## Как работает условный доступ?
Параметры политики соответствия используются для оценки соответствия устройства. Политика условного доступа использует эту оценку для разрешения и ограничения доступа к конкретной службе. При использовании политики условного доступа в сочетании с политикой соответствия доступ к службе получают только соответствующие устройства. Политика соответствия требованиям и политика условного доступа развертываются для пользователя. Любое устройство, используемое пользователем для доступа к службам, проверяется на соответствие политикам.

Имейте в виду, что у пользователя, использующего устройство, должна быть развернута политика соответствия требованиям, оценивающая соответствие устройства.
Если политика соответствия не развернута для пользователя, устройство считается соответствующим, поэтому ограничения доступа к нему не применяются.

Если устройство не удовлетворяет условиям политик, запускается процесс регистрации устройства и исправления проблемы, из-за которой устройство не является соответствующим.

Типовой алгоритм условного доступа:

![На схеме показаны точки принятия решений, используемые для выбора между разрешением доступа к службе и блокировкой устройства.](../media/ConditionalAccess4.png)

## Как настроить условный доступ?
Условный доступ используется для управления доступом к **локальному Microsoft Exchange**, **Exchange Online**, **выделенной среде Exchange Online**, **SharePoint Online** и **Skype для бизнеса Online**.

Чтобы настроить условный доступ, настройте политики соответствия устройств и политику условного доступа.

Политика соответствия включает в себя такие параметры, как секретный код, шифрование, а также наличие рутирования. Устройство должно соответствовать этим правилам, чтобы считаться соответствующим.

Можно задать политику условного доступа для ограничения доступа на основе следующих факторов:
- Состояние соответствия устройства.
- Платформа, запущенная на устройстве.
- Тип приложений, используемый для доступа к службам.

В отличие от других политик Intune, развертывание политик условного доступа не выполняется. Вместо этого после настройки политики и выбора пользователей, которые должны иметь ее, политика применяется ко всем целевым пользователям. Если на пользователя распространяется действие политики, каждое используемое им устройство должно соответствовать этой политике, чтобы он мог получить доступ к ресурсам.


## Дальнейшие действия
1. [Дополнительные сведения о политике соответствия устройств и принципах ее работы ](introduction-to-device-compliance-policies-in-microsoft-intune.md)

2. [Создание политики соответствия](create-a-device-compliance-policy-in-microsoft-intune.md)

2.  Создайте политику условного доступа из одного из следующих объектов:
> [!div class="op_single_selector"]
  - [Создание политики условного доступа для Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)
  - [Создание политики условного доступа для локальной организации Exchange](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  - [Создание политики условного доступа для новой выделенной среды Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)
  - [Создание политики условного доступа для прежней выделенной среды Exchange Online](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  - [Создание политики условного доступа для SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  - [Создание политики условного доступа для Skype для бизнеса Online](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
  - [Создание политики условного доступа для Dynamics CRM Online](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)



<!--HONumber=Jul16_HO5-->

