---
title: Modelli di eventi deboli
description: Informazioni sul modello di evento Windows Presentation Foundation debole, che risolve il problema dei gestori che non vengono eliminati definitivamente, evitando perdite di memoria.
ms.date: 03/30/2017
helpviewer_keywords:
- weak event pattern implementation [WPF]
- event handlers [WPF], weak event pattern
- IWeakEventListener interface [WPF]
ms.assetid: e7c62920-4812-4811-94d8-050a65c856f6
ms.openlocfilehash: 75c6888c8ac20c41d13e3787005377c75248c5d9
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168272"
---
# <a name="weak-event-patterns"></a><span data-ttu-id="36bd6-103">Modelli di eventi deboli</span><span class="sxs-lookup"><span data-stu-id="36bd6-103">Weak Event Patterns</span></span>
<span data-ttu-id="36bd6-104">Nelle applicazioni è possibile che i gestori collegati alle origini eventi non vengano eliminati in modo coordinato con l'oggetto listener che ha collegato il gestore all'origine.</span><span class="sxs-lookup"><span data-stu-id="36bd6-104">In applications, it is possible that handlers that are attached to event sources will not be destroyed in coordination with the listener object that attached the handler to the source.</span></span> <span data-ttu-id="36bd6-105">Questa situazione può causare perdite di memoria.</span><span class="sxs-lookup"><span data-stu-id="36bd6-105">This situation can lead to memory leaks.</span></span> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="36bd6-106">introduce uno schema progettuale che può essere usato per risolvere questo problema, fornendo una classe Manager dedicata per determinati eventi e implementando un'interfaccia nei listener per tale evento.</span><span class="sxs-lookup"><span data-stu-id="36bd6-106">introduces a design pattern that can be used to address this issue, by providing a dedicated manager class for particular events and implementing an interface on listeners for that event.</span></span> <span data-ttu-id="36bd6-107">Questo schema progettuale è noto come *modello di eventi deboli*.</span><span class="sxs-lookup"><span data-stu-id="36bd6-107">This design pattern is known as the *weak event pattern*.</span></span>  
  
