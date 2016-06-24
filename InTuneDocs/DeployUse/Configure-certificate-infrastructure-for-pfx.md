---
title: Настройка инфраструктуры сертификатов для PFX | Microsoft Intune
description:
keywords:
author: nbigman
manager: jeffgilb
ms.date: 05/16/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2c543a02-44a5-4964-8000-a45e3bf2cc69

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: vinaybha
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:


---
# Настройка инфраструктуры сертификатов
В этом разделе описывается, что необходимо для создания и развертывания профилей сертификатов.

Для аутентификации на основе сертификатов в организации требуется центр сертификации предприятия.

Для использования профилей сертификатов PFX, помимо центра сертификации предприятия, требуются следующие компоненты:

-   Компьютер, который может взаимодействовать с центром сертификации, или сам компьютер центра сертификации.

 -  Соединитель сертификатов Intune, работающий на компьютере, который может взаимодействовать с центром сертификации.

## Описание локальной инфраструктуры


-    **Домен Active Directory**: все серверы, указанные в этом разделе (за исключением сервера прокси-службы веб-приложения), должны быть присоединены к домену Active Directory.

-  **Центр сертификации** (ЦС): вам требуется центр сертификации предприятия под управлением выпуска Enterprise Windows Server 2008 R2 или более поздней версии. Автономный ЦС не поддерживается. Инструкции по настройке центра сертификации см. в разделе [Установка центра сертификации](http://technet.microsoft.com/library/jj125375.aspx).
    Если ЦС выполняется под управлением Windows Server 2008 R2, необходимо [установить исправление из KB2483564](http://support.microsoft.com/kb/2483564/).

 -  **Компьютер, который может взаимодействовать с центром сертификации**: также можно использовать сам компьютер центра сертификации.
-  **Соединитель сертификатов Microsoft Intune**: используйте консоль администрирования Intune, чтобы скачать установщик **соединителя сертификатов** (**ndesconnectorssetup.exe**). Затем вы можете запустить **ndesconnectorssetup.exe** на компьютере, где требуется установить соединитель сертификатов. Для профилей сертификата .PFX установите соединитель сертификатов на компьютере, который взаимодействует с центром сертификации.
-  **Cервер прокси-службы веб-приложения** (необязательно): вы можете использовать сервер под управлением Windows Server 2012 R2 или более поздней версии в качестве сервера прокси-службы веб-приложения (WAP). Эта конфигурация:
    -  позволяет устройствам получать сертификаты, используя подключение к Интернету;
    -  является рекомендацией по безопасности, если устройства подключаются к Интернету для получения или возобновления действия сертификатов.

 > [!NOTE]           
> -    На сервере, где размещается WAP, [необходимо установить обновление](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) , обеспечивающее поддержку длинных URL-адресов, которые используются службой регистрации сертификатов для сетевых устройств. Это обновление включено в [накопительный пакет обновления за декабрь 2014 г.](http://support.microsoft.com/kb/3013769), или его можно получить отдельно из [KB3011135](http://support.microsoft.com/kb/3011135).
>-  Сервер, на котором размещается WAP, также должен иметь SSL-сертификат, совпадающий с именем, опубликованным для внешних клиентов, и доверять SSL-сертификату, который используется на сервере NDES. Эти сертификаты позволяют WAP-серверу разорвать SSL-соединение клиентов и создать новое SSL-соединение с сервером NDES.
Сведения о сертификатах для WAP см. в подразделе **Планирование сертификатов** раздела [Планирование публикации приложений с помощью прокси-службы веб-приложения](https://technet.microsoft.com/library/dn383650.aspx). Общие сведения о WAP-серверах см. в разделе [Работа с прокси-службой веб-приложения](http://technet.microsoft.com/library/dn584113.aspx).|


### Сертификаты и шаблоны

|Объект|Подробные сведения|
|----------|-----------|
|**Шаблон сертификата**|Настройте этот шаблон в выдающем ЦС.|
|**Доверенный корневой сертификат ЦС**|Вы экспортируете его в виде **CER** -файла из выдающего ЦС или с любого устройства, доверяющего выдающему ЦС, и развертываете его на устройствах, используя профиль сертификата доверенного ЦС.<br /><br />Для каждой платформы операционной системы используется один доверенный корневой сертификат ЦС, который связывается с каждым созданным профилем доверенного корневого сертификата.<br /><br />При необходимости можно использовать дополнительные доверенные корневые сертификаты ЦС. Например, это можно сделать, чтобы предоставить доверие ЦС, подписывающему сертификаты проверки подлинности сервера для точек доступа Wi-Fi.|


## Настройка инфраструктуры
Перед тем как вы сможете настроить профили сертификатов, необходимо выполнить следующие задачи, для которых требуется знание Windows Server 2012 R2 и служб сертификатов Active Directory (ADCS):

**Задача 1**. Настройка шаблонов сертификатов в центре сертификации **Задача 2**. Включение, установка и настройка соединителя сертификатов Intune

### Задача 1. Настройка шаблонов сертификатов в центре сертификации
В этой задаче будет опубликован шаблон сертификата

##### Настройка центра сертификации

1.  В выдающем центре сертификации с помощью оснастки "Шаблоны сертификатов" создайте новый пользовательский шаблон или скопируйте существующий шаблон (например, шаблон пользователя) и измените его для использования с .pFX.

    Шаблон должен иметь следующие настройки.

    -   Укажите понятное **Отображаемое имя шаблона** .

    -   На вкладке **Имя субъекта** выберите **Отправить в запросе**. (Безопасность обеспечивается модулем политики Intune для NDES.)

    -   На вкладке **Расширения** включите в раздел **Описание политик приложений** пункт **Проверка подлинности клиента**.

        > [!IMPORTANT] Для шаблонов сертификатов iOS и Mac OS X измените на вкладке **Расширения** параметр **Использование ключей** и снимите флажок **Подпись подтверждает подлинность**.


3.  Просмотрите **Период действия** на вкладке **Общие** шаблона. По умолчанию в Intune используется значение, настроенное в шаблоне. Однако в настройках ЦС вы можете разрешить инициатору запроса указывать другое значение, которое можно затем задать в консоли администрирования Intune. Если вы хотите всегда использовать значение в шаблоне, пропустите остальные действия этого шага.

    > [!IMPORTANT] Платформы iOS и Mac OS X всегда используют значение, заданное в шаблоне, независимо от других настроек.

    Чтобы настройки ЦС позволяли инициатору запроса указывать период действия, выполните в ЦС следующие команды:

    1.  **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**

    2.  **net stop certsvc**

    3.  **net start certsvc**

4.  В выдающем ЦС используйте оснастку центра сертификации, чтобы опубликовать шаблон сертификата.

    1.  Выберите узел **Шаблоны сертификата**, щелкните **Действие**-&gt; **Создать** &gt; **Выдаваемый шаблон сертификата**, а затем укажите шаблон, созданный в шаге 2.

    2.  Убедитесь, что шаблон опубликован, просмотрев его в папке **Шаблоны сертификата** .

5.  На компьютере центра сертификации убедитесь, что компьютер, на котором размещается соединитель сертификатов Intune, имеет разрешение на регистрацию и может получить доступ к шаблону, используемому при создании профиля .PFX. Задайте это разрешение на вкладке **Безопасность** свойств компьютера ЦС.

### Задача 2. Включение, установка и настройка соединителя сертификатов Intune
В этой задаче вы:

Скачивание, установка и настройка соединителя сертификатов

##### Включение поддержки для соединителя сертификатов

1.  Откройте [консоль администрирования Intune](https://manage.microsoft.com), щелкните **Администрирование** &gt; **Соединитель сертификатов**.

2.  Щелкните **Настройка локального соединителя сертификатов**.

3.  Выберите **Включить соединитель сертификатов**, а затем нажмите кнопку **ОК**.

##### Скачивание, установка и настройка соединителя сертификатов

1.  Откройте [консоль администрирования Intune](https://manage.microsoft.com), а затем щелкните **Администрирование** &gt; **Управление мобильными устройствами** &gt; **Соединитель сертификатов** &gt; **Скачать соединитель сертификатов**.

2.  После скачивания запустите установщик (**ndesconnectorssetup.exe**).

  Запустите установщик на компьютере, который может подключиться к центру сертификации. Выберите параметр распределения PFX и щелкните "Установить". По завершении установки создайте профиль сертификата, как описано в разделе [Настройка профилей сертификатов](configure-intune-certificate-profiles.md).

   <!-- Not sure about step 3 below -->

3.  При запросе сертификата клиента для соединителя сертификатов щелкните **Выбрать** и укажите сертификат **проверки подлинности клиента**, установленный в задаче 3.

    После выбора сертификата проверки подлинности клиента вы вернетесь на поверхность **Сертификата клиента для соединителя сертификатов Microsoft Intune** . Хотя выбранный сертификат не отображается, нажмите кнопку **Далее** , чтобы просмотреть свойства этого сертификата. Затем нажмите кнопки **Далее**и **Установить**.

4.  После завершения работы мастера, но перед тем, как закрыть его, щелкните **Запустить пользовательский интерфейс соединителя сертификатов**.

    > [!TIP] Если вы закрыли мастер перед запуском пользовательского интерфейса соединителя сертификатов, вы можете повторно открыть его, выполнив следующую команду:
    >
    > **&lt;путь_установки&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  В пользовательском интерфейсе **соединителя сертификатов** :

    Щелкните **Войти** и введите учетные данные администратора службы Intune или учетные данные администратора клиента с разрешениями глобального администратора.

  <!--  If your organization uses a proxy server and the proxy is needed for the NDES server to access the Internet, click **Use proxy server** and then provide the proxy server name, port, and account credentials to connect.-->

    Откройте вкладку **Дополнительно** , а затем укажите учетные данные учетной записи с разрешением **Выдача сертификатов и управление ими** в выдающем центре сертификации и нажмите кнопку **Применить**.

    Теперь можно закрыть пользовательский интерфейс соединителя сертификатов.

6.  Откройте командную строку и введите **services.msc**, а затем нажмите клавишу **ВВОД**, щелкните правой кнопкой мыши элемент **Служба соединителя Intune** и выберите пункт **Перезапустить**.

Чтобы убедиться, что служба работает, откройте браузер и введите следующий URL-адрес (он должен вернуть ошибку **403** ):

**http:// &lt;полное_доменное_имя_сервера_NDES&gt;/certsrv/mscep/mscep.dll**

### Дальнейшие действия
Теперь вы готовы к настройке профилей сертификатов, как описано в разделе [Настройка профилей сертификатов](Configure-Intune-certificate-profiles.md).


<!--HONumber=Jun16_HO1-->

