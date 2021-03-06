---
title: "Управление Магазином Windows для бизнес-приложений | Microsoft Intune"
description: "Сведения о подключении Microsoft Intune к Магазину Windows для бизнеса для развертывания приложений, приобретенных по программе корпоративных закупок, и управления ими в консоли Intune"
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8e38d47d-0c5e-40ce-b379-29d3657f5c28
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c880bd9dfb998355a18e78af898a96d4cee393f7
ms.openlocfilehash: 8eee27e0c24e353143ce2014b65dc91af2c04843


---

# Управление приложениями, приобретенными в Магазине Windows для бизнеса, с помощью Microsoft Intune
[Магазин Windows для бизнеса](https://www.microsoft.com/business-store) позволяет находить и приобретать приложения для вашей организации по отдельности или в рамках корпоративной программы. Подключив хранилище к Microsoft Intune, вы можете управлять приложениями, приобретенными по корпоративной программе, из консоли Intune. Пример.
* можно синхронизировать список приобретенных приложений с Intune;
* синхронизированные приложения отображаются в консоли Intune и могут быть развернуты обычным образом;
* можно отслеживать количество доступных и используемых лицензий в консоли администрирования Intune;
* Intune блокирует развертывание и установку приложений при отсутствии достаточного количества лицензий.

## Перед началом работы
Перед началом синхронизации и развертывания приложений из Магазина Windows для бизнеса, ознакомьтесь со приведенными далее сведениями.
* Необходимо настроить Intune в качестве центра управления мобильными устройствами для вашей организации. Дополнительные сведения см. в разделе [Предварительные требования для регистрации устройств в Microsoft Intune](prerequisites-for-enrollment.md).
* Необходимо иметь действительную учетную запись Магазина Windows для бизнеса.
* После привязки учетной записи Магазина Windows для бизнеса к Intune вы не сможете выбрать другую учетную запись в будущем.
* Приобретенные в Магазине приложения нельзя вручную добавить или удалить в Intune. Их можно только синхронизировать с Магазином Windows для бизнеса.
* Intune синхронизирует только приложения, лицензированные для Интернета, приобретенные в Магазине Windows для бизнеса.
* Для использования этой возможности устройства должны быть присоединены к доменным службам Active Directory или к рабочему месту.
* Зарегистрированные устройства должны использовать выпуск 1511 Windows 10.

## Связывание учетной записи Магазина Windows для бизнеса с Intune
Перед включением синхронизации в консоли Intune необходимо настроить учетную запись хранения для использования Intune в качестве средства управления.
1. Вход в Магазин для бизнеса следует выполнить по той же учетной записи клиента, которая используется для входа в Intune.
2. В Магазине для бизнеса выберите **Параметры** > **Средства управления**.
3. На странице "Средства управления" используйте команду **Добавить средство управления** и выберите **Microsoft Intune**.

Теперь можно настроить синхронизацию в консоли Intune.

## Настройка синхронизации

1. В [консоли администрирования Microsoft Intune](https://manage.microsoft.com) выберите **Администрирование**.
2. В рабочей области **Администрирование** разверните узел **Управление мобильными устройствами**, а затем выберите элемент **Магазин для бизнеса**.
3. На странице **Магазин Windows для бизнеса** выполните следующие действия.
 * Если вы еще не сделали это, щелкните ссылку, чтобы зарегистрироваться в Магазине Windows для бизнеса.
 * После регистрации щелкните **Настройка синхронизации**.
4. В диалоговом окне **Настройка синхронизации для приложений Магазина Windows для бизнеса** выберите **Включить синхронизацию Магазина Windows для бизнеса**.
5. В раскрывающемся списке **Язык** выберите язык, на котором приложения из Магазина Windows для бизнеса будут отображаться в консоли Intune. Независимо от языка, на котором они отображаются, их установка осуществляется на языке конечного пользователя (если доступно).
6. Нажмите кнопку **ОК**.

## Синхронизация приложений

1. На странице **Магазин Windows для бизнеса** выберите команду **Синхронизировать**, чтобы синхронизировать приобретенные приложения с Intune.
2. В рабочей области **Приложения** выберите пункты **Управляемое программное обеспечение** > **Лицензированное программное обеспечение** для просмотра доступных приложений и проверки правильности импорта приобретенных приложений. Приложения в этом узле отображаются с числом приобретенных и доступных лицензий.

## Развертывание приложений

Развертывание приложений производится точно так же, как и любого другого приложения Intune. Дополнительные сведения см. в статье [Развертывание приложений в Microsoft Intune](deploy-apps-in-microsoft-intune.md).
При развертывании приложения Магазина Windows для бизнеса на каждого пользователя, который его устанавливает, расходуется отдельная лицензия. Если использованы все доступные лицензии для развернутого приложения, вы не сможете развернуть дополнительные копии и потребуется одно из следующих действий.
* Удалите приложение с некоторых устройств.
* Сократите область текущего развертывания, чтобы охватить только то число пользователей, на которое хватает лицензий.
* Приобретите дополнительные копии приложения из Магазина Windows для бизнеса.

> [!Important]
> Развернутые приложения доступны только для пользователя, который изначально зарегистрировал соответствующее устройство. Для других пользователей приложение недоступно.


### См. также
[Добавление приложений для мобильных устройств в Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md)



<!--HONumber=Sep16_HO4-->


