---
title: Modelli di eventi deboli
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- weak event pattern implementation [WPF]
- event handlers [WPF], weak event pattern
- IWeakEventListener interface [WPF]
ms.assetid: e7c62920-4812-4811-94d8-050a65c856f6
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3f024ae77740c596d8646b10a036428e2342d084
ms.sourcegitcommit: 8ed4ebc15b5ef89d06a7507dc9d5e306e30accf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/14/2017
---
# <a name="weak-event-patterns"></a><span data-ttu-id="cc7d0-102">Modelli di eventi deboli</span><span class="sxs-lookup"><span data-stu-id="cc7d0-102">Weak Event Patterns</span></span>
<span data-ttu-id="cc7d0-103">Nelle applicazioni, è possibile che i gestori associati alle origini eventi verranno eliminati, in coordinamento con l'oggetto listener che è associato il gestore per l'origine.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-103">In applications, it is possible that handlers that are attached to event sources will not be destroyed in coordination with the listener object that attached the handler to the source.</span></span> <span data-ttu-id="cc7d0-104">Questa situazione può causare perdite di memoria.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-104">This situation can lead to memory leaks.</span></span> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="cc7d0-105">introduce un modello di progettazione che può essere utilizzato per risolvere questo problema, fornendo una classe di gestione dedicata per eventi specifici e implementando un'interfaccia nei listener di tale evento.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-105"> introduces a design pattern that can be used to address this issue, by providing a dedicated manager class for particular events and implementing an interface on listeners for that event.</span></span> <span data-ttu-id="cc7d0-106">Questo modello di progettazione è noto come il *modello di eventi deboli*.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-106">This design pattern is known as the *weak event pattern*.</span></span>  
  
## <a name="why-implement-the-weak-event-pattern"></a><span data-ttu-id="cc7d0-107">Per implementare il modello di eventi deboli?</span><span class="sxs-lookup"><span data-stu-id="cc7d0-107">Why Implement the Weak Event Pattern?</span></span>  
 <span data-ttu-id="cc7d0-108">Ascolto di eventi può causare perdite di memoria.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-108">Listening for events can lead to memory leaks.</span></span> <span data-ttu-id="cc7d0-109">La tecnica standard per l'ascolto di un evento consiste nell'utilizzare la sintassi specifica del linguaggio che associa un gestore a un evento su un'origine.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-109">The typical technique for listening to an event is to use the language-specific syntax that attaches a handler to an event on a source.</span></span> <span data-ttu-id="cc7d0-110">Ad esempio, in [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)], che la sintassi è: `source.SomeEvent += new SomeEventHandler(MyEventHandler)`.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-110">For example, in [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)], that syntax is: `source.SomeEvent += new SomeEventHandler(MyEventHandler)`.</span></span>  
  
 <span data-ttu-id="cc7d0-111">Questa tecnica consente di creare un riferimento forte dall'origine evento per il listener di eventi.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-111">This technique creates a strong reference from the event source to the event listener.</span></span> <span data-ttu-id="cc7d0-112">Associare un gestore eventi per un listener causa in genere, il listener per la durata che è influenzata dalla durata dell'oggetto di origine (a meno che il gestore dell'evento è stato rimosso in modo esplicito).</span><span class="sxs-lookup"><span data-stu-id="cc7d0-112">Ordinarily, attaching an event handler for a listener causes the listener to have an object lifetime that is influenced by the object lifetime of the source (unless the event handler is explicitly removed).</span></span> <span data-ttu-id="cc7d0-113">Ma in determinate circostanze, è possibile la durata dell'oggetto del listener sia controllata da altri fattori, ad esempio, se attualmente a cui appartiene la struttura ad albero visuale dell'applicazione e non dalla durata dell'origine.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-113">But in certain circumstances, you might want the object lifetime of the listener to be controlled by other factors, such as whether it currently belongs to the visual tree of the application, and not by the lifetime of the source.</span></span> <span data-ttu-id="cc7d0-114">Ogni volta che la durata dell'oggetto di origine si estende oltre la durata dell'oggetto del listener, lo schema di eventi normali comporta una perdita di memoria: il listener viene mantenuto attivo più a lungo del previsto.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-114">Whenever the source object lifetime extends beyond the object lifetime of the listener, the normal event pattern leads to a memory leak: the listener is kept alive longer than intended.</span></span>  
  
 <span data-ttu-id="cc7d0-115">Il modello di eventi deboli è progettato per risolvere questo problema di perdita di memoria.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-115">The weak event pattern is designed to solve this memory leak problem.</span></span> <span data-ttu-id="cc7d0-116">Ogni volta che un listener deve effettuare la registrazione per un evento, ma il listener non conosce in modo esplicito quando annullare la registrazione, è possibile utilizzare il modello di eventi deboli.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-116">The weak event pattern can be used whenever a listener needs to register for an event, but the listener does not explicitly know when to unregister.</span></span> <span data-ttu-id="cc7d0-117">Il modello di eventi deboli nonché ogni volta che la durata dell'oggetto di origine supera la durata utile del listener.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-117">The weak event pattern can also be used whenever the object lifetime of the source exceeds the useful object lifetime of the listener.</span></span> <span data-ttu-id="cc7d0-118">(In questo caso, *utile* è determinato dall'utente.) Il modello di eventi deboli consente al listener di registrarsi e ricevere l'evento senza influire sulle caratteristiche di durata del listener in alcun modo.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-118">(In this case, *useful* is determined by you.) The weak event pattern allows the listener to register for and receive the event without affecting the object lifetime characteristics of the listener in any way.</span></span> <span data-ttu-id="cc7d0-119">In effetti, il riferimento implicito dall'origine non determina se il listener è idoneo per l'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-119">In effect, the implied reference from the source does not determine whether the listener is eligible for garbage collection.</span></span> <span data-ttu-id="cc7d0-120">Il riferimento è un riferimento debole, in questo modo la denominazione del modello di eventi deboli e correlata [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc7d0-120">The reference is a weak reference, thus the naming of the weak event pattern and the related [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)].</span></span> <span data-ttu-id="cc7d0-121">Il listener può essere l'operazione di garbage collection o altrimenti eliminato e l'origine può continuare senza mantenere riferimenti al gestore noncollectible a un oggetto ora eliminato.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-121">The listener can be garbage collected or otherwise destroyed, and the source can continue without retaining noncollectible handler references to a now destroyed object.</span></span>  
  
