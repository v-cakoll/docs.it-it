---
title: 'Procedura: gestire più eventi mediante le relative proprietà'
description: Informazioni su come gestire molti eventi usando le proprietà dell'evento. Definire raccolte di delegati, chiavi di evento, & proprietà dell'evento. Implementare i metodi Add & Remove della funzione di accesso.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- event properties [.NET Framework]
- multiple events [.NET Framework]
- event handling [.NET Framework], with multiple events
- events [.NET Framework], multiple
ms.assetid: 30047cba-e2fd-41c6-b9ca-2ad7a49003db
ms.openlocfilehash: 5b528aa2145ba703ce605ce22ae7d643f1e5b8d0
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84769015"
---
# <a name="how-to-handle-multiple-events-using-event-properties"></a><span data-ttu-id="08f3a-105">Procedura: gestire più eventi mediante le relative proprietà</span><span class="sxs-lookup"><span data-stu-id="08f3a-105">How to: Handle Multiple Events Using Event Properties</span></span>
<span data-ttu-id="08f3a-106">Per utilizzare le proprietà evento è necessario definire queste proprietà nella classe tramite cui vengono generati gli eventi e, successivamente, impostarne i delegati nelle classi mediante cui vengono gestiti gli eventi.</span><span class="sxs-lookup"><span data-stu-id="08f3a-106">To use event properties, you define the event properties in the class that raises the events, and then set the delegates for the event properties in classes that handle the events.</span></span> <span data-ttu-id="08f3a-107">Per implementare più proprietà evento in una classe, la classe deve archiviare e mantenere internamente il delegato definito per ogni evento.</span><span class="sxs-lookup"><span data-stu-id="08f3a-107">To implement multiple event properties in a class, the class must internally store and maintain the delegate defined for each event.</span></span> <span data-ttu-id="08f3a-108">Uno degli approcci più comuni consiste nell'implementare una raccolta di delegati indicizzata da una chiave evento.</span><span class="sxs-lookup"><span data-stu-id="08f3a-108">A typical approach is to implement a delegate collection that is indexed by an event key.</span></span>  
  
 <span data-ttu-id="08f3a-109">Per archiviare i delegati per ogni evento, è possibile usare la classe <xref:System.ComponentModel.EventHandlerList> o implementare una raccolta personalizzata.</span><span class="sxs-lookup"><span data-stu-id="08f3a-109">To store the delegates for each event, you can use the <xref:System.ComponentModel.EventHandlerList> class, or implement your own collection.</span></span> <span data-ttu-id="08f3a-110">La classe della raccolta deve fornire metodi per l'impostazione, l'accesso e il recupero del delegato del gestore eventi in base alla chiave evento.</span><span class="sxs-lookup"><span data-stu-id="08f3a-110">The collection class must provide methods for setting, accessing, and retrieving the event handler delegate based on the event key.</span></span> <span data-ttu-id="08f3a-111">È possibile, ad esempio, usare una classe <xref:System.Collections.Hashtable> o derivare una classe personalizzata dalla classe <xref:System.Collections.DictionaryBase>.</span><span class="sxs-lookup"><span data-stu-id="08f3a-111">For example, you could use a <xref:System.Collections.Hashtable> class, or derive a custom class from the <xref:System.Collections.DictionaryBase> class.</span></span> <span data-ttu-id="08f3a-112">I dettagli sull'implementazione della raccolta di delegati non devono necessariamente essere esposti al di fuori della classe.</span><span class="sxs-lookup"><span data-stu-id="08f3a-112">The implementation details of the delegate collection do not need to be exposed outside your class.</span></span>  
  
 <span data-ttu-id="08f3a-113">Ogni proprietà evento all'interno della classe definisce un metodo della funzione di accesso add e un metodo della funzione di accesso remove.</span><span class="sxs-lookup"><span data-stu-id="08f3a-113">Each event property within the class defines an add accessor method and a remove accessor method.</span></span> <span data-ttu-id="08f3a-114">La funzione di accesso add di una proprietà evento aggiunge un'istanza del delegato di input alla raccolta di delegati.</span><span class="sxs-lookup"><span data-stu-id="08f3a-114">The add accessor for an event property adds the input delegate instance to the delegate collection.</span></span> <span data-ttu-id="08f3a-115">La funzione di accesso remove di una proprietà evento rimuove un'istanza del delegato di input dalla raccolta di delegati.</span><span class="sxs-lookup"><span data-stu-id="08f3a-115">The remove accessor for an event property removes the input delegate instance from the delegate collection.</span></span> <span data-ttu-id="08f3a-116">Le funzioni di accesso delle proprietà evento usano la chiave predefinita della proprietà per aggiungere e rimuovere istanze nella raccolta di delegati.</span><span class="sxs-lookup"><span data-stu-id="08f3a-116">The event property accessors use the predefined key for the event property to add and remove instances from the delegate collection.</span></span>  
  
