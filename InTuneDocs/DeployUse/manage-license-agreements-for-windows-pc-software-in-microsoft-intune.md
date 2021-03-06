---
title: "Управление лицензионными соглашениями программного обеспечения для компьютеров под управлением программного клиента Intune | Microsoft Intune"
description: "Intune позволяет управлять лицензионными соглашениями для программного обеспечения, приобретенного в рамках соглашений с Microsoft о корпоративном лицензировании, а также для программного обеспечения, приобретенного другими способами."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 09/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c59d8635-3f66-40f5-824a-a71c738e0341
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f01f2715ebd5666b53de848f06300e7aa3344caf
ms.openlocfilehash: e4febff0ede35f40fd2b0f96fab401a58fb5cb13


---

# Управление лицензионными соглашениями для программного обеспечения компьютеров Windows в Microsoft Intune
Microsoft Intune позволяет добавлять данные о лицензионных соглашениях для программного обеспечения, приобретенного в рамках соглашений о корпоративном лицензировании Майкрософт, и управлять этими данными. Это также можно сделать для программного обеспечения Майкрософт и сторонних разработчиков, приобретенного через другие каналы. Эту информацию можно организовать в логические группы.

> [!IMPORTANT]
> Возможность предоставляется исключительно в целях удобства; точность данных не гарантируется. На эту функцию не стоит полагаться при подтверждении факта выполнения взятых на себя обязательств по соглашениям с Майкрософт о корпоративном лицензировании. Корпорация Майкрософт обязуется не использовать собираемые данные для расследования возможных нарушений или подтверждения выполнения взятых вами на себя обязательств по подписанным лицензионным соглашениям.
>
> Лицензии, добавляемые к Intune, не влияют на лицензионные соглашения или права на использование программного обеспечения. Например, при удалении пары "лицензия-соглашение" из Intune существующие лицензионные соглашения между вами и корпорацией Майкрософт не удаляются и не аннулируются.

В рабочей области **Лицензии** консоли администрирования Intune можно выполнять следующие задачи.

-   Добавление и изменение соглашений о корпоративном лицензировании Майкрософт.

-   Добавление и изменение соглашений о лицензировании другого программного обеспечения.

-   Управление лицензиями и группами.

-   Сравнение сведений о правах на использование, полученных службой Intune с сайта VLSC, с данными инвентаризации программного обеспечения Майкрософт, обнаруженного службой Intune на управляемых компьютерах Windows.

Кроме того, можно создавать отчеты по лицензиям, содержащие количество установок и лицензий для программного обеспечения. Отчеты по лицензиям могут помочь в оценке общей ситуации с лицензиями на программное обеспечение Майкрософт и сторонних производителей.

> [!TIP]
> Рабочая область **Лицензии** будет отображаться на консоли администрирования, только если осуществляется управление по крайней мере одним ПК Windows с клиентом Intune.