## <a name="who-should-implement-the-weak-event-pattern"></a><span data-ttu-id="cc7d0-122">Che deve implementare il modello di eventi deboli?</span><span class="sxs-lookup"><span data-stu-id="cc7d0-122">Who Should Implement the Weak Event Pattern?</span></span>  
 <span data-ttu-id="cc7d0-123">Implementazione del modello di eventi deboli è interessante principalmente per gli autori di controlli.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-123">Implementing the weak event pattern is interesting primarily for control authors.</span></span> <span data-ttu-id="cc7d0-124">Come l'autore di un controllo, è responsabile in gran parte del comportamento e il contenuto del controllo e l'impatto che sul applicazioni in cui viene inserito.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-124">As a control author, you are largely responsible for the behavior and containment of your control and the impact it has on applications in which it is inserted.</span></span> <span data-ttu-id="cc7d0-125">Ciò include il comportamento della durata degli oggetti controllo, in particolare la gestione del problema di perdita di memoria descritto.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-125">This includes the control object lifetime behavior, in particular the handling of the described memory leak problem.</span></span>  
  
 <span data-ttu-id="cc7d0-126">Alcuni scenari si prestano implicitamente all'applicazione del modello di eventi deboli.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-126">Certain scenarios inherently lend themselves to the application of the weak event pattern.</span></span> <span data-ttu-id="cc7d0-127">Uno scenario di questo tipo è l'associazione dati.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-127">One such scenario is data binding.</span></span> <span data-ttu-id="cc7d0-128">Data binding è comune per l'oggetto di origine sia completamente indipendente dell'oggetto listener, che è una destinazione di un'associazione.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-128">In data binding, it is common for the source object to be completely independent of the listener object, which is a target of a binding.</span></span> <span data-ttu-id="cc7d0-129">Molti aspetti di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] già un'associazione dati hanno lo schema di eventi deboli applicato in modalità di implementazione di eventi.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-129">Many aspects of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] data binding already have the weak event pattern applied in how the events are implemented.</span></span>  
  