## <a name="why-implement-the-weak-event-pattern"></a><span data-ttu-id="36bd6-108">Perché implementare il modello di eventi deboli?</span><span class="sxs-lookup"><span data-stu-id="36bd6-108">Why Implement the Weak Event Pattern?</span></span>  
 <span data-ttu-id="36bd6-109">L'ascolto degli eventi può causare perdite di memoria.</span><span class="sxs-lookup"><span data-stu-id="36bd6-109">Listening for events can lead to memory leaks.</span></span> <span data-ttu-id="36bd6-110">La tecnica tipica per l'ascolto di un evento consiste nell'usare la sintassi specifica del linguaggio che connette un gestore a un evento in un'origine.</span><span class="sxs-lookup"><span data-stu-id="36bd6-110">The typical technique for listening to an event is to use the language-specific syntax that attaches a handler to an event on a source.</span></span> <span data-ttu-id="36bd6-111">In C#, ad esempio, la sintassi è: `source.SomeEvent += new SomeEventHandler(MyEventHandler)` .</span><span class="sxs-lookup"><span data-stu-id="36bd6-111">For example, in C#, that syntax is: `source.SomeEvent += new SomeEventHandler(MyEventHandler)`.</span></span>  
  
 <span data-ttu-id="36bd6-112">Questa tecnica crea un riferimento sicuro dall'origine evento al listener di eventi.</span><span class="sxs-lookup"><span data-stu-id="36bd6-112">This technique creates a strong reference from the event source to the event listener.</span></span> <span data-ttu-id="36bd6-113">In genere, il fissaggio di un gestore eventi per un listener fa sì che il listener abbia una durata degli oggetti influenzato dalla durata dell'oggetto dell'origine (a meno che il gestore eventi non venga rimosso in modo esplicito).</span><span class="sxs-lookup"><span data-stu-id="36bd6-113">Ordinarily, attaching an event handler for a listener causes the listener to have an object lifetime that is influenced by the object lifetime of the source (unless the event handler is explicitly removed).</span></span> <span data-ttu-id="36bd6-114">In alcuni casi, tuttavia, potrebbe essere necessario controllare la durata dell'oggetto del listener da altri fattori, ad esempio se appartiene attualmente alla struttura ad albero visuale dell'applicazione e non alla durata dell'origine.</span><span class="sxs-lookup"><span data-stu-id="36bd6-114">But in certain circumstances, you might want the object lifetime of the listener to be controlled by other factors, such as whether it currently belongs to the visual tree of the application, and not by the lifetime of the source.</span></span> <span data-ttu-id="36bd6-115">Ogni volta che la durata dell'oggetto di origine supera la durata dell'oggetto del listener, il modello di evento normale causa una perdita di memoria: il listener viene mantenuto attivo più a lungo del previsto.</span><span class="sxs-lookup"><span data-stu-id="36bd6-115">Whenever the source object lifetime extends beyond the object lifetime of the listener, the normal event pattern leads to a memory leak: the listener is kept alive longer than intended.</span></span>  
  
 <span data-ttu-id="36bd6-116">Il modello di eventi vulnerabili è progettato per risolvere questo problema di perdita di memoria.</span><span class="sxs-lookup"><span data-stu-id="36bd6-116">The weak event pattern is designed to solve this memory leak problem.</span></span> <span data-ttu-id="36bd6-117">Il modello di eventi vulnerabili può essere usato ogni volta che un listener deve registrarsi per un evento, ma il listener non sa in modo esplicito quando annullare la registrazione.</span><span class="sxs-lookup"><span data-stu-id="36bd6-117">The weak event pattern can be used whenever a listener needs to register for an event, but the listener does not explicitly know when to unregister.</span></span> <span data-ttu-id="36bd6-118">Il modello di eventi vulnerabili può essere utilizzato anche ogni volta che la durata dell'oggetto dell'origine supera la durata utile dell'oggetto del listener.</span><span class="sxs-lookup"><span data-stu-id="36bd6-118">The weak event pattern can also be used whenever the object lifetime of the source exceeds the useful object lifetime of the listener.</span></span> <span data-ttu-id="36bd6-119">(In questo caso, l' *utilità* è determinata dall'utente). Il modello di eventi vulnerabili consente al listener di registrarsi e ricevere l'evento senza influire in alcun modo sulle caratteristiche di durata degli oggetti del listener.</span><span class="sxs-lookup"><span data-stu-id="36bd6-119">(In this case, *useful* is determined by you.) The weak event pattern allows the listener to register for and receive the event without affecting the object lifetime characteristics of the listener in any way.</span></span> <span data-ttu-id="36bd6-120">In effetti, il riferimento implicito dall'origine non determina se il listener è idoneo per Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="36bd6-120">In effect, the implied reference from the source does not determine whether the listener is eligible for garbage collection.</span></span> <span data-ttu-id="36bd6-121">Il riferimento è un riferimento debole, quindi la denominazione del modello di eventi deboli e le API correlate.</span><span class="sxs-lookup"><span data-stu-id="36bd6-121">The reference is a weak reference, thus the naming of the weak event pattern and the related APIs.</span></span> <span data-ttu-id="36bd6-122">Il listener può essere sottoposta a Garbage Collection o eliminato in altro modo e l'origine può continuare senza mantenere i riferimenti al gestore non ritirabili a un oggetto distrutto.</span><span class="sxs-lookup"><span data-stu-id="36bd6-122">The listener can be garbage collected or otherwise destroyed, and the source can continue without retaining noncollectible handler references to a now destroyed object.</span></span>  
  
