---
title: "Устранение неполадок условного доступа | Microsoft Intune"
description: "Описывается, что нужно делать, если пользователям не удается получить доступ к ресурсам через условный доступ Intune."
keywords: 
author: karaman
manager: angrobe
ms.date: 07/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 433fc32c-ca9c-4bad-9616-852c72faf996
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7b16c19c95384655e170c199597dd6bd31afb90d
ms.openlocfilehash: a04037453382420540dbec721179ccb623df0829


---

# Устранение неполадок условного доступа

Как правило, когда пользователь пытается получить доступ к электронной почте или SharePoint, он получает запрос на регистрацию. Этот запрос приводит пользователя на портал компании.

В этой статье рассказывается, что нужно делать, если пользователям не удается получить доступ к ресурсам через условный доступ Intune.


## Успешное использование условного доступа

Для успешного использования условного доступа должны выполняться следующие условия.

-   Устройство должно управляться Intune.
-   Устройство должно быть зарегистрировано в Azure Active Directory (AAD). При обычных обстоятельствах эта регистрация выполняется автоматически во время регистрации в Intune.
-   Устройство должно соответствовать политикам соответствия требованиям Intune, установленным для устройства и его пользователя.  Если такие политики отсутствуют, то достаточно регистрации в Intune.
-   В устройстве должна быть активирована служба Exchange ActiveSync, если пользователь получает почту через встроенный почтовый клиент устройства, а не через Outlook.     Это происходит автоматически на устройствах iOS, Windows Phone, Android и KNOX.
-   Необходимо правильно настроить соединитель Windows Intune с Exchange. Дополнительные сведения см. в разделе [Troubleshooting the Exchange Connector in Microsoft Intune](troubleshoot-exchange-connector.md) (Устранение неполадок соединителя Exchange в Microsoft Intune).

Выполнение этих условий можно проверить для каждого устройства на портале управления Azure и в отчете об инвентаризации устройств.

## Проблемы с регистрацией

 -  Устройство не зарегистрировано, поэтому регистрация устранит проблему.
 -  Пользователь зарегистрировал устройство, однако присоединение к рабочему месту выполнить не удалось. Пользователю следует обновить регистрацию на портале компании.

## Проблемы с соответствием

 -  Устройство не соответствует политике Intune. Распространенной проблемой является невыполнение требований к шифрованию и паролю. Пользователь будет перенаправлен на портал компании, где можно настроить параметры соответствия для устройства.
 -  Регистрация сведений о соответствии для устройства может занять некоторое время. Подождите несколько минут и повторите попытку.
 -  Для устройств iOS:
     -   Существующий профиль электронной почты, созданный пользователем, заблокирует развертывание профиля, созданного администратором Intune. Это распространенная проблема, поскольку пользователи iOS обычно создают профиль электронной почты, а затем регистрируются. Портал компании проинформирует пользователя о том, что он не соответствует условиям из-за настроенного вручную профиля электронной почты, и предложит удалить этот профиль. Пользователю следует удалить свой профиль электронной почты, чтобы можно было развернуть профиль Intune. Чтобы избежать этой проблемы, дайте указание своим пользователям регистрироваться без установки профиля электронной почты и разрешите Intune провести развертывание профиля.
     -   Устройство iOS может задержаться в состоянии проверки соответствия требованиям, не позволяя пользователю инициировать еще одну операцию регистрации. Перезапуск корпоративного портала может исправить эту проблему, и тогда состояние соответствия требованиям будет отражать состояние устройства в Intune. После сбора всех данных с устройства выполняется быстрая синхронизация для проверки соответствия требованиям, в среднем длящаяся менее полсекунды.

        Обычно причиной задержки устройства в этом состоянии являются затруднения при подключении к службе или длительная синхронизация.  В случае повторения этой проблемы в разных сетевых конфигурациях (сеть мобильной связи, Wi-Fi, VPN) после перезагрузки устройства и проверки актуальности SSP на устройстве обратитесь в службу технической поддержки Майкрософт, как описано в разделе [Получение поддержки для Microsoft Intune](how-to-get-support-for-microsoft-intune.md).

## Проблемы политики

При создании политики соответствия и ее связи с политикой электронной почты для соответствующего пользователя должны быть развернуты обе политики, поэтому будьте внимательны при планировании развертывания политик для групп. Пользователи, для которых действует только одна политика, вероятно, столкнутся с тем, что их устройства будут несоответствующими.


