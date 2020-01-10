---
title: Eventi - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- classes [C#], events
- C# language, events
- events [C#]
ms.assetid: a8e51b22-d294-44fb-9539-0072f06c4cb3
ms.openlocfilehash: 183f53a579bdd9f70deb16ca9157c377fa3aff3f
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712312"
---
# <a name="events-c-programming-guide"></a><span data-ttu-id="a3f61-102">Eventi (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="a3f61-102">Events (C# Programming Guide)</span></span>
<span data-ttu-id="a3f61-103">Tramite gli eventi, una [classe](../../language-reference/keywords/class.md) o un oggetto è in grado di segnalare ad altre classi o oggetti una situazione di interesse.</span><span class="sxs-lookup"><span data-stu-id="a3f61-103">Events enable a [class](../../language-reference/keywords/class.md) or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="a3f61-104">La classe che invia (o *genera*) l'evento è chiamata *autore* e le classi che ricevono (o *gestiscono*) l'evento sono chiamate *sottoscrittori*.</span><span class="sxs-lookup"><span data-stu-id="a3f61-104">The class that sends (or *raises*) the event is called the *publisher* and the classes that receive (or *handle*) the event are called *subscribers*.</span></span>  
  
<span data-ttu-id="a3f61-105">In un'applicazione C# Web o Windows Form tipica si sottoscrivono eventi generati da controlli quali pulsanti e caselle di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="a3f61-105">In a typical C# Windows Forms or Web application, you subscribe to events raised by controls such as buttons and list boxes.</span></span> <span data-ttu-id="a3f61-106">È possibile usare l'ambiente di sviluppo integrato (IDE) di Visual C# per cercare gli eventi pubblicati da un controllo e selezionare quelli che si vuole gestire.</span><span class="sxs-lookup"><span data-stu-id="a3f61-106">You can use the Visual C# integrated development environment (IDE) to browse the events that a control publishes and select the ones that you want to handle.</span></span> <span data-ttu-id="a3f61-107">L'IDE consente di aggiungere automaticamente un metodo vuoto del gestore eventi e il codice per sottoscrivere l'evento.</span><span class="sxs-lookup"><span data-stu-id="a3f61-107">The IDE provides an easy way to automatically add an empty event handler method and the code to subscribe to the event.</span></span> <span data-ttu-id="a3f61-108">Per ulteriori informazioni, vedere [come sottoscrivere e annullare la sottoscrizione di eventi](./how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="a3f61-108">For more information, see [How to subscribe to and unsubscribe from events](./how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>
  
## <a name="events-overview"></a><span data-ttu-id="a3f61-109">Cenni preliminari sugli eventi</span><span class="sxs-lookup"><span data-stu-id="a3f61-109">Events Overview</span></span>  
 <span data-ttu-id="a3f61-110">Di seguito sono riportate le proprietà degli eventi:</span><span class="sxs-lookup"><span data-stu-id="a3f61-110">Events have the following properties:</span></span>  
  
- <span data-ttu-id="a3f61-111">L'autore determina quando viene generato un evento. I sottoscrittori determinano quale azione viene eseguita in risposta all'evento.</span><span class="sxs-lookup"><span data-stu-id="a3f61-111">The publisher determines when an event is raised; the subscribers determine what action is taken in response to the event.</span></span>  
  
- <span data-ttu-id="a3f61-112">Un evento può avere più sottoscrittori.</span><span class="sxs-lookup"><span data-stu-id="a3f61-112">An event can have multiple subscribers.</span></span> <span data-ttu-id="a3f61-113">Un sottoscrittore può gestire più eventi da più autori.</span><span class="sxs-lookup"><span data-stu-id="a3f61-113">A subscriber can handle multiple events from multiple publishers.</span></span>  
  
- <span data-ttu-id="a3f61-114">Gli eventi che non hanno sottoscrittore non vengono mai generati.</span><span class="sxs-lookup"><span data-stu-id="a3f61-114">Events that have no subscribers are never raised.</span></span>  
  
- <span data-ttu-id="a3f61-115">Gli eventi vengono in genere usati per segnalare azioni dell'utente, ad esempio la scelta di un pulsante o di una voce di menu nell'interfaccia utente grafica.</span><span class="sxs-lookup"><span data-stu-id="a3f61-115">Events are typically used to signal user actions such as button clicks or menu selections in graphical user interfaces.</span></span>  
  
- <span data-ttu-id="a3f61-116">Quando un evento ha più sottoscrittori, i gestori eventi vengono richiamati in modo sincrono al momento della generazione dell'evento.</span><span class="sxs-lookup"><span data-stu-id="a3f61-116">When an event has multiple subscribers, the event handlers are invoked synchronously when an event is raised.</span></span> <span data-ttu-id="a3f61-117">Per richiamare gli eventi in modo asincrono, vedere [Calling Synchronous Methods Asynchronously](../../../standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).</span><span class="sxs-lookup"><span data-stu-id="a3f61-117">To invoke events asynchronously, see [Calling Synchronous Methods Asynchronously](../../../standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).</span></span>  
  
- <span data-ttu-id="a3f61-118">Nella libreria di classi .NET Framework gli eventi sono basati sul delegato <xref:System.EventHandler> e sulla classe di base <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="a3f61-118">In the .NET Framework class library, events are based on the <xref:System.EventHandler> delegate and the <xref:System.EventArgs> base class.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a3f61-119">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="a3f61-119">Related Sections</span></span>  
 <span data-ttu-id="a3f61-120">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="a3f61-120">For more information, see:</span></span>  
  
- [<span data-ttu-id="a3f61-121">Come sottoscrivere e annullare la sottoscrizione di eventi</span><span class="sxs-lookup"><span data-stu-id="a3f61-121">How to subscribe to and unsubscribe from events</span></span>](./how-to-subscribe-to-and-unsubscribe-from-events.md)

- [<span data-ttu-id="a3f61-122">Come pubblicare eventi conformi alle linee guida di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a3f61-122">How to publish events that conform to .NET Framework Guidelines</span></span>](./how-to-publish-events-that-conform-to-net-framework-guidelines.md)

- [<span data-ttu-id="a3f61-123">Come generare eventi di classe base nelle classi derivate</span><span class="sxs-lookup"><span data-stu-id="a3f61-123">How to raise base class events in derived classes</span></span>](./how-to-raise-base-class-events-in-derived-classes.md)

- [<span data-ttu-id="a3f61-124">Come implementare gli eventi di interfaccia</span><span class="sxs-lookup"><span data-stu-id="a3f61-124">How to implement interface events</span></span>](./how-to-implement-interface-events.md)

- [<span data-ttu-id="a3f61-125">Come implementare funzioni di accesso agli eventi personalizzati</span><span class="sxs-lookup"><span data-stu-id="a3f61-125">How to implement custom event accessors</span></span>](./how-to-implement-custom-event-accessors.md)

## <a name="c-language-specification"></a><span data-ttu-id="a3f61-126">Specifica del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="a3f61-126">C# Language Specification</span></span>  

<span data-ttu-id="a3f61-127">Per altre informazioni, vedere [Eventi](~/_csharplang/spec/classes.md#events) nella [Specifica del linguaggio C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="a3f61-127">For more information, see [Events](~/_csharplang/spec/classes.md#events) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="a3f61-128">La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.</span><span class="sxs-lookup"><span data-stu-id="a3f61-128">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="featured-book-chapters"></a><span data-ttu-id="a3f61-129">Capitoli del libro rappresentati</span><span class="sxs-lookup"><span data-stu-id="a3f61-129">Featured Book Chapters</span></span>  
 <span data-ttu-id="a3f61-130">[Delegates, Events, and Lambda Expressions](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) (Delegati, eventi ed espressioni lambda) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)</span><span class="sxs-lookup"><span data-stu-id="a3f61-130">[Delegates, Events, and Lambda Expressions](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)</span></span>  
  
 <span data-ttu-id="a3f61-131">[Delegati ed eventi](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652490%28v=orm.10%29) (Delegati, eventi ed espressioni lambda) in [Learning C# 3.0: Master the fundamentals of C# 3.0](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652493%28v=orm.10%29)</span><span class="sxs-lookup"><span data-stu-id="a3f61-131">[Delegates and Events](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652490%28v=orm.10%29) in [Learning C# 3.0: Master the fundamentals of C# 3.0](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652493%28v=orm.10%29)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3f61-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3f61-132">See also</span></span>

- <xref:System.EventHandler>
- [<span data-ttu-id="a3f61-133">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="a3f61-133">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="a3f61-134">Delegati</span><span class="sxs-lookup"><span data-stu-id="a3f61-134">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="a3f61-135">Creazione di gestori eventi in Windows Form</span><span class="sxs-lookup"><span data-stu-id="a3f61-135">Creating Event Handlers in Windows Forms</span></span>](../../../framework/winforms/creating-event-handlers-in-windows-forms.md)
