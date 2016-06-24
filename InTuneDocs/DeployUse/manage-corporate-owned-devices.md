---
# required metadata

title: Управление корпоративными устройствами | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2b60bbff-25e6-489b-9621-c71b4275fa06

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Регистрация корпоративных устройств в Microsoft Intune
В Intune существует множество разных способов управления корпоративными устройствами (COD), которые зависят от типа устройства, способа его приобретения и потребностей организации.

## Корпоративные устройства iOS
Эти методы регистрации оптимально подходят для сценариев с выбором собственных устройств (CYOD), когда организация приобретает устройства для пользователей, но хочет сохранить управление этими устройствами. Если организация приобрела устройства iOS, можно предварительно настроить регистрацию так, чтобы управление устройством начиналось с момента его первого включения пользователем. Служба Intune поддерживает регистрацию устройств с помощью [ программы регистрации устройств Apple (DEP)](ios-device-enrollment-program-in-microsoft-intune.md) или средства Apple Configurator на компьютере Mac для [прямой](ios-direct-enrollment-in-microsoft-intune.md) регистрации или регистрации с использованием [помощника по настройке](ios-setup-assistant-enrollment-in-microsoft-intune.md).

[Регистрация корпоративных устройств iOS](enroll-corporate-owned-ios-devices-in-microsoft-intune.md)

## Диспетчер регистрации устройств
Организации могут использовать Intune для управления большим количеством мобильных устройств с помощью одной учетной записи пользователя, которая называется учетной записью диспетчера регистрации устройств. Менеджер может использовать созданную учетную запись диспетчера регистрации устройств для регистрации устройств, количество которых превышает стандартные пять устройств, разрешенных по умолчанию для обычных пользователей. Регистрация устройств с помощью диспетчера регистрации действует только для устройств, не используемых конкретным пользователем. Эти устройства хорошо подходят для приложений в сфере розничной торговли или коммунального обслуживания, но являются неприемлемым вариантом для доступа к электронной почте или корпоративным ресурсам.

[Регистрация корпоративных устройств с помощью диспетчера регистрации устройств](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)

## Международный идентификатор мобильного оборудования (IMEI)
Уникальные номера IMEI являются общим свойством устройств для многих производителей мобильных устройств. Администраторы Intune могут импортировать номера IMEI для принадлежащих организации устройств. Когда устройство попадает под управление Intune, его можно пометить как корпоративное и применить к нему соответствующую политику.

