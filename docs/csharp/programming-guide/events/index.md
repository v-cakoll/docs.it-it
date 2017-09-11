---
title: Eventi (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- classes [C#], events
- C# language, events
- events [C#]
ms.assetid: a8e51b22-d294-44fb-9539-0072f06c4cb3
caps.latest.revision: 43
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6a913a615de8185bb358376def1e2a051bdaa951
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="events-c-programming-guide"></a><span data-ttu-id="bce5e-102">Eventi (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="bce5e-102">Events (C# Programming Guide)</span></span>
<span data-ttu-id="bce5e-103">Tramite gli eventi, una [classe](../../../csharp/language-reference/keywords/class.md) o un oggetto è in grado di segnalare ad altre classi o oggetti una situazione di interesse.</span><span class="sxs-lookup"><span data-stu-id="bce5e-103">Events enable a [class](../../../csharp/language-reference/keywords/class.md) or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="bce5e-104">La classe che invia (o *genera*) l'evento è chiamata *autore* e le classi che ricevono (o *gestiscono*) l'evento sono chiamate *sottoscrittori*.</span><span class="sxs-lookup"><span data-stu-id="bce5e-104">The class that sends (or *raises*) the event is called the *publisher* and the classes that receive (or *handle*) the event are called *subscribers*.</span></span>  
  
 <span data-ttu-id="bce5e-105">In un'applicazione C# Web o Windows Form tipica si sottoscrivono eventi generati da controlli quali pulsanti e caselle di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="bce5e-105">In a typical C# Windows Forms or Web application, you subscribe to events raised by controls such as buttons and list boxes.</span></span> <span data-ttu-id="bce5e-106">È possibile usare l'ambiente di sviluppo integrato (IDE) di [!INCLUDE[csprcs](~/includes/csprcs-md.md)] per cercare gli eventi pubblicati da un controllo e selezionare quelli che si vuole gestire.</span><span class="sxs-lookup"><span data-stu-id="bce5e-106">You can use the [!INCLUDE[csprcs](~/includes/csprcs-md.md)] integrated development environment (IDE) to browse the events that a control publishes and select the ones that you want to handle.</span></span> <span data-ttu-id="bce5e-107">L'IDE aggiunge automaticamente un metodo vuoto del gestore eventi e il codice per sottoscrivere l'evento.</span><span class="sxs-lookup"><span data-stu-id="bce5e-107">The IDE automatically adds an empty event handler method and the code to subscribe to the event.</span></span> <span data-ttu-id="bce5e-108">Per altre informazioni, vedere [Procedura: sottoscrivere e annullare la sottoscrizione di eventi](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="bce5e-108">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>  
  
## <a name="events-overview"></a><span data-ttu-id="bce5e-109">Cenni preliminari sugli eventi</span><span class="sxs-lookup"><span data-stu-id="bce5e-109">Events Overview</span></span>  
 <span data-ttu-id="bce5e-110">Di seguito sono riportate le proprietà degli eventi:</span><span class="sxs-lookup"><span data-stu-id="bce5e-110">Events have the following properties:</span></span>  
  
-   <span data-ttu-id="bce5e-111">L'autore determina quando viene generato un evento. I sottoscrittori determinano quale azione viene eseguita in risposta all'evento.</span><span class="sxs-lookup"><span data-stu-id="bce5e-111">The publisher determines when an event is raised; the subscribers determine what action is taken in response to the event.</span></span>  
  
-   <span data-ttu-id="bce5e-112">Un evento può avere più sottoscrittori.</span><span class="sxs-lookup"><span data-stu-id="bce5e-112">An event can have multiple subscribers.</span></span> <span data-ttu-id="bce5e-113">Un sottoscrittore può gestire più eventi da più autori.</span><span class="sxs-lookup"><span data-stu-id="bce5e-113">A subscriber can handle multiple events from multiple publishers.</span></span>  
  
-   <span data-ttu-id="bce5e-114">Gli eventi che non hanno sottoscrittore non vengono mai generati.</span><span class="sxs-lookup"><span data-stu-id="bce5e-114">Events that have no subscribers are never raised.</span></span>  
  
-   <span data-ttu-id="bce5e-115">Gli eventi vengono in genere usati per segnalare azioni dell'utente, ad esempio la scelta di un pulsante o di una voce di menu nell'interfaccia utente grafica.</span><span class="sxs-lookup"><span data-stu-id="bce5e-115">Events are typically used to signal user actions such as button clicks or menu selections in graphical user interfaces.</span></span>  
  
-   <span data-ttu-id="bce5e-116">Quando un evento ha più sottoscrittori, i gestori eventi vengono richiamati in modo sincrono al momento della generazione dell'evento.</span><span class="sxs-lookup"><span data-stu-id="bce5e-116">When an event has multiple subscribers, the event handlers are invoked synchronously when an event is raised.</span></span> <span data-ttu-id="bce5e-117">Per richiamare gli eventi in modo asincrono, vedere [Calling Synchronous Methods Asynchronously](https://msdn.microsoft.com/library/2e08f6yc).</span><span class="sxs-lookup"><span data-stu-id="bce5e-117">To invoke events asynchronously, see [Calling Synchronous Methods Asynchronously](https://msdn.microsoft.com/library/2e08f6yc).</span></span>  
  
-   <span data-ttu-id="bce5e-118">Nella libreria di classi di [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] gli eventi sono basati sul delegato <xref:System.EventHandler> e sulla classe di base <xref:System.EventArgs> .</span><span class="sxs-lookup"><span data-stu-id="bce5e-118">In the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] class library, events are based on the <xref:System.EventHandler> delegate and the <xref:System.EventArgs> base class.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="bce5e-119">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="bce5e-119">Related Sections</span></span>  
 <span data-ttu-id="bce5e-120">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="bce5e-120">For more information, see:</span></span>  
  
-   [<span data-ttu-id="bce5e-121">Procedura: Eseguire e annullare la sottoscrizione a eventi</span><span class="sxs-lookup"><span data-stu-id="bce5e-121">How to: Subscribe to and Unsubscribe from Events</span></span>](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)  
  
-   [<span data-ttu-id="bce5e-122">Procedura: Pubblicare eventi conformi alle linee guida di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="bce5e-122">How to: Publish Events that Conform to .NET Framework Guidelines</span></span>](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md)  
  
-   [<span data-ttu-id="bce5e-123">Procedura: Generare eventi di classe base nelle classi derivate</span><span class="sxs-lookup"><span data-stu-id="bce5e-123">How to: Raise Base Class Events in Derived Classes</span></span>](../../../csharp/programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md)  
  
-   [<span data-ttu-id="bce5e-124">Procedura: Implementare eventi di interfaccia</span><span class="sxs-lookup"><span data-stu-id="bce5e-124">How to:  Implement Interface Events</span></span>](../../../csharp/programming-guide/events/how-to-implement-interface-events.md)  
  
-   [<span data-ttu-id="bce5e-125">Sincronizzazione di thread</span><span class="sxs-lookup"><span data-stu-id="bce5e-125">Thread Synchronization</span></span>](../../../csharp/programming-guide/concepts/threading/thread-synchronization.md)  
  
-   [<span data-ttu-id="bce5e-126">Procedura: Usare un dizionario per archiviare istanze di evento</span><span class="sxs-lookup"><span data-stu-id="bce5e-126">How to: Use a Dictionary to Store Event Instances</span></span>](../../../csharp/programming-guide/events/how-to-use-a-dictionary-to-store-event-instances.md)  
  
-   [<span data-ttu-id="bce5e-127">Procedura: Implementare funzioni di accesso a eventi personalizzati</span><span class="sxs-lookup"><span data-stu-id="bce5e-127">How to: Implement Custom Event Accessors</span></span>](../../../csharp/programming-guide/events/how-to-implement-custom-event-accessors.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="bce5e-128">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="bce5e-128">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="featured-book-chapters"></a><span data-ttu-id="bce5e-129">Capitoli del libro rappresentati</span><span class="sxs-lookup"><span data-stu-id="bce5e-129">Featured Book Chapters</span></span>  
 <span data-ttu-id="bce5e-130">[Delegates, Events, and Lambda Expressions](http://go.microsoft.com/fwlink/?LinkId=195395) (Delegati, eventi ed espressioni lambda) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](http://go.microsoft.com/fwlink/?LinkId=195369)</span><span class="sxs-lookup"><span data-stu-id="bce5e-130">[Delegates, Events, and Lambda Expressions](http://go.microsoft.com/fwlink/?LinkId=195395) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](http://go.microsoft.com/fwlink/?LinkId=195369)</span></span>  
  
 <span data-ttu-id="bce5e-131">[Delegati ed eventi](http://go.microsoft.com/fwlink/?LinkId=195418) (Delegati, eventi ed espressioni lambda) in [Learning C# 3.0: Master the fundamentals of C# 3.0](http://go.microsoft.com/fwlink/?LinkId=195412)</span><span class="sxs-lookup"><span data-stu-id="bce5e-131">[Delegates and Events](http://go.microsoft.com/fwlink/?LinkId=195418) in [Learning C# 3.0: Master the fundamentals of C# 3.0](http://go.microsoft.com/fwlink/?LinkId=195412)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bce5e-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bce5e-132">See Also</span></span>  
 <span data-ttu-id="bce5e-133"><xref:System.EventHandler></span><span class="sxs-lookup"><span data-stu-id="bce5e-133"><xref:System.EventHandler></span></span>   
 <span data-ttu-id="bce5e-134">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="bce5e-134">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="bce5e-135">[Delegati](../../../csharp/programming-guide/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="bce5e-135">[Delegates](../../../csharp/programming-guide/delegates/index.md) </span></span>  
 <span data-ttu-id="bce5e-136">[Creazione di gestori eventi in Windows Forms](https://msdn.microsoft.com/library/dacysss4.aspx) </span><span class="sxs-lookup"><span data-stu-id="bce5e-136">[Creating Event Handlers in Windows Forms](https://msdn.microsoft.com/library/dacysss4.aspx) </span></span>  
 [<span data-ttu-id="bce5e-137">Programmazione multithreading con il modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="bce5e-137">Multithreaded Programming with the Event-based Asynchronous Pattern</span></span>](https://msdn.microsoft.com/library/hkasytyf)

