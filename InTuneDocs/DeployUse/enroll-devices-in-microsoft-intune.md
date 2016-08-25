---
title: "Регистрация устройств | Microsoft Intune"
description: "В системе управления мобильными устройствами (MDM) регистрация используется для обеспечения управления устройствами и доступа к ресурсам."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8fc415f7-0053-4aa5-8d2b-03202eca4b87
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c329bd08aaf72ae2acaa03dcb12c911d84b46b4e
ms.openlocfilehash: 9d624da7931c56476b476b7a9fd5711f398052c4


---

# Регистрация устройств для управления в Intune
В системе управления мобильными устройствами Microsoft регистрация используется для обеспечения управления устройствами и доступа к ресурсам. Способ регистрации устройств зависит от типа устройства, от того, кому оно принадлежит, и от требуемого уровня управления. В сценариях "Принеси свое устройство" (BYOD) и устройств, принадлежащих организации, требуется процедура регистрации. Организации, использующие локальную или размещенную в облаке службу Exchange ActiveSync, могут реализовать более простой процесс управления без обязательной регистрации. Компьютерами с ОС Windows также можно управлять с помощью клиентского ПО Intune.

Справочные сведения см. в разделе [Выбор способа регистрации мобильных устройств](/intune/get-started/choose-how-to-enroll-devices1).

###  Поддерживаемые платформы устройств

Intune может управлять следующими платформами устройств:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

## Указание центра управления мобильными устройствами
Центр MDM определяет службу управления, у которой есть разрешение на управление набором устройств. Возможные варианты центра управления мобильными устройствами — отдельная служба Intune или Configuration Manager с Intune. Если Configuration Manager задан в качестве центра управления, использовать другие службы для управления мобильными устройствами нельзя.

>[!IMPORTANT]
> Необходимо тщательно продумать вариант управления мобильными устройствами: с помощью только Intune (веб-служба) или System Center Configuration Manager с Intune (локальное программное решение в сочетании с веб-службой). Заданный центр управления мобильными устройствами изменить нельзя.

