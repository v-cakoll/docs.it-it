---
title: Ricerca dei fusi orari definiti in un sistema locale
description: Ricerca dei fusi orari definiti in un sistema locale
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 3a6ee323-f3cf-486d-aa0c-103931f1eba9
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: e61017e2a0e26295c3be7e8265674b1a5d2ae5a3
ms.contentlocale: it-it
ms.lasthandoff: 03/02/2017

---

# <a name="finding-the-time-zones-defined-on-a-local-system"></a><span data-ttu-id="d5558-104">Ricerca dei fusi orari definiti in un sistema locale</span><span class="sxs-lookup"><span data-stu-id="d5558-104">Finding the time zones defined on a local system</span></span>

<span data-ttu-id="d5558-105">La classe [System.TimeZoneInfo](xref:System.TimeZoneInfo) non espone un costruttore pubblico.</span><span class="sxs-lookup"><span data-stu-id="d5558-105">The [System.TimeZoneInfo](xref:System.TimeZoneInfo) class does not expose a public constructor.</span></span> <span data-ttu-id="d5558-106">Di conseguenza, non è possibile usare la parola chiave `new` per creare un nuovo oggetto [TimeZoneInfo](xref:System.TimeZoneInfo).</span><span class="sxs-lookup"><span data-stu-id="d5558-106">As a result, the `new` keyword cannot be used to create a new [TimeZoneInfo](xref:System.TimeZoneInfo) object.</span></span> <span data-ttu-id="d5558-107">Le istanze degli oggetti [TimeZoneInfo](xref:System.TimeZoneInfo) vengono invece create recuperando le informazioni sui fusi orari predefiniti dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="d5558-107">Instead, [TimeZoneInfo](xref:System.TimeZoneInfo) objects are instantiated by retrieving information on predefined time zones from the operating system.</span></span> <span data-ttu-id="d5558-108">Questo argomento descrive la creazione dell'istanza di un fuso orario da dati archiviati dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="d5558-108">This topic discusses instantiating a time zone from data stored by the operating system.</span></span> <span data-ttu-id="d5558-109">Inoltre, le proprietà `static` (`Shared` in Visual Basic) della classe [TimeZoneInfo](xref:System.TimeZoneInfo) consentono l'accesso all'ora Coordinated Universal Time (UTC) e al fuso orario locale.</span><span class="sxs-lookup"><span data-stu-id="d5558-109">In addition, `static` (`Shared` in Visual Basic) properties of the [TimeZoneInfo](xref:System.TimeZoneInfo) class provide access to Coordinated Universal Time (UTC) and the local time zone.</span></span>

## <a name="accessing-individual-time-zones"></a><span data-ttu-id="d5558-110">Accesso a singoli fusi orari</span><span class="sxs-lookup"><span data-stu-id="d5558-110">Accessing Individual Time Zones</span></span>

<span data-ttu-id="d5558-111">La classe [TimeZoneInfo](xref:System.TimeZoneInfo) offre due oggetti fuso orario predefiniti che rappresentano l'ora UTC e il fuso orario locale.</span><span class="sxs-lookup"><span data-stu-id="d5558-111">The [TimeZoneInfo](xref:System.TimeZoneInfo) class provides two predefined time zone objects that represent the UTC time and the local time zone.</span></span> <span data-ttu-id="d5558-112">Gli oggetti sono disponibili rispettivamente dalle proprietà [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) e [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local).</span><span class="sxs-lookup"><span data-stu-id="d5558-112">They are available from the [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) and [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) properties, respectively.</span></span> <span data-ttu-id="d5558-113">Per istruzioni sull'accesso all'ora UTC o ai fusi orari locali, vedere [Procedura: Accedere agli oggetti predefiniti dell'ora UTC e del fuso orario locale](access-utc-and-local.md).</span><span class="sxs-lookup"><span data-stu-id="d5558-113">For instructions on accessing the UTC or local time zones, see [How to: access the predefined UTC and local time zone objects](access-utc-and-local.md).</span></span> 

