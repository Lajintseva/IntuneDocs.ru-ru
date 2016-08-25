---
title: "Снятие устройств с учета | Microsoft Intune"
description: "Intune поддерживает выборочную и полную очистку для удаления устройства из системы управления Intune. Для этого удаляются его политики, а также сведения о нем на корпоративном портале."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3dbec400-5d8a-47be-b892-7745811d9de2
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7bea7ba4ef59c6b1400414b59456e19dc1c152fb
ms.openlocfilehash: ad5e9453f8132d383f8c23886e48505769c7f44b


---

# Снятие устройств с учета из системы управления Intune

Как для устройств организации, так и для личных устройств наступает момент, когда устройство требуется удалить из системы управления Intune. Снятие устройства с учета не вызывает больших сложностей. Вы можете выполнить выборочную или полную очистку данных на устройствах, управляемых как мобильные устройства. Вы можете также снять с учета компьютеры, управляемые клиентским программным обеспечением Intune.

## Очистка данных и приложений с устройств
Как выборочная, так и полная очистка убирает устройство из системы управления Intune, удаляя его политику и корпоративный портал. Это означает, что у устройства больше не будет учетных данных, необходимых для подключения к ресурсам компании, например к Microsoft SharePoint, электронной почте или Office 365.

[Выборочная очистка](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#selective-wipe) предпочтительнее для сотрудников, которые зарегистрировали свои устройства в Intune, так как это не влияет на личные сведения на устройстве. Удаляются только корпоративные данные.

Для устройств организации, которые следует переназначить, можно также выполнить [полную очистку данных](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#full-wipe), в ходе которой устройство возвращается к заводским настройкам по умолчанию.

## Порядок удаления устройств на портале Azure Active Directory

1.  Войдите, используя учетные данные в организации, по ссылке [http://aka.ms/accessaad](http://aka.ms/accessaad) или [https://portal.office.com](https://portal.office.com), а затем выберите **Центры администрирования** &gt; **Azure AD**.

2.  Создайте подписку Azure, если у вас ее нет. Если у вас платная учетная запись, кредитная карта или оплата не потребуются (щелкните ссылку **Зарегистрировать бесплатную подписку Azure Active Directory**).

4.  Выберите **Active Directory** , а затем выберите вашу организацию.

5.  Откройте вкладку **Пользователи** .

6.  Выберите пользователя, устройства которого требуется удалить.

7.  Выберите **Устройства**.

8.  Выберите нужные устройства и щелкните **Удалить устройство**. Устройство будет удалено при следующей синхронизации с Active Directory. Обычно это происходит в течение четырех часов. После синхронизации устройство будет удалено из системы управления. Одно устройство будет удалено из квоты на устройства конкретного пользователя.

## Снятие с учета управляемых компьютеров
Компьютеры, управляемые клиентским программным обеспечением Intune, можно удалить из системы управления в консоли администрирования Intune. При этом с компьютера вместе с политикой Intune будет удалено и клиентское программное обеспечение. Ознакомьтесь с информацией о [снятии с учета компьютеров, управляемых клиентским программным обеспечением Intune](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#retire-a-computer.md).

## Блокировка доступа к устройству
В случае утери устройства или необходимости снять устройство с учета, если сотрудник уволился из компании, не вернув устройство компании, можно также [сбросить секретный код и удаленно заблокировать](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) устройство. Это позволяет предотвратить ненадлежащее использование информации компании несмотря на то, что устройство потребуется списать как утерянное.

Также можно отозвать лицензию из учетной записи пользователя Intune конкретного сотрудника. Это позволяет освободить лицензию и при необходимости назначить ее учетной записи другого пользователя.

## Снятие оборудования с учета
В некоторых случаях само устройство достигает конца своего срока службы. В таких случаях [возврат заводских настроек](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md) в рамках полной очистки удаляет все данные, а само устройство — из Intune. Затем от такого оборудования можно избавиться в соответствии с политикой компании.

### См. также
[Защита данных с помощью полной или выборочной очистки](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md)



<!--HONumber=Aug16_HO2-->