[Указание корпоративных устройств по номерам IMEI](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

## Общие сведения о методах регистрации корпоративных устройств

В следующей таблице приведены методы регистрации корпоративных устройств и их преимущества.

**Методы регистрации в iOS**

| **Метод** |  **[Сброс](#Reset)** |   **[Сходство](#Affinity)**   |   **[Заблокировано](#Locked)** |
|:---:|:---:|:---:|:---:|
|**[BYOD](#BYOD)** | Нет|    Да |   Нет |
|**[DEM](#DEM)**|   Нет |Нет |Нет  |
|**[DEP](#DEP)**|   Да |   Необязательно |   Необязательно|
|**[USB-SA](#USB-SA)**| Да |   Необязательно |   Нет|
|**[Прямое подключение USB](#USB-Direct)**| Нет |    Нет  | Нет|

**Методы регистрации Windows и Android**

| **Метод** |  **[Очистка](#Wipe)** | **[User (Пользователь)](#User)**   |   **[Заблокировано](#Locked)** |
|:---:|:---:|:---:|:---:|
|**[BYOD](#BYOD)** | Нет|    Да |   Нет |
|**[DEM](#DEM)**|   Нет |Нет |Нет  |

**Методы регистрации корпоративных устройств**

### BYOD
"Принеси свое устройство". Пользователи устанавливают приложение корпоративного портала и регистрируют свое устройство. При регистрации устройства с помощью корпоративного портала оно будет присоединено к рабочему месту. Для регистрации устройств iOS с помощью корпоративного портала требуется идентификатор Apple. Для корпоративных BYOD-устройств дополнительной настройки не требуется. См. [Настройка управления устройствами](get-ready-to-enroll-devices-in-microsoft-intune#set-up-device-management.md). ([Вернуться к таблице](#overview-of corporate-owned-device-enrollment-methods))

### DEM
Диспетчер регистрации устройств. Администратор создает учетные записи DEM. Затем менеджеры могут установить корпоративный портал и зарегистрировать многие устройства без пользователей. Ознакомьтесь с дополнительными сведениями о [DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md). ([Вернуться к таблице](#overview-of corporate-owned-device-enrollment-methods))

### DEP
Программа регистрации устройств Apple. Администратор создает и развертывает политику "по воздуху" для устройств iOS, приобретенных и управляемых с помощью DEP. Устройство регистрируется, когда пользователь запускает помощник по настройке на устройстве iOS. Этот метод поддерживает **контролируемый режим iOS**, который, в свою очередь, обладает следующими характеристиками:
  - Блокировка регистрации
  - Условный доступ
  - Обнаружение снятия защиты
  - Управление мобильными приложениями

Ознакомьтесь с дополнительными сведениями о [DEP](ios-device-enrollment-program-in-microsoft-intune.md). ([Вернуться к таблице](#overview-of corporate-owned-device-enrollment-methods))

### USB-SA
Регистрация с помощником по установке и с подключением USB. Администратор создает политику Intune и экспортирует ее в Apple Configurator. Подключенные по USB устройства подготавливаются с помощью политики Intune. Администратор должен зарегистрировать каждое устройство вручную. Пользователи получают свои устройства и запускают помощник по настройке, регистрирующий их устройства. Этот метод поддерживает **контролируемый режим iOS**, который, в свою очередь, обладает следующими характеристиками:
  - Условный доступ
  - Обнаружение снятия защиты
  - Управление мобильными приложениями

Ознакомьтесь с дополнительными сведениями о [Помощнике по настройке регистрации с Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md). ([Вернуться к таблице](#overview-of corporate-owned-device-enrollment-methods))

### Прямое подключение USB
Прямая регистрация Администратор создает политику Intune и экспортирует ее в Apple Configurator. Подключенные по USB устройства регистрируются напрямую без необходимости сброса до заводских настроек. Администратор должен зарегистрировать каждое устройство вручную. Устройства управляются как устройства без пользователя. Они не заблокированы и не контролируются, а также не поддерживают условный доступ, обнаружение снятия защиты и управление мобильными приложениями. Ознакомьтесь с дополнительными сведениями о [прямой регистрации с Apple Configurator](ios-direct-enrollment-in-microsoft-intune.md). ([Вернуться к таблице](#overview-of corporate-owned-device-enrollment-methods))

**Поведение корпоративных мобильных устройств**

### Сброс
Указывает, необходим ли для регистрации устройства сброс до заводских установок, при котором удаляются все данные устройства и оно возвращается в первоначальное состояние.
([Вернуться к таблице](#overview-of corporate-owned-device-enrollment-methods))

### Сходство
Указывает, поддерживает ли метод регистрации "Сопоставление пользователей", при котором устройство связывается с конкретным пользователем. "Необязательные" устройства могут быть зарегистрированы независимо от сопоставления пользователей. Сопоставление пользователей необходимо для поддержки следующих функций:
  - Приложения MAM
  - Условный доступ к корпоративной электронной почте и данным
  - Приложение корпоративного портала

([Вернуться к таблице](#overview-of corporate-owned-device-enrollment-methods))

### Блокировка
Указывает, можно ли заблокировать устройство для предотвращения удаления политики Intune. При этом устройство по существу исключается из управления. Для блокировки устройства iOS оно должно находиться в контролируемом режиме.
([Вернуться к таблице](#overview-of corporate-owned-device-enrollment-methods)) ([Вернуться к таблице](#overview-of corporate-owned-device-enrollment-methods))


<!--HONumber=Jun16_HO3-->