## <a name="how-to-implement-the-weak-event-pattern"></a><span data-ttu-id="cc7d0-130">Come implementare il modello di eventi deboli</span><span class="sxs-lookup"><span data-stu-id="cc7d0-130">How to Implement the Weak Event Pattern</span></span>  
 <span data-ttu-id="cc7d0-131">Esistono tre modi per implementare il modello di eventi deboli.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-131">There are three ways to implement weak event pattern.</span></span> <span data-ttu-id="cc7d0-132">Nella tabella seguente sono elencati i tre approcci e fornite alcune indicazioni per quando è consigliabile utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-132">The following table lists the three approaches and provides some guidance for when you should use each.</span></span>  
  
|<span data-ttu-id="cc7d0-133">Approccio</span><span class="sxs-lookup"><span data-stu-id="cc7d0-133">Approach</span></span>|<span data-ttu-id="cc7d0-134">Quando implementare</span><span class="sxs-lookup"><span data-stu-id="cc7d0-134">When to Implement</span></span>|  
|--------------|-----------------------|  
|<span data-ttu-id="cc7d0-135">Utilizzare una classe di gestione di eventi deboli esistente</span><span class="sxs-lookup"><span data-stu-id="cc7d0-135">Use an existing weak event manager class</span></span>|<span data-ttu-id="cc7d0-136">Se l'evento che si desidera eseguire la sottoscrizione ha un corrispondente <xref:System.Windows.WeakEventManager>, utilizzare la gestione di eventi deboli esistente.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-136">If the event you want to subscribe to has a corresponding <xref:System.Windows.WeakEventManager>, use the existing weak event manager.</span></span> <span data-ttu-id="cc7d0-137">Per un elenco di gestori di eventi deboli incluse in WPF, vedere la gerarchia di ereditarietà nel <xref:System.Windows.WeakEventManager> classe.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-137">For a list of weak event managers that are included with WPF, see the inheritance hierarchy in the <xref:System.Windows.WeakEventManager> class.</span></span> <span data-ttu-id="cc7d0-138">Si noti, tuttavia, che sono presenti relativamente pochi gestori di eventi deboli che sono inclusi in WPF, pertanto sarà probabilmente necessario scegliere uno degli approcci.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-138">Note, however, that there are relatively few weak event managers that are included with WPF, so you will probably need to choose one of the other approaches.</span></span>|  
|<span data-ttu-id="cc7d0-139">Utilizzare una classe di gestione di eventi deboli generico</span><span class="sxs-lookup"><span data-stu-id="cc7d0-139">Use a generic weak event manager class</span></span>|<span data-ttu-id="cc7d0-140">Utilizzare un oggetto generico <xref:System.Windows.WeakEventManager%602> quando un oggetto esistente <xref:System.Windows.WeakEventManager> non disponibile, si desidera un modo semplice per implementare e non si intende l'efficienza.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-140">Use a generic <xref:System.Windows.WeakEventManager%602> when an existing <xref:System.Windows.WeakEventManager> is not available, you want an easy way to implement, and you are not concerned about efficiency.</span></span> <span data-ttu-id="cc7d0-141">Il tipo generico <xref:System.Windows.WeakEventManager%602> è meno efficace rispetto a un gestore di eventi deboli esistenti o personalizzate.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-141">The generic <xref:System.Windows.WeakEventManager%602> is less efficient than an existing or custom weak event manager.</span></span> <span data-ttu-id="cc7d0-142">Ad esempio, la classe generica non più la reflection per individuare l'evento specificato il nome dell'evento.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-142">For example, the generic class does more reflection to discover the event given the event's name.</span></span> <span data-ttu-id="cc7d0-143">Inoltre, il codice per registrare l'evento utilizzando il tipo generico <xref:System.Windows.WeakEventManager%602> è più dettagliato rispetto all'utilizzo di un oggetto esistente o personalizzato <xref:System.Windows.WeakEventManager>.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-143">Also, the code to register the event by using the generic <xref:System.Windows.WeakEventManager%602> is more verbose than using an existing or custom <xref:System.Windows.WeakEventManager>.</span></span>|  
|<span data-ttu-id="cc7d0-144">Creare una classe di gestione di eventi deboli personalizzato</span><span class="sxs-lookup"><span data-stu-id="cc7d0-144">Create a custom weak event manager class</span></span>|<span data-ttu-id="cc7d0-145">Creare una classe personalizzata <xref:System.Windows.WeakEventManager> quando un oggetto esistente <xref:System.Windows.WeakEventManager> non è disponibile e si desidera ottenere migliori prestazioni.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-145">Create a custom <xref:System.Windows.WeakEventManager> when an existing <xref:System.Windows.WeakEventManager> is not available and you want the best efficiency.</span></span> <span data-ttu-id="cc7d0-146">Utilizzo di un <xref:System.Windows.WeakEventManager> per sottoscrivere un evento sarà più efficiente, ma si comportano il costo della scrittura del codice più all'inizio.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-146">Using a custom <xref:System.Windows.WeakEventManager> to subscribe to an event will be more efficient, but you do incur the cost of writing more code at the beginning.</span></span>|  
  
 <span data-ttu-id="cc7d0-147">Nelle sezioni seguenti viene descritto come implementare il modello di eventi deboli.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-147">The following sections describe how to implement the weak event pattern.</span></span>  <span data-ttu-id="cc7d0-148">Ai fini di questa discussione, sottoscrivere l'evento ha le caratteristiche seguenti.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-148">For purposes of this discussion, the event to subscribe to has the following characteristics.</span></span>  
  
