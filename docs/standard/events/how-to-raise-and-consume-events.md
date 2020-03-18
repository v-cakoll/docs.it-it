---
title: 'Procedura: generare e utilizzare eventi'
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
ms.openlocfilehash: 256b5ae9ac2145e339136985872dfa5423aca730
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73131589"
---
# <a name="how-to-raise-and-consume-events"></a><span data-ttu-id="86539-102">Procedura: generare e utilizzare eventi</span><span class="sxs-lookup"><span data-stu-id="86539-102">How to: Raise and Consume Events</span></span>
<span data-ttu-id="86539-103">Gli esempi in questo argomento illustrano come usare gli eventi.</span><span class="sxs-lookup"><span data-stu-id="86539-103">The examples in this topic show how to work with events.</span></span> <span data-ttu-id="86539-104">Sono inclusi esempi del delegato <xref:System.EventHandler>, del delegato <xref:System.EventHandler%601> e di un delegato personalizzato, per illustrare gli eventi con e senza dati.</span><span class="sxs-lookup"><span data-stu-id="86539-104">They include examples of the <xref:System.EventHandler> delegate, the <xref:System.EventHandler%601> delegate, and a custom delegate, to illustrate events with and without data.</span></span>  
  
 <span data-ttu-id="86539-105">Gli esempi usano i concetti descritti nell'articolo [Eventi](../../../docs/standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="86539-105">The examples use concepts described in the [Events](../../../docs/standard/events/index.md) article.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86539-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="86539-106">Example</span></span>  
 <span data-ttu-id="86539-107">Il primo esempio mostra come generare e utilizzare un evento che non ha dati.</span><span class="sxs-lookup"><span data-stu-id="86539-107">The first example shows how to raise and consume an event that doesn't have data.</span></span> <span data-ttu-id="86539-108">Contiene una classe denominata `Counter` che ha un evento denominato `ThresholdReached`.</span><span class="sxs-lookup"><span data-stu-id="86539-108">It contains a class named `Counter` that has an event named `ThresholdReached`.</span></span> <span data-ttu-id="86539-109">Questo evento viene generato quando un valore di un contatore è maggiore o uguale a un valore soglia.</span><span class="sxs-lookup"><span data-stu-id="86539-109">This event is raised when a counter value equals or exceeds a threshold value.</span></span> <span data-ttu-id="86539-110">Il delegato <xref:System.EventHandler> è associato all'evento, perché non vengono forniti dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="86539-110">The <xref:System.EventHandler> delegate is associated with the event, because no event data is provided.</span></span>  
  
 [!code-csharp[EventsOverview#5](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programnodata.cs#5)]
 [!code-vb[EventsOverview#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1nodata.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="86539-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="86539-111">Example</span></span>  
 <span data-ttu-id="86539-112">L'esempio seguente mostra come generare e utilizzare un evento che fornisce i dati.</span><span class="sxs-lookup"><span data-stu-id="86539-112">The next example shows how to raise and consume an event that provides data.</span></span> <span data-ttu-id="86539-113">Il delegato <xref:System.EventHandler%601> è associato all'evento e viene fornita un'istanza di un oggetto dati evento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="86539-113">The <xref:System.EventHandler%601> delegate is associated with the event, and an instance of a custom event data object is provided.</span></span>  
  
 [!code-cpp[EventsOverview#6](../../../samples/snippets/cpp/VS_Snippets_CLR/eventsoverview/cpp/programwithdata.cpp#6)]
 [!code-csharp[EventsOverview#6](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programwithdata.cs#6)]
 [!code-vb[EventsOverview#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1withdata.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="86539-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="86539-114">Example</span></span>  
 <span data-ttu-id="86539-115">L'esempio seguente mostra come dichiarare un delegato per un evento.</span><span class="sxs-lookup"><span data-stu-id="86539-115">The next example shows how to declare a delegate for an event.</span></span> <span data-ttu-id="86539-116">Il delegato è denominato `ThresholdReachedEventHandler`.</span><span class="sxs-lookup"><span data-stu-id="86539-116">The delegate is named `ThresholdReachedEventHandler`.</span></span> <span data-ttu-id="86539-117">Si tratta solo di un esempio.</span><span class="sxs-lookup"><span data-stu-id="86539-117">This is just an illustration.</span></span> <span data-ttu-id="86539-118">In genere, non è necessario dichiarare un delegato per un evento, perché è possibile usare il delegato <xref:System.EventHandler> o <xref:System.EventHandler%601>.</span><span class="sxs-lookup"><span data-stu-id="86539-118">Typically, you do not have to declare a delegate for an event, because you can use either the <xref:System.EventHandler> or the <xref:System.EventHandler%601> delegate.</span></span> <span data-ttu-id="86539-119">È necessario dichiarare un delegato solo in rari casi, ad esempio per rendere la classe disponibile per il codice legacy che non può usare generics.</span><span class="sxs-lookup"><span data-stu-id="86539-119">You should declare a delegate only in rare scenarios, such as making your class available to legacy code that cannot use generics.</span></span>  
  
 [!code-csharp[EventsOverview#7](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programwithdelegate.cs#7)]
 [!code-vb[EventsOverview#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1withdelegate.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="86539-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86539-120">See also</span></span>

- [<span data-ttu-id="86539-121">Events</span><span class="sxs-lookup"><span data-stu-id="86539-121">Events</span></span>](../../../docs/standard/events/index.md)