<span data-ttu-id="d5558-114">È anche possibile creare l'istanza di un oggetto [TimeZoneInfo](xref:System.TimeZoneInfo) che rappresenta qualsiasi fuso orario definito dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="d5558-114">You can also instantiate a [TimeZoneInfo](xref:System.TimeZoneInfo) object that represents any time zone defined by the operating system.</span></span> <span data-ttu-id="d5558-115">Per istruzioni sulla creazione dell'istanza di un oggetto fuso orario specifico, vedere [Procedura: Creare un'istanza di un oggetto TimeZoneInfo](instantiate-time-zone-info.md).</span><span class="sxs-lookup"><span data-stu-id="d5558-115">For instructions on instantiating a specific time zone object, see [How to: instantiate a TimeZoneInfo object](instantiate-time-zone-info.md).</span></span>

## <a name="time-zone-identifiers"></a><span data-ttu-id="d5558-116">Identificatori del fuso orario</span><span class="sxs-lookup"><span data-stu-id="d5558-116">Time Zone Identifiers</span></span>

<span data-ttu-id="d5558-117">L'identificatore del fuso orario è un campo chiave che identifica in modo univoco il fuso orario.</span><span class="sxs-lookup"><span data-stu-id="d5558-117">The time zone identifier is a key field that uniquely identifies the time zone.</span></span> <span data-ttu-id="d5558-118">Benché la maggior parte delle chiavi sia relativamente breve, in confronto l'identificatore del fuso orario è piuttosto lungo.</span><span class="sxs-lookup"><span data-stu-id="d5558-118">While most keys are relatively short, the time zone identifier is comparatively long.</span></span> <span data-ttu-id="d5558-119">Nella maggior parte dei casi, il suo valore corrisponde alla proprietà [TimeZoneInfo.StandardName](xref:System.TimeZoneInfo.StandardName), che viene usata per specificare il nome dell'ora solare del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="d5558-119">In most cases, its value corresponds to the [TimeZoneInfo.StandardName](xref:System.TimeZoneInfo.StandardName) property, which is used to provide the name of the time zone's standard time.</span></span> <span data-ttu-id="d5558-120">Esistono tuttavia alcune eccezioni.</span><span class="sxs-lookup"><span data-stu-id="d5558-120">However, there are exceptions.</span></span> <span data-ttu-id="d5558-121">Il modo migliore per assicurarsi di specificare un identificatore univoco consiste nell'enumerare i fusi orari disponibili nel sistema e annotare gli identificatori associati.</span><span class="sxs-lookup"><span data-stu-id="d5558-121">The best way to make sure that you supply a valid identifier is to enumerate the time zones available on your system and note their associated identifiers.</span></span> <span data-ttu-id="d5558-122">Per istruzioni sull'enumerazione dei fusi orari, vedere [Procedura: Enumerare i fusi orari presenti in un computer](enumerate-time-zones.md).</span><span class="sxs-lookup"><span data-stu-id="d5558-122">For instructions on enumerating time zones, see [How to: enumerate time zones present on a computer](enumerate-time-zones.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d5558-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5558-123">See Also</span></span>

[<span data-ttu-id="d5558-124">Date, ore e fusi orari</span><span class="sxs-lookup"><span data-stu-id="d5558-124">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="d5558-125">Procedura: Accedere agli oggetti predefiniti dell'ora UTC e del fuso orario locale</span><span class="sxs-lookup"><span data-stu-id="d5558-125">How to: access the predefined UTC and local time zone objects</span></span>](access-utc-and-local.md)

[<span data-ttu-id="d5558-126">Procedura: Creare un'istanza di un oggetto TimeZoneInfo</span><span class="sxs-lookup"><span data-stu-id="d5558-126">How to: instantiate a TimeZoneInfo object</span></span>](instantiate-time-zone-info.md)

[<span data-ttu-id="d5558-127">Procedura: Enumerare i fusi orari presenti in un computer</span><span class="sxs-lookup"><span data-stu-id="d5558-127">How to: enumerate time zones present on a computer</span></span>](enumerate-time-zones.md)

[<span data-ttu-id="d5558-128">Conversione degli orari tra fusi orari</span><span class="sxs-lookup"><span data-stu-id="d5558-128">Converting times between time zones</span></span>](converting-between-time-zones.md)
