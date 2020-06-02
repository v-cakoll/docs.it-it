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
ms.openlocfilehash: 86602cd6e662b1b1057832247babc558ef67b79f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84276933"
---
# <a name="dates-times-and-time-zones"></a><span data-ttu-id="df379-102">Date, ore e fusi orari</span><span class="sxs-lookup"><span data-stu-id="df379-102">Dates, times, and time zones</span></span>

<span data-ttu-id="df379-103">Oltre alla struttura di base <xref:System.DateTime>, .NET fornisce le classi seguenti che supportano l'uso dei fusi orari:</span><span class="sxs-lookup"><span data-stu-id="df379-103">In addition to the basic <xref:System.DateTime> structure, .NET provides the following classes that support working with time zones:</span></span>

* <xref:System.TimeZone>

  <span data-ttu-id="df379-104">Usare questa classe con il fuso orario locale del sistema e il fuso UTC (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="df379-104">Use this class to work with the system's local time zone and the Coordinated Universal Time (UTC) zone.</span></span> <span data-ttu-id="df379-105">La funzionalità della <xref:System.TimeZone> classe è ampiamente sostituita dalla <xref:System.TimeZoneInfo> classe.</span><span class="sxs-lookup"><span data-stu-id="df379-105">The functionality of the <xref:System.TimeZone> class is largely superseded by the <xref:System.TimeZoneInfo> class.</span></span>

* <xref:System.TimeZoneInfo>

  <span data-ttu-id="df379-106">Utilizzare questa classe per utilizzare qualsiasi fuso orario predefinito in un sistema, per creare nuovi fusi orari e per convertire facilmente date e ore da un fuso orario a un altro.</span><span class="sxs-lookup"><span data-stu-id="df379-106">Use this class to work with any time zone that is predefined on a system, to create new time zones, and to easily convert dates and times from one time zone to another.</span></span> <span data-ttu-id="df379-107">Per i nuovi progetti di sviluppo usare la classe <xref:System.TimeZoneInfo> anziché la classe <xref:System.TimeZone>.</span><span class="sxs-lookup"><span data-stu-id="df379-107">For new development, use the <xref:System.TimeZoneInfo> class instead of the <xref:System.TimeZone> class.</span></span>

* <xref:System.DateTimeOffset>

  <span data-ttu-id="df379-108">Usare questa struttura con le date e le ore il cui offset (o differenza) rispetto all'ora UTC è noto.</span><span class="sxs-lookup"><span data-stu-id="df379-108">Use this structure to work with dates and times whose offset (or difference) from UTC is known.</span></span> <span data-ttu-id="df379-109">La struttura <xref:System.DateTimeOffset> combina un valore di data e ora con l'offset di quell'ora rispetto all'ora UTC.</span><span class="sxs-lookup"><span data-stu-id="df379-109">The <xref:System.DateTimeOffset> structure combines a date and time value with that time's offset from UTC.</span></span> <span data-ttu-id="df379-110">Per via della relazione con l'ora UTC, un singolo valore di data e ora identifica un momento specifico senza ambiguità.</span><span class="sxs-lookup"><span data-stu-id="df379-110">Because of its relationship to UTC, an individual date and time value unambiguously identifies a single point in time.</span></span> <span data-ttu-id="df379-111">Un valore <xref:System.DateTimeOffset> risulta pertanto più portabile da un computer a un altro rispetto a un valore <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="df379-111">This makes a <xref:System.DateTimeOffset> value more portable from one computer to another than a <xref:System.DateTime> value.</span></span>

<span data-ttu-id="df379-112">Questa sezione della documentazione include le informazioni necessarie per usare i fusi orari e per creare applicazioni in grado di riconoscere i fusi orari e convertire date e ore da un fuso orario a un altro.</span><span class="sxs-lookup"><span data-stu-id="df379-112">This section of the documentation provides the information that you need to work with time zones and to create time zone-aware applications that can convert dates and times from one time zone to another.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="df379-113">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="df379-113">In this section</span></span>

<span data-ttu-id="df379-114">[Panoramica sul fuso orario](time-zone-overview.md): illustra concetti, terminologia e problemi relativi alla creazione di applicazioni che dipendono dal fuso orario.</span><span class="sxs-lookup"><span data-stu-id="df379-114">[Time zone overview](time-zone-overview.md) Discusses the terminology, concepts, and issues involved in creating time zone-aware applications.</span></span>

<span data-ttu-id="df379-115">[Scelta tra DateTime, DateTimeOffset, TimeSpan e TimeZoneInfo](choosing-between-datetime.md) Viene illustrato quando utilizzare i <xref:System.DateTime> tipi, e quando si utilizzano i <xref:System.DateTimeOffset> <xref:System.TimeZoneInfo> dati di data e ora.</span><span class="sxs-lookup"><span data-stu-id="df379-115">[Choosing between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo](choosing-between-datetime.md) Discusses when to use the <xref:System.DateTime>, <xref:System.DateTimeOffset>, and <xref:System.TimeZoneInfo> types when working with date and time data.</span></span>

<span data-ttu-id="df379-116">[Ricerca dei fusi orari definiti in un sistema locale](finding-the-time-zones-on-local-system.md): descrive come enumerare i fusi orari che si trovano in un sistema locale.</span><span class="sxs-lookup"><span data-stu-id="df379-116">[Finding the time zones defined on a local system](finding-the-time-zones-on-local-system.md) Describes how to enumerate the time zones found on a local system.</span></span>

<span data-ttu-id="df379-117">[Procedura: Enumerare i fusi orari presenti in un computer](enumerate-time-zones.md): include esempi che enumerano i fusi orari definiti nel Registro di sistema di un computer e che consentono agli utenti di selezionare un fuso orario predefinito da un elenco.</span><span class="sxs-lookup"><span data-stu-id="df379-117">[How to: Enumerate time zones present on a computer](enumerate-time-zones.md) Provides examples that enumerate the time zones defined in a computer's registry and that let users select a predefined time zone from a list.</span></span>

<span data-ttu-id="df379-118">[Procedura: Accedere agli oggetti predefiniti dell'ora UTC e del fuso orario locale](access-utc-and-local.md): descrive come accedere all'ora UTC e al fuso orario locale.</span><span class="sxs-lookup"><span data-stu-id="df379-118">[How to: Access the predefined UTC and local time zone objects](access-utc-and-local.md) Describes how to access Coordinated Universal Time and the local time zone.</span></span>

<span data-ttu-id="df379-119">[Procedura: creare un'istanza di un oggetto TimeZoneInfo](instantiate-time-zone-info.md) Descrive come creare un'istanza di un oggetto <xref:System.TimeZoneInfo> dal Registro di sistema locale.</span><span class="sxs-lookup"><span data-stu-id="df379-119">[How to: Instantiate a TimeZoneInfo object](instantiate-time-zone-info.md) Describes how to instantiate a <xref:System.TimeZoneInfo> object from the local system registry.</span></span>

<span data-ttu-id="df379-120">[Creazione di un'istanza di un oggetto DateTimeOffset](instantiating-a-datetimeoffset-object.md) Illustra i modi per creare un'istanza di un oggetto <xref:System.DateTimeOffset> e i modi per convertire un valore <xref:System.DateTime> in un valore <xref:System.DateTimeOffset>.</span><span class="sxs-lookup"><span data-stu-id="df379-120">[Instantiating a DateTimeOffset object](instantiating-a-datetimeoffset-object.md) Discusses the ways in which a <xref:System.DateTimeOffset> object can be instantiated, and the ways in which a <xref:System.DateTime> value can be converted to a <xref:System.DateTimeOffset> value.</span></span>

<span data-ttu-id="df379-121">[Procedura: Creare fusi orari senza regole di regolazione](create-time-zones-without-adjustment-rules.md): descrive come creare un fuso orario personalizzato che non supporta la transizione da e verso l'ora legale.</span><span class="sxs-lookup"><span data-stu-id="df379-121">[How to: Create time zones without adjustment rules](create-time-zones-without-adjustment-rules.md) Describes how to create a custom time zone that does not support the transition to and from daylight saving time.</span></span>

<span data-ttu-id="df379-122">[Procedura: Creare fusi orari con regole di regolazione](create-time-zones-with-adjustment-rules.md): descrive come creare un fuso orario personalizzato che supporta una o più transizioni da e verso l'ora legale.</span><span class="sxs-lookup"><span data-stu-id="df379-122">[How to: Create time zones with adjustment rules](create-time-zones-with-adjustment-rules.md) Describes how to create a custom time zone that supports one or more transitions to and from daylight saving time.</span></span>

<span data-ttu-id="df379-123">[Salvataggio e ripristino dei fusi orari](saving-and-restoring-time-zones.md) Descrive il supporto <xref:System.TimeZoneInfo> per la serializzazione e deserializzazione dei dati del fuso orario e illustra alcuni degli scenari in cui è possibile usare tali funzionalità.</span><span class="sxs-lookup"><span data-stu-id="df379-123">[Saving and restoring time zones](saving-and-restoring-time-zones.md) Describes <xref:System.TimeZoneInfo> support for serialization and deserialization of time zone data and illustrates some of the scenarios in which these features can be used.</span></span>

<span data-ttu-id="df379-124">[Procedura: Salvare fusi orari in una risorsa incorporata](save-time-zones-to-an-embedded-resource.md): descrive come creare un fuso orario personalizzato e salvare le informazioni in un file di risorse.</span><span class="sxs-lookup"><span data-stu-id="df379-124">[How to: Save time zones to an embedded resource](save-time-zones-to-an-embedded-resource.md) Describes how to create a custom time zone and save its information in a resource file.</span></span>

<span data-ttu-id="df379-125">[Procedura: Ripristinare i fusi orari da una risorsa incorporata](restore-time-zones-from-an-embedded-resource.md): descrive come creare un'istanza di fusi orari personalizzati che sono stati salvati in un file di risorsa incorporata.</span><span class="sxs-lookup"><span data-stu-id="df379-125">[How to: Restore time zones from an embedded resource](restore-time-zones-from-an-embedded-resource.md) Describes how to instantiate custom time zones that have been saved to an embedded resource file.</span></span>

<span data-ttu-id="df379-126">[Esecuzione di operazioni aritmetiche con date e ore](performing-arithmetic-operations.md) Descrive i problemi relativi ad aggiunta, sottrazione e confronto dei valori <xref:System.DateTime> e <xref:System.DateTimeOffset>.</span><span class="sxs-lookup"><span data-stu-id="df379-126">[Performing arithmetic operations with dates and times](performing-arithmetic-operations.md) Discusses the issues involved in adding, subtracting, and comparing <xref:System.DateTime> and <xref:System.DateTimeOffset> values.</span></span>

<span data-ttu-id="df379-127">[Procedura: Usare fusi orari nell'aritmetica di data e ora](use-time-zones-in-arithmetic.md): illustra come eseguire operazioni aritmetiche di data e ora che riflettano le regole di regolazione di un fuso orario.</span><span class="sxs-lookup"><span data-stu-id="df379-127">[How to: Use time zones in date and time arithmetic](use-time-zones-in-arithmetic.md) Discusses how to perform date and time arithmetic that reflects a time zone's adjustment rules.</span></span>

<span data-ttu-id="df379-128">[Conversione tra DateTime e DateTimeOffset](converting-between-datetime-and-offset.md) Descrive come eseguire la conversione tra i valori <xref:System.DateTime> e <xref:System.DateTimeOffset>.</span><span class="sxs-lookup"><span data-stu-id="df379-128">[Converting between DateTime and DateTimeOffset](converting-between-datetime-and-offset.md) Describes how to convert between <xref:System.DateTime> and <xref:System.DateTimeOffset> values.</span></span>

<span data-ttu-id="df379-129">[Conversione degli orari tra fusi orari](converting-between-time-zones.md): descrive come eseguire la conversione di ore tra un fuso orario e un altro.</span><span class="sxs-lookup"><span data-stu-id="df379-129">[Converting times between time zones](converting-between-time-zones.md) Describes how to convert times from one time zone to another.</span></span>

<span data-ttu-id="df379-130">[Procedura: Risolvere orari ambigui](resolve-ambiguous-times.md): descrive come risolvere un orario ambiguo eseguendone il mapping all'ora solare del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="df379-130">[How to: Resolve ambiguous times](resolve-ambiguous-times.md) Describes how to resolve an ambiguous time by mapping it to the time zone's standard time.</span></span>

<span data-ttu-id="df379-131">[Procedura: Consentire agli utenti di risolvere orari ambigui](let-users-resolve-ambiguous-times.md): descrive come consentire agli utenti di determinare il mapping tra un'ora locale ambigua e l'ora UTC.</span><span class="sxs-lookup"><span data-stu-id="df379-131">[How to: Let users resolve ambiguous times](let-users-resolve-ambiguous-times.md) Describes how to let a user determine the mapping between an ambiguous local time and Coordinated Universal Time.</span></span>

## <a name="reference"></a><span data-ttu-id="df379-132">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="df379-132">Reference</span></span>

<xref:System.TimeZoneInfo?displayProperty=nameWithType>