-   <span data-ttu-id="cc7d0-149">Il nome dell'evento è `SomeEvent`.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-149">The event name is `SomeEvent`.</span></span>  
  
-   <span data-ttu-id="cc7d0-150">L'evento viene generato per la `EventSource` classe.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-150">The event is raised by the `EventSource` class.</span></span>  
  
-   <span data-ttu-id="cc7d0-151">Il gestore dell'evento è di tipo: `SomeEventEventHandler` (o `EventHandler<SomeEventEventArgs>`).</span><span class="sxs-lookup"><span data-stu-id="cc7d0-151">The event handler has type: `SomeEventEventHandler` (or `EventHandler<SomeEventEventArgs>`).</span></span>  
  
-   <span data-ttu-id="cc7d0-152">L'evento passa un parametro di tipo `SomeEventEventArgs` ai gestori di eventi.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-152">The event passes a parameter of type `SomeEventEventArgs` to the event handlers.</span></span>  
  
### <a name="using-an-existing-weak-event-manager-class"></a><span data-ttu-id="cc7d0-153">Utilizzando una classe di gestione degli eventi deboli esistente</span><span class="sxs-lookup"><span data-stu-id="cc7d0-153">Using an Existing Weak Event Manager Class</span></span>  
  
1.  <span data-ttu-id="cc7d0-154">Trovare un evento debole esistente di gestione.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-154">Find an existing weak event manager.</span></span>  
  
     <span data-ttu-id="cc7d0-155">Per un elenco di gestori di eventi deboli incluse in WPF, vedere la gerarchia di ereditarietà nel <xref:System.Windows.WeakEventManager> classe.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-155">For a list of weak event managers that are included with WPF, see the inheritance hierarchy in the <xref:System.Windows.WeakEventManager> class.</span></span>  
  
2.  <span data-ttu-id="cc7d0-156">Utilizzare la gestione degli eventi debole anziché il collegamento di un evento normale.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-156">Use the new weak event manager instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="cc7d0-157">Ad esempio, se il codice utilizza il modello seguente per sottoscrivere un evento:</span><span class="sxs-lookup"><span data-stu-id="cc7d0-157">For example, if your code uses the following pattern to subscribe to an event:</span></span>  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="cc7d0-158">Selezionare il modello seguente:</span><span class="sxs-lookup"><span data-stu-id="cc7d0-158">Change it to the following pattern:</span></span>  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     <span data-ttu-id="cc7d0-159">Analogamente, se il codice utilizza il modello seguente per annullare la sottoscrizione a un evento:</span><span class="sxs-lookup"><span data-stu-id="cc7d0-159">Similarly, if your code uses the following pattern to unsubscribe to an event:</span></span>  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     <span data-ttu-id="cc7d0-160">Selezionare il modello seguente:</span><span class="sxs-lookup"><span data-stu-id="cc7d0-160">Change it to the following pattern:</span></span>  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
### <a name="using-the-generic-weak-event-manager-class"></a><span data-ttu-id="cc7d0-161">Utilizzando la classe generica di gestione degli eventi deboli</span><span class="sxs-lookup"><span data-stu-id="cc7d0-161">Using the Generic Weak Event Manager Class</span></span>  
  
