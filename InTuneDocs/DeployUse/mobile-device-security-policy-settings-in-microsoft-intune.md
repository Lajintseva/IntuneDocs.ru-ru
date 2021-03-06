---
title: "Параметры политики безопасности мобильных устройств | Microsoft Intune"
description: "Сведения об использовании Intune для настройки ряда параметров, которые можно развернуть на управляемых устройствах в организации."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e5ab3b76-08af-4893-b294-fb6627fdc4c6
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 388426657c5fa96289f5e14a85e8c299e4b50037
ms.openlocfilehash: ac19128499f078b4fe7d16713f18c78b248d38db



---

# Параметры политики безопасности мобильных устройств в Microsoft Intune
> [!IMPORTANT]
> Microsoft Intune теперь включает отдельные политики конфигурации для каждой платформы устройств. Эти политики содержат самые последние параметры для настройки устройств. Вы можете продолжать использовать политики безопасности мобильных устройств, и любые существующие развертывания по-прежнему будут работать. Тем не менее следует как можно быстрее запланировать переход на новые политики конфигурации, так как политика безопасности мобильных устройств в будущем будет удалена.

Политики безопасности мобильных устройств Intune можно использовать для настройки ряда параметров, которые можно развернуть на управляемых устройствах в организации. Эти параметры используются для управления функциями и безопасностью устройств.

Можно создать и развернуть политики безопасности мобильных устройств для следующих типов устройств.

-   Windows RT 8.1 и зарегистрированные устройства Windows 8.1

-   Windows RT

-   Windows Phone 8 и Windows Phone 8.1

-   iOS

-   Android и Samsung KNOX

> [!NOTE]
> Некоторые параметры применяются не ко всем устройствам. Полный список параметров, которые можно настроить, см. в следующей таблице.

## параметры безопасности;

|Имя параметра|Windows 8.1 и Windows RT 8.1|Windows RT|Windows Phone 8 и Windows Phone 8.1|iOS|Android и Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Требовать пароль для разблокировки мобильных устройств**|Нет|Нет|Да|Да|Да|
|**Требуемый тип пароля**<br /><br />Этот параметр определяет необходимый тип пароля, например только цифровой или буквенно-цифровой.|да|Да|Да|Да|Нет|
|**Требуемый тип пароля — минимальное число наборов символов**<br /><br />Существует четыре набора символов: строчные буквы, прописные буквы, цифры и символы. Этот параметр определяет, сколько различных наборов символов должно быть включено в пароль. Но для устройств iOS он указывает количество символов, которое должно быть включено в пароль.|да|Да|Да|Да|Нет|
|**Минимальная длина пароля**|Да|Да|Да|Да|Да|
|**Разрешить простые пароли**<br /><br />К простым паролям относятся 0000 и 1234.|Нет|Нет|Да|Да|Нет|
|**Число разрешенных неудачных попыток входа перед очисткой устройства**|Да|Да|Да|Да|Да|
|**Время бездействия (в минутах), по истечении которого экран выключается**<sup>1</sup>|Да|Да|Да|Да|Да|
|**Срок действия пароля (дней)**|Да|Да|Да|Да|Да|
|**Запоминать историю паролей**|Да|Да|Да|Да|Да|
|**Вести журнал паролей** — **Запретить использование предыдущих паролей**|Да|Да|Да|Да|Да|
|**Качество пароля**|Нет|Нет|Нет|Нет|Да|
|**Разрешить графические пароли и ПИН-коды**|Да|Да|Нет|Нет|Нет|
|**Минут бездействия до требования пароля**|Нет|Нет|Нет|Да|Нет|
|**Разрешить разблокировку по отпечатку пальца**|Нет|Нет|Нет|iOS 7 и более поздних версий|Нет|
<sup>1</sup> При настройке для устройств iOS параметры **Время бездействия (в минутах), по истечении которого экран выключается**, и **Время бездействия (в минутах), по истечении которого требуется ввод пароля**, применяются последовательно. Например, если для обоих параметров задать значение **5** минут, через 5 минут экран автоматически выключится, а устройство будет заблокировано еще спустя 5 минут. Однако если пользователь включит экран вручную, второй параметр будет сразу же применен. В предыдущем примере после выключения экрана пользователем устройство блокируется на 5 минут позже.

Если на устройствах под управлением Windows RT развернута политика длины пароля, пользователи будут вынуждены сбросить пароль, даже если их текущий пароль соответствует требованиям политики.

## Параметры шифрования