## <a name="who-should-implement-the-weak-event-pattern"></a><span data-ttu-id="36bd6-123">Chi deve implementare il modello di eventi deboli?</span><span class="sxs-lookup"><span data-stu-id="36bd6-123">Who Should Implement the Weak Event Pattern?</span></span>  
 <span data-ttu-id="36bd6-124">L'implementazione del modello di eventi vulnerabili è particolarmente interessante per gli autori di controlli.</span><span class="sxs-lookup"><span data-stu-id="36bd6-124">Implementing the weak event pattern is interesting primarily for control authors.</span></span> <span data-ttu-id="36bd6-125">In qualità di autore del controllo, l'utente è in gran parte responsabile del comportamento e del contenimento del controllo e dell'incidenza sulle applicazioni in cui viene inserito.</span><span class="sxs-lookup"><span data-stu-id="36bd6-125">As a control author, you are largely responsible for the behavior and containment of your control and the impact it has on applications in which it is inserted.</span></span> <span data-ttu-id="36bd6-126">Questo include il comportamento di controllo della durata degli oggetti, in particolare la gestione del problema di perdita di memoria descritto.</span><span class="sxs-lookup"><span data-stu-id="36bd6-126">This includes the control object lifetime behavior, in particular the handling of the described memory leak problem.</span></span>  
  
 <span data-ttu-id="36bd6-127">Determinati scenari si prestano intrinsecamente all'applicazione del modello di eventi deboli.</span><span class="sxs-lookup"><span data-stu-id="36bd6-127">Certain scenarios inherently lend themselves to the application of the weak event pattern.</span></span> <span data-ttu-id="36bd6-128">Uno scenario di questo tipo è data binding.</span><span class="sxs-lookup"><span data-stu-id="36bd6-128">One such scenario is data binding.</span></span> <span data-ttu-id="36bd6-129">In data binding, è normale che l'oggetto di origine sia completamente indipendente dall'oggetto listener, che è la destinazione di un'associazione.</span><span class="sxs-lookup"><span data-stu-id="36bd6-129">In data binding, it is common for the source object to be completely independent of the listener object, which is a target of a binding.</span></span> <span data-ttu-id="36bd6-130">Molti aspetti di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Data Binding hanno già il modello di eventi deboli applicato nella modalità di implementazione degli eventi.</span><span class="sxs-lookup"><span data-stu-id="36bd6-130">Many aspects of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] data binding already have the weak event pattern applied in how the events are implemented.</span></span>  
  
## <a name="how-to-implement-the-weak-event-pattern"></a><span data-ttu-id="36bd6-131">Come implementare il modello di eventi deboli</span><span class="sxs-lookup"><span data-stu-id="36bd6-131">How to Implement the Weak Event Pattern</span></span>  
 <span data-ttu-id="36bd6-132">Esistono tre modi per implementare il modello di eventi deboli.</span><span class="sxs-lookup"><span data-stu-id="36bd6-132">There are three ways to implement weak event pattern.</span></span> <span data-ttu-id="36bd6-133">Nella tabella seguente sono elencati i tre approcci e vengono fornite alcune indicazioni per l'utilizzo di ciascuno di essi.</span><span class="sxs-lookup"><span data-stu-id="36bd6-133">The following table lists the three approaches and provides some guidance for when you should use each.</span></span>  
  
