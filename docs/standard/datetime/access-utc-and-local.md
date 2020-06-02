---
title: "Procedura: accedere agli oggetti predefiniti dell'ora UTC e del fuso orario locale"
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], local
- predefined time zones
- UTC times, predefined
- local time zone access
- time zones [.NET Framework], retrieving
- time zones [.NET Framework], UTC
ms.assetid: 961fb70b-83f0-4dab-a042-cb5fcd817cf5
ms.openlocfilehash: ebb07800b2a35f4faf312dc55b8c5679079b4b68
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291409"
---
# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a><span data-ttu-id="c2f89-102">Procedura: accedere agli oggetti predefiniti dell'ora UTC e del fuso orario locale</span><span class="sxs-lookup"><span data-stu-id="c2f89-102">How to: Access the predefined UTC and local time zone objects</span></span>

<span data-ttu-id="c2f89-103">La <xref:System.TimeZoneInfo> classe fornisce due proprietà, <xref:System.TimeZoneInfo.Utc%2A> e <xref:System.TimeZoneInfo.Local%2A> , che consentono al codice di accedere agli oggetti predefiniti del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="c2f89-103">The <xref:System.TimeZoneInfo> class provides two properties, <xref:System.TimeZoneInfo.Utc%2A> and <xref:System.TimeZoneInfo.Local%2A>, that give your code access to predefined time zone objects.</span></span> <span data-ttu-id="c2f89-104">In questo argomento viene illustrato come accedere agli oggetti <xref:System.TimeZoneInfo> restituiti da tali proprietà.</span><span class="sxs-lookup"><span data-stu-id="c2f89-104">This topic discusses how to access the <xref:System.TimeZoneInfo> objects returned by those properties.</span></span>

### <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a><span data-ttu-id="c2f89-105">Per accedere all'oggetto TimeZoneInfo dell'ora UTC (Coordinated Universal Time)</span><span class="sxs-lookup"><span data-stu-id="c2f89-105">To access the Coordinated Universal Time (UTC) TimeZoneInfo object</span></span>

1. <span data-ttu-id="c2f89-106">Utilizzare la `static` `Shared` Proprietà (in Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> per accedere all'ora UTC (Coordinated Universal Time).</span><span class="sxs-lookup"><span data-stu-id="c2f89-106">Use the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property to access Coordinated Universal Time.</span></span>

2. <span data-ttu-id="c2f89-107">Anziché assegnare l' <xref:System.TimeZoneInfo> oggetto restituito dalla proprietà a una variabile oggetto, continuare ad accedere all'ora UTC (Coordinated Universal Time) tramite la <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="c2f89-107">Rather than assigning the <xref:System.TimeZoneInfo> object returned by the property to an object variable, continue to access Coordinated Universal Time through the <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property.</span></span>

### <a name="to-access-the-local-time-zone"></a><span data-ttu-id="c2f89-108">Per accedere al fuso orario locale</span><span class="sxs-lookup"><span data-stu-id="c2f89-108">To access the local time zone</span></span>

1. <span data-ttu-id="c2f89-109">Utilizzare la `static` `Shared` Proprietà (in Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> per accedere al fuso orario del sistema locale.</span><span class="sxs-lookup"><span data-stu-id="c2f89-109">Use the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property to access the local system time zone.</span></span>

2. <span data-ttu-id="c2f89-110">Anziché assegnare l' <xref:System.TimeZoneInfo> oggetto restituito dalla proprietà a una variabile oggetto, continuare ad accedere al fuso orario locale tramite la <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="c2f89-110">Rather than assigning the <xref:System.TimeZoneInfo> object returned by the property to an object variable, continue to access the local time zone through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property.</span></span>

## <a name="example"></a><span data-ttu-id="c2f89-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="c2f89-111">Example</span></span>

<span data-ttu-id="c2f89-112">Nel codice seguente vengono utilizzate le proprietà <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> e <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> per convertire un orario del fuso orario standard degli Stati Uniti e Canada orientale, nonché per visualizzare il nome del fuso orario nella console.</span><span class="sxs-lookup"><span data-stu-id="c2f89-112">The following code uses the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> and <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> properties to convert a time from the U.S. and Canadian Eastern Standard time zone, as well as to display the time zone name to the console.</span></span>

[!code-csharp[System.TimeZone2.Concepts#13](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#13)]
[!code-vb[System.TimeZone2.Concepts#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#13)]

<span data-ttu-id="c2f89-113">È necessario accedere sempre al fuso orario locale tramite la <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> proprietà anziché assegnare il fuso orario locale a una <xref:System.TimeZoneInfo> variabile oggetto.</span><span class="sxs-lookup"><span data-stu-id="c2f89-113">You should always access the local time zone through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property rather than assigning the local time zone to a <xref:System.TimeZoneInfo> object variable.</span></span> <span data-ttu-id="c2f89-114">Analogamente, è consigliabile accedere sempre all'ora UTC (Coordinated Universal Time) tramite la <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> proprietà anziché assegnare la zona UTC a una <xref:System.TimeZoneInfo> variabile oggetto.</span><span class="sxs-lookup"><span data-stu-id="c2f89-114">Similarly, you should always access Coordinated Universal Time through the <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property rather than assigning the UTC zone to a <xref:System.TimeZoneInfo> object variable.</span></span> <span data-ttu-id="c2f89-115">In questo modo si impedisce <xref:System.TimeZoneInfo> che la variabile oggetto venga invalidata da una chiamata al <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="c2f89-115">This prevents the <xref:System.TimeZoneInfo> object variable from being invalidated by a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="c2f89-116">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="c2f89-116">Compiling the code</span></span>

<span data-ttu-id="c2f89-117">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c2f89-117">This example requires:</span></span>

- <span data-ttu-id="c2f89-118">Che lo <xref:System> spazio dei nomi venga importato con l' `using` istruzione (obbligatoria nel codice C#).</span><span class="sxs-lookup"><span data-stu-id="c2f89-118">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="c2f89-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2f89-119">See also</span></span>

- [<span data-ttu-id="c2f89-120">Date, ore e fusi orari</span><span class="sxs-lookup"><span data-stu-id="c2f89-120">Dates, times, and time zones</span></span>](index.md)
- [<span data-ttu-id="c2f89-121">Ricerca dei fusi orari definiti in un sistema locale</span><span class="sxs-lookup"><span data-stu-id="c2f89-121">Finding the time zones defined on a local system</span></span>](finding-the-time-zones-on-local-system.md)
- [<span data-ttu-id="c2f89-122">Procedura: creare un'istanza di un oggetto TimeZoneInfo</span><span class="sxs-lookup"><span data-stu-id="c2f89-122">How to: Instantiate a TimeZoneInfo object</span></span>](instantiate-time-zone-info.md)
