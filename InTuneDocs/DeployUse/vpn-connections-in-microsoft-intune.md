---
title: "VPN-подключения | Microsoft Intune"
description: "Сведения о развертывании параметров VPN для пользователей и устройств в организации с помощью профилей VPN."
keywords: 
author: Nbigman
manager: angrobe
ms.date: 09/06/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: abc57093-7351-408f-9f41-a30877f96f73
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 957edcf6910dd15f15ab5020773233c6a6ba0ea7
ms.openlocfilehash: fb5fbbe50295d3fc26f3cd4def4f40898bb6ffd2


---

# VPN-подключения в Microsoft Intune
 Вы можете использовать виртуальную частную сеть (VPN) для предоставления пользователям безопасного удаленного доступа к своей локальной сети. Удаленные пользователи могут работать, как если бы их устройства были физически подключены к сети. Устройства используют профиль VPN-подключения для создания подключения к VPN-серверу. Используйте *профили VPN* в Microsoft Intune, чтобы развернуть параметры VPN для пользователей и устройств в организации. Развертывание этих параметров упрощает для конечного пользователя подключение к ресурсам в локальной сети.

Например, предположим, что вам необходимо подготовить все устройства iOS с параметрами, необходимыми для подключения к общей папке в корпоративной сети. Создайте профиль VPN, содержащий параметры, необходимые для подключения к корпоративной сети, а затем разверните этот профиль для всех пользователей с устройствами iOS. VPN-подключение появится в списке доступных сетей, и пользователи смогут с легкостью использовать его.

С помощью профилей VPN можно настроить следующие типы устройств.

* Устройства под управлением Android 4 и более поздней версии.
* Устройства под управлением iOS 8.0 и более поздней версии.
* Устройства под управлением Mac OS X 10.9 и более поздней версии.
* Зарегистрированные устройства под управлением Windows 8.1 и более поздней версии.
* Устройства под управлением Windows Phone 8.1 и более поздней версии.
* Устройства под управлением Windows 10 Desktop и Mobile.

Параметры конфигурации для профиля VPN различаются в зависимости от выбранного типа устройств.

## Типы VPN-подключений

Intune поддерживает создание профилей VPN, которые используют следующие типы подключений:




Тип подключения |iOS и Mac OS X  |Android|Windows 8.1|Windows RT|Windows RT 8.1|Windows Phone 8.1|Windows 10 Desktop и Mobile |
----------------|------------------|-------|-----------|----------|--------------|-----------------|----------------------|
Cisco AnyConnect|Да |Да   |Нет    |     Нет    |Нет  |Нет    | Да (OMA-URI, только Mobile)|     
Cisco (IPsec)|да |Нет   |Нет  |  Нет|Нет  |Нет | Нет|
Citrix|да |Нет   |Нет  |  Нет|Нет  |Нет | Нет|
Pulse Secure|Да  |Да |Да   |Нет  |Да  |Да| Да|        
F5 Edge Client|Да |Да |Да |Нет  |Да  |   Да |  Да|   
Dell SonicWALL Mobile Connect|Да |Да |Да |Нет  |Да |Да |Да|         
CheckPoint Mobile VPN|Да |Да |Да |Да |Да|Да|Да|
Microsoft SSL (SSTP)|Нет |Нет |Нет |Нет |Нет|Нет|VPNv1 OMA-URI*|
Microsoft Automatic|Нет |Нет |Нет |Нет |Нет|Да (OMA-URI)|Да|
IKEv2|Настраиваемый профиль iOS|Нет |Нет |Нет |Нет|Да (OMA-URI)|Да|
PPTP|Настраиваемый профиль iOS|Нет |Нет |Нет |Нет|Нет|Да|
L2TP|Настраиваемый профиль iOS|Нет |Нет |Нет |Нет|Да (OMA-URI)|Да|

\* Без дополнительных параметров, которые в противном случае доступны для Windows 10.

> [!IMPORTANT]
> Перед использованием профилей VPN, развернутых на устройстве, необходимо установить приложение VPN, подходящее для профиля. Можно обратиться к статье [Развертывание приложений с помощью Microsoft Intune](deploy-apps-in-microsoft-intune.md) за информацией, которая окажется полезной при развертывании подходящего приложения с использованием Intune.  

 Сведения о создании настраиваемых профилей VPN с помощью параметров URI см. в статье [Настраиваемые конфигурации профилей VPN](custom-configurations-for-vpn-profiles.md).     

