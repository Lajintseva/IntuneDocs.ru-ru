---
# required metadata

title: Регистрация устройств iOS с использованием помощника по настройке в Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 46e5b027-4280-4809-b45f-651a6ab6d0cd

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Регистрация устройств iOS с Apple Configurator с использованием помощника по настройке
Intune поддерживает регистрацию корпоративных устройств iOS с помощью средства [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017), запущенного на компьютере Mac. Этот процесс сбрасывает настройки устройства до заводских и подготавливает его для запуска помощника по настройке новым пользователем устройства с предварительно установленными политиками компании.


## Регистрация с помощником по настройке для устройств iOS с помощью Microsoft Intune
С помощью Apple Configurator можно сбросить параметры устройств iOS и подготовить их для настройки для нового пользователя.  При использовании этого метода требуется подключить устройство iOS к USB-порту на компьютере Mac для настройки корпоративной регистрации (подразумевается, что вы используете Apple Configurator 2.0). В большинстве сценариев требуется, чтобы политика, применяемая к устройству iOS, поддерживала *соответствие пользователей* для включения приложение корпоративного портала Intune.

**Необходимые компоненты**
* Физический доступ к устройствам iOS — устройства должны быть сброшены до заводских настроек и не иметь парольной защиты.
* Серийные номера устройств — см. раздел [Получение серийного номера устройства iOS](https://support.apple.com/en-us/HT204308).
* Соединительные USB-кабели
* Компьютер Mac с [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)


1.  **Создание группы мобильных устройств** (необязательно). Если вашей организации нужны группы мобильных устройств для управления устройствами, создайте их. [Use groups to manage users and devices with Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md) (Использование групп для управления пользователями и устройствами в Microsoft Intune).

2.  **Создание профиля для устройств**. Профиль регистрации устройств определяет параметры, применяемые к группе устройств. Создайте профиль регистрации устройств для устройств iOS, зарегистрированных с помощью Apple Configurator, если вы еще этого не сделали.

    ###### Создание профиля

    1.  В [консоли администрирования Microsoft Intune](http://manage.microsoft.com) перейдите в меню **Политика** &gt; **Корпоративные устройства** и нажмите кнопку **Добавить...**.

    ![Создание профиля регистрации устройства](../media/pol-sa-corp-enroll.png)

    2.  Введите сведения для профилей устройств.

        -   **Имя** — имя профиля регистрации устройства. (Не отображается для пользователей.)

        -   **Описание** — описание профиля регистрации устройства. (Не отображается для пользователей.)

        -   **Сведения о регистрации** — указывает способ регистрации устройств.

            -   **Запрос соответствия пользователей** — устройство iOS может быть связано с пользователем во время начальной настройки и затем получить доступ к данным и электронной почте организации от имени этого пользователя. В большинстве сценариев помощника по настройке используется **Запрос соответствия пользователей**.
            Этот режим поддерживает несколько сценариев.

                -   **Корпоративное личное устройство** — возможность "Выбери свое устройство" (CYOD) аналогична личным устройствам, но администратор имеет определенные привилегии, включая разрешение на очистку, сброс, администрирование и отмену регистрации устройства. Пользователь устройства может устанавливать приложения и имеет большинство других разрешений для использования устройства, не заблокированных политикой управления.

                -   **Учетная запись диспетчера регистрации устройств** — устройство регистрируется с помощью конкретной учетной записи администратора Intune. Ей можно управлять как личной учетной записью, но устанавливать приложения, выполнять очистку, сброс, администрирование и отмену регистрации устройства может только пользователь, который знает учетные данные диспетчера регистрации. Сведения о регистрации устройства, которое совместно используется несколькими пользователями с общей учетной записью, см. в статье [Enroll corporate-owned devices with the Device Enrollment Manager in Microsoft Intune](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) (Регистрация устройств организации с помощью диспетчера регистрации устройств в Microsoft Intune).

            -   **Без соответствия пользователей** — устройство не связано с пользователем. Используйте эту принадлежность для устройств, которые выполняют задачи без осуществления доступа к локальным данным пользователя. Приложения, требующие принадлежности пользователя, отключены или не будут работать.

        -   **Предварительное назначение группы устройств** — все устройства, развернувшие данный профиль, будут изначально принадлежать к этой группе. После регистрации можно повторно назначить устройства.

          -  **Программа регистрации устройств** — параметры программы регистрации устройств (DEP) Apple не могут использоваться с помощником по настройке регистрации. Убедитесь, что переключатель находится в состоянии **выключено**.

    3.  Нажмите кнопку **Сохранить профиль**, чтобы добавить профиль.

3.  **Добавление устройств с iOS для регистрации с помощью помощника по настройке**. В [консоли администрирования Microsoft Intune](http://manage.microsoft.com) перейдите в меню **Группы** &gt; **Все устройства** &gt; **Все корпоративные устройства** &gt; **Все устройства**, а затем нажмите кнопку **Добавить устройства…**. Добавить устройства можно двумя способами.

    ![Диалоговое окно "Добавление устройств"](../media/pol-SA-enroll-iOS-SetupAssistant.png)

    -   **Отправка CSV-файла с серийными номерами** — создайте список значений с разделителями-запятыми (CSV-файл) с двумя столбцами без заголовка с ограничением в 5000 устройств или 5 МБ на CSV-файл.

        |||
        |-|-|
        |&lt;Серийный номер 1&gt;|&lt;Сведения об устройстве 1&gt;|
        |&lt;Серийный номер 2&gt;|&lt;Сведения об устройстве 2&gt;|
        В текстовом редакторе CSV-файл отображается следующим образом:

        ```
        0000000,PO 1234
        111111111,PO 1234
        ```

    -   **Добавление сведений об устройстве вручную** — введите серийный номер и сведения об устройстве не более чем для пяти устройств.

    > [!NOTE]
    > Если позже потребуется удалить устройства организации из системы управления Intune, то для отключения регистрации устройства может потребоваться удалить серийный номер устройства из Intune в группе устройств **По серийному номеру iOS** в разделе **Корпоративные устройства с предварительной регистрацией**.  Если Intune выполняет процедуру аварийного восстановления примерно в то же время, когда были удалены серийные номера, необходимо убедиться, что в этой группе присутствуют только серийные номера активных устройств.

    Нажмите кнопку **Далее**.

4.  **Выбор устройств для регистрации**. Подтвердите регистрируемые устройства. Уже зарегистрированные серийные номера или устройства, зарегистрированные другими способами, невозможно импортировать. Для продолжения нажмите кнопку **Далее**.

5.  **Назначение профиля**. Выберите назначаемый добавленным устройствам профиль из списка доступных профилей, просмотрите **Сведения о профиле регистрации** и нажмите кнопку **Готово**. Устройства, добавленные вручную, можно назначить любому профилю регистрации.

6.  **Экспорт профиля для развертывания на устройствах с iOS**. В [консоли администрирования Microsoft Intune](http://manage.microsoft.com) перейдите в меню **Политика** &gt; **Регистрация корпоративных устройств**, а затем выберите профиль устройств для развертывания на мобильных устройствах. Выберите **Экспортировать...**. на панели задач. Скопируйте и сохраните **URL-адрес профиля**. Позже его потребуется отправить в Apple Configurator для определения профиля Intune, использующегося устройствами iOS.
    Для поддержки Apple Configurator 2 необходимо отредактировать URL-адрес профиля 2.0. Замените
    ```
    https://manage.microsoft.com/EnrollmentServer/Discovery.svc/iOS/ESProxy?id=
    ```
    с

    ```
    https://appleconfigurator2.manage.microsoft.com/MDMServiceConfig?id=
    ```

   Этот URL-адрес профиля будет отправлен в службу Apple DEP службу с помощью Apple Configurator в следующей процедуре для определения профиля Intune, используемого устройствами iOS.



7.  **Подготовка устройства с помощью Apple Configurator**. Устройства с iOS подключаются к компьютеру Mac и регистрируются в системе управления мобильными устройствами.

    1.  На компьютере Mac откройте **Apple Configurator 2**. В строке меню щелкните **Apple Configurator 2** и выберите **Preferences** (Предпочтения).

         > [!WARNING]
         > Во время процесса регистрации настройки устройств будут сброшены. Рекомендуется выполнить сброс устройства и включить питание. При подключении устройства на нем должен быть экран **Hello**.

    2. На панели предпочтений выберите **Servers** (Серверы) и щелкните значок "+" под левой панелью, чтобы запустить мастер сервера MDM. Нажмите кнопку **Далее**.

    3. Введите значения в поля **Имя** и **URL-адрес регистрации** для сервера MDM с шага 6 выше. В поле "URL-адрес регистрации" введите URL-адрес профиля регистрации, экспортированный из Intune. Нажмите кнопку **Далее**.  

       Если появится предупреждение о требованиях к профилю доверия для Apple TV, можно отменить параметр **Trust Profile** (Профиль доверия), щелкнув серый значок "X". Можно также игнорировать любые предупреждения привязки сертификата. Чтобы продолжить, нажимайте кнопку **Next** (Далее) до завершения работы мастера.

    4.  В панели **Servers** (Серверы) нажмите кнопку Edit (Изменить) рядом с профилем нового сервера. Убедитесь, что URL-адрес регистрации точно соответствует URL-адресу, экспортированному из Intune. Повторно введите исходный URL-адрес, если он отличается, нажмите кнопку **Сохранить** для сохранения профиля регистрации, экспортированного из Intune.

    5.  Подключите мобильные устройства iOS к компьютеру Apple с помощью USB-адаптера.

        > [!WARNING]
        > Во время процесса регистрации настройки устройств будут сброшены. Рекомендуется выполнить сброс устройства и включить питание. При подключении запуске помощника по настройке на устройстве должен быть экран **приветствия**.

    6.  Выберите **Prepare** (Подготовка). На панели **Prepare iOS Device** (Подготовка устройства iOS) выберите **Manual** (Вручную) и нажмите кнопку **Next** (Далее).

    7. На панели **Enroll in MDM Server** (Регистрация на сервере MDM) выберите имя созданного сервера и нажмите кнопку **Next** (Далее).

    8. На панели **Supervise Devices** (Контроль за устройствами) выберите уровень контроля и нажмите кнопку **Next** (Далее).

    9. На панели **Create an Organization** (Создание организации) выберите существующую **организацию** или создайте новую организацию, а затем нажмите кнопку **Next** (Далее).

    10. На панели **Configure iOS Setup Assistant** (Настройка помощника по настройке iOS) выберите действия, которые будут отображаться для пользователя, и нажмите кнопку **Prepare** (Подготовить). При появлении запроса пройдите проверку подлинности, чтобы обновить параметры отношения доверия.  

    11. После завершения подготовки устройства iOS можно отключить кабель USB.  

8.  **Распространение устройств**. Теперь устройства готовы к регистрации в среде организации. Выключите устройства и распределите их пользователям. При включении устройства запустится помощник по настройке.



### См. также
[Подготовка к регистрации устройств](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=Jun16_HO3-->

