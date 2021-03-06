---
title: "Получение сведений об операциях с помощью отчетов | Microsoft Intune"
description: "Сведения о создании отчетов о программном обеспечении, оборудовании и лицензиях в организации, а также управлении ими."
keywords: 
author: Nbigman
manager: angrobe
ms.date: 06/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 857309c2-61c9-4c22-becf-4839fedeaece
ms.reviewer: pbala
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 936989a19c836c558efc43e3778180d5d4a8fb7a
ms.openlocfilehash: e6b81b1bfb53f0a85d5550b7a25ece1b948afeb6



---

# Получение сведений об операциях Microsoft Intune с помощью отчетов
В этом разделе представлены сведения о создании отчетов Microsoft Intune, содержащих данные о программном обеспечении, оборудовании и лицензиях на ПО в организации, и управлении ими.

## Использование отчетов
Отчеты Intune содержат сведения о программном обеспечении, оборудовании и лицензиях в организации. Отчеты позволяют точно устанавливать текущие потребности или прогнозировать будущие затраты. В рабочей области **Отчеты** находятся средства для создания отчетов и управления ими. 

### Типы отчетов

|Тип отчета|Описание|
|---------------|---------------|
|**Update Reports**|Отображают список обновлений ПО, успешно установленных на компьютерах организации. Кроме того, в них указан список сбоев обновлений, обновлений, ожидающих установки, и требующихся обновлений. Дополнительные сведения об обновлениях программного обеспечения см. в статье [Keep Windows PCs up to date with software updates in Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md) (Обновление программного обеспечения на компьютерах Windows с помощью Microsoft Intune).|
|**Отчеты об обнаруженном ПО**|Отображают список программного обеспечения, установленного на компьютерах в организации. Также указаны версии ПО. Отображенные сведения можно отфильтровать по издателю ПО и категории ПО. Развернув обновления в списке с помощью стрелки рядом с элементом списка, можно просмотреть дополнительные сведения (например, о компьютерах, на которых установлено обновление).<br /><br />При снятии компьютеров с учета или изменении их членства в группах Intune может пройти несколько минут, прежде чем эти изменения отобразятся в отчете об обнаруженном программном обеспечении. Для отображения наиболее точных данных инвентаризации программного обеспечения после снятия компьютеров с учета или изменения их членства в группах подождите несколько минут и только после этого запустите отчет об обнаруженном ПО, включающего эти компьютеры.|
|**Computer Inventory Reports**|Отображают сведения об управляемых компьютерах в организации. Этот отчет можно использовать для планирования закупок оборудования и анализа потребности организации в определенном оборудовании. Дополнительные сведения о работе с управляемыми компьютерами см. в статье [Manage Windows PCs with Microsoft Intune](manage-windows-pcs-with-microsoft-intune.md) (Управление компьютерами Windows с помощью Microsoft Intune).|
|**Отчеты об инвентаризации мобильных устройств**|Отображают сведения о мобильных устройствах в организации. Отображенные сведения можно отфильтровать по группам, является ли устройство устройством со снятой защитой или с административным доступом и по операционной системе.|
|**License Purchase Reports**|Отображают названия программных продуктов всего лицензированного ПО в выбранных лицензионных группах на основе лицензионных соглашений. Если сведения о лицензиях не обновлялись более 24 часов, обновление будет выполнено во время создания отчета о лицензиях. Отчет о лицензиях не используется для точного подсчета названий программ или доказательства соблюдения условий соглашений. Отчет — это вспомогательное средство для принятия решений о лицензировании в организации. Intune может не обнаружить некоторые продукты, для которых может существовать корпоративная лицензия Майкрософт. Доступны следующие фильтры:<br /><br />**Все соглашения** — отображаются все лицензированные программные продукты, управляемые Intune.<br /><br />**Соглашения корпоративного лицензирования** — отображаются только программные продукты центра Volume Licensing Service Center (VLSC).<br /><br />**Другие соглашения о лицензировании программного обеспечения** — отображаются программные продукты, управляемые за пределами VLSC.|
|**License Installation Reports**|Сравнивают число установленных программных продуктов на компьютерах организации с текущим лицензионным покрытием, предусмотренным соглашением, согласно VLSC. Доступны следующие фильтры:<br /><br />**Все соглашения** — отображаются все лицензированные программные продукты, управляемые Intune.<br /><br />**Соглашения корпоративного лицензирования** — отображаются только программные продукты центра VLSC.<br /><br />**Другие соглашения о лицензировании программного обеспечения** — отображаются программные продукты, управляемые за пределами VLSC.|
|**Terms and Conditions Reports**|Показывают, приняли ли пользователи развернутые вами условия, а также версии принятых условий. Можно указать до 10 пользователей, для которых отображаются сведения о принятии всех развернутых условий, или же просматривать состояние принятия определенного условия.|
|**Отчеты о приложениях, не соответствующих политике**|Отображают сведения об установивших приложения пользователях, которые находятся в списках приложений, соответствующих и не соответствующих политике. Используйте этот отчет, чтобы найти пользователей и устройства, которые не соответствуют политикам приложений компании.|
|**Certificate Compliance Reports**|Показывают сертификаты, выданные пользователям и устройствам через SCEP или PKCS 12 (.PFX). Используйте этот отчет, чтобы найти выданные, отозванные сертификаты и сертификаты с истекшим сроком действия.|
|**Device History Reports**|Показывают журнал действий списания, очистки и удаления. Используйте этот отчет, чтобы выяснить, кто инициировал действия на устройствах в прошлом.|
|**Отчеты аттестации работоспособности**|Показывают работоспособность мобильных устройств.|
|**Отчет об оборудовании Mac OS X**|Отображает сведения об оборудовании для всех зарегистрированных устройств Mac OS X в выбранных группах. Данные об инвентаризации оборудования, собираемые с этих устройств, см. в статье [Получение сведений об устройствах с помощью инвентаризации в Microsoft Intune](understand-your-devices-with-inventory-in-microsoft-intune.md).|
|**Отчет о программном обеспечении Mac OS X**|Отображает сведения о программном обеспечении, установленном на всех устройствах Mac OS X в выбранных группах. В отчете указано имя программного обеспечения (в виде идентификатора набора), краткое (или понятное) имя версии, версия и количество устройств с установленным программным обеспечением.|