|<span data-ttu-id="36bd6-134">Approccio</span><span class="sxs-lookup"><span data-stu-id="36bd6-134">Approach</span></span>|<span data-ttu-id="36bd6-135">Quando implementare</span><span class="sxs-lookup"><span data-stu-id="36bd6-135">When to Implement</span></span>|  
|--------------|-----------------------|  
|<span data-ttu-id="36bd6-136">Usa una classe di gestione degli eventi vulnerabili esistente</span><span class="sxs-lookup"><span data-stu-id="36bd6-136">Use an existing weak event manager class</span></span>|<span data-ttu-id="36bd6-137">Se l'evento a cui si desidera eseguire la sottoscrizione ha un corrispondente <xref:System.Windows.WeakEventManager> , utilizzare il gestore eventi vulnerabile esistente.</span><span class="sxs-lookup"><span data-stu-id="36bd6-137">If the event you want to subscribe to has a corresponding <xref:System.Windows.WeakEventManager>, use the existing weak event manager.</span></span> <span data-ttu-id="36bd6-138">Per un elenco di gestori di eventi vulnerabili inclusi in WPF, vedere la gerarchia di ereditarietà nella <xref:System.Windows.WeakEventManager> classe.</span><span class="sxs-lookup"><span data-stu-id="36bd6-138">For a list of weak event managers that are included with WPF, see the inheritance hierarchy in the <xref:System.Windows.WeakEventManager> class.</span></span> <span data-ttu-id="36bd6-139">Poiché i gestori di eventi deboli inclusi sono limitati, probabilmente sarà necessario scegliere uno degli altri approcci.</span><span class="sxs-lookup"><span data-stu-id="36bd6-139">Because the included weak event managers are limited, you will probably need to choose one of the other approaches.</span></span>|  
|<span data-ttu-id="36bd6-140">Usare una classe generica di gestione eventi debole</span><span class="sxs-lookup"><span data-stu-id="36bd6-140">Use a generic weak event manager class</span></span>|<span data-ttu-id="36bd6-141">Usare un oggetto generico <xref:System.Windows.WeakEventManager%602> quando <xref:System.Windows.WeakEventManager> non è disponibile una esistente, si vuole un modo semplice per implementare e non si è interessati all'efficienza.</span><span class="sxs-lookup"><span data-stu-id="36bd6-141">Use a generic <xref:System.Windows.WeakEventManager%602> when an existing <xref:System.Windows.WeakEventManager> is not available, you want an easy way to implement, and you are not concerned about efficiency.</span></span> <span data-ttu-id="36bd6-142">Il generico <xref:System.Windows.WeakEventManager%602> è meno efficiente di un gestore di eventi vulnerabile esistente o personalizzato.</span><span class="sxs-lookup"><span data-stu-id="36bd6-142">The generic <xref:System.Windows.WeakEventManager%602> is less efficient than an existing or custom weak event manager.</span></span> <span data-ttu-id="36bd6-143">La classe generica, ad esempio, esegue più reflection per individuare l'evento in base al nome dell'evento.</span><span class="sxs-lookup"><span data-stu-id="36bd6-143">For example, the generic class does more reflection to discover the event given the event's name.</span></span> <span data-ttu-id="36bd6-144">Inoltre, il codice per registrare l'evento usando il generico <xref:System.Windows.WeakEventManager%602> è più dettagliato rispetto all'uso di un oggetto esistente o personalizzato <xref:System.Windows.WeakEventManager> .</span><span class="sxs-lookup"><span data-stu-id="36bd6-144">Also, the code to register the event by using the generic <xref:System.Windows.WeakEventManager%602> is more verbose than using an existing or custom <xref:System.Windows.WeakEventManager>.</span></span>|  
|<span data-ttu-id="36bd6-145">Creare una classe personalizzata di gestione eventi vulnerabili</span><span class="sxs-lookup"><span data-stu-id="36bd6-145">Create a custom weak event manager class</span></span>|<span data-ttu-id="36bd6-146">Creare un'personalizzata <xref:System.Windows.WeakEventManager> quando <xref:System.Windows.WeakEventManager> non è disponibile una esistente e si desidera ottenere la migliore efficienza.</span><span class="sxs-lookup"><span data-stu-id="36bd6-146">Create a custom <xref:System.Windows.WeakEventManager> when an existing <xref:System.Windows.WeakEventManager> is not available and you want the best efficiency.</span></span> <span data-ttu-id="36bd6-147">L'uso di un oggetto personalizzato <xref:System.Windows.WeakEventManager> per sottoscrivere un evento è più efficiente, ma comporta il costo di scrivere altro codice all'inizio.</span><span class="sxs-lookup"><span data-stu-id="36bd6-147">Using a custom <xref:System.Windows.WeakEventManager> to subscribe to an event will be more efficient, but you do incur the cost of writing more code at the beginning.</span></span>|  
|<span data-ttu-id="36bd6-148">Usare un gestore eventi vulnerabile di terze parti</span><span class="sxs-lookup"><span data-stu-id="36bd6-148">Use a third-party weak event manager</span></span>|<span data-ttu-id="36bd6-149">NuGet dispone di [diversi gestori di eventi vulnerabili](https://www.nuget.org/packages?q=weak+event+manager&prerel=false) e molti framework WPF supportano anche il modello (ad esempio, vedere la [documentazione di Prisma sulla sottoscrizione di eventi a regime di controllo libero](https://github.com/PrismLibrary/Prism-Documentation/blob/master/docs/wpf/legacy/Communication.md#subscribing-to-events)).</span><span class="sxs-lookup"><span data-stu-id="36bd6-149">NuGet has [several weak event managers](https://www.nuget.org/packages?q=weak+event+manager&prerel=false) and many WPF frameworks also support the pattern (for instance, see [Prism's documentation on loosely coupled event subscription](https://github.com/PrismLibrary/Prism-Documentation/blob/master/docs/wpf/legacy/Communication.md#subscribing-to-events)).</span></span>|

 <span data-ttu-id="36bd6-150">Le sezioni seguenti descrivono come implementare il modello di eventi deboli.</span><span class="sxs-lookup"><span data-stu-id="36bd6-150">The following sections describe how to implement the weak event pattern.</span></span>  <span data-ttu-id="36bd6-151">Ai fini di questa discussione, l'evento da sottoscrivere presenta le caratteristiche seguenti.</span><span class="sxs-lookup"><span data-stu-id="36bd6-151">For purposes of this discussion, the event to subscribe to has the following characteristics.</span></span>  
  
- <span data-ttu-id="36bd6-152">Il nome dell'evento è `SomeEvent` .</span><span class="sxs-lookup"><span data-stu-id="36bd6-152">The event name is `SomeEvent`.</span></span>  
  
- <span data-ttu-id="36bd6-153">L'evento viene generato dalla `EventSource` classe.</span><span class="sxs-lookup"><span data-stu-id="36bd6-153">The event is raised by the `EventSource` class.</span></span>  
  
- <span data-ttu-id="36bd6-154">Il gestore eventi è di tipo: `SomeEventEventHandler` (o `EventHandler<SomeEventEventArgs>` ).</span><span class="sxs-lookup"><span data-stu-id="36bd6-154">The event handler has type: `SomeEventEventHandler` (or `EventHandler<SomeEventEventArgs>`).</span></span>  
  
- <span data-ttu-id="36bd6-155">L'evento passa un parametro di tipo `SomeEventEventArgs` ai gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="36bd6-155">The event passes a parameter of type `SomeEventEventArgs` to the event handlers.</span></span>  
  
### <a name="using-an-existing-weak-event-manager-class"></a><span data-ttu-id="36bd6-156">Utilizzo di una classe di gestione eventi debole esistente</span><span class="sxs-lookup"><span data-stu-id="36bd6-156">Using an Existing Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="36bd6-157">Trovare un gestore eventi vulnerabile esistente.</span><span class="sxs-lookup"><span data-stu-id="36bd6-157">Find an existing weak event manager.</span></span>  
  
     <span data-ttu-id="36bd6-158">Per un elenco di gestori di eventi vulnerabili inclusi in WPF, vedere la gerarchia di ereditarietà nella <xref:System.Windows.WeakEventManager> classe.</span><span class="sxs-lookup"><span data-stu-id="36bd6-158">For a list of weak event managers that are included with WPF, see the inheritance hierarchy in the <xref:System.Windows.WeakEventManager> class.</span></span>  
  
2. <span data-ttu-id="36bd6-159">Utilizzare il nuovo gestore eventi debole anziché il normale collegamento evento.</span><span class="sxs-lookup"><span data-stu-id="36bd6-159">Use the new weak event manager instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="36bd6-160">Ad esempio, se il codice usa il modello seguente per sottoscrivere un evento:</span><span class="sxs-lookup"><span data-stu-id="36bd6-160">For example, if your code uses the following pattern to subscribe to an event:</span></span>  
  
    ```csharp  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="36bd6-161">Modificare il modello nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="36bd6-161">Change it to the following pattern:</span></span>  
  
    ```csharp  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     <span data-ttu-id="36bd6-162">Analogamente, se il codice usa il modello seguente per annullare la sottoscrizione di un evento:</span><span class="sxs-lookup"><span data-stu-id="36bd6-162">Similarly, if your code uses the following pattern to unsubscribe from an event:</span></span>  
  
    ```csharp  
    source.SomeEvent -= new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="36bd6-163">Modificare il modello nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="36bd6-163">Change it to the following pattern:</span></span>  
  
    ```csharp  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
### <a name="using-the-generic-weak-event-manager-class"></a><span data-ttu-id="36bd6-164">Uso della classe generica di gestione eventi debole</span><span class="sxs-lookup"><span data-stu-id="36bd6-164">Using the Generic Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="36bd6-165">Usare la classe generica <xref:System.Windows.WeakEventManager%602> anziché il normale collegamento evento.</span><span class="sxs-lookup"><span data-stu-id="36bd6-165">Use the generic <xref:System.Windows.WeakEventManager%602> class instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="36bd6-166">Quando si usa <xref:System.Windows.WeakEventManager%602> per registrare i listener di eventi, è necessario fornire l'origine e il tipo di evento <xref:System.EventArgs> come parametri di tipo alla classe e chiamare <xref:System.Windows.WeakEventManager%602.AddHandler%2A> come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="36bd6-166">When you use <xref:System.Windows.WeakEventManager%602> to register event listeners, you supply the event source and <xref:System.EventArgs> type as the type parameters to the class and call <xref:System.Windows.WeakEventManager%602.AddHandler%2A> as shown in the following code:</span></span>  
  
    ```csharp  
    WeakEventManager<EventSource, SomeEventEventArgs>.AddHandler(source, "SomeEvent", source_SomeEvent);  
    ```  
  
### <a name="creating-a-custom-weak-event-manager-class"></a><span data-ttu-id="36bd6-167">Creazione di una classe personalizzata di gestione eventi vulnerabili</span><span class="sxs-lookup"><span data-stu-id="36bd6-167">Creating a Custom Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="36bd6-168">Copiare il modello di classe seguente nel progetto.</span><span class="sxs-lookup"><span data-stu-id="36bd6-168">Copy the following class template to your project.</span></span>  
  
     <span data-ttu-id="36bd6-169">Questa classe eredita dalla <xref:System.Windows.WeakEventManager> classe.</span><span class="sxs-lookup"><span data-stu-id="36bd6-169">This class inherits from the <xref:System.Windows.WeakEventManager> class.</span></span>  
  
     [!code-csharp[WeakEvents#WeakEventManagerTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/WeakEvents/CSharp/WeakEventManagerTemplate.cs#weakeventmanagertemplate)]  
  
2. <span data-ttu-id="36bd6-170">Sostituire il `SomeEventWeakEventManager` nome con il proprio nome.</span><span class="sxs-lookup"><span data-stu-id="36bd6-170">Replace the `SomeEventWeakEventManager` name with your own name.</span></span>  
  
3. <span data-ttu-id="36bd6-171">Sostituire i tre nomi descritti in precedenza con i nomi corrispondenti per l'evento.</span><span class="sxs-lookup"><span data-stu-id="36bd6-171">Replace the three names described previously with the corresponding names for your event.</span></span> <span data-ttu-id="36bd6-172">( `SomeEvent` , `EventSource` e `SomeEventEventArgs` )</span><span class="sxs-lookup"><span data-stu-id="36bd6-172">(`SomeEvent`, `EventSource`, and `SomeEventEventArgs`)</span></span>  
  
4. <span data-ttu-id="36bd6-173">Impostare la visibilità (pubblica/interna/privata) della classe del gestore eventi debole sulla stessa visibilità dell'evento gestito.</span><span class="sxs-lookup"><span data-stu-id="36bd6-173">Set the visibility (public / internal / private) of the weak event manager class to the same visibility as event it manages.</span></span>  
  
5. <span data-ttu-id="36bd6-174">Utilizzare il nuovo gestore eventi debole anziché il normale collegamento evento.</span><span class="sxs-lookup"><span data-stu-id="36bd6-174">Use the new weak event manager instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="36bd6-175">Ad esempio, se il codice usa il modello seguente per sottoscrivere un evento:</span><span class="sxs-lookup"><span data-stu-id="36bd6-175">For example, if your code uses the following pattern to subscribe to an event:</span></span>  
  
    ```csharp  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="36bd6-176">Modificare il modello nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="36bd6-176">Change it to the following pattern:</span></span>  
  
    ```csharp  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     <span data-ttu-id="36bd6-177">Analogamente, se il codice usa il modello seguente per annullare la sottoscrizione di un evento:</span><span class="sxs-lookup"><span data-stu-id="36bd6-177">Similarly, if your code uses the following pattern to unsubscribe to an event:</span></span>  
  
    ```csharp  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     <span data-ttu-id="36bd6-178">Modificare il modello nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="36bd6-178">Change it to the following pattern:</span></span>  
  
    ```csharp  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="36bd6-179">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36bd6-179">See also</span></span>

- <xref:System.Windows.WeakEventManager>
- <xref:System.Windows.IWeakEventListener>
- [<span data-ttu-id="36bd6-180">Cenni preliminari sugli eventi indirizzati</span><span class="sxs-lookup"><span data-stu-id="36bd6-180">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="36bd6-181">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="36bd6-181">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
