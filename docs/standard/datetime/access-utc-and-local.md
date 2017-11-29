---
title: 'Procedura: accedere a oggetti fuso UTC e l''ora locali predefiniti'
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4538407bc66ad7974a9a4998c8e5d7ccb38fab4e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a><span data-ttu-id="c356b-102">Procedura: accedere a oggetti fuso UTC e l'ora locali predefiniti</span><span class="sxs-lookup"><span data-stu-id="c356b-102">How to: Access the predefined UTC and local time zone objects</span></span>

<span data-ttu-id="c356b-103">Il <xref:System.TimeZoneInfo> classe fornisce due proprietà, <xref:System.TimeZoneInfo.Utc%2A> e <xref:System.TimeZoneInfo.Local%2A>, che forniscono il codice di accesso agli oggetti predefiniti del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="c356b-103">The <xref:System.TimeZoneInfo> class provides two properties, <xref:System.TimeZoneInfo.Utc%2A> and <xref:System.TimeZoneInfo.Local%2A>, that give your code access to predefined time zone objects.</span></span> <span data-ttu-id="c356b-104">In questo argomento viene illustrato come accedere agli oggetti <xref:System.TimeZoneInfo> restituiti da tali proprietà.</span><span class="sxs-lookup"><span data-stu-id="c356b-104">This topic discusses how to access the <xref:System.TimeZoneInfo> objects returned by those properties.</span></span>

### <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a><span data-ttu-id="c356b-105">Per accedere all'oggetto TimeZoneInfo dell'ora UTC (Coordinated Universal Time)</span><span class="sxs-lookup"><span data-stu-id="c356b-105">To access the Coordinated Universal Time (UTC) TimeZoneInfo object</span></span>

1. <span data-ttu-id="c356b-106">Utilizzare il `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> proprietà a cui accedere Coordinated Universal Time.</span><span class="sxs-lookup"><span data-stu-id="c356b-106">Use the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property to access Coordinated Universal Time.</span></span>

2. <span data-ttu-id="c356b-107">Invece di assegnare il <xref:System.TimeZoneInfo> oggetto restituito dalla proprietà a una variabile oggetto, continuare ad accedere a Coordinated Universal Time tramite il <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> proprietà.</span><span class="sxs-lookup"><span data-stu-id="c356b-107">Rather than assigning the <xref:System.TimeZoneInfo> object returned by the property to an object variable, continue to access Coordinated Universal Time through the <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property.</span></span>

### <a name="to-access-the-local-time-zone"></a><span data-ttu-id="c356b-108">Per accedere al fuso orario locale</span><span class="sxs-lookup"><span data-stu-id="c356b-108">To access the local time zone</span></span>

1. <span data-ttu-id="c356b-109">Utilizzare il `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> proprietà per accedere al fuso orario di sistema locale.</span><span class="sxs-lookup"><span data-stu-id="c356b-109">Use the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property to access the local system time zone.</span></span>

2. <span data-ttu-id="c356b-110">Invece di assegnare il <xref:System.TimeZoneInfo> oggetto restituito dalla proprietà a una variabile oggetto, continuare ad accedere al fuso orario locale tramite la <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> proprietà.</span><span class="sxs-lookup"><span data-stu-id="c356b-110">Rather than assigning the <xref:System.TimeZoneInfo> object returned by the property to an object variable, continue to access the local time zone through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property.</span></span>

## <a name="example"></a><span data-ttu-id="c356b-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="c356b-111">Example</span></span>

<span data-ttu-id="c356b-112">Nel codice seguente vengono utilizzate le proprietà <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> e <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> per convertire un orario del fuso orario standard degli Stati Uniti e Canada orientale, nonché per visualizzare il nome del fuso orario nella console.</span><span class="sxs-lookup"><span data-stu-id="c356b-112">The following code uses the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> and <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> properties to convert a time from the U.S. and Canadian Eastern Standard time zone, as well as to display the time zone name to the console.</span></span>

[!code-csharp[System.TimeZone2.Concepts#13](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#13)]
[!code-vb[System.TimeZone2.Concepts#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#13)]

<span data-ttu-id="c356b-113">È necessario accedere sempre il fuso orario locale tramite la <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> proprietà anziché assegnare l'ora locale della zona per una <xref:System.TimeZoneInfo> variabile oggetto.</span><span class="sxs-lookup"><span data-stu-id="c356b-113">You should always access the local time zone through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property rather than assigning the local time zone to a <xref:System.TimeZoneInfo> object variable.</span></span> <span data-ttu-id="c356b-114">Analogamente, è necessario accedere sempre Coordinated Universal Time tramite il <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> proprietà anziché assegnare l'ora UTC della zona per una <xref:System.TimeZoneInfo> variabile oggetto.</span><span class="sxs-lookup"><span data-stu-id="c356b-114">Similarly, you should always access Coordinated Universal Time through the <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property rather than assigning the UTC zone to a <xref:System.TimeZoneInfo> object variable.</span></span> <span data-ttu-id="c356b-115">In questo modo il <xref:System.TimeZoneInfo> variabile oggetto venga invalidata da una chiamata al <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="c356b-115">This prevents the <xref:System.TimeZoneInfo> object variable from being invalidated by a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="c356b-116">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="c356b-116">Compiling the code</span></span>

<span data-ttu-id="c356b-117">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c356b-117">This example requires:</span></span>

* <span data-ttu-id="c356b-118">Un riferimento a System.Core.dll essere aggiunto al progetto.</span><span class="sxs-lookup"><span data-stu-id="c356b-118">That a reference to System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="c356b-119">Che il <xref:System> dello spazio dei nomi importati con il `using` istruzione (richiesto nel codice c#).</span><span class="sxs-lookup"><span data-stu-id="c356b-119">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="c356b-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c356b-120">See also</span></span>

<span data-ttu-id="c356b-121">[Date, ore e fusi orari](../../../docs/standard/datetime/index.md)
[ricerca dei fusi orari definiti in un sistema locale](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
[procedura: creare un'istanza di un oggetto TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md)</span><span class="sxs-lookup"><span data-stu-id="c356b-121">[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[Finding the time zones defined on a local system](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
[How to: Instantiate a TimeZoneInfo object](../../../docs/standard/datetime/instantiate-time-zone-info.md)</span></span>
