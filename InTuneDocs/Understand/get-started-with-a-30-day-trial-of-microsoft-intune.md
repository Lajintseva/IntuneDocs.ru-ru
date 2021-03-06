---
title: "Руководство по оценке Intune | Microsoft Intune"
description: "Общие сведения о настройке бесплатной 30-дневной ознакомительной версии Intune и предварительные требования"
keywords: 
author: lindavr
manager: angrobe
ms.date: 08/09/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 619a1d11-3d22-4635-8f70-770eba3e1712
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 51fba2b01d8978bc062c50c4388714609be0fdf0
ms.openlocfilehash: cbf863619a385d596630ee4ff0b216a4cbbe6cb7


---

# Руководство по оценке Intune
Настройка бесплатной 30-дневной ознакомительной версии Intune для управления мобильными устройствами и компьютерами выполняется быстро и просто. С помощью нескольких простых шагов в ознакомительной версии вы можете добавить до 100 пользователей и устройств, настроить группы, политики соответствия и зарегистрировать мобильные устройства и компьютеры, а также управлять ими.

В этом разделе вы научитесь основам запуска ознакомительной версии Intune и получите общие сведения о службе, чтобы оценить функции и возможности Intune.

Посмотрите следующее пятиминутное демонстрационное видео, чтобы узнать, как легко начать работу с бесплатной ознакомительной версией Microsoft Intune и управлять устройствами. В первой части видео упоминается портал, который был удален. Однако несмотря на то, что будет использоваться другой портал, действия будут одинаковыми. Подробнее об этом портале можно прочитать [здесь](https://docs.microsoft.com/intune/deploy-use/account-portal-merged-with-Office-365).

<iframe width="675" height="480" src="https://www.youtube.com/embed/ltcZvm4VOFU" frameborder="0" allowfullscreen></iframe>

## Подготовка к работе
Для начала работы с Intune вам потребуется следующее.

-   Устройство с браузером, поддерживающим Silverlight, которое можно использовать для доступа к веб-сайтам, где создаются учетные записи пользователя Intune (**Центр администрирования Office 365**) и где вы управляете устройствами, группами и политиками (**консоль администрирования Intune**).

-   Второе устройство с браузером, которое будет использоваться для тестирования того, как пользователи Intune будут регистрировать устройства и управлять ими с помощью корпоративного портала. Вы также сможете протестировать, как пользователи найдут и установят приложения и запросят помощь у администраторов. Если у вас нет второго устройства, можно использовать параметр "Режим конфиденциальности" в том же браузере, который применяется для администрирования Intune (например, в Internet Explorer можно выбрать **Сервис** &gt; **Просмотр InPrivate**).

-   Если у вас есть учетная запись Microsoft Online Services, для нее потребуется получить учетные данные администратора клиента. Вам это не требуется, если у вас нет такой учетной записи или вы используете клиент Intune только для оценки.

-   Если управление устройствами iOS или Windows Phone осуществляется с помощью ознакомительной версии Intune, вам понадобятся сертификаты (или ключи) и учетные записи для получения этих сертификатов (см. таблицу ниже). Устройствам Android не требуются дополнительные сертификаты.

    |Платформа|Требования к сертификатам|Дополнительные сведения|
    |------------|----------------------------|--------------------|
    |Windows Phone 8.1 и Windows Phone 8 |Пользователи Windows Phone 8.1, устанавливающие приложение корпоративного портала из Магазина, не нуждаются в сертификате. Сертификат Symantec необходим для Windows Phone 8.0 или при использовании Intune для развертывания приложения корпоративного портала на устройствах Windows Phone 8.1.|В этом руководстве предполагается, что пользователи получают приложение корпоративного портала в Магазине Windows Phone 8.1 или на более поздней версии устройства. Сведения о поддержке Windows Phone 8.0 см. в разделе [Настройка управления Windows Phone с помощью Microsoft Intune](/Intune/Deploy-Use/set-up-windows-phone-management-with-microsoft-intune).|
    |Устройства с Windows 10, Windows RT 8.1, Windows RT или Windows 8.1|Требования к сертификатам для регистрации устройств Windows RT и Windows отсутствуют.|[Установка клиента на компьютере Windows с помощью Microsoft Intune](/Intune/Deploy-Use/install-the-windows-pc-client-with-microsoft-intune).|
    |iOS 7.1 или более поздней версии|Получите сертификат службы уведомлений Apple Push.|Запросите сертификат службы push-уведомлений Apple у Apple, как описано здесь: [Настройка управления устройствами iOS и Mac с помощью Microsoft Intune](/Intune/Deploy-Use/set-up-ios-and-mac-management-with-microsoft-intune).|

## Действия по настройке 30-дневной ознакомительной версии Intune
- [Шаг 1. Войдите в 30-дневную ознакомительную версию или зарегистрируйтесь для ее получения](get-started-with-a-30-day-trial-of-microsoft-intune-step-1.md). Прежде чем регистрироваться или входить в Intune, следует решить, будете ли вы выполнять вход с помощью существующей учетной записи или создадите временную учетную запись, которая будет применяться только в течение 30-дневного периода ознакомительного использования Microsoft Intune.
- [Шаг 2. Добавьте пользователей](get-started-with-a-30-day-trial-of-microsoft-intune-step-2.md). Теперь, когда вы настроили учетную запись, вы можете либо добавить отдельные учетные записи пользователей в Intune, либо добавить группы пользователей (см. инструкции в этом разделе). Перед началом работы важно понять, как Intune обрабатывает учетные записи администратора.
- [Шаг 3. Создайте группы для организации пользователей и устройств](get-started-with-a-30-day-trial-of-microsoft-intune-step-3.md). Группы в Intune обеспечивают гибкость управления устройствами и пользователями. Можно настроить группы в соответствии с потребностями организации (например, по географическому положению, отделам или характеристикам оборудования) и использовать их для выполнения разнообразных административных задач в масштабе, от развертывания политики для группы пользователей до развертывания приложений на наборе устройств.
- [Шаг 4. Создайте политики и опубликуйте приложение](get-started-with-a-30-day-trial-of-microsoft-intune-step-4.md). Политики Intune предоставляют параметры, позволяющие контролировать безопасность на мобильных устройствах, поддерживать параметры брандмауэра Windows и Endpoint Protection для компьютеров и развертывать приложения.
- [Шаг 5. Зарегистрируйте мобильные устройства и установите приложение](get-started-with-a-30-day-trial-of-microsoft-intune-step-5.md). Чтобы настроить управление мобильными устройствами с помощью Intune, необходимо задать центр управления мобильными устройствами, включить управление для определенных платформ устройств, а затем зарегистрировать устройства с помощью приложения корпоративного портала. Затем можно развернуть опубликованное приложение Microsoft Skype.
- [Шаг 6. Другие параметры и дополнения](get-started-with-a-30-day-trial-of-microsoft-intune-step-6.md). Выберите способы использования оповещений, отчетов и других возможностей Intune в соответствии с потребностями бизнеса.
- [Шаг 7. Дальнейшие действия](get-started-with-a-30-day-trial-of-microsoft-intune-step-7.md). Подготовьтесь к переходу на платную подписку на Intune и воспользуйтесь преимуществом FastTrack Center для Intune.


### Дальнейшие действия
Пришло время приступить к использованию 30-дневной ознакомительной подписки!

>[!div class="step-by-step"]
[**Регистрация в Intune** &rarr;](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-1.md)

### См. также
[Краткое руководство по Intune](/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune)



<!--HONumber=Aug16_HO2-->


