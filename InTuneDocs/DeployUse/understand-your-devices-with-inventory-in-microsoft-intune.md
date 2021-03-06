---
title: "Получение сведений об устройствах с помощью инвентаризации | Microsoft Intune"
description: "Сведения об использовании Intune для просмотра информации об оборудовании управляемых устройств."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 312911fe-b963-4949-9911-ae425e0590b2
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 18ef1ca18244b202a35fc8fc23fc994105b7b47e
ms.openlocfilehash: ff55533499494488cd4cd692c6e36fe547ade3e4


---

# Получение сведений об устройствах с помощью инвентаризации в Microsoft Intune
Microsoft Intune позволяет просматривать данные инвентаризацию зарегистрированных устройств и компьютеров под управлением Windows, где запущено клиентское программное обеспечение Intune.
Обычно Intune собирает данные инвентаризации с управляемых устройств раз в 7 дней. Из-за этого внесенные на устройствах изменения, например смена имени или свободное дисковое пространство, могут отображаться в отчетах с задержкой.

## Данные, собираемые с зарегистрированных устройств
Чтобы просмотреть данные инвентаризации, собранные мобильными устройствами, запустите [Отчеты инвентаризации мобильных устройств](understand-microsoft-intune-operations-by-using-reports.md). Intune собирает следующие данные инвентаризации с зарегистрированных устройств:

|Свойство|Кто собирает|
|------------|-----------------------|
|**Название**|Все устройства|
|**Операционная система**|Все устройства|
|**Изготовитель**|Все устройства|
|**Модель**|Все устройства|
|**Канал управления**|Все устройства|
|**Зарегистрировано в AAD**|Все устройства, кроме Mac OS X|
|**Соответствие**|Все устройства|
|**EAS активирована**|Все устройства, кроме Mac OS X|
|**Идентификатор активации EAS**|Все устройства, кроме Mac OS X|
|**Время активации EAS**|Все устройства, кроме Mac OS X|
|**Состояние управления**|Все устройства|
|**Адрес электронной почты**|Все устройства|
|**Идентификатор Exchange ActiveSync**|Все устройства|
|**Устройства, на которых получен корневой доступ или выполнен взлом ОС**|Только устройства iOS и Android|
|**Уникальный идентификатор устройства**|Все устройства, кроме Exchange ActiveSync|
|**Серийный номер**|Устройства iOS, Mac OS X, Android, Windows 8.1 и Windows 10|
|**Общая вместимость хранилища**|Устройства iOS, Mac OS X, Windows 8.1 и Windows 10|
|**Свободное место для хранения данных**|Устройства iOS, Mac OS X, Windows 8.1 и Windows 10|
|**Номер телефона**<br>Телефоны, отнесенные к корпоративным, идентифицируются по полному номеру телефона (например, при запуске отчета об инвентаризации мобильных устройств). Номера телефонов BYOD маскируются символами *; отображаются только четыре последние цифры.|Устройства iOS, Android и Windows Phone|
|**IMEI**|Устройства Exchange ActiveSync, iOS, Android и Windows Phone|
|**MEID**<br>Идентификатор мобильного оборудования|Только устройства iOS|
|**Wi-Fi MAC**|Все устройства, кроме Exchange ActiveSync|
|**Абонентская система связи**|Только устройства iOS и Android|
|**Сотовая технология**|Только устройства iOS и Android|
|**Защищено**|Только устройства iOS|
|**Состояние блокировки активации**|Только устройства iOS|
|**Дата регистрации**|Все устройства|
|**Последнее обновление**|Все устройства|
|**Ethernet MAC**|Только устройства Mac OS X|
|**Блокировка активации включена**|Только устройства iOS|
|**Шифрование включено**|Все устройства|

## Данные, собираемые с компьютеров Windows
> [!IMPORTANT]
> Этот раздел применим только для компьютеров под управлением Windows, где запущено клиентское программное обеспечение Windows Intune.

Чтобы просмотреть данные инвентаризации компьютеров Windows, выполните [Отчеты об инвентаризации компьютеров](understand-microsoft-intune-operations-by-using-reports.md). Intune собирает следующие данные инвентаризации с компьютеров Windows:

-   **Название**

-   **Тип шасси**

-   **Изготовитель**

-   **Модель**

-   **Операционная система**

-   **Версия TPM**

-   **Общий объем дискового пространства**

-   **Используется места на диске**

-   **Свободное место на диске**

-   **Имя диска ОС**

-   **Место на диске ОС**

-   **Свободное место на диске ОС**

-   **Физическая память**

-   **Имя процессора**

-   **Архитектура процессора**

-   **Скорость ЦП**

-   **IP-адрес**

-   **Серийный номер**

-   **Последний пользователь, вошедший в систему**

-   **Назначенный пользователь**

-   **Последнее обновление**

<!-- this section below belongs in the planning journey
### See Also
[Monitoring and reports with Microsoft Intune](monitoring-and-reports-with-microsoft-intune.md)
-->



<!--HONumber=Aug16_HO5-->


