---
title: 'Procedura: Enumerare i fusi orari presenti in un computer'
description: Come enumerare i fusi orari presenti in un computer
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: c5ae4a6c-1790-4355-b5b1-879aaf956129
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: f30ba2a483ff7e5867417969946c2774175d5e3d
ms.contentlocale: it-it
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-enumerate-time-zones-present-on-a-computer"></a><span data-ttu-id="04800-104">Procedura: Enumerare i fusi orari presenti in un computer</span><span class="sxs-lookup"><span data-stu-id="04800-104">How to: enumerate time zones present on a computer</span></span>

<span data-ttu-id="04800-105">Per poter usare correttamente un determinato fuso orario è necessario che nel sistema siano disponibili le informazioni sul fuso orario.</span><span class="sxs-lookup"><span data-stu-id="04800-105">Successfully working with a designated time zone requires that information about that time zone be available to the system.</span></span> <span data-ttu-id="04800-106">Nel sistema operativo Windows, ad esempio, le informazioni sono archiviate nel Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="04800-106">For example, the Windows operating system stores this information in the registry.</span></span> <span data-ttu-id="04800-107">Sebbene nel mondo esistano molti fusi orari, le informazioni presenti nel Registro di sistema sono relative solo a una parte di essi.</span><span class="sxs-lookup"><span data-stu-id="04800-107">However, although the total number of time zones that exist throughout the world is large, the registry contains information about only a subset of them.</span></span> <span data-ttu-id="04800-108">Inoltre, il Registro di sistema è una struttura dinamica il cui contenuto è soggetto a modifiche intenzionali e accidentali.</span><span class="sxs-lookup"><span data-stu-id="04800-108">In addition, the registry itself is a dynamic structure whose contents are subject to both deliberate and accidental change.</span></span> <span data-ttu-id="04800-109">Di conseguenza, un'applicazione non può sempre presupporre che un determinato fuso orario sia definito e disponibile in un sistema.</span><span class="sxs-lookup"><span data-stu-id="04800-109">As a result, an application cannot always assume that a particular time zone is defined and available on a system.</span></span> <span data-ttu-id="04800-110">Il primo passaggio per molte applicazioni che si basano sulle informazioni del fuso orario è determinare se i fusi orari richiesti sono disponibili nel sistema locale o offrire all'utente un elenco di fusi orari da selezionare.</span><span class="sxs-lookup"><span data-stu-id="04800-110">The first step for many applications that use time zone information applications is to determine whether required time zones are available on the local system, or to give the user a list of time zones from which to select.</span></span> <span data-ttu-id="04800-111">A tale scopo, è necessario che un'applicazione sia in grado di enumerare i fusi orari definiti in un sistema locale.</span><span class="sxs-lookup"><span data-stu-id="04800-111">This requires that an application enumerate the time zones defined on a local system.</span></span> 

## <a name="to-enumerate-the-time-zones-present-on-the-local-system"></a><span data-ttu-id="04800-112">Per enumerare i fusi orari presenti nel sistema locale</span><span class="sxs-lookup"><span data-stu-id="04800-112">To enumerate the time zones present on the local system</span></span>

1. <span data-ttu-id="04800-113">Chiamare il metodo [TimeZoneInfo.GetSystemTimeZones](xref:System.TimeZoneInfo.GetSystemTimeZones).</span><span class="sxs-lookup"><span data-stu-id="04800-113">Call the [TimeZoneInfo.GetSystemTimeZones](xref:System.TimeZoneInfo.GetSystemTimeZones) method.</span></span> <span data-ttu-id="04800-114">Il metodo restituisce una raccolta [ReadOnlyCollection&lt;T&gt;](xref:System.Collections.ObjectModel.ReadOnlyCollection%601) generica di oggetti [TimeZoneInfo](xref:System.TimeZoneInfo).</span><span class="sxs-lookup"><span data-stu-id="04800-114">The method returns a generic [ReadOnlyCollection&lt;T&gt;](xref:System.Collections.ObjectModel.ReadOnlyCollection%601) collection of [TimeZoneInfo](xref:System.TimeZoneInfo) objects.</span></span> <span data-ttu-id="04800-115">Le voci della raccolta sono ordinate in base alla relativa proprietà [DisplayName](xref:System.TimeZoneInfo.DisplayName).</span><span class="sxs-lookup"><span data-stu-id="04800-115">The entries in the collection are sorted by their [DisplayName](xref:System.TimeZoneInfo.DisplayName) property.</span></span> <span data-ttu-id="04800-116">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="04800-116">For example:</span></span>

    ```csharp
    ReadOnlyCollection<TimeZoneInfo> tzCollection;
    tzCollection = TimeZoneInfo.GetSystemTimeZones();
    ```

    ```vb
    Dim tzCollection As ReadOnlyCollection(Of TimeZoneInfo) = TimeZoneInfo.GetSystemTimeZones
    ```

2. <span data-ttu-id="04800-117">Enumerare i singoli oggetti [TimeZoneInfo](xref:System.TimeZoneInfo) della raccolta usando un ciclo `foreach` (in C#) o un ciclo `For Each…Next` (in Visual Basic) ed eseguire tutte le elaborazioni necessarie su ogni oggetto.</span><span class="sxs-lookup"><span data-stu-id="04800-117">Enumerate the individual [TimeZoneInfo](xref:System.TimeZoneInfo) objects in the collection by using a `foreach` loop (in C#) or a `For Each…Next` loop (in Visual Basic), and perform any necessary processing on each object.</span></span> <span data-ttu-id="04800-118">Nel codice seguente, ad esempio, viene enumerata la raccolta [ReadOnlyCollection&lt;T&gt;](xref:System.Collections.ObjectModel.ReadOnlyCollection%601) degli oggetti [TimeZoneInfo](xref:System.TimeZoneInfo) restituiti nel passaggio 1 ed elencato il nome visualizzato di ogni fuso orario nella console.</span><span class="sxs-lookup"><span data-stu-id="04800-118">For example, the following code enumerates the [ReadOnlyCollection&lt;T&gt;](xref:System.Collections.ObjectModel.ReadOnlyCollection%601) collection of [TimeZoneInfo](xref:System.TimeZoneInfo) objects returned in step 1 and lists the display name of each time zone on the console.</span></span>

    ```csharp
    foreach (TimeZoneInfo timeZone in tzCollection)
    Console.WriteLine("   {0}: {1}", timeZone.Id, timeZone.DisplayName);
    ```

    ```vb
    For Each timeZone As TimeZoneInfo In tzCollection
        Console.WriteLine("   {0}: {1}", timeZone.Id, timeZone.DisplayName)
    Next
    ```

## <a name="see-also"></a><span data-ttu-id="04800-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04800-119">See Also</span></span>

[<span data-ttu-id="04800-120">Date, ore e fusi orari</span><span class="sxs-lookup"><span data-stu-id="04800-120">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="04800-121">Ricerca dei fusi orari definiti in un sistema locale</span><span class="sxs-lookup"><span data-stu-id="04800-121">Finding the time zones defined on a local system</span></span>](finding-the-time-zones-on-local-system.md)