1.  В [консоли администрирования Microsoft Intune](http://manage.microsoft.com) щелкните **Администрирование** &gt; **Управление мобильными устройствами**.

2.  В списке **Задачи** выберите **Задать центр управления мобильными устройствами**. Откроется диалоговое окно **Установка центра MDM** .

    ![Диалоговое окно "Задать центр MDM"](../media/intune-mdm-authority.png)

3.  Intune просит подтвердить, что Intune должен быть вашим центром MDM. Установите флажок и нажмите кнопку **Да**, чтобы использовать Microsoft Intune для управления мобильными устройствами.

## Настройка корпоративного портала Intune

С помощью корпоративного портала Intune пользователи могут обращаться к данным компании и решать общие задачи, такие как регистрация устройств, установка приложений и получение поддержки отдела ИТ.

> [!TIP]
> При настройке корпоративного портала все конфигурации применяются к веб-сайту корпоративного портала и приложениям корпоративного портала.

Настройка корпоративного портала позволяет обеспечить удобную и привычную среду для пользователей. Для этого просто войдите в [консоль администрирования Microsoft Intune](https://manage.microsoft.com) с правами администратора клиента или службы, выберите **Администрирование** &gt; **Корпоративный портал** и настройте параметры корпоративного портала.

![admin-console-admin-workspace-comp-portal-settings](../media/cp_sa_cpsetup.PNG)

## Общие сведения о методах регистрации устройств

В следующей таблице приведены методы регистрации корпоративных устройств и их преимущества.

**Методы регистрации в iOS**

| **Метод** |  **[Очистка](#Wipe)** | **[Сходство](#Affinity)**   |   **[Заблокировано](#Lock)** |
|:---:|:---:|:---:|:---:|
|**[BYOD](#BYOD)** | Нет|    Да |   Нет |
|**[DEM](#DEM)**|   Нет |Нет |Нет  |
|**[DEP](#DEP)**|   Да |   Необязательно |   Необязательно|
|**[USB-SA](#USB-SA)**| Да |   Необязательно |   Нет|
|**[Прямое подключение USB](#USB-Direct)**| Нет |    Нет  | Нет|

**Методы регистрации Windows и Android**

| **Метод** |  **[Очистка](#Wipe)** | **[Сходство](#Affinity)**   |   **[Заблокировано](#Lock)** |
|:---:|:---:|:---:|:---:|
|**[BYOD](#BYOD)** | Нет|    Да |   Нет |
|**[DEM](#DEM)**|   Нет |Нет |Нет  |

**Методы регистрации корпоративных устройств**

### BYOD
"Принеси свое устройство". Пользователи устанавливают приложение корпоративного портала и регистрируют свое устройство. При регистрации устройства с помощью корпоративного портала оно будет присоединено к рабочему месту. Для регистрации устройств iOS с помощью корпоративного портала требуется идентификатор Apple. Для корпоративных BYOD-устройств дополнительной настройки не требуется. См. статью [Настройка управления устройствами](get-ready-to-enroll-devices-in-microsoft-intune.md#set-up-device-management). ([Вернуться к таблице](#overview-of-device-enrollment-methods))

### DEM
Диспетчер регистрации устройств. Администратор создает учетные записи диспетчера регистрации устройств для управления корпоративными устройствами. Затем менеджеры могут установить корпоративный портал и зарегистрировать многие устройства без пользователей. Ознакомьтесь с дополнительными сведениями о [DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md). ([Вернуться к таблице](#overview-of-device-enrollment-methods))

### DEP
Программа регистрации устройств Apple. Администратор создает и развертывает политику "по воздуху" для корпоративных устройств iOS, приобретенных и управляемых с помощью DEP. Устройство регистрируется, когда пользователь запускает помощник по настройке на устройстве iOS. Этот метод поддерживает **контролируемый режим iOS**, который, в свою очередь, обладает следующими характеристиками:
  - Блокировка регистрации
  - Условный доступ
  - Обнаружение снятия защиты
  - Управление мобильными приложениями

Ознакомьтесь с дополнительными сведениями о [DEP](ios-device-enrollment-program-in-microsoft-intune.md). ([Вернуться к таблице](#overview-of-device-enrollment-methods))

### USB-SA
Регистрация с помощником по установке и с подключением USB. Администратор создает политику Intune и экспортирует ее в Apple Configurator. Подключенные по USB корпоративные устройства подготавливаются с помощью политики Intune. Администратор должен зарегистрировать каждое устройство вручную. Пользователи получают свои устройства и запускают помощник по настройке, регистрирующий их устройства. Этот метод поддерживает **контролируемый режим iOS**, который, в свою очередь, обладает следующими характеристиками:
  - Условный доступ
  - Обнаружение снятия защиты
  - Управление мобильными приложениями

Ознакомьтесь с дополнительными сведениями о [Помощнике по настройке регистрации с Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md). ([Вернуться к таблице](#overview-of-device-enrollment-methods))

### Прямое подключение USB
Прямая регистрация Администратор создает политику Intune и экспортирует ее в Apple Configurator. Подключенные по USB корпоративные устройства регистрируются напрямую без необходимости сброса до заводских настроек. Администратор должен зарегистрировать каждое устройство вручную. Устройства управляются как устройства без пользователя. Они не заблокированы и не контролируются, а также не поддерживают условный доступ, обнаружение снятия защиты и управление мобильными приложениями. Ознакомьтесь с дополнительными сведениями о [прямой регистрации с Apple Configurator](ios-direct-enrollment-in-microsoft-intune.md). ([Вернуться к таблице](#overview-of-device-enrollment-methods))

**Поведение корпоративных мобильных устройств**

### Очистка
Указывает, необходим ли для регистрации устройства сброс до заводских установок, при котором удаляются все данные устройства и оно возвращается в первоначальное состояние.
[Снятие устройств с учета](retire-devices-from-microsoft-intune-management.md) ([Вернуться к таблице](#overview-of-device-enrollment-methods))

### Сходство
Указывает, поддерживает ли метод регистрации "Сопоставление пользователей", при котором устройство связывается с конкретным пользователем. "Необязательные" устройства могут быть зарегистрированы независимо от сопоставления пользователей. Сопоставление пользователей необходимо для поддержки следующих функций:
  - Приложения MAM
  - Условный доступ к корпоративной электронной почте и данным
  - Приложение корпоративного портала

[Сходство пользователей](enroll-corporate-owned-ios-devices-in-microsoft-intune.md#using-company-portal-on-dep-or-apple-configurator-enrolled-devices) ([Вернуться к таблице](#overview-of-device-enrollment-methods))

### Блокировка
Указывает, можно ли заблокировать устройство для предотвращения удаления политики Intune. При этом устройство по существу исключается из управления. Для блокировки устройства iOS оно должно находиться в контролируемом режиме.
([Вернуться к таблице](#overview-of-device-enrollment-methods))

## Обеспечение регистрации устройств  
 Регистрация позволяет пользователям получать доступ к ресурсам организации с личных устройств, а администраторам — обеспечивать соответствие этих устройств политикам защиты ресурсов организации. Это лучший способ реализации сценариев "Принеси свое устройство" с помощью Intune. Администратору необходимо включить регистрацию в консоли Intune, для чего может потребоваться установить отношение доверия с устройством и назначить лицензии пользователям. Затем устройство регистрируется, обычно пользователем, который вводит для этого свои рабочие или учебные учетные данные. После этого устройство принимает параметры политики из Intune и получает доступ к ресурсам.

[Подготовка к регистрации устройств в Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)

## Регистрация устройств, принадлежащих организации
Принадлежащими организации устройствами можно управлять с помощью консоли Intune. Устройства iOS можно регистрировать напрямую с помощью средств, предоставляемых компанией Apple. Администратор или руководитель может регистрировать устройства любых типов с помощью диспетчера регистрации устройств. Устройства с номерами IMEI также могут определяться и помечаться как принадлежащие организации для реализации этого сценария.

[Регистрация устройств, принадлежащих организации](manage-corporate-owned-devices.md)

## Управление мобильными устройствами с помощью Exchange ActiveSync и Intune
Мобильные устройства, которые не зарегистрированы, но подключены к Exchange ActiveSync, могут управляться службой Intune с помощью политики управления мобильными устройствами Exchange ActiveSync. Intune использует соединитель Exchange для взаимодействия с локальной или размещенной в облаке службой Exchange ActiveSync.

[Управление мобильными устройствами с помощью Exchange ActiveSync и Intune](mobile-device-management-with-exchange-activesync-and-microsoft-intune.md)


## Управление ПК под управлением Windows с помощью Intune  
Кроме того, Microsoft Intune можно использовать для управления компьютерами с ОС Windows с помощью клиентского ПО Intune для Windows. Компьютеры под управлением клиента Intune могут:

 - предоставлять отчеты по инвентаризации программного обеспечения и оборудования;
 - устанавливать классические приложения (например, файлы EXE и MSI).
 - Параметры брандмауэра

Компьютеры под управлением клиентского ПО Intune нельзя избирательно очищать и снимать с учета. Кроме того, им недоступно множество функций управления Intune, таких как условный доступ, параметры VPN и Wi-Fi, а также развертывание сертификатов и конфигураций электронной почты.

[Управление ПК под управлением Windows с помощью Intune](manage-windows-pcs-with-microsoft-intune.md)



<!--HONumber=Aug16_HO3-->