### <a name="to-handle-multiple-events-using-event-properties"></a><span data-ttu-id="08f3a-117">Per gestire più eventi mediante le relative proprietà</span><span class="sxs-lookup"><span data-stu-id="08f3a-117">To handle multiple events using event properties</span></span>  
  
1. <span data-ttu-id="08f3a-118">Definire una raccolta di delegati all'interno della classe che genera gli eventi.</span><span class="sxs-lookup"><span data-stu-id="08f3a-118">Define a delegate collection within the class that raises the events.</span></span>  
  
2. <span data-ttu-id="08f3a-119">Definire una chiave per ogni evento.</span><span class="sxs-lookup"><span data-stu-id="08f3a-119">Define a key for each event.</span></span>  
  
3. <span data-ttu-id="08f3a-120">Definire le proprietà evento nella classe che genera gli eventi.</span><span class="sxs-lookup"><span data-stu-id="08f3a-120">Define the event properties in the class that raises the events.</span></span>  
  
4. <span data-ttu-id="08f3a-121">Usare la raccolta di delegati per implementare i metodi delle funzioni di accesso add e remove per le proprietà evento.</span><span class="sxs-lookup"><span data-stu-id="08f3a-121">Use the delegate collection to implement the add and remove accessor methods for the event properties.</span></span>  
  
5. <span data-ttu-id="08f3a-122">Usare le proprietà evento pubbliche per aggiungere e rimuovere i delegati dei gestori eventi nelle classi che gestiscono gli eventi.</span><span class="sxs-lookup"><span data-stu-id="08f3a-122">Use the public event properties to add and remove event handler delegates in the classes that handle the events.</span></span>  
  
## <a name="example"></a><span data-ttu-id="08f3a-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="08f3a-123">Example</span></span>  
 <span data-ttu-id="08f3a-124">L'esempio C# seguente implementa le proprietà evento `MouseDown` e `MouseUp`, usando un oggetto <xref:System.ComponentModel.EventHandlerList> per archiviare il delegato di ogni evento.</span><span class="sxs-lookup"><span data-stu-id="08f3a-124">The following C# example implements the event properties `MouseDown` and `MouseUp`, using an <xref:System.ComponentModel.EventHandlerList> to store each event's delegate.</span></span> <span data-ttu-id="08f3a-125">Le parole chiave dei costrutti delle proprietà evento sono riportate in grassetto.</span><span class="sxs-lookup"><span data-stu-id="08f3a-125">The keywords of the event property constructs are in bold type.</span></span>  
  
 [!code-cpp[Conceptual.Events.Other#31](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.events.other/cpp/example3.cpp#31)]
 [!code-csharp[Conceptual.Events.Other#31](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.events.other/cs/example3.cs#31)]
 [!code-vb[Conceptual.Events.Other#31](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.events.other/vb/example3.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="08f3a-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08f3a-126">See also</span></span>

- <xref:System.ComponentModel.EventHandlerList?displayProperty=nameWithType>
- [<span data-ttu-id="08f3a-127">Events</span><span class="sxs-lookup"><span data-stu-id="08f3a-127">Events</span></span>](index.md)
- <xref:System.Web.UI.Control.Events%2A?displayProperty=nameWithType>
- [<span data-ttu-id="08f3a-128">Procedura: dichiarare eventi personalizzati per proteggere la memoria</span><span class="sxs-lookup"><span data-stu-id="08f3a-128">How to: Declare Custom Events To Conserve Memory</span></span>](../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)