#### Создание отчета

1.  В консоли администрирования Intune выберите **Отчеты**. Выберите тип отчета, который требуется создать, как описано в предыдущей таблице.

2.  На странице **Создать новый отчет** примите значения по умолчанию или настройте их для фильтрации результатов, возвращаемых отчетом. Например, можно выбрать, чтобы в отчете об обнаруженном ПО отображалось только программное обеспечение, опубликованное Майкрософт.

3.  Выберите **Просмотреть отчет**, чтобы открыть отчет в новом окне.

Чтобы отсортировать отчет по любому отображаемому столбцу, выберите заголовок столбца. Кроме того, в некоторых отчетах можно разворачивать элементы списка и просматривать дополнительные сведения.

## Дополнительные действия с отчетами
Отчеты поддерживают выполнение следующих действий.

|Действие|Дополнительные сведения|
|----------|--------------------|
|**Печать**|В открытом отчете выберите значок печати и следуйте инструкциям.|
|**Экспортировать**|В открытом отчете выберите значок экспорта и следуйте инструкциям. Можно экспортировать отчет в CSV- или HTML-файл.|
|**Сохранить**|На странице **Создание отчета** каждый пользователь может сохранить до 100 отчетов. Настройте параметры отчета в соответствии со своими требованиями, а затем нажмите кнопку **Сохранить**или **Сохранить как** (чтобы задать другое имя).|
|**Загрузить**|На странице **Создание отчета** нажмите кнопку **Загрузить**, чтобы извлечь сохраненные ранее наборы параметров отчета.|
|**Удалить**|В рабочей области **Отчеты** выберите нужный тип отчета и нажмите кнопку **Загрузить**. Затем в списке отчетов щелкните значок удаления (x) рядом с отчетом.|

### См. также
[Мониторинг и отчеты в Microsoft Intune](monitoring-and-reports-with-microsoft-intune.md)



<!--HONumber=Aug16_HO5-->


