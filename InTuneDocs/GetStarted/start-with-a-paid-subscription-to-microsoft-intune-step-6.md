---
title: "Создание политик и публикация приложения | Microsoft Intune"
description: "Описывается, как создать политики и опубликовать пример приложения для подписки Intune."
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e0d8e98f-7dd8-4cbf-887c-a9af63ffe970
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2a192c71b1b82f59b34ea614d09d895174f8112b
ms.openlocfilehash: 539df37b239f61ab31e5994db00b46a9d5b6310c


---

# Создание политик и публикация приложения
Политики Intune предоставляют параметры, позволяющие контролировать безопасность на мобильных устройствах, поддерживать параметры брандмауэра Windows и Endpoint Protection для компьютеров и развертывать приложения. Дополнительные сведения см. в статьях [Управление параметрами и компонентами на устройствах с помощью политик Microsoft Intune](/Intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) и [Обеспечение защиты компьютеров с ОС Windows с помощью Endpoint Protection для Microsoft Intune](/Intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune).

Можно использовать два вида установки приложения с помощью Intune. Первый — **обязательная установка**, которая автоматически развертывает приложение на управляемых компьютерах. Второе — **доступная установка**, которая развертывает приложение или ссылку на приложение на корпоративном портале Intune, чтобы пользователи могли выбрать необходимость установки на своих компьютерах или мобильных устройствах.

Приведенные ниже шаги посвящены настройке политики конфигурации мобильного устройства и политики брандмауэра Windows для компьютера, а также настройке Skype в качестве доступной установки для мобильных устройств после их регистрации.

> [!TIP]
> После добавления и развертывания новой политики все пользователи и устройства в группе, в которой развернута политика, наследуют параметры как базовую политику. Всегда можно просмотреть и изменить сведения о политиках позже в рабочей области «Политика».


## Создание и развертывание политики конфигурации мобильного устройства

1.  Откройте [консоль администрирования Intune](https://manage.microsoft.com/).

2.  На левой панели щелкните значок **Политика**.

    ![admin-console-policy-workspace](./media/policy.png)

3.  На странице **Обзор политики** в списке **Задачи** выберите команду **Добавить политику**.

4.  В списке политик разверните платформу, для которой необходимо создать политику, а затем выберите пункты **Общая конфигурация** > **Создание и развертывание политики с рекомендуемыми параметрами** > **Создать политику**.

> [!NOTE]
> Для политик конфигурации устройств не предусмотрены рекомендуемые параметры, так как на выбор предоставляется множество параметров. Необходимо создать пользовательскую политику конфигурации устройств.


5.  При появлении запроса **Выберите группы для развертывания этой политики** выберите группу из списка доступных групп и нажмите **Добавить** > **ОК**.

Политика развертывается в группе **Пользователи Intune** и отображается в списке политик конфигурации. Дважды щелкните политику, чтобы просмотреть ее параметры.

## Публикация приложения Skype для мобильных устройств

1.  В [консоли администрирования Intune](https://manage.microsoft.com/) щелкните значок **Приложения** и выберите **Приложения** > **Добавить приложение**. Если необходимо, введите свои учетные данные [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

    ![admin-console-apps-workspace](./media/apps.png)

    > [!NOTE]
    > При первом запуске **издателя программного обеспечения Intune** происходит небольшая задержка, необходимая для установки приложения.

2.  Просмотрите предупреждение безопасности и нажмите кнопку **Выполнить**.

3.  На странице **Перед началом работы** нажмите кнопку **Далее**.

4.  На странице **Установка ПО** в разделе **Выберите, как программа будет доступна для устройств** выберите пункт **Внешняя ссылка**.

5.  Введите внешнюю ссылку в поле **Укажите URL-адрес**, а затем нажмите кнопку **Далее**. Убедитесь, что в начале URL-адреса стоит **http://**. Для приложения Skype используйте следующую ссылку, соответствующую используемой платформе мобильных устройств:

    -   **iOS:**   [https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8](https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8)

    -   **Android:**  [https://play.google.com/store/apps/details?id=com.skype.raider](https://play.google.com/store/apps/details?id=com.skype.raider)

    -   **Windows Phone 8 или Windows Phone 8.1:**  [http://www.windowsphone.com/en-us/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51](http://www.windowsphone.com/en-us/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51)

6.  На странице **Описание ПО** укажите информацию о программном обеспечении, которая будет отображаться на корпоративном портале, а затем нажмите кнопку **Далее**. Доступны следующие параметры (этот пример относится к Skype):

    -   **Издатель:** Введите имя издателя: «Microsoft».

    -   **Имя.** Введите **Skype**

    -   **Описание:** Введите описание программного обеспечения, например **Приложение для связи Skype**

    -   **Категория:** Выберите категорию, которая оптимально подходит для этой программы, например **Совместная работа**

    -   **Отображать это приложение как рекомендуемое и выделить его на портале организации:** установите этот флажок, чтобы приложение отображалось на видном месте корпоративного портала на мобильных устройствах.

    -   **Значок**: выберите, следует ли связать значок с программным обеспечением. Максимальный размер для необязательного значка составляет 250 x 250 пикселей, а рекомендуемый размер — 32 x 32 пикселя.

7.  На странице **Сводка** проверьте сведения о программном обеспечении, а затем нажмите кнопку **Отправить**. Чтобы выйти из мастера, нажмите кнопку **Закрыть**.

8.  В [консоли администрирования Intune](https://manage.microsoft.com/) последовательно выберите **Приложения** > **Приложения** > **Skype** > **Управление развертыванием**.

9. На странице **Выберите группы** выберите **Пользователи Intune**, чтобы развернуть программное обеспечение для этой группы пользователей, а затем нажмите кнопки **Добавить** > **Далее**.

10. На странице **Действие развертывания** выберите пункт **Доступная установка** в столбце **Утверждение** для своей группы.

11. Нажмите кнопку **Готово**.

Приложение Skype теперь доступно для установки на мобильных устройствах с корпоративного портала, но сначала необходимо установить [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] на компьютерах и мобильных устройствах.


### Дальнейшие действия
Поздравляем! Вы завершили шаг 6 *краткого руководства по Intune*.

>[!div class="step-by-step"]

>[&larr; **Организация пользователей и устройств**](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)       [**Настройка корпоративного портала** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-7.md)  



<!--HONumber=Jul16_HO4-->