|Имя параметра|Windows 8.1 и Windows RT 8.1|Windows RT|Windows Phone 8 и Windows Phone 8.1|iOS|Android и Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Требовать шифрование на мобильном устройстве**<sup>1</sup><br /><br />Для устройств Windows Phone 8 необходимо установить значение **Да**.<br /><br />Чтобы включить шифрование на устройствах iOS, включите параметр **Запрашивать пароль для разблокировки мобильных устройств**.|Да|Нет|Да|Нет|Да|
|**Обязательное использование шифрования на картах памяти**<br /><br />Этот параметр применяется к устройствам, которые, помимо прочего, управляются Exchange ActiveSync.|н/д|н/д|н/д <br />Приложения и связанные данные автоматически шифруются.|н/д|да|
<sup>1</sup> Дополнительная информация для устройств, работающих под управлением Windows 8.1.

-   Чтобы применить шифрование на устройствах, работающих под управлением Windows 8.1, необходимо установить [обновление клиента MDM для Windows за декабрь 2014 года](http://support.microsoft.com/kb/3013816) на каждом устройстве.

-   Если включить этот параметр для устройств с Windows 8.1, все пользователи таких устройств должны иметь учетную запись Майкрософт.

-   Для выполнения шифрования устройства должны соответствовать требованиям к сертификации оборудования Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) .

-   При включении шифрования для устройства ключ восстановления доступен только из учетной записи Майкрософт пользователя, к которой осуществляется доступ из его учетной записи OneDrive. Получить этот ключ от имени пользователя нельзя.

## Параметры защиты от вредоносных программ

|Имя параметра|Windows 8.1 и Windows RT 8.1|Windows RT|Windows Phone 8 и Windows Phone 8.1|iOS|Android и Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Требовать использование сетевого брандмауэра**|Да|Нет|Нет|Нет|Нет|
|**Включить SmartScreen**|Да|Нет|Нет|Нет|Нет|

## Системные параметры

|Имя параметра|Windows 8.1 и Windows RT 8.1|Windows RT|Windows Phone 8 и Windows Phone 8.1|iOS|Android и Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Требовать получение автоматических обновлений**|Да|Нет|Нет|Нет|Нет|
|**Требовать получение автоматических обновлений — минимальная классификация обновлений для автоматической установки**<br /><br />Выберите классификацию обновлений, которые будут установлены автоматически.<br /><br />- **Важно**. Выполняется установка всех обновлений, которые классифицируются как важные.<br /><br />- **Рекомендованные**. Выполняется установка всех обновлений, которые классифицируются как важные или рекомендуемые.|да|Нет|Нет|Нет|Нет|
|**Разрешить снимок экрана**|Нет|Нет|Только Windows Phone 8.1|Да|Да (только Samsung KNOX)|
|**Разрешить доступ к центру управления с экрана блокировки**|Нет|Нет|Нет|iOS 7 и более поздних версий|Нет|
|**Разрешить доступ к представлению "Уведомления" с экрана блокировки**|Нет|Нет|Нет|iOS 7 и более поздних версий|Нет|
|**Разрешить доступ к представлению "Сегодня" с экрана блокировки**|Нет|Нет|Нет|iOS 7 и более поздних версий|Нет|
|**Контроль учетных записей пользователей**|Да|Нет|Нет|Нет|Нет|
|**Разрешить отправку диагностических данных**|Да|Нет|Только Windows Phone 8.1|Да|Да (только Samsung KNOX)|
|**Разрешить недоверенные сертификаты TLS**|Нет|Нет|Нет|Да|Нет|
|**Разрешить личный бумажник в заблокированном состоянии**|Нет|Нет|Нет|Да|Нет|
|**Разрешить восстановление заводских настроек**|Нет|Нет|Нет|Нет|Да (только Samsung KNOX)|


## Облачные параметры — документы и данные

|Имя параметра|Windows 8.1 и Windows RT 8.1|Windows RT|Windows Phone 8 и Windows Phone 8.1|iOS|Android и Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Разрешить резервное копирование в iCloud**|Нет|Нет|Нет|Да|Нет|
|**Разрешить синхронизацию документов с iCloud**|Нет|Нет|Нет|Да|Нет|
|**Разрешить синхронизация Photo Stream с iCloud**|Нет|Нет|Нет|Да|Нет|
|**Требовать использование зашифрованного резервного копирования.**|Нет|Нет|Нет|Да|Нет|
|**URL-адрес рабочих папок**<br /><br />Этот параметр задает URL-адрес рабочей папки, чтобы обеспечить синхронизацию документов на устройствах.|да|Нет|Нет|Нет|Нет|
|**Разрешить резервное копирование Google**|Нет|Нет|Нет|Нет|Да (только Samsung KNOX)|

