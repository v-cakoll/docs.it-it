---
title: Eventi (Guida per programmatori C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- classes [C#], events
- C# language, events
- events [C#]
ms.assetid: a8e51b22-d294-44fb-9539-0072f06c4cb3
caps.latest.revision: "43"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f714bded446e62ac6165d691d2404249275178e8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="events-c-programming-guide"></a><span data-ttu-id="77ddc-102">Eventi (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="77ddc-102">Events (C# Programming Guide)</span></span>
<span data-ttu-id="77ddc-103">Tramite gli eventi, una [classe](../../../csharp/language-reference/keywords/class.md) o un oggetto è in grado di segnalare ad altre classi o oggetti una situazione di interesse.</span><span class="sxs-lookup"><span data-stu-id="77ddc-103">Events enable a [class](../../../csharp/language-reference/keywords/class.md) or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="77ddc-104">La classe che invia (o *genera*) l'evento è chiamata *autore* e le classi che ricevono (o *gestiscono*) l'evento sono chiamate *sottoscrittori*.</span><span class="sxs-lookup"><span data-stu-id="77ddc-104">The class that sends (or *raises*) the event is called the *publisher* and the classes that receive (or *handle*) the event are called *subscribers*.</span></span>  
  
 <span data-ttu-id="77ddc-105">In un'applicazione C# Web o Windows Form tipica si sottoscrivono eventi generati da controlli quali pulsanti e caselle di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="77ddc-105">In a typical C# Windows Forms or Web application, you subscribe to events raised by controls such as buttons and list boxes.</span></span> <span data-ttu-id="77ddc-106">È possibile usare l'ambiente di sviluppo integrato (IDE) di [!INCLUDE[csprcs](~/includes/csprcs-md.md)] per cercare gli eventi pubblicati da un controllo e selezionare quelli che si vuole gestire.</span><span class="sxs-lookup"><span data-stu-id="77ddc-106">You can use the [!INCLUDE[csprcs](~/includes/csprcs-md.md)] integrated development environment (IDE) to browse the events that a control publishes and select the ones that you want to handle.</span></span> <span data-ttu-id="77ddc-107">L'IDE aggiunge automaticamente un metodo vuoto del gestore eventi e il codice per sottoscrivere l'evento.</span><span class="sxs-lookup"><span data-stu-id="77ddc-107">The IDE automatically adds an empty event handler method and the code to subscribe to the event.</span></span> <span data-ttu-id="77ddc-108">Per altre informazioni, vedere [Procedura: sottoscrivere e annullare la sottoscrizione di eventi](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="77ddc-108">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>  
  
## <a name="events-overview"></a><span data-ttu-id="77ddc-109">Cenni preliminari sugli eventi</span><span class="sxs-lookup"><span data-stu-id="77ddc-109">Events Overview</span></span>  
 <span data-ttu-id="77ddc-110">Di seguito sono riportate le proprietà degli eventi:</span><span class="sxs-lookup"><span data-stu-id="77ddc-110">Events have the following properties:</span></span>  
  
-   <span data-ttu-id="77ddc-111">L'autore determina quando viene generato un evento. I sottoscrittori determinano quale azione viene eseguita in risposta all'evento.</span><span class="sxs-lookup"><span data-stu-id="77ddc-111">The publisher determines when an event is raised; the subscribers determine what action is taken in response to the event.</span></span>  
  
-   <span data-ttu-id="77ddc-112">Un evento può avere più sottoscrittori.</span><span class="sxs-lookup"><span data-stu-id="77ddc-112">An event can have multiple subscribers.</span></span> <span data-ttu-id="77ddc-113">Un sottoscrittore può gestire più eventi da più autori.</span><span class="sxs-lookup"><span data-stu-id="77ddc-113">A subscriber can handle multiple events from multiple publishers.</span></span>  
  
-   <span data-ttu-id="77ddc-114">Gli eventi che non hanno sottoscrittore non vengono mai generati.</span><span class="sxs-lookup"><span data-stu-id="77ddc-114">Events that have no subscribers are never raised.</span></span>  
  
-   <span data-ttu-id="77ddc-115">Gli eventi vengono in genere usati per segnalare azioni dell'utente, ad esempio la scelta di un pulsante o di una voce di menu nell'interfaccia utente grafica.</span><span class="sxs-lookup"><span data-stu-id="77ddc-115">Events are typically used to signal user actions such as button clicks or menu selections in graphical user interfaces.</span></span>  
  
-   <span data-ttu-id="77ddc-116">Quando un evento ha più sottoscrittori, i gestori eventi vengono richiamati in modo sincrono al momento della generazione dell'evento.</span><span class="sxs-lookup"><span data-stu-id="77ddc-116">When an event has multiple subscribers, the event handlers are invoked synchronously when an event is raised.</span></span> <span data-ttu-id="77ddc-117">Per richiamare gli eventi in modo asincrono, vedere [Calling Synchronous Methods Asynchronously](https://msdn.microsoft.com/library/2e08f6yc).</span><span class="sxs-lookup"><span data-stu-id="77ddc-117">To invoke events asynchronously, see [Calling Synchronous Methods Asynchronously](https://msdn.microsoft.com/library/2e08f6yc).</span></span>  
  
-   <span data-ttu-id="77ddc-118">Nella libreria di classi di [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] gli eventi sono basati sul delegato <xref:System.EventHandler> e sulla classe di base <xref:System.EventArgs> .</span><span class="sxs-lookup"><span data-stu-id="77ddc-118">In the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] class library, events are based on the <xref:System.EventHandler> delegate and the <xref:System.EventArgs> base class.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="77ddc-119">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="77ddc-119">Related Sections</span></span>  
 <span data-ttu-id="77ddc-120">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="77ddc-120">For more information, see:</span></span>  
  
-   [<span data-ttu-id="77ddc-121">Procedura: Eseguire e annullare la sottoscrizione a eventi</span><span class="sxs-lookup"><span data-stu-id="77ddc-121">How to: Subscribe to and Unsubscribe from Events</span></span>](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)  
  
-   [<span data-ttu-id="77ddc-122">Procedura: Pubblicare eventi conformi alle linee guida di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="77ddc-122">How to: Publish Events that Conform to .NET Framework Guidelines</span></span>](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md)  
  
-   [<span data-ttu-id="77ddc-123">Procedura: Generare eventi di classe base nelle classi derivate</span><span class="sxs-lookup"><span data-stu-id="77ddc-123">How to: Raise Base Class Events in Derived Classes</span></span>](../../../csharp/programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md)  
  
-   [<span data-ttu-id="77ddc-124">Procedura: Implementare eventi di interfaccia</span><span class="sxs-lookup"><span data-stu-id="77ddc-124">How to:  Implement Interface Events</span></span>](../../../csharp/programming-guide/events/how-to-implement-interface-events.md)  
  
-   [<span data-ttu-id="77ddc-125">Sincronizzazione di thread</span><span class="sxs-lookup"><span data-stu-id="77ddc-125">Thread Synchronization</span></span>](../../../csharp/programming-guide/concepts/threading/thread-synchronization.md)  
  
-   [<span data-ttu-id="77ddc-126">Procedura: Usare un dizionario per archiviare istanze di evento</span><span class="sxs-lookup"><span data-stu-id="77ddc-126">How to: Use a Dictionary to Store Event Instances</span></span>](../../../csharp/programming-guide/events/how-to-use-a-dictionary-to-store-event-instances.md)  
  
-   [<span data-ttu-id="77ddc-127">Procedura: Implementare funzioni di accesso a eventi personalizzati</span><span class="sxs-lookup"><span data-stu-id="77ddc-127">How to: Implement Custom Event Accessors</span></span>](../../../csharp/programming-guide/events/how-to-implement-custom-event-accessors.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="77ddc-128">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="77ddc-128">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="featured-book-chapters"></a><span data-ttu-id="77ddc-129">Capitoli del libro rappresentati</span><span class="sxs-lookup"><span data-stu-id="77ddc-129">Featured Book Chapters</span></span>  
 <span data-ttu-id="77ddc-130">[Delegates, Events, and Lambda Expressions](http://go.microsoft.com/fwlink/?LinkId=195395) (Delegati, eventi ed espressioni lambda) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](http://go.microsoft.com/fwlink/?LinkId=195369)</span><span class="sxs-lookup"><span data-stu-id="77ddc-130">[Delegates, Events, and Lambda Expressions](http://go.microsoft.com/fwlink/?LinkId=195395) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](http://go.microsoft.com/fwlink/?LinkId=195369)</span></span>  
  
 <span data-ttu-id="77ddc-131">[Delegati ed eventi](http://go.microsoft.com/fwlink/?LinkId=195418) (Delegati, eventi ed espressioni lambda) in [Learning C# 3.0: Master the fundamentals of C# 3.0](http://go.microsoft.com/fwlink/?LinkId=195412)</span><span class="sxs-lookup"><span data-stu-id="77ddc-131">[Delegates and Events](http://go.microsoft.com/fwlink/?LinkId=195418) in [Learning C# 3.0: Master the fundamentals of C# 3.0](http://go.microsoft.com/fwlink/?LinkId=195412)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77ddc-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77ddc-132">See Also</span></span>  
 <xref:System.EventHandler>  
 [<span data-ttu-id="77ddc-133">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="77ddc-133">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="77ddc-134">Delegati</span><span class="sxs-lookup"><span data-stu-id="77ddc-134">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
 [<span data-ttu-id="77ddc-135">Creazione di gestori eventi in Windows Form</span><span class="sxs-lookup"><span data-stu-id="77ddc-135">Creating Event Handlers in Windows Forms</span></span>](https://msdn.microsoft.com/library/dacysss4.aspx)  
 [<span data-ttu-id="77ddc-136">Programmazione multithreading con il modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="77ddc-136">Multithreaded Programming with the Event-based Asynchronous Pattern</span></span>](https://msdn.microsoft.com/library/hkasytyf)
