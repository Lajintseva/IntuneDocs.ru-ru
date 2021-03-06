---
title: "Использование политик конфигурации мобильных приложений iOS | Microsoft Intune"
description: "Используйте политики конфигурации мобильных приложений в Intune для предоставления параметров, которые могут быть необходимы, когда пользователи работают с приложением iOS."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 09/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fc6b645a-e837-4b2a-a10f-144065cbd8dd
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 360865bcd97230e264ee3439407e8dd3017d0055
ms.openlocfilehash: 1f239270c26a70b161e52c24e94ca5c2cae9ca3a


---

# Настройка приложений iOS с помощью политик конфигурации мобильных приложений в Microsoft Intune
Используйте политики конфигурации мобильных приложений в Microsoft Intune для предоставления параметров, которые могут быть необходимы, когда пользователи работают с приложением iOS. Например, приложение может потребовать от пользователей указать:

-   пользовательский номер порта;

-   языковые параметры;

-   параметры безопасности;

-   параметры фирменной символики, такие как эмблема компании.

Если пользователи неправильно вводят эти параметры, это может увеличить нагрузку на службу поддержки и замедлить внедрение новых приложений.

Политики конфигурации мобильных приложений помогут устранить эти проблемы, позволяя развертывать эти параметры для пользователей в политике перед запуском приложения. Параметры затем заполняются автоматически, и пользователям не нужно выполнять никаких действий.

Эти политики не развертываются непосредственно для пользователей и устройств. Они связываются с приложением, которое впоследствии развертывается. Параметры политики будут использоваться каждый раз, когда приложение проверяет их наличие (как правило, при первом запуске).

> [!TIP]
> Такой тип политики в настоящее время доступен только устройствам под управлением iOS 8.0 и более поздних версий. Он поддерживает следующие типы установки приложения:
>
> -   **Управляемое приложение iOS из магазина приложений**
> -   **Пакет приложений для iOS**
>
> Дополнительные сведения о типах установки приложений см. в разделе [Развертывание приложений в Microsoft Intune](deploy-apps.md).

## Настройка политики конфигурации мобильных приложений

1.  В [консоли администрирования Microsoft Intune](https://manage.microsoft.com) последовательно выберите **Политика** &gt; **Обзор** &gt; **Добавить политику**.

2.  В списке политик разверните узел **iOS**, выберите **Настройка мобильного приложения** и нажмите кнопку **Создать политику**.

    > [!TIP]
    > Для этого типа политики можно настроить только пользовательские параметры. Рекомендуемые параметры недоступны.

3.  В разделе **Общие** страницы **Создание политики** введите имя и необязательное описание политики настройки мобильного приложения.

4.  В разделе **Политика настройки мобильного приложения** введите или вставьте в поле список свойств XML, содержащий необходимые параметры конфигурации приложения. Формат списка свойств XML будет зависеть от настраиваемого приложения. Обратитесь к поставщику приложения для получения сведений о необходимом формате.

    > [!TIP]
    > Подробнее о списках свойств XML см. в статье [Общие сведения о списках свойств XML](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) в библиотеке разработчика iOS.

5.  Нажмите кнопку **Проверить**, чтобы проверить формат введенного списка свойств XML.

    > [!IMPORTANT]
    > При нажатии кнопки **Проверить** Intune проверяет, введены ли данные XML в допустимом формате. Программа не проверяет, будет ли список свойств XML работать со связанным приложением.

6.  По завершении щелкните элемент **Сохранить политику**.

Новая политика отображается в узле **Политики конфигурации** .

## Сведения о формате XML-файла

Intune поддерживает следующие типы данных в списке свойств:
    
- &lt;целое число&gt;
- &lt;real&gt;
- &lt;строка&gt;
- &lt;array&gt;
- &lt;dict&gt;
- &lt;true /&gt; или &lt;false /&gt;
     
Подробнее о типах данных см. в разделе [Сведения о списках свойств](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/AboutPropertyLists/AboutPropertyLists.html) в библиотеке разработчика iOS.

Кроме того, Intune поддерживает следующие типы токенов в списке свойств:
- \{\{userprincipalname\}\} — (пример: **ilya@contoso.com**);
- \{\{mail\}\} — (пример: **ilya@contoso.com**);
- \{\{partialupn\}\} — (пример: **Ilya**);
- \{\{accountid\}\} — (пример: **fc0dc142-71d8-4b12-bbea-bae2a8514c81**);
- \{\{deviceid\}\} — (пример: **b9841cd9-9843-405f-be28-b2265c59ef97**);
- \{\{userid\}\} — (пример: **3ec2c00f-b125-4519-acf0-302ac3761822**);
- \{\{username\}\} — (пример: **Илья Глазков**);
- \{\{serialnumber\}\} — (пример: **F4KN99ZUG5V2**) для устройств iOS;
- \{\{serialnumberlast4digits\}\} — (пример: **G5V2**) для устройств iOS.
    
Символы \{\{ и \}\} используются только для типов маркеров и не должны применяться в других целях.

## Сопоставление политики конфигурации мобильных приложений с приложением
После создания политики конфигурации мобильных приложений необходимо связать ее с приложением iOS, к которому она должна применяться.

Для этого выполните действия по созданию развертывания приложения, как описано в разделах [Добавление приложений для зарегистрированных устройств в Intune](add-apps-for-mobile-devices-in-microsoft-intune.md) и [Развертывание приложений с помощью Microsoft Intune](deploy-apps-in-microsoft-intune.md). Когда вы перейдете на страницу мастера **Настройка мобильного приложения**, выберите политику, которую требуется связать с приложением, из раскрывающегося списка **Политика настройки приложения**.

Продолжайте развертывание и отслеживайте его в обычном режиме.

При запуске развернутого приложения на устройстве будут применяться параметры, настроенные в политике конфигурации.

> [!TIP]
> В случае конфликта одной или нескольких политик конфигурации ни одна из них не будет применяться принудительно. О конфликте появится сообщение на **панели мониторинга** консоли администрирования Intune.

## Пример формата для XML-файла конфигурации мобильного приложения

При создании файла конфигурации мобильного приложения можно указать одно или несколько следующих значений в данном формате:

```
<dict>
  <key>userprincipalname</key>
  <string>{{userprincipalname}}</string>
  <key>mail</key>
  <string>{{mail}}</string>
  <key>partialupn</key>
  <string>{{partialupn}}</string>
  <key>accountid</key>
  <string>{{accountid}}</string>
  <key>deviceid</key>
  <string>{{deviceid}}</string>
  <key>userid</key>
  <string>{{userid}}</string>
  <key>username</key>
  <string>{{username}}</string>
  <key>serialnumber</key>
  <string>{{serialnumber}}</string>
  <key>serialnumberlast4digits</key>
  <string>{{serialnumberlast4digits}}</string>
  <key>udidlast4digits</key>
  <string>{{udidlast4digits}}</string>
</dict>

```



<!--HONumber=Sep16_HO3-->