## Облачные параметры — учетные записи и синхронизация

|Имя параметра|Windows 8.1 и Windows RT 8.1|Windows RT|Windows Phone 8 и Windows Phone 8.1|iOS|Android и Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Разрешить использование учетной записи Майкрософт**|Нет|Нет|Только Windows Phone 8.1|Нет|Нет|
|**Разрешить автоматическую синхронизацию учетной записи Google**|Нет|Нет|Нет|Нет|Да (только Samsung KNOX)|

## Параметры электронной почты

|Имя параметра|Windows 8.1 и Windows RT 8.1|Windows RT|Windows Phone 8 и Windows Phone 8.1|iOS|Android и Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Разрешить пользователям загрузку вложений электронной почты**<sup>1</sup>|н/д|н/д|н/д|н/д|н/д|
|**Период синхронизации электронной почты** <br /><br />Этот параметр применяется к устройствам, которые, помимо прочего, управляются Exchange ActiveSync.|н/д|н/д|н/д|н/д|н/д|
|**Разрешить синхронизацию мобильных устройств, которые не полностью поддерживают эти параметры, с Exchange (Exchange ActiveSync)** <br /><br />Этот параметр применяется к устройствам, которые, помимо прочего, управляются Exchange ActiveSync.|н/д|н/д|н/д|н/д|н/д|
|**Сделать учетную запись Майкрософт необязательной в приложении Почта Windows**|Да|Нет|Нет|Нет|Нет|
|**Разрешить пользовательские учетные записи электронной почты**|Нет|Нет|Только Windows Phone 8.1|Нет|Нет|

## Параметры приложений — браузер

|Имя параметра|Windows 8.1 и Windows RT 8.1|Windows RT|Windows Phone 8 и Windows Phone 8.1|iOS|Android и Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Разрешить веб-браузер**|Нет|Нет|Только Windows Phone 8.1|Да|Да (только Samsung KNOX)|
|**Разрешить автозаполнение**|Да|Нет|Нет|Да|Да (только Samsung KNOX)|
|**Разрешить блокирование всплывающих окон**|Да|Нет|Нет|Да|Да (только Samsung KNOX)|
|**Разрешить файлы cookie**|Нет|Нет|Нет|Да|Да (только Samsung KNOX)|
|**Разрешить подключаемые модули**|Да|Нет|Нет|Нет|Нет|
|**Разрешить выполнение активных сценариев**|Да|Нет|Нет|Да|Да (только Samsung KNOX)|
|**Разрешить предупреждение о мошенничестве**|Да|Нет|Нет|Да|Нет|
|**Разрешить переход на сайт интрасети при вводе одного слова**<br /><br />(Этот параметр позволяет использовать одно слово для перенаправления Internet Explorer на веб-сайт, например Bing.)|да|Нет|Нет|Нет|Нет|
|**Разрешить автоматическое определение интрасети**|Да|Нет|Нет|Нет|Нет|
|**Уровень безопасности Интернета**|Да|Нет|Нет|Нет|Нет|
|**Уровень безопасности интрасети**|Да|Нет|Нет|Нет|Нет|
|**Уровень безопасности надежных узлов**|Да|Нет|Нет|Нет|Нет|
|**Уровень безопасности ограниченных узлов**|Да|Нет|Нет|Нет|Нет|
|**Отправлять заголовок "Не отслеживать"**|Да|Нет|Нет|Нет|Нет|
|**Разрешить доступ к меню режима предприятия**|Да|Нет|Нет|Нет|Нет|
|**Расположение списка сайтов режима предприятия**|Да|Нет|Нет|Нет|Нет|

## Параметры приложений — приложения

|Имя параметра|Windows 8.1 и Windows RT 8.1|Windows RT|Windows Phone 8 и Windows Phone 8.1|iOS|Android и Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Разрешить Магазин приложений**|Нет|Нет|Только Windows Phone 8.1|Да|Да (только Samsung KNOX)|
|**Требовать ввод пароля для доступа к магазину приложения**|Нет|Нет|Нет|Да|Нет|
|**Разрешить покупки из приложений**|Нет|Нет|Нет|Да|Нет|
|**Разрешить открывать управляемые документы в других неуправляемых приложениях**|Нет|Нет|Нет|iOS 7 и более поздних версий|Нет|
|**Разрешить открывать неуправляемые документы в других управляемых приложениях**|Нет|Нет|Нет|iOS 7 и более поздних версий|Нет|
|**Разрешить проведение видеоконференций**|Нет|Нет|Нет|Да|Нет|
|**Разрешить доступ к содержимому для взрослых в магазине мультимедиа**|Нет|Нет|Нет|Да|Нет|
|**Разрешить установку приложений**|Нет|Нет|Нет|iOS 6 и более поздних версий|Нет|

