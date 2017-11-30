---
title: 'Procedura: generare e utilizzare eventi'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- events [.NET Framework], raising
- raising events
- events [.NET Framework], samples
ms.assetid: 42afade7-3a02-4f2e-868b-95845f302f8f
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d052c865a554977ce5c8b0a347337d9d9b92fc57
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-raise-and-consume-events"></a><span data-ttu-id="24755-102">Procedura: generare e utilizzare eventi</span><span class="sxs-lookup"><span data-stu-id="24755-102">How to: Raise and Consume Events</span></span>
<span data-ttu-id="24755-103">Gli esempi in questo argomento viene illustrato come utilizzare gli eventi.</span><span class="sxs-lookup"><span data-stu-id="24755-103">The examples in this topic show how to work with events.</span></span> <span data-ttu-id="24755-104">Gli esempi includono la <xref:System.EventHandler> delegato, il <xref:System.EventHandler%601> delegato e un delegato personalizzato, per illustrare gli eventi con e senza dati.</span><span class="sxs-lookup"><span data-stu-id="24755-104">They include examples of the <xref:System.EventHandler> delegate, the <xref:System.EventHandler%601> delegate, and a custom delegate, to illustrate events with and without data.</span></span>  
  
 <span data-ttu-id="24755-105">Gli esempi utilizzano i concetti illustrati nella sezione di [eventi](../../../docs/standard/events/index.md) articolo.</span><span class="sxs-lookup"><span data-stu-id="24755-105">The examples use concepts described in the [Events](../../../docs/standard/events/index.md) article.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24755-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="24755-106">Example</span></span>  
 <span data-ttu-id="24755-107">Nel primo esempio viene illustrato come generare e utilizzare un evento che non dispone di dati.</span><span class="sxs-lookup"><span data-stu-id="24755-107">The first example shows how to raise and consume an event that doesn't have data.</span></span> <span data-ttu-id="24755-108">Contiene una classe denominata `Counter` che dispone di un evento denominato `ThresholdReached`.</span><span class="sxs-lookup"><span data-stu-id="24755-108">It contains a class named `Counter` that has an event named `ThresholdReached`.</span></span> <span data-ttu-id="24755-109">Questo evento viene generato quando un valore uguale o maggiore di un valore soglia.</span><span class="sxs-lookup"><span data-stu-id="24755-109">This event is raised when a counter value equals or exceeds a threshold value.</span></span> <span data-ttu-id="24755-110">Il <xref:System.EventHandler> delegato è associato all'evento, perché non è stato specificato nessun dato dell'evento.</span><span class="sxs-lookup"><span data-stu-id="24755-110">The <xref:System.EventHandler> delegate is associated with the event, because no event data is provided.</span></span>  
  
 [!code-csharp[EventsOverview#5](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programnodata.cs#5)]
 [!code-vb[EventsOverview#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1nodata.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="24755-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="24755-111">Example</span></span>  
 <span data-ttu-id="24755-112">Nell'esempio seguente viene illustrato come generare e utilizzare un evento che fornisce i dati.</span><span class="sxs-lookup"><span data-stu-id="24755-112">The next example shows how to raise and consume an event that provides data.</span></span> <span data-ttu-id="24755-113">Il <xref:System.EventHandler%601> delegato è associato all'evento e viene fornita un'istanza di un oggetto dati di evento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="24755-113">The <xref:System.EventHandler%601> delegate is associated with the event, and an instance of a custom event data object is provided.</span></span>  
  
 [!code-cpp[EventsOverview#6](../../../samples/snippets/cpp/VS_Snippets_CLR/eventsoverview/cpp/programwithdata.cpp#6)]
 [!code-csharp[EventsOverview#6](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programwithdata.cs#6)]
 [!code-vb[EventsOverview#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1withdata.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="24755-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="24755-114">Example</span></span>  
 <span data-ttu-id="24755-115">Nell'esempio seguente viene illustrato come dichiarare un delegato per un evento.</span><span class="sxs-lookup"><span data-stu-id="24755-115">The next example shows how to declare a delegate for an event.</span></span> <span data-ttu-id="24755-116">Il delegato denominato `ThresholdReachedEventHandler`.</span><span class="sxs-lookup"><span data-stu-id="24755-116">The delegate is named `ThresholdReachedEventHandler`.</span></span> <span data-ttu-id="24755-117">Questa è solo un'illustrazione.</span><span class="sxs-lookup"><span data-stu-id="24755-117">This is just an illustration.</span></span> <span data-ttu-id="24755-118">In genere, non è necessario dichiarare un delegato per un evento, poiché è possibile utilizzare il <xref:System.EventHandler> o <xref:System.EventHandler%601> delegato.</span><span class="sxs-lookup"><span data-stu-id="24755-118">Typically, you do not have to declare a delegate for an event, because you can use either the <xref:System.EventHandler> or the <xref:System.EventHandler%601> delegate.</span></span> <span data-ttu-id="24755-119">È necessario dichiarare un delegato solo in rari scenari, ad esempio, per la classe disponibile per il codice legacy che non è possibile utilizzare generics.</span><span class="sxs-lookup"><span data-stu-id="24755-119">You should declare a delegate only in rare scenarios, such as making your class available to legacy code that cannot use generics.</span></span>  
  
 [!code-csharp[EventsOverview#7](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programwithdelegate.cs#7)]
 [!code-vb[EventsOverview#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1withdelegate.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="24755-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24755-120">See Also</span></span>  
 [<span data-ttu-id="24755-121">Eventi</span><span class="sxs-lookup"><span data-stu-id="24755-121">Events</span></span>](../../../docs/standard/events/index.md)
