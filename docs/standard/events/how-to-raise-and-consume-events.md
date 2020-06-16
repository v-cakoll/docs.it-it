---
title: 'Procedura: generare e utilizzare eventi'
description: Generare & utilizzare eventi in .NET. Vedere esempi che usano il delegato EventHandler, il <TEventArgs> delegato EventHandler, & un delegato personalizzato.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- events [.NET Framework], raising
- raising events
- events [.NET Framework], samples
ms.assetid: 42afade7-3a02-4f2e-868b-95845f302f8f
ms.openlocfilehash: 4054e1a26c3392870af994a6eceafae92176a332
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84769275"
---
# <a name="how-to-raise-and-consume-events"></a><span data-ttu-id="2ebaa-104">Procedura: generare e utilizzare eventi</span><span class="sxs-lookup"><span data-stu-id="2ebaa-104">How to: Raise and Consume Events</span></span>
<span data-ttu-id="2ebaa-105">Gli esempi in questo argomento illustrano come usare gli eventi.</span><span class="sxs-lookup"><span data-stu-id="2ebaa-105">The examples in this topic show how to work with events.</span></span> <span data-ttu-id="2ebaa-106">Sono inclusi esempi del delegato <xref:System.EventHandler>, del delegato <xref:System.EventHandler%601> e di un delegato personalizzato, per illustrare gli eventi con e senza dati.</span><span class="sxs-lookup"><span data-stu-id="2ebaa-106">They include examples of the <xref:System.EventHandler> delegate, the <xref:System.EventHandler%601> delegate, and a custom delegate, to illustrate events with and without data.</span></span>  
  
 <span data-ttu-id="2ebaa-107">Gli esempi usano i concetti descritti nell'articolo [Eventi](index.md).</span><span class="sxs-lookup"><span data-stu-id="2ebaa-107">The examples use concepts described in the [Events](index.md) article.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ebaa-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="2ebaa-108">Example</span></span>  
 <span data-ttu-id="2ebaa-109">Il primo esempio mostra come generare e utilizzare un evento che non ha dati.</span><span class="sxs-lookup"><span data-stu-id="2ebaa-109">The first example shows how to raise and consume an event that doesn't have data.</span></span> <span data-ttu-id="2ebaa-110">Contiene una classe denominata `Counter` che ha un evento denominato `ThresholdReached`.</span><span class="sxs-lookup"><span data-stu-id="2ebaa-110">It contains a class named `Counter` that has an event named `ThresholdReached`.</span></span> <span data-ttu-id="2ebaa-111">Questo evento viene generato quando un valore di un contatore è maggiore o uguale a un valore soglia.</span><span class="sxs-lookup"><span data-stu-id="2ebaa-111">This event is raised when a counter value equals or exceeds a threshold value.</span></span> <span data-ttu-id="2ebaa-112">Il delegato <xref:System.EventHandler> è associato all'evento, perché non vengono forniti dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="2ebaa-112">The <xref:System.EventHandler> delegate is associated with the event, because no event data is provided.</span></span>  
  
 [!code-csharp[EventsOverview#5](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programnodata.cs#5)]
 [!code-vb[EventsOverview#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1nodata.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="2ebaa-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="2ebaa-113">Example</span></span>  
 <span data-ttu-id="2ebaa-114">L'esempio seguente mostra come generare e utilizzare un evento che fornisce i dati.</span><span class="sxs-lookup"><span data-stu-id="2ebaa-114">The next example shows how to raise and consume an event that provides data.</span></span> <span data-ttu-id="2ebaa-115">Il delegato <xref:System.EventHandler%601> è associato all'evento e viene fornita un'istanza di un oggetto dati evento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="2ebaa-115">The <xref:System.EventHandler%601> delegate is associated with the event, and an instance of a custom event data object is provided.</span></span>  
  
 [!code-cpp[EventsOverview#6](../../../samples/snippets/cpp/VS_Snippets_CLR/eventsoverview/cpp/programwithdata.cpp#6)]
 [!code-csharp[EventsOverview#6](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programwithdata.cs#6)]
 [!code-vb[EventsOverview#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1withdata.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="2ebaa-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="2ebaa-116">Example</span></span>  
 <span data-ttu-id="2ebaa-117">L'esempio seguente mostra come dichiarare un delegato per un evento.</span><span class="sxs-lookup"><span data-stu-id="2ebaa-117">The next example shows how to declare a delegate for an event.</span></span> <span data-ttu-id="2ebaa-118">Il delegato è denominato `ThresholdReachedEventHandler`.</span><span class="sxs-lookup"><span data-stu-id="2ebaa-118">The delegate is named `ThresholdReachedEventHandler`.</span></span> <span data-ttu-id="2ebaa-119">Si tratta solo di un esempio.</span><span class="sxs-lookup"><span data-stu-id="2ebaa-119">This is just an illustration.</span></span> <span data-ttu-id="2ebaa-120">In genere, non è necessario dichiarare un delegato per un evento, perché è possibile usare il delegato <xref:System.EventHandler> o <xref:System.EventHandler%601>.</span><span class="sxs-lookup"><span data-stu-id="2ebaa-120">Typically, you do not have to declare a delegate for an event, because you can use either the <xref:System.EventHandler> or the <xref:System.EventHandler%601> delegate.</span></span> <span data-ttu-id="2ebaa-121">È necessario dichiarare un delegato solo in rari casi, ad esempio per rendere la classe disponibile per il codice legacy che non può usare generics.</span><span class="sxs-lookup"><span data-stu-id="2ebaa-121">You should declare a delegate only in rare scenarios, such as making your class available to legacy code that cannot use generics.</span></span>  
  
 [!code-csharp[EventsOverview#7](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programwithdelegate.cs#7)]
 [!code-vb[EventsOverview#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1withdelegate.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="2ebaa-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ebaa-122">See also</span></span>

- [<span data-ttu-id="2ebaa-123">Events</span><span class="sxs-lookup"><span data-stu-id="2ebaa-123">Events</span></span>](index.md)