1.  <span data-ttu-id="cc7d0-162">Utilizzare il metodo generico <xref:System.Windows.WeakEventManager%602> classe anziché il collegamento di un evento normale.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-162">Use the generic <xref:System.Windows.WeakEventManager%602> class instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="cc7d0-163">Quando si utilizza <xref:System.Windows.WeakEventManager%602> per registrare i listener di eventi, si fornisce l'origine evento e <xref:System.EventArgs> tipo dei parametri di tipo di classe e chiamare <xref:System.Windows.WeakEventManager%602.AddHandler%2A> come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="cc7d0-163">When you use <xref:System.Windows.WeakEventManager%602> to register event listeners, you supply the event source and <xref:System.EventArgs> type as the type parameters to the class and call <xref:System.Windows.WeakEventManager%602.AddHandler%2A> as shown in the following code:</span></span>  
  
    ```  
    WeakEventManager<EventSource, SomeEventEventArgs>.AddHandler(source, "SomeEvent", source_SomeEvent);  
    ```  
  
### <a name="creating-a-custom-weak-event-manager-class"></a><span data-ttu-id="cc7d0-164">Creazione di una classe di gestione degli eventi deboli personalizzato</span><span class="sxs-lookup"><span data-stu-id="cc7d0-164">Creating a Custom Weak Event Manager Class</span></span>  
  
1.  <span data-ttu-id="cc7d0-165">Copiare il modello di classe seguente al progetto.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-165">Copy the following class template to your project.</span></span>  
  
     <span data-ttu-id="cc7d0-166">Questa classe eredita la <xref:System.Windows.WeakEventManager> classe.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-166">This class inherits from the <xref:System.Windows.WeakEventManager> class.</span></span>  
  
     [!code-csharp[WeakEvents#WeakEventManagerTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WeakEvents/CSharp/WeakEventManagerTemplate.cs#weakeventmanagertemplate)]  
  
2.  <span data-ttu-id="cc7d0-167">Sostituire il `SomeEventWeakEventManager` nome con il nome desiderato.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-167">Replace the `SomeEventWeakEventManager` name with your own name.</span></span>  
  
3.  <span data-ttu-id="cc7d0-168">Sostituire i nomi di tre descritti in precedenza con i nomi corrispondenti per l'evento.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-168">Replace the three names described previously with the corresponding names for your event.</span></span> <span data-ttu-id="cc7d0-169">(`SomeEvent`, `EventSource`, e `SomeEventEventArgs`)</span><span class="sxs-lookup"><span data-stu-id="cc7d0-169">(`SomeEvent`, `EventSource`, and `SomeEventEventArgs`)</span></span>  
  
4.  <span data-ttu-id="cc7d0-170">Impostare la visibilità della classe di gestione di eventi deboli (pubblica / interna / privata) per la stessa visibilità gestisce l'evento.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-170">Set the visibility (public / internal / private) of the weak event manager class to the same visibility as event it manages.</span></span>  
  
5.  <span data-ttu-id="cc7d0-171">Utilizzare la gestione degli eventi debole anziché il collegamento di un evento normale.</span><span class="sxs-lookup"><span data-stu-id="cc7d0-171">Use the new weak event manager instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="cc7d0-172">Ad esempio, se il codice utilizza il modello seguente per sottoscrivere un evento:</span><span class="sxs-lookup"><span data-stu-id="cc7d0-172">For example, if your code uses the following pattern to subscribe to an event:</span></span>  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="cc7d0-173">Selezionare il modello seguente:</span><span class="sxs-lookup"><span data-stu-id="cc7d0-173">Change it to the following pattern:</span></span>  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     <span data-ttu-id="cc7d0-174">Analogamente, se il codice utilizza il modello seguente per annullare la sottoscrizione a un evento:</span><span class="sxs-lookup"><span data-stu-id="cc7d0-174">Similarly, if your code uses the following pattern to unsubscribe to an event:</span></span>  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     <span data-ttu-id="cc7d0-175">Selezionare il modello seguente:</span><span class="sxs-lookup"><span data-stu-id="cc7d0-175">Change it to the following pattern:</span></span>  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="cc7d0-176">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc7d0-176">See Also</span></span>  
 <xref:System.Windows.WeakEventManager>  
 <xref:System.Windows.IWeakEventListener>  
 [<span data-ttu-id="cc7d0-177">Cenni preliminari sugli eventi indirizzati</span><span class="sxs-lookup"><span data-stu-id="cc7d0-177">Routed Events Overview</span></span>](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [<span data-ttu-id="cc7d0-178">Cenni preliminari sull'associazione dati</span><span class="sxs-lookup"><span data-stu-id="cc7d0-178">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)