## Проблемы в работе Exchange ActiveSync

### Совместимые устройства Android получают уведомление о карантине
- Зарегистрированное и соответствующее устройство Android все равно может получить уведомление о карантине при попытке доступа к корпоративным ресурсам. Прежде чем перейти по ссылке **Начать**, пользователь должен убедиться, что корпоративный портал не был открыт, когда он пытался получить доступ к ресурсам. Пользователь должен закрыть корпоративный портал, повторить попытку доступа к ресурсам, а затем перейти по ссылке **Начать**.

### Снятое с учета устройство по-прежнему имеет доступ
- При использовании Exchange Online устройство может сохранять доступ к ресурсам в течение нескольких часов после снятия с учета. Это объясняется тем, что Exchange кэширует права доступа на 6 часов. В этом сценарии следует рассмотреть другие способы защиты данных на устройствах, снятых с учета.

### Совместимое устройство зарегистрировано в AAD, но по-прежнему блокируется
- Иногда при подготовке идентификатора Exchange ActiveSync (EASID) в AAD имеет место задержка. Распространенной причиной этой проблемы является регулирование, поэтому подождите несколько минут и повторите попытку.

### Устройство заблокировано

Условный доступ устройства может быть заблокирован без получения электронного сообщения для активации.

- Существует ли в Exchange какое-либо правило по умолчанию, которое помещает устройства в карантин или блокирует их? Если правило по умолчанию блокирует устройства или помещает их в карантин, то они не смогут получить электронное сообщение для активации от соединителя Exchange. Это предусмотрено проектом.
- Учетная запись уведомлений настроена правильно, как описано в базовой конфигурации?
- Отображается ли устройство в консоли администрирования Intune как устройство Exchange ActiveSync? Если нет, то, скорее всего, при обнаружении устройства произошел сбой. Возможная причина — проблема синхронизации с соединителем Exchange. Ознакомьтесь с разделом "Устройство Exchange ActiveSync не обнаруживается из Exchange".
- Просмотрите действия sendemail в журналах соединителя Exchange и проверьте их на наличие ошибок. Пример команды для поиска: SendEmail from notification account to useremail.
- Прежде чем заблокировать устройство, соединитель Exchange отправляет электронное сообщение для активации. Если устройство находится вне сети, то оно может не получить это сообщение. Проверьте, использует ли почтовый клиент на устройстве для получения электронной почты технологию Push, а не Poll, так как из-за этого пользователь также может пропустить электронное сообщение. Переключите клиент на использование технологии Poll и проверьте, получит ли устройство электронное сообщение.

## Несовместимое устройство не заблокировано

При выявлении устройства, которое не соответствует требованиям, но все равно имеет доступ, выполните следующие действия.

- Просмотрите целевую группу и группу исключений. Если пользователь не находится в соответствующей целевой группе или находится в группе исключений, то он не будет заблокирован. На соответствие требованиям проверяются только устройства пользователей в целевой группе.
- Убедитесь, что устройство обнаруживается. Указывает ли соединитель Exchange на разграничение доступа кода Exchange 2010, тогда как пользователь находится на сервере Exchange 2013? В этом случае, если правило по умолчанию Exchange имеет значение "Разрешить", даже если пользователь находится в целевой группе, Intune не может учитывать подключение устройства к Exchange.
- Проверьте существование и состояние доступа устройства в Exchange.
    - Используйте следующий командлет PowerShell, чтобы получить список всех мобильных устройств для почтового ящика: Get-ActiveSyncDeviceStatistics -mailbox mbx. Если устройства нет в списке, значит, оно не обращается к Exchange.
    - Если устройство есть в списке, то выполните командлет Get-CASmailbox -identity:’upn’ | fl, чтобы получить подробные сведения о его состоянии доступа, и предоставьте эти сведения в службе технической поддержки Майкрософт.

## Прежде чем создать запрос в службу поддержки
Если приведенные выше процедуры не помогли устранить проблему, то вам потребуется предоставить службе технической поддержки Майкрософт определенные сведения, например журналы почтовых ящиков OWA или журналы соединителя Exchange.

### Сбор журналов почтовых ящиков OWA

