---
title: Date, ore e fusi orari
ms.date: 04/10/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- time zone objects [.NET Framework]
- date and time data [.NET Framework]
- time zones [.NET Framework]
- times [.NET Framework], time zones
- time [.NET Framework], time zones
ms.assetid: 295c16e0-641b-4771-94b3-39c1ffa98c13
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03a5594b689a52b641ecece0f9a92fb6cdfe5735
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991279"
---
# <a name="dates-times-and-time-zones"></a><span data-ttu-id="177d5-102">Date, ore e fusi orari</span><span class="sxs-lookup"><span data-stu-id="177d5-102">Dates, times, and time zones</span></span>

<span data-ttu-id="177d5-103">Oltre alla struttura di base <xref:System.DateTime>, .NET fornisce le classi seguenti che supportano l'uso dei fusi orari:</span><span class="sxs-lookup"><span data-stu-id="177d5-103">In addition to the basic <xref:System.DateTime> structure, .NET provides the following classes that support working with time zones:</span></span>

* <xref:System.TimeZone>

  <span data-ttu-id="177d5-104">Usare questa classe con il fuso orario locale del sistema e il fuso UTC (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="177d5-104">Use this class to work with the system's local time zone and the Coordinated Universal Time (UTC) zone.</span></span> <span data-ttu-id="177d5-105">La funzionalità della <xref:System.TimeZone> classe è ampiamente sostituita <xref:System.TimeZoneInfo> dalla classe.</span><span class="sxs-lookup"><span data-stu-id="177d5-105">The functionality of the <xref:System.TimeZone> class is largely superseded by the <xref:System.TimeZoneInfo> class.</span></span>

* <xref:System.TimeZoneInfo>

  <span data-ttu-id="177d5-106">Utilizzare questa classe per utilizzare qualsiasi fuso orario predefinito in un sistema, per creare nuovi fusi orari e per convertire facilmente date e ore da un fuso orario a un altro.</span><span class="sxs-lookup"><span data-stu-id="177d5-106">Use this class to work with any time zone that is predefined on a system, to create new time zones, and to easily convert dates and times from one time zone to another.</span></span> <span data-ttu-id="177d5-107">Per i nuovi progetti di sviluppo usare la classe <xref:System.TimeZoneInfo> anziché la classe <xref:System.TimeZone>.</span><span class="sxs-lookup"><span data-stu-id="177d5-107">For new development, use the <xref:System.TimeZoneInfo> class instead of the <xref:System.TimeZone> class.</span></span>

* <xref:System.DateTimeOffset>

  <span data-ttu-id="177d5-108">Usare questa struttura con le date e le ore il cui offset (o differenza) rispetto all'ora UTC è noto.</span><span class="sxs-lookup"><span data-stu-id="177d5-108">Use this structure to work with dates and times whose offset (or difference) from UTC is known.</span></span> <span data-ttu-id="177d5-109">La struttura <xref:System.DateTimeOffset> combina un valore di data e ora con l'offset di quell'ora rispetto all'ora UTC.</span><span class="sxs-lookup"><span data-stu-id="177d5-109">The <xref:System.DateTimeOffset> structure combines a date and time value with that time's offset from UTC.</span></span> <span data-ttu-id="177d5-110">Per via della relazione con l'ora UTC, un singolo valore di data e ora identifica un momento specifico senza ambiguità.</span><span class="sxs-lookup"><span data-stu-id="177d5-110">Because of its relationship to UTC, an individual date and time value unambiguously identifies a single point in time.</span></span> <span data-ttu-id="177d5-111">Un valore <xref:System.DateTimeOffset> risulta pertanto più portabile da un computer a un altro rispetto a un valore <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="177d5-111">This makes a <xref:System.DateTimeOffset> value more portable from one computer to another than a <xref:System.DateTime> value.</span></span>

<span data-ttu-id="177d5-112">Questa sezione della documentazione include le informazioni necessarie per usare i fusi orari e per creare applicazioni in grado di riconoscere i fusi orari e convertire date e ore da un fuso orario a un altro.</span><span class="sxs-lookup"><span data-stu-id="177d5-112">This section of the documentation provides the information that you need to work with time zones and to create time zone-aware applications that can convert dates and times from one time zone to another.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="177d5-113">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="177d5-113">In this section</span></span>

<span data-ttu-id="177d5-114">[Panoramica sul fuso orario](../../../docs/standard/datetime/time-zone-overview.md) Illustra concetti, terminologia e problemi relativi alla creazione di applicazioni che dipendono dal fuso orario.</span><span class="sxs-lookup"><span data-stu-id="177d5-114">[Time zone overview](../../../docs/standard/datetime/time-zone-overview.md) Discusses the terminology, concepts, and issues involved in creating time zone-aware applications.</span></span>

<span data-ttu-id="177d5-115">[Scelta tra DateTime, DateTimeOffset, TimeSpan e TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md) Illustra quando usare i tipi <xref:System.DateTime>, <xref:System.DateTimeOffset> e <xref:System.TimeZoneInfo> con i dati relativi a data e ora.</span><span class="sxs-lookup"><span data-stu-id="177d5-115">[Choosing between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md) Discusses when to use the <xref:System.DateTime>, <xref:System.DateTimeOffset>, and <xref:System.TimeZoneInfo> types when working with date and time data.</span></span>

<span data-ttu-id="177d5-116">[Ricerca dei fusi orari definiti in un sistema locale](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md) Descrive come enumerare i fusi orari disponibili in un sistema locale.</span><span class="sxs-lookup"><span data-stu-id="177d5-116">[Finding the time zones defined on a local system](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md) Describes how to enumerate the time zones found on a local system.</span></span>

<span data-ttu-id="177d5-117">[Procedura: Enumerare i fusi orari presenti in](../../../docs/standard/datetime/enumerate-time-zones.md) un computer fornisce esempi che enumerano i fusi orari definiti nel registro di sistema di un computer e che consentono agli utenti di selezionare un fuso orario predefinito da un elenco.</span><span class="sxs-lookup"><span data-stu-id="177d5-117">[How to: Enumerate time zones present on a computer](../../../docs/standard/datetime/enumerate-time-zones.md) Provides examples that enumerate the time zones defined in a computer's registry and that let users select a predefined time zone from a list.</span></span>

<span data-ttu-id="177d5-118">[Procedura: Accedere agli oggetti](../../../docs/standard/datetime/access-utc-and-local.md) predefiniti dell'ora UTC e del fuso orario locale descrive come accedere all'ora UTC e al fuso orario locale.</span><span class="sxs-lookup"><span data-stu-id="177d5-118">[How to: Access the predefined UTC and local time zone objects](../../../docs/standard/datetime/access-utc-and-local.md) Describes how to access Coordinated Universal Time and the local time zone.</span></span>

<span data-ttu-id="177d5-119">[Procedura: Creare un'istanza di un](../../../docs/standard/datetime/instantiate-time-zone-info.md) oggetto TimeZoneInfo descrive come creare un' <xref:System.TimeZoneInfo> istanza di un oggetto dal registro di sistema locale.</span><span class="sxs-lookup"><span data-stu-id="177d5-119">[How to: Instantiate a TimeZoneInfo object](../../../docs/standard/datetime/instantiate-time-zone-info.md) Describes how to instantiate a <xref:System.TimeZoneInfo> object from the local system registry.</span></span>

<span data-ttu-id="177d5-120">[Creazione di un'istanza di un oggetto DateTimeOffset](../../../docs/standard/datetime/instantiating-a-datetimeoffset-object.md) Illustra i modi per creare un'istanza di un oggetto <xref:System.DateTimeOffset> e i modi per convertire un valore <xref:System.DateTime> in un valore <xref:System.DateTimeOffset>.</span><span class="sxs-lookup"><span data-stu-id="177d5-120">[Instantiating a DateTimeOffset object](../../../docs/standard/datetime/instantiating-a-datetimeoffset-object.md) Discusses the ways in which a <xref:System.DateTimeOffset> object can be instantiated, and the ways in which a <xref:System.DateTime> value can be converted to a <xref:System.DateTimeOffset> value.</span></span>

<span data-ttu-id="177d5-121">[Procedura: Crea fusi orari senza regole](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) di regolazione descrive come creare un fuso orario personalizzato che non supporta la transizione da e verso l'ora legale.</span><span class="sxs-lookup"><span data-stu-id="177d5-121">[How to: Create time zones without adjustment rules](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) Describes how to create a custom time zone that does not support the transition to and from daylight saving time.</span></span>

<span data-ttu-id="177d5-122">[Procedura: Creare fusi orari con regole](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md) di regolazione descrive come creare un fuso orario personalizzato che supporta una o più transizioni da e verso l'ora legale.</span><span class="sxs-lookup"><span data-stu-id="177d5-122">[How to: Create time zones with adjustment rules](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md) Describes how to create a custom time zone that supports one or more transitions to and from daylight saving time.</span></span>

<span data-ttu-id="177d5-123">[Salvataggio e ripristino dei fusi orari](../../../docs/standard/datetime/saving-and-restoring-time-zones.md) Descrive il supporto <xref:System.TimeZoneInfo> per la serializzazione e deserializzazione dei dati del fuso orario e illustra alcuni degli scenari in cui è possibile usare tali funzionalità.</span><span class="sxs-lookup"><span data-stu-id="177d5-123">[Saving and restoring time zones](../../../docs/standard/datetime/saving-and-restoring-time-zones.md) Describes <xref:System.TimeZoneInfo> support for serialization and deserialization of time zone data and illustrates some of the scenarios in which these features can be used.</span></span>

<span data-ttu-id="177d5-124">[Procedura: Salva fusi orari in una risorsa](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) incorporata descrive come creare un fuso orario personalizzato e salvare le informazioni in un file di risorse.</span><span class="sxs-lookup"><span data-stu-id="177d5-124">[How to: Save time zones to an embedded resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) Describes how to create a custom time zone and save its information in a resource file.</span></span>

<span data-ttu-id="177d5-125">[Procedura: Ripristina fusi orari da una risorsa](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md) incorporata descrive come creare un'istanza di fusi orari personalizzati che sono stati salvati in un file di risorse incorporato.</span><span class="sxs-lookup"><span data-stu-id="177d5-125">[How to: Restore time zones from an embedded resource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md) Describes how to instantiate custom time zones that have been saved to an embedded resource file.</span></span>

<span data-ttu-id="177d5-126">[Esecuzione di operazioni aritmetiche con date e ore](../../../docs/standard/datetime/performing-arithmetic-operations.md) Descrive i problemi relativi ad aggiunta, sottrazione e confronto dei valori <xref:System.DateTime> e <xref:System.DateTimeOffset>.</span><span class="sxs-lookup"><span data-stu-id="177d5-126">[Performing arithmetic operations with dates and times](../../../docs/standard/datetime/performing-arithmetic-operations.md) Discusses the issues involved in adding, subtracting, and comparing <xref:System.DateTime> and <xref:System.DateTimeOffset> values.</span></span>

<span data-ttu-id="177d5-127">[Procedura: Usare fusi orari nell'aritmetica](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md) di data e ora illustra come eseguire operazioni aritmetiche di data e ora che riflettano le regole di rettifica del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="177d5-127">[How to: Use time zones in date and time arithmetic](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md) Discusses how to perform date and time arithmetic that reflects a time zone's adjustment rules.</span></span>

<span data-ttu-id="177d5-128">[Conversione tra DateTime e DateTimeOffset](../../../docs/standard/datetime/converting-between-datetime-and-offset.md) Descrive come eseguire la conversione tra i valori <xref:System.DateTime> e <xref:System.DateTimeOffset>.</span><span class="sxs-lookup"><span data-stu-id="177d5-128">[Converting between DateTime and DateTimeOffset](../../../docs/standard/datetime/converting-between-datetime-and-offset.md) Describes how to convert between <xref:System.DateTime> and <xref:System.DateTimeOffset> values.</span></span>

<span data-ttu-id="177d5-129">[Conversione degli orari tra fusi orari](../../../docs/standard/datetime/converting-between-time-zones.md) Descrive come eseguire la conversione di ore tra un fuso orario e un altro.</span><span class="sxs-lookup"><span data-stu-id="177d5-129">[Converting times between time zones](../../../docs/standard/datetime/converting-between-time-zones.md) Describes how to convert times from one time zone to another.</span></span>

<span data-ttu-id="177d5-130">[Procedura: Risolvi orari](../../../docs/standard/datetime/resolve-ambiguous-times.md) ambigui descrive come risolvere un orario ambiguo eseguendone il mapping all'ora solare del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="177d5-130">[How to: Resolve ambiguous times](../../../docs/standard/datetime/resolve-ambiguous-times.md) Describes how to resolve an ambiguous time by mapping it to the time zone's standard time.</span></span>

<span data-ttu-id="177d5-131">[Procedura: Consentire agli utenti di risolvere](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md) orari ambigui descrive come consentire a un utente di determinare il mapping tra un'ora locale ambigua e l'ora UTC (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="177d5-131">[How to: Let users resolve ambiguous times](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md) Describes how to let a user determine the mapping between an ambiguous local time and Coordinated Universal Time.</span></span>

## <a name="reference"></a><span data-ttu-id="177d5-132">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="177d5-132">Reference</span></span>

<xref:System.TimeZoneInfo?displayProperty=nameWithType>