## Добавление соглашений корпоративного лицензирования Майкрософт
Соглашения корпоративного лицензирования Intune предоставляют сведения о программном обеспечении, приобретенном в рамках соглашений корпоративного лицензирования Майкрософт. Можно добавить соглашения о корпоративном лицензировании Майкрософт в Intune, указав совпадающие пары номеров соглашений. Номера соглашения или разрешения должны совпадать с номерами действительных лицензий или соглашений о регистрации. Пары номеров соглашений предоставляются в [Центре поддержки корпоративных лицензий (VLSC)](http://go.microsoft.com/fwlink/?LinkID=223842)во время приобретения лицензионных соглашений.

1.  В [консоли администрирования Microsoft Intune](https://account.manage.microsoft.com/admin/default.aspx) выберите **Лицензии**.

2.  На странице **Добавление соглашений** в разделе **Выбор типа соглашения**выберите **Соглашение корпоративного лицензирования**.

3.  В разделе **Добавление сведений о соглашении** укажите, хотите ли вы отправить файл или вручную добавить данные.

    -   **Отправить CSV-файл со сведениями о соглашениях**. Нажмите кнопку **Обзор** и выберите отправляемый CSV-файл.

        -   Файл может содержать два или три столбца: два только для пар соглашений или три, если необходимо добавить понятное имя для каждой пары соглашений.

        -   Общее число знаков в паре номеров соглашения не должно превышать 16 символов ASCII.

        -   Поддерживаются только символы ASCII.

        -   В названии соглашения нельзя использовать следующие символы: **~ ! @ # $ ^ &amp; &#42; ( ) = + [ ] { } \ | ; : ' " &lt; &gt; /**. Использование пробелов допускается.

        -   Имя файла должно содержать не более 128 символов.

        -   Файл должен содержать как минимум одну пару соглашений и максимум 5000 пар соглашений.

        **Формат файла**

        Создать этот файл можно, добавив свои пары соглашений в новый текстовый файл в одном из перечисленных ниже форматов в зависимости от типа организации, которая была зарегистрирована с помощью VLSC. Укажите по одной паре номеров соглашения в строке.

        -   **Клиенты Open Value:** *номер соглашения*, *повтор номера соглашения*, *название соглашения*

        -   **Клиенты Open:** *номер разрешения*, *связанный номер соглашения*, *название соглашения*

        -   **Клиенты Select и Enterprise:** *номер соглашения*, *связанный номер соглашения о регистрации*, *название соглашения*

        При добавлении нового соглашения в форме **Добавление соглашений** будет предложено выбрать файл.

        Ниже представлен пример содержимого CSV-файла для клиента Open Value.

        `01-07001, 01-07001, Office agreements`

    -   **Добавить сведения о соглашении вручную**. Укажите следующие данные и введите пары номеров соглашений в полях **Номер разрешения/соглашения** и **Номер лицензии/соглашения о регистрации/клиента**. После ввода обоих номеров щелкните значок **Добавить пару**, чтобы сохранить эти номера, после чего при необходимости добавьте новую пару.

        -   **Название соглашения**: укажите уникальное имя для соглашения.

            Длина названия соглашения не может превышать 256 символов. Название не может содержать следующие символы: **~ ! @ # $ ^ &amp; &#42; ( ) = + [ ] { } \ | ; : ' " &lt; &gt; /**. Использование пробелов допускается.

        -   **Номер разрешения/соглашения**: введите номер разрешения/соглашения пары лицензий.

        -   **Номер лицензии/соглашения о регистрации/клиента**: введите номер лицензии/соглашения о регистрации/клиента пары лицензий.

        > [!NOTE]
        > Если добавить несколько пар номеров соглашений, в Intune создается одно соглашение с указанным названием, в которое будут включены все добавленные пары.

    Вы можете щелкнуть **+** для добавления еще одной пары номеров соглашения или **-** для удаления уже введенной пары номеров соглашения.

4.  В области **Выбрать лицензионную группу** выполните одно из указанных ниже действий.

    -   **Добавить соглашения в группу "Неназначенные соглашения"**. Выберите этот пункт, если не хотите добавлять новые соглашения в группу лицензирования.

    -   **Добавить соглашения в новую лицензионную группу**. Введите имя для новой группы лицензирования.

    -   **Добавить соглашения в существующую лицензионную группу**. В списке **Имя группы** выберите лицензионную группу, в которую требуется добавить соглашения.

5.  Нажмите кнопку **ОК**.

Отобразится представление **Все соглашения**, и Intune подключится к Microsoft VLSC, чтобы проверить указанные пары номеров соглашений.

Чтобы обновить данные о корпоративном лицензировании после добавления лицензионных соглашений в Intune, на странице **Обзор лицензий** щелкните **Обновить**. Это действие получает текущие сведения о лицензиях из [центра поддержки корпоративных лицензий Майкрософт (VLSC)](http://go.microsoft.com/fwlink/?LinkId=223842).

> [!IMPORTANT]
> До обновления сведений о корпоративном лицензировании данные в списке соглашений и сведения о правах на странице **Обзор соглашений** могут не совпадать.

После обновления сведений о корпоративном лицензировании можно сравнить сведения о лицензиях с обнаруженным программным обеспечением Майкрософт в рабочей области **Приложения** . Кроме того, вы можете запустить следующие отчеты о лицензиях.

-   **Отчеты о приобретении лицензий** позволяют просмотреть лицензированное программное обеспечение в выбранных группах лицензий для выявления пробелов в покрытии лицензионных соглашений.

-   **Отчеты об установке лицензий** помогают оценить достаточность покрытия лицензионных соглашений.

> [!NOTE]
> В поле **Название продукта** для всех соглашений о корпоративном лицензировании с Майкрософт отображается значение **Нет данных**.

## Добавление и изменение соглашений о лицензировании программного обеспечения.
Наряду с соглашениями корпоративного лицензирования Майкрософт в Intune также вы можете добавить сторонние лицензионные соглашения. Такие соглашения могут включать стороннее ПО или ПО Майкрософт, приобретенное в сети розничной торговли.

> [!IMPORTANT]
> Перед добавлением соглашения, отличного от соглашения корпоративного лицензирования, необходимо зарегистрировать в Intune как минимум один компьютер под управлением Windows.  Кроме того, как минимум один зарегистрированный компьютер должен отправить лицензируемый пакет ПО, который будет использоваться для добавления соглашения.

### Добавление других соглашений о лицензировании программного обеспечения

1.  В [консоли администрирования Microsoft Intune](https://account.manage.microsoft.com/admin/default.aspx) выберите **Лицензии**.

2.  В разделе **Другие соглашения о лицензировании программного обеспечения** щелкните **Добавить соглашения**.

3.  На странице **Добавление соглашений** в разделе **Выбор типа соглашения** выберите **Другое соглашение о лицензировании программного обеспечения**.

4.  В области **Добавление сведений о соглашении** , укажите следующее данные.

    -   **Agreement name** (обязательно). Длина названия соглашения не может превышать 256 символов. Название не может содержать следующие символы: **~ ! @ # $ ^ &amp; &#42; ( ) = + [ ] { } \ | ; : ' " &lt; &gt; /**. Использование пробелов допускается.

    -   **Издатель** (обязательно). Когда вы начинаете печатать имя издателя, служба получает все имена издателей, содержащие вводимые буквы. Например, если напечатать слово soft, служба получит все имена, содержащие это сочетание букв, например Microsoft и Microsoft Research. Имена издателей поступают из каталога активов программного обеспечения. Прежде чем вводить название продукта, необходимо выбрать имя издателя.

        > [!IMPORTANT]
        > Компания, которую вы хотите добавить, может отсутствовать в этом списке. Соглашения о лицензировании ПО можно добавить только для тех компаний, которые уже присутствуют в каталоге активов. Тем не менее, корпорация Майкрософт постоянно работает над тем, чтобы добавить в этот каталог наиболее популярные программы. Если вы хотите отправить запрос для добавления вашей компании в этот список, это можно сделать на [сайте Intune Uservoice](https://microsoftintune.uservoice.com/).

    -   **Название продукта** (обязательно). Когда вы начинаете печатать название продукта, служба получает все названия продуктов, содержащие вводимые буквы. Прежде чем можно будет указать **название продукта** , необходимо указать **издателя**.

    -   **Количество лицензий** (обязательно). Введите число приобретенных лицензий.

    -   **Дата начала срока действия лицензии**. Введите дату начала срока действия лицензионного покрытия.

    -   **Дата окончания срока действия лицензии**. Введите дату окончания срока действия лицензионного покрытия.

    -   **Сведения о соглашениях**. Можно дополнительно указать контактные данные, ключи регистрации и прочие сведения.

5.  В области **Выбрать лицензионную группу** выполните одно из указанных ниже действий.

    -   Если добавлять новые соглашения в новую или существующую лицензионную группу не требуется, выберите **Добавить соглашения в группу "Неназначенные соглашения"** . Добавить соглашения в пользовательские лицензионные группы можно в любое время.

    -   Чтобы добавить новые соглашения в новую лицензионную группу, выберите **Добавить соглашения в новую лицензионную группу** . Будет предложено ввести имя новой лицензионной группы.

    -   Чтобы добавить новые соглашения в существующую лицензионную группу, выберите **Добавить соглашения в существующую лицензионную группу** . В списке **Имя группы** выберите лицензионную группу, в которую требуется добавить соглашения.

6.  Нажмите кнопку **ОК**.

Откроется представление списка **Все соглашения** .

## Управление лицензионными соглашениями
Соглашения о лицензировании программного обеспечения можно добавлять в лицензионные группы. Создание лицензионных групп позволяет организовать лицензионные соглашения в логические блоки, удобные для организации. Кроме того, вы можете удалить ранее созданные лицензионные соглашения.

|||
|-|-|
|Задача|Подробные сведения|
|Создание лицензионной группы|На странице **Обзор** в рабочей области **Лицензии** выберите пункт **Создать лицензионную группу** в меню **Задачи**. **Примечание.** Можно создать до 500 групп лицензирования.|
|Переименование лицензионной группы|В рабочей области **Лицензии** выберите группу лицензирования и щелкните **Изменить лицензионную группу** в меню **Задачи**.|
|Удаление лицензионной группы|В рабочей области **Лицензии** выберите группу лицензирования и щелкните **Удалить лицензионную группу** в меню **Задачи**. **Совет.** При удалении лицензионной группы все лицензии из этой группы перемещаются в группу **Неназначенные соглашения**.|
|Удаление лицензионного соглашения|В рабочей области **Лицензии** выберите соглашение и нажмите кнопку **Удалить**. **Совет.** После удаления соглашений о корпоративном лицензировании нажмите кнопку **Обновить** на странице **Обзор лицензий** или на вкладке **Общие** для конкретной группы лицензирования, чтобы обновить данные о лицензиях.|



<!--HONumber=Sep16_HO2-->