1. Войдите в систему через OWA и щелкните символ шестеренки (параметры) рядом со своим именем в правом верхнем углу.
2. Выберите **Параметры**.
3. Выберите **Телефон** (возможно, этот пункт будет называться **Мобильные устройства**) в столбце слева.
4. В верхнем меню выберите **Мобильные устройства**.
5. Выберите устройство из списка и нажмите кнопку **Начать запись**.
6. При появлении запроса нажмите кнопку **Да** во всплывающем диалоговом окне.
7. Выполните действия, вызвавшие проблему, чтобы воспроизвести ее.
8. Подождите 1–2 минуты, а затем вернитесь к списку телефонов в OWA. Убедитесь, что ваш телефон выбран в списке, и в верхнем меню выберите **Получить журнал**.
9. Вы должны будете получить электронное сообщение от самого себя с вложением. При открытии запроса в службу поддержки укажите содержимое сообщения электронной почты в службу поддержки Майкрософт.

### Журналы соединителя с Exchange

#### Общая информация о журнале
Чтобы просмотреть журналы соединителя Exchange, используйте [инструмент Server Trace Viewer] (инструмент Server Trace Viewer (https://msdn.microsoft.com/en-us/library/ms732023(v=vs.110).aspx'). Для работы этого инструмента необходимо скачать пакет SDK для Windows Server.

>[!NOTE]
>Журналы расположены в папке C:\ProgramData\Microsoft\Windows Intune Exchange Connector\Logs. Они хранятся в наборе из 30 файлов журнала, начиная с *Connector0.log* и заканчивая *Connector29.log*. После записи в файл журнала 10 МБ данных выбирается следующий файл журнала и запись производится в него. Когда заполняется файл журнала Connector29, запись снова переключается на файл журнала Connector0. При этом предыдущий файл журнала перезаписывается.

#### Поиск журналов синхронизации

-    Найдите операцию полной синхронизации в журналах, выполнив поиск текста **full sync**. В начале операции полной синхронизации будет следующий текст:

    "Handling command: Getting the mobile device list without a time filter (full sync) for <number> users" (Обработка команды: получение списка мобильных устройств без фильтра времени (полная синхронизация) для следующего числа пользователей: <number>).

    В конце журнала для полной синхронизации указывается следующий текст:

    "Getting the mobile device list without a time filter (full sync) for 4 users completed successfully" (Успешно завершено получение списка мобильных устройств без фильтра времени (полная синхронизация) для следующего числа пользователей: 4). "Details: Inventory command result - Devices synced: 0 Commmand ID: commandIDGUID' Exchange health: 'Server health 'Name: 'PowerShellExchangeServer: <Name=mymailservername>' Status: Connected','" (Сведения: результат команды учета — Синхронизировано устройств: 0. ИД команды: commandIDGUID'. Работоспособность Exchange: 'Работоспособность сервера'. 'Имя: 'PowerShellExchangeServer: <Name=mymailservername>'. Состояние: подключен',')

-   Найдите в журналах операцию быстрой (разностной) синхронизации, выполнив поиск текста **quick sync**.

##### Исключения для команды Get next
Проверьте журналы соединителя Exchange на наличие исключений для **команды Get next** и отправьте их в службу технической поддержки Майкрософт.

#### Подробное ведение журнала

Чтобы включить подробное ведение журнала, выполните следующее.

1.  Откройте файл конфигурации трассировки соединителя Exchange. Путь к этому файлу: %ProgramData%\Microsoft\Windows Intune Exchange Connector\TracingConfiguration.xml.
2.  Найдите TraceSourceLine с следующим ключом: OnPremisesExchangeConnectorService.
3.  Измените значение узла **SourceLevel** с **Warning ActivityTracing** (по умолчанию) на **Verbose ActivityTracing**, как показано ниже.

    <TraceSourceLine>
          <Key xsi:type="xsd:string">OnPremisesExchangeConnectorService</Key>
          <Value xsi:type="TraceSource">
            <SourceLevel>All</SourceLevel>
            <Listeners>
              <Listener>
                <ListenerType>CircularTraceListener</ListenerType>
                <SourceLevel>Verbose ActivityTracing</SourceLevel>
                <FileSizeQuotaInBytes>10000000</FileSizeQuotaInBytes>
                <FileName>Microsoft\Windows Intune Exchange Connector\Logs\Connector.svclog</FileName>
                <FileQuota>30</FileQuota>
              </Listener>
            </Listeners>
          </Value>
    </TraceSourceLine>



### Дальнейшие действия
Если эта информация не помогла, обратитесь в службу поддержки Майкрософт, как описано в статье [Получение поддержки для Microsoft Intune](how-to-get-support-for-microsoft-intune.md).



<!--HONumber=Aug16_HO1-->

