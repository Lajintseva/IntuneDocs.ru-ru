---
title: "Устранение неполадок с профилями электронной почты | Microsoft Intune"
description: "Перечень проблем, возникающих с профилями электронной почты, а также способы их устранения."
keywords: 
author: Nbigman
manager: angrobe
ms.date: 08/01/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5c944ea-32a6-48af-bb57-16d5f1f3c588
ms.reviewer: tscott
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb0aeac2f94dfde50d9398b09c6b21c7ae40624
ms.openlocfilehash: 79076b65fe85adeaffd5435915cb5eca2a15413f


---

# Устранение неполадок с профилями электронной почты в Microsoft Intune
Ниже приведены некоторые проблемы, возникающие с профилями электронной почты, а также способы их устранения.

Если эти сведения не позволяют решить проблему, см. дополнительные справочные материалы в статье [Получение поддержки для Microsoft Intune](how-to-get-support-for-microsoft-intune.md).


## Не удается отправить изображения из учетной записи электронной почты
Пользователи, учетные записи электронной почты которых настраиваются автоматически, не могут отправить изображения или рисунки со своих устройств.
Это происходит, когда параметр **Разрешить отправку сообщений электронной почты сторонними приложениями** отключен.

### Решение Intune

1.  Откройте консоль администрирования Microsoft Intune, выберите рабочую нагрузку **Политика** &gt; **Политики конфигурации**.

2.  Выберите профиль электронной почты и нажмите кнопку **Изменить**.

3.  Выберите **Разрешить отправку сообщений электронной почты сторонними приложениями**.

### Интеграция Configuration Manager с решением Intune

1.  Откройте консоль Configuration Manager и выберите элемент &gt;**Ресурсы и соответствие**.

2.  Разверните узлы **Обзор** -&gt;**Параметры соответствия** -&gt;**Доступ к ресурсам организации** и выберите **Профили электронной почты**.

3.  Щелкните правой кнопкой мыши профиль электронной почты и выберите **Свойства**.

4.  На вкладке **Параметры синхронизации** выберите **Разрешить отправку сообщений электронной почты из сторонних приложений**.


## На устройстве уже установлен профиль электронной почты

Если пользователь установил профиль электронной почты прежде, чем Intune подготовил профиль, результаты развертывания профиля электронной почты Intune будут зависеть от платформы устройства.

-**iOS**. Intune обнаружит существующий дубликат профиля электронной почты по имени узла и адресу электронной почты. Созданный пользователем дубликат профиля электронной почты не позволит развернуть профиль, созданный администратором Intune. Это распространенная проблема, поскольку пользователи iOS обычно создают профиль электронной почты, а затем регистрируются. Портал компании проинформирует пользователя о том, что он не соответствует условиям из-за настроенного вручную профиля электронной почты, и предложит удалить этот профиль. Пользователю следует удалить свой профиль электронной почты, чтобы можно было развернуть профиль Intune. Чтобы избежать этой проблемы, дайте своим пользователям указание регистрироваться до установки профиля электронной почты и разрешите Intune развернуть профиль.

-**Windows**. Intune обнаружит существующий дубликат профиля электронной почты по имени узла и адресу электронной почты. Intune перезапишет существующий профиль электронной почты, созданный пользователем.

-**Samsung KNOX**. Intune обнаружит дубликат учетной записи электронной почты по адресу электронной почты и перезапишет его профилем Intune. Если пользователь настроил эту учетную запись, она будет снова заменена на профиль Intune. Обратите внимание, это может вызвать некоторую путаницу e пользователя, конфигурация учетной записи которого перезаписывается.

Поскольку Samsung KNOX не использует имя узла для идентификации профиля, не рекомендуем создавать несколько профилей электронной почты для развертывания с одним и тем же адресом электронной почты на разных узлах, поскольку в этом случае они будут перезаписывать друг друга.

## Ошибка 0x87D1FDE8 для устройства KNOX
**Проблема**: после создания и развертывания профиля электронной почты Exchange Active Sync для Samsung KNOX для различных устройств Android они сообщают об ошибке **0x87D1FDE8** или **сбое исправления** на вкладке политики &gt; в свойствах устройства.

Проверьте конфигурацию профиля EAS для Samsung KNOX и исходную политику. Параметр синхронизации заметок Samsung больше не поддерживается, поэтому не следует выбирать его в своем профиле. Убедитесь, что у устройств было достаточно времени (до 24 часов) на обработку политики.

## Дальнейшие шаги
Если эта информация не помогла, обратитесь в службу поддержки Майкрософт, как описано в статье [Получение поддержки для Microsoft Intune](how-to-get-support-for-microsoft-intune.md).



<!--HONumber=Aug16_HO1-->


