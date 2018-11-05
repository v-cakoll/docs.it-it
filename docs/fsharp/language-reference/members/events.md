---
title: Eventi (F#)
description: Informazioni su come gli eventi F# consentono di associare chiamate di funzione con le azioni utente, che sono importanti nella programmazione GUI.
ms.date: 05/16/2016
ms.openlocfilehash: ce547bc9ec7b5e0ef9a7492c0889bb690e3040c2
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "43871933"
---
# <a name="events"></a><span data-ttu-id="59fec-103">Eventi</span><span class="sxs-lookup"><span data-stu-id="59fec-103">Events</span></span>

> [!NOTE]
<span data-ttu-id="59fec-104">I collegamenti di riferimento all'API in questo articolo portano a MSDN.</span><span class="sxs-lookup"><span data-stu-id="59fec-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="59fec-105">Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.</span><span class="sxs-lookup"><span data-stu-id="59fec-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="59fec-106">Gli eventi consentono di associare chiamate di funzione alle azioni utente e sono importanti nella programmazione dell'interfaccia utente grafica.</span><span class="sxs-lookup"><span data-stu-id="59fec-106">Events enable you to associate function calls with user actions and are important in GUI programming.</span></span> <span data-ttu-id="59fec-107">Gli eventi possono essere attivati anche dalle applicazioni o dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="59fec-107">Events can also be triggered by your applications or by the operating system.</span></span>

## <a name="handling-events"></a><span data-ttu-id="59fec-108">Gestione degli eventi</span><span class="sxs-lookup"><span data-stu-id="59fec-108">Handling Events</span></span>

<span data-ttu-id="59fec-109">Quando si utilizza una libreria come Windows Form o Windows Presentation Foundation (WPF), una parte consistente del codice nell'applicazione viene eseguita in risposta a eventi predefiniti dalla libreria.</span><span class="sxs-lookup"><span data-stu-id="59fec-109">When you use a GUI library like Windows Forms or Windows Presentation Foundation (WPF), much of the code in your application runs in response to events that are predefined by the library.</span></span> <span data-ttu-id="59fec-110">Questi eventi predefiniti sono membri di classi GUI come form e controlli.</span><span class="sxs-lookup"><span data-stu-id="59fec-110">These predefined events are members of GUI classes such as forms and controls.</span></span> <span data-ttu-id="59fec-111">È possibile aggiungere un comportamento personalizzato a un evento preesistente, ad esempio la selezione di un pulsante, facendo riferimento all'evento denominato specifico di interesse (ad esempio, l'evento `Click` della classe `Form`) e richiamando il metodo `Add`, come illustrato nel codice indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="59fec-111">You can add custom behavior to a preexisting event, such as a button click, by referencing the specific named event of interest (for example, the `Click` event of the `Form` class) and invoking the `Add` method, as shown in the following code.</span></span> <span data-ttu-id="59fec-112">Se si esegue questo codice da F# Interactive, omettere la chiamata a `System.Windows.Forms.Application.Run(System.Windows.Forms.Form)`.</span><span class="sxs-lookup"><span data-stu-id="59fec-112">If you run this from F# Interactive, omit the call to `System.Windows.Forms.Application.Run(System.Windows.Forms.Form)`.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3601.fs)]

<span data-ttu-id="59fec-113">Il tipo del metodo `Add` è `('a -> unit) -> unit`.</span><span class="sxs-lookup"><span data-stu-id="59fec-113">The type of the `Add` method is `('a -> unit) -> unit`.</span></span> <span data-ttu-id="59fec-114">Il metodo del gestore eventi accetta pertanto un parametro, in genere gli argomenti dell'evento, e restituisce `unit`.</span><span class="sxs-lookup"><span data-stu-id="59fec-114">Therefore, the event handler method takes one parameter, typically the event arguments, and returns `unit`.</span></span> <span data-ttu-id="59fec-115">Nell'esempio precedente viene illustrato il gestore eventi come un'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="59fec-115">The previous example shows the event handler as a lambda expression.</span></span> <span data-ttu-id="59fec-116">Il gestore eventi può anche essere un valore di funzione, come nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="59fec-116">The event handler can also be a function value, as in the following code example.</span></span> <span data-ttu-id="59fec-117">Nell'esempio di codice seguente viene illustrato anche l'utilizzo dei parametri del gestore eventi, che forniscono informazioni specifiche del tipo di evento.</span><span class="sxs-lookup"><span data-stu-id="59fec-117">The following code example also shows the use of the event handler parameters, which provide information specific to the type of event.</span></span> <span data-ttu-id="59fec-118">Per un evento `MouseMove`, il sistema passa un oggetto `System.Windows.Forms.MouseEventArgs`, che contiene la posizione `X` e `Y` del puntatore.</span><span class="sxs-lookup"><span data-stu-id="59fec-118">For a `MouseMove` event, the system passes a `System.Windows.Forms.MouseEventArgs` object, which contains the `X` and `Y` position of the pointer.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3602.fs)]

## <a name="creating-custom-events"></a><span data-ttu-id="59fec-119">Creazione di eventi personalizzati</span><span class="sxs-lookup"><span data-stu-id="59fec-119">Creating Custom Events</span></span>

<span data-ttu-id="59fec-120">Gli eventi F# sono rappresentati da F# [evento](https://msdn.microsoft.com/library/f3b47c8a-4ee5-4ce8-9a72-ad305a17c4b9) classe che implementa il [IEvent](https://msdn.microsoft.com/library/8dbca0df-f8a1-40bd-8d50-aa26f6a8b862) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="59fec-120">F# events are represented by the F# [Event](https://msdn.microsoft.com/library/f3b47c8a-4ee5-4ce8-9a72-ad305a17c4b9) class, which implements the [IEvent](https://msdn.microsoft.com/library/8dbca0df-f8a1-40bd-8d50-aa26f6a8b862) interface.</span></span> <span data-ttu-id="59fec-121">`IEvent` è un'interfaccia che combina la funzionalità di altre due interfacce, a sua volta `System.IObservable<'T>` e [IDelegateEvent](https://msdn.microsoft.com/library/3d849465-6b8e-4fc5-b36c-2941d734268a).</span><span class="sxs-lookup"><span data-stu-id="59fec-121">`IEvent` is itself an interface that combines the functionality of two other interfaces, `System.IObservable<'T>` and [IDelegateEvent](https://msdn.microsoft.com/library/3d849465-6b8e-4fc5-b36c-2941d734268a).</span></span> <span data-ttu-id="59fec-122">Gli oggetti `Event` dispongono pertanto di funzionalità equivalenti a quelle dei delegati in altri linguaggi, nonché della funzionalità aggiuntiva di `IObservable`, grazie a cui gli eventi F# supportano il filtraggio degli eventi e l'utilizzo delle espressioni lambda e delle funzioni di prima classe F# come gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="59fec-122">Therefore, `Event`s have the equivalent functionality of delegates in other languages, plus the additional functionality from `IObservable`, which means that F# events support event filtering and using F# first-class functions and lambda expressions as event handlers.</span></span> <span data-ttu-id="59fec-123">Questa funzionalità viene fornita nel [modulo di evento](https://msdn.microsoft.com/library/8b883baa-a460-4840-9baa-de8260351bc7).</span><span class="sxs-lookup"><span data-stu-id="59fec-123">This functionality is provided in the [Event module](https://msdn.microsoft.com/library/8b883baa-a460-4840-9baa-de8260351bc7).</span></span>

<span data-ttu-id="59fec-124">Per creare un evento in una classe che agisca come qualsiasi altro evento .NET Framework, aggiungere alla classe un'associazione `let` che definisce un oggetto `Event` come campo in una classe.</span><span class="sxs-lookup"><span data-stu-id="59fec-124">To create an event on a class that acts just like any other .NET Framework event, add to the class a `let` binding that defines an `Event` as a field in a class.</span></span> <span data-ttu-id="59fec-125">È possibile specificare il tipo di argomento dell'evento desiderato come argomento tipo oppure lasciare vuoto il valore affinché il tipo appropriato venga dedotto dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="59fec-125">You can specify the desired event argument type as the type argument, or leave it blank and have the compiler infer the appropriate type.</span></span> <span data-ttu-id="59fec-126">È inoltre necessario definire un membro dell'evento che espone l'evento come evento CLI.</span><span class="sxs-lookup"><span data-stu-id="59fec-126">You also must define an event member that exposes the event as a CLI event.</span></span> <span data-ttu-id="59fec-127">Il membro deve disporre di [CLIEvent](https://msdn.microsoft.com/library/d359f1dd-ffa5-42fb-8808-b4c8131a0333) attributo.</span><span class="sxs-lookup"><span data-stu-id="59fec-127">This member should have the [CLIEvent](https://msdn.microsoft.com/library/d359f1dd-ffa5-42fb-8808-b4c8131a0333) attribute.</span></span> <span data-ttu-id="59fec-128">Viene dichiarato come una proprietà e la relativa implementazione corrisponde a una chiamata per il [pubblica](https://msdn.microsoft.com/library/b0fdaad5-25e5-43d0-9c0c-ce37c4aeb68e) proprietà dell'evento.</span><span class="sxs-lookup"><span data-stu-id="59fec-128">It is declared like a property and its implementation is just a call to the [Publish](https://msdn.microsoft.com/library/b0fdaad5-25e5-43d0-9c0c-ce37c4aeb68e) property of the event.</span></span> <span data-ttu-id="59fec-129">Gli utenti della classe possono utilizzare il metodo `Add` dell'evento pubblicato per aggiungere un gestore.</span><span class="sxs-lookup"><span data-stu-id="59fec-129">Users of your class can use the `Add` method of the published event to add a handler.</span></span> <span data-ttu-id="59fec-130">L'argomento del metodo `Add` può essere un'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="59fec-130">The argument for the `Add` method can be a lambda expression.</span></span> <span data-ttu-id="59fec-131">È possibile utilizzare la proprietà `Trigger` dell'evento per generare l'evento passando un argomento alla funzione del gestore.</span><span class="sxs-lookup"><span data-stu-id="59fec-131">You can use the `Trigger` property of the event to raise the event, passing the arguments to the handler function.</span></span> <span data-ttu-id="59fec-132">Questo aspetto è illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="59fec-132">The following code example illustrates this.</span></span> <span data-ttu-id="59fec-133">In questo esempio, l'argomento tipo dedotto per l'evento è una tupla, che rappresenta gli argomenti per l'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="59fec-133">In this example, the inferred type argument for the event is a tuple, which represents the arguments for the lambda expression.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3605.fs)]

<span data-ttu-id="59fec-134">L'output è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="59fec-134">The output is as follows.</span></span>

```
Event1 occurred! Object data: Hello World!
```

<span data-ttu-id="59fec-135">Di seguito viene illustrata la funzionalità aggiuntiva fornita dal modulo `Event`.</span><span class="sxs-lookup"><span data-stu-id="59fec-135">The additional functionality provided by the `Event` module is illustrated here.</span></span> <span data-ttu-id="59fec-136">Nell'esempio di codice seguente viene illustrato l'utilizzo di base di `Event.create` per creare un evento e un metodo trigger, aggiungere due gestori eventi sotto forma di espressioni lambda e quindi attivare l'evento per eseguire entrambe le espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="59fec-136">The following code example illustrates the basic use of `Event.create` to create an event and a trigger method, add two event handlers in the form of lambda expressions, and then trigger the event to execute both lambda expressions.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3603.fs)]

<span data-ttu-id="59fec-137">Di seguito è riportato l'output del codice precedente.</span><span class="sxs-lookup"><span data-stu-id="59fec-137">The output of the previous code is as follows.</span></span>

```
Event occurred.
Given a value: Event occurred.
```

## <a name="processing-event-streams"></a><span data-ttu-id="59fec-138">Elaborazione di flussi di eventi</span><span class="sxs-lookup"><span data-stu-id="59fec-138">Processing Event Streams</span></span>

<span data-ttu-id="59fec-139">Anziché aggiungere solo un gestore eventi per un evento usando il [Event. Add](https://msdn.microsoft.com/library/10670d3b-8d47-4f6e-b8df-ebc6f64ef4fd) funzione, è possibile usare le funzioni nel `Event` modulo a elaborare i flussi di eventi in modalità estremamente personalizzate.</span><span class="sxs-lookup"><span data-stu-id="59fec-139">Instead of just adding an event handler for an event by using the [Event.add](https://msdn.microsoft.com/library/10670d3b-8d47-4f6e-b8df-ebc6f64ef4fd) function, you can use the functions in the `Event` module to process streams of events in highly customized ways.</span></span> <span data-ttu-id="59fec-140">A tale scopo, utilizzare l'operatore pipe (`|>`) insieme all'evento come primo valore in una serie di chiamate di funzione e le funzioni del modulo `Event` come chiamate di funzione successive.</span><span class="sxs-lookup"><span data-stu-id="59fec-140">To do this, you use the forward pipe (`|>`) together with the event as the first value in a series of function calls, and the `Event` module functions as subsequent function calls.</span></span>

<span data-ttu-id="59fec-141">Nell'esempio di codice seguente viene mostrato come configurare un evento per il quale il gestore viene chiamato solo in determinate condizioni.</span><span class="sxs-lookup"><span data-stu-id="59fec-141">The following code example shows how to set up an event for which the handler is only called under certain conditions.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3604.fs)]

<span data-ttu-id="59fec-142">Il [Observable (modulo)](https://msdn.microsoft.com/library/16b8610b-b30a-4df7-aa99-d9d352276227) contiene funzioni analoghe che operano su oggetti osservabili.</span><span class="sxs-lookup"><span data-stu-id="59fec-142">The [Observable module](https://msdn.microsoft.com/library/16b8610b-b30a-4df7-aa99-d9d352276227) contains similar functions that operate on observable objects.</span></span> <span data-ttu-id="59fec-143">Gli oggetti osservabili sono simili agli eventi, ma sottoscrivono gli eventi in modo attivo solo se vengono anch'essi sottoscritti.</span><span class="sxs-lookup"><span data-stu-id="59fec-143">Observable objects are similar to events but only actively subscribe to events if they themselves are being subscribed to.</span></span>

## <a name="implementing-an-interface-event"></a><span data-ttu-id="59fec-144">Implementazione di un evento di interfaccia</span><span class="sxs-lookup"><span data-stu-id="59fec-144">Implementing an Interface Event</span></span>

<span data-ttu-id="59fec-145">Quando si sviluppano componenti dell'interfaccia utente, spesso si inizia creando un nuovo form o un nuovo controllo che eredita da un form o un controllo esistente.</span><span class="sxs-lookup"><span data-stu-id="59fec-145">As you develop UI components, you often start by creating a new form or a new control that inherits from an existing form or control.</span></span> <span data-ttu-id="59fec-146">Gli eventi sono definiti di frequente su un'interfaccia e, in tal caso, è necessario implementare l'interfaccia per implementare l'evento.</span><span class="sxs-lookup"><span data-stu-id="59fec-146">Events are frequently defined on an interface, and, in that case, you must implement the interface to implement the event.</span></span> <span data-ttu-id="59fec-147">L'interfaccia `System.ComponentModel.INotifyPropertyChanged` definisce un solo evento `System.ComponentModel.INotifyPropertyChanged.PropertyChanged`.</span><span class="sxs-lookup"><span data-stu-id="59fec-147">The `System.ComponentModel.INotifyPropertyChanged` interface defines a single `System.ComponentModel.INotifyPropertyChanged.PropertyChanged` event.</span></span> <span data-ttu-id="59fec-148">Il codice seguente illustra come implementare l'evento definito da questa interfaccia ereditata:</span><span class="sxs-lookup"><span data-stu-id="59fec-148">The following code illustrates how to implement the event that this inherited interface defined:</span></span>

```fsharp
module CustomForm

open System.Windows.Forms
open System.ComponentModel

type AppForm() as this =
    inherit Form()

    // Define the propertyChanged event.
    let propertyChanged = Event<PropertyChangedEventHandler, PropertyChangedEventArgs>()
    let mutable underlyingValue = "text0"

    // Set up a click event to change the properties.
    do
        this.Click |> Event.add(fun evArgs -> this.Property1 <- "text2"
        this.Property2 <- "text3")

    // This property does not have the property-changed event set.
    member val Property1 : string = "text" with get, set

    // This property has the property-changed event set.
    member this.Property2
        with get() = underlyingValue
        and set(newValue) =
            underlyingValue <- newValue
            propertyChanged.Trigger(this, new PropertyChangedEventArgs("Property2"))

    // Expose the PropertyChanged event as a first class .NET event.
    [<CLIEvent>]
    member this.PropertyChanged = propertyChanged.Publish


    // Define the add and remove methods to implement this interface.
    interface INotifyPropertyChanged with
        member this.add_PropertyChanged(handler) = propertyChanged.Publish.AddHandler(handler)
        member this.remove_PropertyChanged(handler) = propertyChanged.Publish.RemoveHandler(handler)

    // This is the event-handler method.
    member this.OnPropertyChanged(args : PropertyChangedEventArgs) =
        let newProperty = this.GetType().GetProperty(args.PropertyName)
        let newValue = newProperty.GetValue(this :> obj) :?> string
        printfn "Property %s changed its value to %s" args.PropertyName newValue

// Create a form, hook up the event handler, and start the application.
let appForm = new AppForm()
let inpc = appForm :> INotifyPropertyChanged
inpc.PropertyChanged.Add(appForm.OnPropertyChanged)
Application.Run(appForm)
```

<span data-ttu-id="59fec-149">Se si desidera collegare l'evento nel costruttore, il codice è un po' più complesso perché il collegamento di evento deve trovarsi in un blocco `then` in un costruttore aggiuntivo, come nel seguente esempio:</span><span class="sxs-lookup"><span data-stu-id="59fec-149">If you want to hook up the event in the constructor, the code is a bit more complicated because the event hookup must be in a `then` block in an additional constructor, as in the following example:</span></span>

```fsharp
module CustomForm

open System.Windows.Forms
open System.ComponentModel

// Create a private constructor with a dummy argument so that the public
// constructor can have no arguments.
type AppForm private (dummy) as this =
    inherit Form()

    // Define the propertyChanged event.
    let propertyChanged = Event<PropertyChangedEventHandler, PropertyChangedEventArgs>()
    let mutable underlyingValue = "text0"

    // Set up a click event to change the properties.
    do
        this.Click |> Event.add(fun evArgs -> this.Property1 <- "text2"
        this.Property2 <- "text3")


    // This property does not have the property changed event set.
    member val Property1 : string = "text" with get, set

    // This property has the property changed event set.
    member this.Property2
        with get() = underlyingValue
        and set(newValue) =
            underlyingValue <- newValue
            propertyChanged.Trigger(this, new PropertyChangedEventArgs("Property2"))

    [<CLIEvent>]
    member this.PropertyChanged = propertyChanged.Publish

    // Define the add and remove methods to implement this interface.
    interface INotifyPropertyChanged with
        member this.add_PropertyChanged(handler) = this.PropertyChanged.AddHandler(handler)
        member this.remove_PropertyChanged(handler) = this.PropertyChanged.RemoveHandler(handler)

    // This is the event handler method.
    member this.OnPropertyChanged(args : PropertyChangedEventArgs) =
        let newProperty = this.GetType().GetProperty(args.PropertyName)
        let newValue = newProperty.GetValue(this :> obj) :?> string
        printfn "Property %s changed its value to %s" args.PropertyName newValue

    new() as this =
        new AppForm(0)
        then
            let inpc = this :> INotifyPropertyChanged
            inpc.PropertyChanged.Add(this.OnPropertyChanged)


// Create a form, hook up the event handler, and start the application.
let appForm = new AppForm()
Application.Run(appForm)
```

## <a name="see-also"></a><span data-ttu-id="59fec-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="59fec-150">See also</span></span>

- [<span data-ttu-id="59fec-151">Membri</span><span class="sxs-lookup"><span data-stu-id="59fec-151">Members</span></span>](index.md)
- [<span data-ttu-id="59fec-152">La gestione e generazione di eventi</span><span class="sxs-lookup"><span data-stu-id="59fec-152">Handling and Raising Events</span></span>](../../../../docs/standard/events/index.md)
- [<span data-ttu-id="59fec-153">Espressioni lambda: I `fun` (parola chiave)</span><span class="sxs-lookup"><span data-stu-id="59fec-153">Lambda Expressions: The `fun` Keyword</span></span>](../functions/lambda-expressions-the-fun-keyword.md)
- [<span data-ttu-id="59fec-154">Modulo Control. event</span><span class="sxs-lookup"><span data-stu-id="59fec-154">Control.Event Module</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.event-module-%5bfsharp%5d)
- [<span data-ttu-id="59fec-155">Control. event&#60;l&#62; classe</span><span class="sxs-lookup"><span data-stu-id="59fec-155">Control.Event&#60;'T&#62; Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.event%5b%27t%5d-class-%5bfsharp%5d)
- [<span data-ttu-id="59fec-156">Control. event&#60;'Delegate' Args&#62; classe</span><span class="sxs-lookup"><span data-stu-id="59fec-156">Control.Event&#60;'Delegate,'Args&#62; Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.event%5b%27delegate%2c%27args%5d-class-%5bfsharp%5d)