## Методы защиты профилей VPN

Профили VPN могут использовать несколько разных типов и протоколов подключения от разных поставщиков. Эти подключения обычно защищаются с помощью одного из двух методов.

### Сертификаты

При создании профиля VPN вы выбираете профиль сертификата SCEP или PFX, созданный ранее в Intune.

Это называется сертификатом удостоверения. Он используется для аутентификации в профиле доверенного сертификата (или корневого сертификата), указывающего, что устройству пользователя разрешено подключаться. Доверенный сертификат развертывается на компьютере, выполняющем проверку подлинности VPN-подключения, как правило, VPN-сервера.

Дополнительные сведения о способах создания и использования профилей сертификатов см. в статье [Защита доступа к ресурсам с помощью профилей сертификатов](secure-resource-access-with-certificate-profiles.md).

### Имя пользователя и пароль.

Пользователь проходит проверку на VPN-сервере, предоставляя свои имя пользователя и пароль.

## Создание профиля VPN

1. В [консоли администрирования Microsoft Intune](https://manage.microsoft.com) выберите **Политика** > **Добавить политику**.
2. Выберите шаблон для новой политики, развернув соответствующий тип устройства, а затем выберите профиль VPN для этого устройства:
    * **Профиль VPN (Android 4 и более поздней версии)**
    * **Профиль VPN (iOS 8.0 или более поздней версии)**
    * **Профиль VPN (Mac OS X 10.9 и более поздние версии)**
    * **Профиль VPN (Windows 8.1 и более поздней версии)**
    * **Профиль VPN (Windows Phone 8.1 и более поздней версии)**
    * **Профиль VPN (Windows 10 Desktop и Mobile и более поздних версий)**

 Можно создать и развернуть только пользовательскую политику профилей VPN. Рекомендуемые параметры недоступны.

3. Для настройки параметров профиля VPN используйте следующую таблицу.

Имя параметра  |Дополнительные сведения  
---------|---------
**Имя**     |Введите уникальное имя для профиля VPN, чтобы идентифицировать его в консоли Intune.         
**Описание**     |Предоставьте в описании общие сведения о профиле VPN и актуальную информацию о его расположении.         
**Имя подключения VPN (отображается пользователям)**     |Укажите имя для профиля VPN. Это имя, которое отображается в списке доступных VPN-подключений на устройствах пользователей.         
**Тип подключения**     |  Выберите один из следующих типов подключения для профиля VPN: **Cisco AnyConnect** (недоступно для Windows 8.1 и Windows Phone 8.1), **Pulse Secure**, **F5 Edge Client**, **Dell SonicWALL Mobile Connect**, **CheckPoint Mobile VPN**.
**Описание VPN-сервера**     | Дайте описание VPN-сервера, к которому будут подключаться устройства. Пример: **Contoso VPN Server**. Если тип соединения — **F5 Edge Client**, укажите в поле **Список серверов** список описаний серверов и IP-адреса.
**IP-адрес или полное доменное имя сервера**    |Укажите IP-адрес или полное доменное имя VPN-сервера, к которому будут подключаться устройства. Примеры: **192.168.1.1**, **vpn.contoso.com**.  Если тип соединения — **F5 Edge Client**, укажите в поле **Список серверов** список описаний серверов и IP-адреса.         |         
**Список серверов**     |Нажмите кнопку **Добавить**, чтобы добавить новый VPN-сервер для VPN-подключения. Можно также указать, какой сервер будет сервером по умолчанию для подключения. Этот параметр отображается, только если выбран тип соединения **F5 Edge Client**.         
**Отправлять весь сетевой трафик через VPN-подключение**     |Если выбран этот параметр, весь сетевой трафик отправляется через VPN-подключение. Если этот параметр не выбран, клиент будет динамически согласовывать маршруты для раздельного туннелирования после подключения к стороннему VPN-серверу. Только подключения к локальной сети отправляются через туннель VPN. VPN-туннелирование не используется при подключении к ресурсам в Интернете.
**Метод проверки подлинности**| Выберите метод аутентификации, используемый VPN-подключением: **Сертификаты** или **Имя пользователя и пароль**. (Параметр **Имя пользователя и пароль** недоступен, если выбран тип соединения Cisco AnyConnect). Параметр **Метод проверки подлинности** недоступен для Windows 8.1.
**Запоминать учетные данные пользователя при каждом входе в систему**|Выберите этот параметр для запоминания учетных данных пользователя, чтобы пользователю не нужно было вводить учетные данные при каждом подключении.
**Выберите сертификат клиента для проверки подлинности клиента (сертификат удостоверения)**|Выберите созданный ранее сертификат SCEP клиента, который будет использоваться для аутентификации VPN-подключения. Дополнительные сведения о способах использования профилей сертификатов см. в статье [Защита доступа к ресурсам с помощью профилей сертификатов](secure-resource-access-with-certificate-profiles.md). Этот параметр отображается только в том случае, если метод проверки подлинности — **Сертификаты**.
**Роль**| Укажите имя роли пользователя, имеющего доступ к этому подключению. Роль пользователя определяет личные настройки и параметры, а также включает или отключает определенные функции доступа. Этот параметр отображается только в том случае, если выбран тип соединения **Pulse Secure**.
**Область**|Укажите имя области проверки подлинности, которую следует использовать. Область аутентификации — это группа ресурсов аутентификации, которая используется типом подключения Pulse Secure. Этот параметр отображается только в том случае, если выбран тип соединения **Pulse Secure**.
**Группа или домен входа**|Укажите имя группы входа или домен, к которому следует подключиться. Этот параметр отображается только в том случае, если выбран тип соединения **Dell SonicWALL Mobile Connect**.
**Отпечаток**|Укажите строку (например "Код отпечатка Contoso"), которая будет использоваться для проверки доверия VPN-сервера. Отпечаток можно отправлять клиенту, чтобы он доверял любому серверу, представившему этот же отпечаток при подключении. Если на устройстве еще нет отпечатка, пользователь получит запрос на доверие к VPN-серверу, к которому осуществляется подключение, с отображением отпечатка. (Пользователь должен вручную проверить отпечаток и нажать кнопку **Доверять** для подключения). Этот параметр отображается только в том случае, если выбран тип соединения **CheckPoint Mobile VPN**.
**VPN для каждого приложения**|Выберите этот параметр, если требуется связать VPN-подключение с приложением iOS или Mac OS X, чтобы устанавливать подключение при запуске приложения. Профиль VPN можно связать с приложения при развертывании программного обеспечения. Дополнительные сведения см. в статье [Развертывание приложений в Microsoft Intune](deploy-apps-in-microsoft-intune.md).
**VPN по запросу**|VPN по запросу можно настроить для устройств под управлением iOS 8.0 или более поздней версии. Инструкции по настройке приводятся в разделе [VPN по запросу для устройств iOS](#on-demand-vpn-for-ios-devices).
**Автоматическое определение параметров прокси-сервера** (только iOS, Mac OS X, Windows 8.1 и Windows Phone 8.1)|Если VPN-серверу требуется прокси-сервер для подключения, укажите, следует ли устройствам автоматически определять параметры подключения. Дополнительные сведения см. в документации по Windows Server.
**Использовать сценарий автоматической настройки** (только iOS, Mac OS X, Windows 8.1 и Windows Phone 8.1)|Если VPN-серверу требуется прокси-сервер для подключения, укажите, следует ли использовать сценарий автоматической настройки для определения параметров, а затем укажите URL-адрес файла с параметрами. Дополнительные сведения см. в документации по Windows Server.
**Использовать прокси-сервер** (только iOS, Mac OS X, Windows 8.1 и Windows Phone 8.1)|Если VPN-серверу требуется прокси-сервер для подключения, выберите этот параметр, а затем укажите адрес и номер порта прокси-сервера. Дополнительные сведения см. в документации по Windows Server.
**Обход параметров прокси-сервера для локальных адресов** (только iOS, Mac OS X, Windows 8.1 и Windows Phone 8.1)|Если VPN-серверу требуется прокси-сервер для подключения, выберите этот параметр, если вы не хотите использовать прокси-сервер для указанных локальных адресов. Дополнительные сведения см. в документации по Windows Server.
**Настраиваемый XML** (Windows 8.1 и более поздние версии, Windows Phone 8.1 и более поздние версии)|Укажите пользовательские команды XML, настраивающие VPN-подключение. Пример для **Pulse Secure**: &lt;pulse-schema&gt;&lt;isSingleSignOnCredential&gt;true&lt;/isSingleSignOnCredential&gt;&lt;/pulse-schema&gt;. Пример для **CheckPoint Mobile VPN**: &lt;CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" /&gt;. Пример для **Dell SonicWALL Mobile Connect**: &lt;MobileConnect&gt;&lt;Compression&gt;false&lt;/Compression&gt;&lt;debugLogging&gt;True&lt;/debugLogging&gt;&lt;packetCapture&gt;False&lt;/packetCapture&gt;&lt;/MobileConnect&gt;. Пример для **F5 Edge Client**: &lt;f5-vpn-conf&gt;&lt;single-sign-on-credential /&gt;&lt;/f5-vpn-conf&gt;. Дополнительные сведения о создании пользовательских команд XML см. в документации VPN каждого производителя.
**Список DNS-суффиксов** (только Windows Phone 8.1)|Укажите один DNS-суффикс в каждой строке. При подключении к веб-сайту с использованием короткого имени будет выполнен поиск каждого указанного DNS-суффикса. Например, укажите DNS-суффиксы **domain1.contoso.com** и **domain2.contoso.com**, перейдите по URL-адресу **http://mywebsite** для поиска URL-адресов **http://mywebsite.domain1.contoso.com** и **http://mywebsite.domain2.contoso.com**.
**Обходить VPN при подключении к сети Wi-Fi компании** (только Windows Phone 8.1)|Выберите этот параметр, чтобы указать, что VPN-подключение не будет использоваться, когда устройство подключено к локальной сети Wi-Fi.
**Обходить VPN при подключении к домашней сети Wi-Fi** (только Windows Phone 8.1)|Выберите этот параметр, чтобы указать, что VPN-подключение не будет использоваться, когда устройство подключено к домашней сети Wi-Fi.

Следующие дополнительные параметры доступны для устройств Windows 10 Desktop и Mobile.

Имя параметра  |Дополнительные сведения  
---------|---------
**Правила сетевого трафика**|Выберите, какие протоколы, локальные и удаленные порты, а также диапазоны адресов будут включены для VPN-подключения. Если не создать правило сетевого трафика, будут включены все протоколы, порты и диапазоны адресов. После создания правила VPN-подключение будет использовать только протоколы, порты и диапазоны адресов, указанные в нем.
**Маршруты**|Выберите, какие маршруты будут использовать VPN-подключение.
**DNS-серверы**| Выберите, какие DNS-серверы будут использоваться VPN-подключением после установки соединения.         
**Связанные приложения**|Укажите список приложений, которые будут автоматически использовать VPN-подключение. Идентификатор приложения определяется типом приложения. Для универсальных приложений укажите имя семейства пакетов. А для классических приложений — путь к файлу приложения.          


> [!IMPORTANT]
> Рекомендуется защитить все списки компилируемых приложений при использовании в конфигурации VPN для отдельных приложений. Если неавторизованный пользователь изменит список и вы импортируете его в список приложений VPN, вы можете разрешить доступ VPN приложениям, которые не должны иметь доступа. Списки приложений можно защитить с помощью списка контроля доступа (ACL).

Вот пример использования параметров корпоративных границ. Если требуется включить VPN только для удаленного рабочего стола, создайте правило сетевого трафика, которое разрешает трафик для протокола 27 на внешнем порте 3996. Другой трафик не будет использовать VPN-подключение.

Определение маршрутов в корпоративных границах полезно, если тип VPN-подключения не позволяет определять способ обработки трафика в раздельном туннелировании. В этом случае используйте параметр **Маршруты**, чтобы указать маршруты, которые будут использовать VPN-подключение.

Вы можете ограничить использование VPN-подключения для устройств Windows 10 списком конкретных приложений, создав пользовательский параметр OMA-URI.

Новая политика отображается в узле **Политики конфигураций** рабочей области **Политика**.

### VPN по запросу для устройств iOS
VPN по запросу можно настроить для устройств под управлением iOS 8.0 или более поздней версии.

> [!NOTE]
>  
> Нельзя использовать в одной политике VPN на уровне приложения и VPN по запросу.
 
1. На странице настройки политики найдите **Правила по запросу для этого VPN-подключения**. Здесь вы увидите столбцы **Совпадение**, в котором указано условие для правила, и **Действие**, где указано действие, которое политика активирует при выполнении условия. 
2. Щелкните **Добавить**, чтобы создать правило. Для этого правила существуют два типа соответствия. Для каждого правила можно указать только один из этих типов.
  - **SSID**, который относится к беспроводным сетям. 
  - **Домены поиска DNS**, в котором вы можете использовать  полные доменные имена, например *team.corp.contoso.com*, или имена доменов, например *contoso.com* (это будет эквивалентно использованию **.contoso.com*).
3. Необязательно: введите строковую пробу, то есть URL-адрес, который будет применяться в этом правиле для проверки. Если устройство, на котором установлен этот профиль, может обратиться к указанному URL-адресу без перенаправления, устанавливается VPN-подключение и устройство подключаются к запрошенному URL-адресу. Пользователь не увидит этот URL-адрес проверки. Например, в качестве зонда строки URL-адреса можно использовать адрес веб-сервера аудита, который будет проверять параметры устройства перед подключением к виртуальной частной сети. Также можно, чтобы этот URL-адрес проверял возможность подключения к сайту, прежде чем подключать устройство к запрошенному целевому URL-адресу через VPN-подключение.
4. Выберите одно из следующих действий.
  - **Подключить**
  - **Оценить подключение** с тремя настраиваемыми параметрами: а) **Действие домена** — выберите **Подключить, если требуется** или **Никогда не подключать**.
     б) **Список доменов с разделителями-запятыми** — этот параметр устанавливается только в том случае, если для параметра **Действие для домена** выбран вариант **Подключить, если требуется**. 
     в) **Обязательный зонд строки URL-адреса** — это URL-адрес для подключения по протоколу HTTP или HTTPS (предпочтительно), например *https://vpntestprobe.contoso.com*. Правило проверит, можно ли получить ответ от этого адреса. Если ответа нет, а для параметра **Действие домена** выбран вариант **Подключить, если требуется**, будет активировано VPN-подключение.
     > [!TIP]
     >
     >Это действие применяется, если для некоторых узлов в сети организации требуется подключение только напрямую или через корпоративное VPN-подключение, а для других узлов такое требование не установлено. Если включить *corp.contoso.com* в **список доменов поиска DNS с разделителями-запятыми**, вы сможете указать вариант **Подключить, если требуется** и перечислить отдельные сайты в сети, для которых требуется VPN-подключение, например *sharepoint.corp.contoso.com*. Тогда правило будет проверять, есть ли связь с узлом *vpntestprobe.contoso.com*. Если связи нет, для сервера Sharepoint будет применяться VPN-подключение.
  - **Игнорировать** — параметры VPN-подключений не изменяются. Оставьте подключение VPN в текущем состоянии (не разрывайте установленное и не устанавливайте отсутствующее). Например, у вас может быть правило, которое создает VPN-подключение для связи с любым из внутренних корпоративных веб-узлов, но один из этих узлов должен быть доступен, только если устройство фактически подключено к корпоративной сети. Тогда вы можете создать для такого узла правило с действием "Игнорировать".
  - **Отключить** — VPN-подключение на устройстве будет разорвано при выполнении соответствующих условий. Например, в поле **SSID** можно перечислить все беспроводные сети организации и создать правило, которое будет отключать устройство от VPN при подключении к одной из этих сетей.

Сначала проверяются правила для конкретных доменов, а затем общие правила для всех доменов. 


## Развертывание политики

1.  В рабочей области **Политика** выберите политику, которую требуется развернуть, а затем щелкните **Управление развертыванием**.

2.  В диалоговом окне **Управление развертыванием** выполните следующие действия.

    -   Чтобы развернуть политику, выберите одну или несколько групп для развертывания, а затем щелкните **Добавить** &gt; **ОК**.

    -   Чтобы закрыть диалоговое окно, не развертывая политику, нажмите кнопку **Отмена**.


После успешного развертывания пользователи увидят имя VPN-подключения, указанное в списке VPN-подключений на устройствах.

В сводке состояния и оповещениях на странице **Обзор** рабочей области **Политика** указаны проблемы с политикой, требующие вашего внимания. Кроме того, сводка состояния отображается в рабочей области "Панель мониторинга".

### См. также
[Настраиваемые конфигурации профилей VPN](Custom-configurations-for-VPN-profiles.md)

[VPN на уровне приложения в Android с использованием Pulse Secure](per-app-vpn-for-android-pulse-secure.md)



<!--HONumber=Sep16_HO1-->


