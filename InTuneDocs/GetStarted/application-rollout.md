---
title: "Развертывание приложений | Microsoft Intune"
description: "Рекомендации по поэтапному развертыванию приложений в Microsoft Intune."
keywords: 
author: Nbigman
manager: angrobe
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0fc32ed3-bcf4-472a-80e7-eb20986f78fa
ms.reviewer: tscott
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2a192c71b1b82f59b34ea614d09d895174f8112b
ms.openlocfilehash: 83306c0847eaf98d499e649308669a33306aa97e


---

# Развертывание приложений
В этом разделе приведены некоторые рекомендации по поэтапному развертыванию приложений в Microsoft Intune. Общие сведения об этапах развертывания см. в статье [Этапы развертывания Microsoft Intune](rollout-phases-for-microsoft-intune-deployment.md).

### Этапы развертывания приложений
Развертывание приложений осуществляется по следующим этапам:

-   определение области проекта;

-   Подтверждение концепции

-   Пилотное развертывание

-   Корпоративное развертывание

-   Использование и обслуживание

## Определение области проекта
Рекомендуется учесть следующие моменты:

-   задачи пользователя, выполнение которых должно обеспечивать приложение;

-   пригодность приложения для пользователей и их устройств (все операционные системы, которые, вероятно, будут использоваться).

-   Проверьте, поддерживается ли установщик выбранного приложения функцией распространения приложений Intune, как описано в разделе [Добавление приложений с помощью Microsoft Intune](/intune/deploy-use/add-apps).

-   Убедитесь в том, что установлены необходимые компоненты для распространения приложений. <!---, as described in [Plan for app deployment in Microsoft Intune](plan-for-app-deployment-in-microsoft-intune.md).--->

-   Определите, поддерживается ли тип приложения службой Intune.

-   Убедитесь в том, что в облачном хранилище достаточно места для отправки приложения. Инструкции по приобретению дополнительного хранилища см. в разделе [Добавление приложений с помощью Microsoft Intune](/intune/deploy-use/add-apps).

> [!NOTE]           
> Для помощи в процессе развертывания можно загрузить этот [шаблон планирования для мобильных приложений](https://gallery.technet.microsoft.com/Mobile-app-planning-18689d59).

## Подтверждение концепции
На этапе подтверждения концепции необходимо протестировать развертывание приложения в лабораторной среде на основе устройств и пользователей, настроенных исключительно в целях тестирования.

-   Привлеките службу технической поддержки к участию в этом этапе, чтобы выяснить, какие проблемы могут возникнуть во время пилотного и рабочего развертывания. Сведения об устранении неполадок доступны в разделе [Устранение неполадок, связанных с развертыванием приложений, в Microsoft Intune](/intune/troubleshoot/troubleshoot-app-deployment-problems-in-microsoft-intune).

-   На этом этапе процесса следует разработать планы коммуникации для пользователей пилотного и рабочего развертывания. Этот план должен содержать по крайней мере следующие сведения: какое приложение развертывается, как и когда пользователи получат его, в чем заключается бизнес-цель развертывания и что делать при возникновении проблем (информация для самостоятельного устранения неполадок и контактные данные службы поддержки).

## Пилотный проект
В рамках пилотного проекта приложение развертывается для небольшой группы тестовых пользователей и устройств. Рекомендуется учесть следующие моменты.

-   В тестовой группе должны быть представлены устройства и пользователи, которые будут использовать приложение после развертывания в рабочей среде.

-   Проведите обучение специалистов службы поддержки по развертыванию приложения и подготовьте их к оказанию помощи пользователям из тестовой группы.

-   Выберите тестовых пользователей, которые испытают приложение в стандартных сценариях использования и предоставят достоверные сведения о возникших проблемах администраторам пилотного проекта.

-   Активируйте план коммуникации для пользователей пилотного проекта.

## Корпоративное развертывание

-   Используйте результаты пилотного проекта для корректировки корпоративного развертывания.

-   Уведомите службу технической поддержки о расписании развертывания приложения. Реализуйте механизмы реагирования на обращения в службу поддержки и корректировки развертывания по мере необходимости.

-   Будьте готовы устранять возникающие неполадки в процессе развертывания.

-   Активируйте план коммуникации для пользователей рабочей среды.

-   Используйте поэтапный подход к развертыванию приложения, добавляя группы постепенно, чтобы обеспечить благополучное протекание процесса.

## Использование и обслуживание
**Операции**: отслеживайте в консоли Intune оповещения и сообщения о проблемах пользователей и устройств, чтобы гарантировать распространение приложения в соответствии с планом.

**Служба технической поддержки**: проинформируйте службу технической поддержки об изменениях, касающихся доступности приложения, которые могут привести к обращениям в службу.

### См. также
[Развертывание приложений](/intune/deploy-use/deploy-apps)

[Устранение неполадок, связанных с развертыванием приложений, в Microsoft Intune](/intune/troubleshoot/troubleshoot-app-deployment-problems-in-microsoft-intune)



<!--HONumber=Jul16_HO4-->