## Параметры приложений — игры

|Имя параметра|Windows 8.1 и Windows RT 8.1|Windows RT|Windows Phone 8 и Windows Phone 8.1|iOS|Android и Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Разрешить добавление друзей в Game Center**|Нет|Нет|Нет|Да|Нет|
|**Разрешить многопользовательские игры**|Нет|Нет|Нет|Да|Нет|

## Параметры возможностей устройств — аппаратное обеспечение

|Имя параметра|Windows 8.1 и Windows RT 8.1|Windows RT|Windows Phone 8 и Windows Phone 8.1|iOS|Android и Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Разрешить камеру**|Нет|Нет|Только Windows Phone 8.1|Да|Да|
|**Разрешить съемные носители**|Нет|Нет|Да|Нет|Да (только Samsung KNOX)|
|**Разрешить Wi-Fi**|Нет|Нет|Только Windows Phone 8.1|Нет|Да (только Samsung KNOX)|
|**Разрешить модем Wi-Fi**|Нет|Нет|Только Windows Phone 8.1|Нет|Да (только Samsung KNOX)|
|**Разрешить автоматическое подключение к свободным хот-спотам Wi-Fi**|Нет|Нет|Только Windows Phone 8.1|Нет|Нет|
|**Разрешить отчеты хот-спотов Wi-Fi**<br /><br />Этот параметр отправляет сведения о подключениях Wi-Fi, чтобы упростить поиск ближайших точек подключения.|Нет|Нет|Только Windows Phone 8.1|Нет|Нет|
|**Разрешить геолокацию**<br /><br />Этот параметр разрешает устройству использовать сведения о расположении.|Нет|Нет|Только Windows Phone 8.1|Нет|Да (только Samsung KNOX)|
|**Разрешить NFC**<br /><br />Этот параметр разрешает выполнение операций, использующих радиочастотную связь ближнего действия.|Нет|Нет|Только Windows Phone 8.1|Нет|Да (только Samsung KNOX)|
|**Разрешить Bluetooth**|Нет|Нет|Только Windows Phone 8.1|Нет|Да (только Samsung KNOX)|
|**Разрешить выключение**<br>Если этот параметр отключен, параметр **Допустимое число неудачных попыток входа перед очисткой устройства** для устройств Samsung KNOX не работает.|Нет|Нет|Нет|Нет|Да (только Samsung KNOX)|

## Параметры возможностей устройств — сотовая сеть

|Имя параметра|Windows 8.1 и Windows RT 8.1|Windows RT|Windows Phone 8 и Windows Phone 8.1|iOS|Android и Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Разрешить голосовой роуминг**|Нет|Нет|Нет|Да|Да (только Samsung KNOX)|
|**Разрешить передачу данных в роуминге**|Да|Нет|Нет|Да|Да (только Samsung KNOX)|
|**Разрешить автоматическую синхронизацию в роуминге**|Нет|Нет|Нет|Да|Нет|
|**Разрешить обмен SMS и MMS**|Нет|Нет|Нет|Нет|Да (только Samsung KNOX)|

## Параметры возможностей устройств — функции

|Имя параметра|Windows 8.1 и Windows RT 8.1|Windows RT|Windows Phone 8 и Windows Phone 8.1|iOS|Android и Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Разрешить использование голосового помощника**|Нет|Нет|Нет|Да|Да (только Samsung KNOX)|
|**Разрешить использование голосового помощника на заблокированном устройстве**|Нет|Нет|Нет|Да|Нет|
|**Разрешить голосовой набор**|Нет|Нет|Нет|Да|Да (только Samsung KNOX)|
|**Разрешить копирование и вставку**|Нет|Нет|Только Windows Phone 8.1|Нет|Да (только Samsung KNOX)|
|**Разрешить приложениям общий доступ к буферу обмена**|Нет|Нет|Нет|Нет|Да (только Samsung KNOX)|
|**Разрешить YouTube**|Нет|Нет|Нет|Нет|Да (только Samsung KNOX)|

### См. также
[Управление параметрами и компонентами на устройствах с помощью политик Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Aug16_HO3-->


