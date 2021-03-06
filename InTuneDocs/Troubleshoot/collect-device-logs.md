---
title: "Сбор журналов устройств | Microsoft Intune"
description: 
keywords: 
author: Nbigman
manager: angrobe
ms.date: 09/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d97fb610-9d88-40e5-bb06-447eec533630
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d3233346702cf6de968abb251e885dc208d7720c
ms.openlocfilehash: 183888119325568c857240a038740898a630a696


---

# Журналы устройств

При устранении неполадок вам могут потребоваться журналы с устройств пользователя. Ниже описаны инструкции для сбора этих журналов. Для сбора обычно необходим доступ к устройству или запрос от пользователя на сбор журналов и их отправку вам.

### Расположение журналов в Android
Журналы в Android расположены в каталоге *<Android Device>\Phone\Android\data\com.microsoft.windowsintune.companyportal\files*. Пользователь также может отправить файлы журналов по электронной почте, как описано в статье [Отправка журналов диагностических данных Android ИТ-администратору по электронной почте](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android).

### Журналы iOS

Пользователь может отправить вам ошибки регистрации, как описано в разделе [Отправка ошибок регистрации iOS ИТ-администратору](/intune/enduser/send-errors-to-your-it-admin-ios).

### Устройства Mac OS X

1. Откройте консоль приложение **Консоль**.
2. В разделе **ФАЙЛЫ** выберите **system.log**.
3. На панели меню вверху выберите **Файл** > **Сохранить копию как...** и сохраните файл.

### Windows Phone

На **корпоративном портале Windows Phone** пользователь должен выбрать **...** для доступа к меню, а затем **Отправить журналы**. Этот параметр доступен как до, так и после входа на портал.

### Windows

Для корпоративного портала Windows файлы журнала расположены в каталоге *%localappdata%\Packages\Microsoft.CompanyPortal_8wekyb3d8bbwe\LocalState*.



<!--HONumber=Sep16_HO2-->


