---
title: "Настройка службы Lookout MTP в подписке | Microsoft Intune"
description: "Этот раздел содержит сведения о настройке Lookout MTP."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 8477a2f1-2e1d-4d42-8bcb-e1181cc900bb
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 61480eb11cc8f4b6b336e48a50c2fe1b5fcd3fac
ms.openlocfilehash: 8e2c71127801afc21d52e08d13dd9099b263e801


---

# Настройка подписки для работы службы защиты от угроз на мобильных устройствах Lookout MTP
Чтобы подготовить вашу подписку для работы службы Lookout MTP, специалистам по поддержке Lookout (enterprisesupport@lookout.com) потребуются следующие сведения о вашей среде Azure Active Directory (Azure AD). 

* Идентификатор клиента Azure Active Directory
* Идентификатор объекта группы Azure AD для полного доступа к консоли Lookout MTP
* Идентификатор объекта группы Azure AD для ограниченного доступа к консоли Lookout MTP (при необходимости)

В следующем разделе приводятся процедуры для сбора сведений, которые необходимо предоставить службе поддержки Lookout.  

## Получение сведений о среде Azure AD
### Получение идентификатора клиента Azure AD
Выполните вход на портал управления Azure AD (https://manage.windowsazure.com) и выберите свою подписку. 

![снимок экрана страницы Azure AD, на которой отображается имя клиента ](../media/mtp/aad_tenant_name.png). При выборе имени подписки полученный URL-адрес содержит идентификатор подписки.  Если вам не удается найти идентификатор подписки, вы можете обратиться к полезным советам в [статье службы поддержки Майкрософт](https://support.office.com/en-us/article/Find-your-Office-365-tenant-ID-6891b561-a52d-4ade-9f39-b492285e2c9b?ui=en-US&rs=en-US&ad=US).   
### Получение идентификатора группы Azure AD
Консоль Lookout MTP поддерживает два уровня доступа.  
* **Полный доступ.** Администратор Azure AD может создать две группы пользователей — с полным и ограниченным доступом.  Только пользователи в этих группах смогут выполнять вход в **консоль Lookout MTP**.
* **Ограниченный доступ.** Отсутствие доступа к нескольким конфигурациям и модулям консоли Lookout MTP, связанным с регистрацией; доступ только для чтения к модулю консоли **Политика безопасности**.  

Дополнительные сведения о разрешениях см. [в этой статье](https://personal.support.lookout.com/hc/en-us/articles/114094105653) на веб-сайте Lookout.

**Идентификатор объекта группы** можно найти на странице свойств группы в консоли управления Azure AD.

![снимок экрана страницы свойств с выделенным полем GroupID](../media/mtp/aad_group_object_id.png)

Как только вы соберете эти данные, обратитесь в службу поддержки Lookout (адрес электронной почты: enterprisesupport@lookout.com).

Служба поддержки Lookout будет взаимодействовать с вашим основным контактным лицом по вопросам регистрации подписки и создания корпоративной учетной записи Lookout MTP, используя собранные вами сведения.


## Настройка службы Lookout MTP в подписке
### Шаг 1. Настройка службы MTP
После того как служба поддержки Lookout создаст учетную запись Lookout MTP для вашей организации, вы сможете выполнить вход в консоль Lookout MTP.   Сообщение электронной почты Lookout основному контактному лицу организации со ссылкой на URL-адрес для входа: https://aad.lookout.com/les?action=consent

При первом входе в консоль Lookout MTP необходимо использовать учетную запись пользователя с ролью глобального администратора Azure AD, так как она требуется службе Lookout MTP для регистрации вашего клиента Azure AD.   В дальнейшем для входа пользователю не потребуется этот уровень прав Azure AD.  При первом входе в консоль на экран будет выведена страница согласия. Выберите **Принять** для завершения регистрации.

![снимок экрана страницы консоли Lookout MTP при первом входе ](../media/mtp/lookout_mtp_initial_login.png). После принятия условий и подтверждения согласия вы будете перенаправлены в консоль Lookout MTP. В дальнейшем (после первоначальной регистрации) вход в систему можно выполнять по URL-адресу https://aad.lookout.com.

Если у вас возникли проблемы при входе в систему, ознакомьтесь со [статьей по устранению неполадок](https://docs.microsoft.com/en-us/intune/troubleshoot/troubleshooting-lookout-integration).

Далее приведены задачи, которые необходимо выполнить для завершения настройки службы Lookout MTP в [консоли Lookout MTP](https://aad.lookout.com).

### Шаг 2. Настройка соединителя Intune

В консоли Lookout MTP перейдите в модуль **Система**, выберите вкладку **Соединители** и далее — **Intune**.

![снимок экрана консоли Lookout MTP с открытой вкладкой "Соединители" с выделенным параметром Intune](../media/mtp/lookout_mtp_setup-intune-connector.png)

В параметрах подключения настройте частоту пульса в минутах.  После выполнения этого шага соединитель Intune будет готов к работе.  

![снимок экрана вкладки "Параметры подключения" с настроенной частотой пульса](../media/mtp/lookout-mtp-connection-settings.png)

### Шаг 3. Настройка групп регистрации
На странице **Управление регистрацией** определите набор пользователей, устройства которых должны быть зарегистрированы в Lookout.   Рекомендуется начать с небольшой группы пользователей для тестирования и ознакомления с принципами работы интеграции.  Когда вы будете удовлетворены результатами тестов, можно будет расширить регистрацию для дополнительных групп пользователей.

Чтобы начать работу с группами регистрации, необходимо сначала определить группу безопасности Azure AD, которую удобно использовать в качестве первого набора пользователей для регистрации в Lookout MTP. После создания группы в Azure AD в консоли Lookout MTP перейдите в раздел **Управление регистрацией** и добавьте **отображаемое имя** группы безопасности Azure AD для регистрации.

Если пользователь входит в группу регистрации, любое из его устройств, которые идентифицируются и поддерживаются в Azure AD, регистрируются и подлежат активации в Lookout MTP.  При первом открытии приложения Lookout for Work на поддерживаемом устройстве оно активируется в службе Lookout MTP.
![снимок экрана: страница регистрации соединителя Intune](../media/mtp/lookout-mtp-enrollment.png)

Рекомендуется оставить в качества шага проверки новых устройств значение по умолчанию: 5 минут.

>[!IMPORTANT]
> Отображаемое имя вводится с учетом регистра.  Используйте **отображаемое имя**, как показано на странице **Свойства** группы безопасности на портале Azure. На рисунке ниже обратите внимание, что на странице **Свойства** группы безопасности отображаемое имя указано с первыми буквами в верхнем регистре.  При этом заголовок отображается полностью строчными буквами: такое написание не следует использовать для ввода в консоли Lookout MTP.
>![снимок экрана портала Azure, служба Azure Active Directory, страница "Свойства"](../media/mtp/aad-group-display-name.png)

Текущий выпуск имеет указанные ниже ограничения.  
* Отсутствует проверка для отображаемых имен групп.  Необходимо использовать значение в поле **ОТОБРАЖАЕМОЕ ИМЯ**, отображаемом для группы безопасности Azure AD на портале Azure.
* Создание групп внутри групп пока не поддерживается.  Указанные группы безопасности Azure AD должны содержать только пользователей, но не вложенные группы.


### Шаг 4. Настройка синхронизации состояния
В разделе **Синхронизация состояния** укажите тип данных, которые должны отправляться Intune.  Для правильной работы интеграции Lookout и Intune сейчас требуется включать состояние устройства и состояние угрозы.  Эти параметры включены по умолчанию.
### Шаг 5. Настройка сведений о получателе отчетов об ошибках по электронной почте
В разделе **Управление ошибками** введите адрес электронной почты, на который будут передаваться отчеты об ошибках.

![снимок экрана страницы управления ошибками соединителя Intune](../media/mtp/lookout-mtp-connector-error-notifications.png)

### Шаг 6. Настройка уведомлений по электронной почте
Если вы хотите получать по электронной почте оповещения об угрозах, войдите в [консоль Lookout MTP](https://aad.lookout.com) с учетной записью пользователя, который должен получать уведомления.  Перейдите в модуль **Система** и на вкладке **Настройки** выберите нужные уведомления и задайте для них значение **ВКЛ.** Сохраните внесенные изменения.

![снимок экрана страницы "Настройки" с отображаемой учетной записью пользователя ](../media/mtp/lookout-mtp-email-notifications.png). Если вы больше не хотите получать уведомления по электронной почте, задайте для уведомлений значение **ВЫКЛ.** и сохраните изменения.
### Шаг 7. Настройка классификации угроз
Lookout MTP классифицирует мобильные угрозы различных типов. В [классификации угроз Lookout MTP](http://personal.support.lookout.com/hc/en-us/articles/114094130693) с ними связаны разные уровни риска по умолчанию. Эти настройки можно изменить в любое время в соответствии с потребностями вашей организации.

![снимок экрана страницы политики с угрозой и классификациями](../media/mtp/lookout-mtp-threat-classification.png)

>[!IMPORTANT]
> Указанный здесь уровень риска — важный аспект MTP, так как функция интеграции с Intune определяет соответствие устройства согласно таким уровням рисков во время выполнения. Другими словами, администратор Intune задает правило в политике для определения устройства как несоответствующего при наличии активной угрозы с заданным минимальным уровнем (высоким, средним или низким). Политика классификации угроз в MTP непосредственно определяет правила оценки соответствия устройств в Intune.

## Просмотр сведений о регистрации
После завершения установки Lookout MTP отправляет в Azure AD запрос об устройствах, которые соответствуют указанным группам регистрации.  Сведения о зарегистрированных устройствах можно найти в модуле "Устройства".  Начальное состояние для устройств указывается как состояние ожидания.  Состояние устройства изменится после установки, открытия и активации приложения Lookout for Work на устройстве.  Сведения о принудительной установке Lookout for Work на устройстве можно найти в статье [Настройка и развертывание приложения Lookout for Work](configure-and-deploy-lookout-for-work-apps.md).
## Дальнейшие шаги
[Включение подключения Lookout MTP в Intune](enable-lookout-mtp-connection-in-intune.md)



<!--HONumber=Sep16_HO2-->

