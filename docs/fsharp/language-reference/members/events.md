---
title: Eventi
description: Informazioni su F# come gli eventi consentono di associare chiamate di funzione a azioni utente, che sono importanti nella programmazione GUI.
ms.date: 05/16/2016
ms.openlocfilehash: ad60aff318832ab3ba5e9f7c43928898e171cea8
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543625"
---
# <a name="events"></a>Eventi

> [!NOTE]
> I collegamenti di riferimento all'API in questo articolo portano a MSDN.  Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.

Gli eventi consentono di associare chiamate di funzione alle azioni utente e sono importanti nella programmazione dell'interfaccia utente grafica. Gli eventi possono essere attivati anche dalle applicazioni o dal sistema operativo.

## <a name="handling-events"></a>Gestione degli eventi

Quando si utilizza una libreria come Windows Form o Windows Presentation Foundation (WPF), una parte consistente del codice nell'applicazione viene eseguita in risposta a eventi predefiniti dalla libreria. Questi eventi predefiniti sono membri di classi GUI come form e controlli. È possibile aggiungere un comportamento personalizzato a un evento preesistente, ad esempio la selezione di un pulsante, facendo riferimento all'evento denominato specifico di interesse (ad esempio, l'evento `Click` della classe `Form`) e richiamando il metodo `Add`, come illustrato nel codice indicato di seguito. Se si esegue questo codice da F# Interactive, omettere la chiamata a `System.Windows.Forms.Application.Run(System.Windows.Forms.Form)`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3601.fs)]

Il tipo del metodo `Add` è `('a -> unit) -> unit`. Il metodo del gestore eventi accetta pertanto un parametro, in genere gli argomenti dell'evento, e restituisce `unit`. Nell'esempio precedente viene illustrato il gestore eventi come un'espressione lambda. Il gestore eventi può anche essere un valore di funzione, come nell'esempio di codice seguente. Nell'esempio di codice seguente viene illustrato anche l'utilizzo dei parametri del gestore eventi, che forniscono informazioni specifiche del tipo di evento. Per un evento `MouseMove`, il sistema passa un oggetto `System.Windows.Forms.MouseEventArgs`, che contiene la posizione `X` e `Y` del puntatore.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3602.fs)]

## <a name="creating-custom-events"></a>Creazione di eventi personalizzati

F#gli eventi sono rappresentati F# dalla classe di [evento](https://msdn.microsoft.com/library/f3b47c8a-4ee5-4ce8-9a72-ad305a17c4b9) , che implementa l'interfaccia [IEvent](https://msdn.microsoft.com/library/8dbca0df-f8a1-40bd-8d50-aa26f6a8b862) . `IEvent` è un'interfaccia che combina la funzionalità di altre due interfacce, `System.IObservable<'T>` e [IDelegateEvent](https://msdn.microsoft.com/library/3d849465-6b8e-4fc5-b36c-2941d734268a). Gli oggetti `Event` dispongono pertanto di funzionalità equivalenti a quelle dei delegati in altri linguaggi, nonché della funzionalità aggiuntiva di `IObservable`, grazie a cui gli eventi F# supportano il filtraggio degli eventi e l'utilizzo delle espressioni lambda e delle funzioni di prima classe F# come gestori eventi. Questa funzionalità è disponibile nel [modulo degli eventi](https://msdn.microsoft.com/library/8b883baa-a460-4840-9baa-de8260351bc7).

Per creare un evento in una classe che agisca come qualsiasi altro evento .NET Framework, aggiungere alla classe un'associazione `let` che definisce un oggetto `Event` come campo in una classe. È possibile specificare il tipo di argomento dell'evento desiderato come argomento tipo oppure lasciare vuoto il valore affinché il tipo appropriato venga dedotto dal compilatore. È inoltre necessario definire un membro dell'evento che espone l'evento come evento CLI. Questo membro deve avere l'attributo [CLIEvent (](https://msdn.microsoft.com/library/d359f1dd-ffa5-42fb-8808-b4c8131a0333) . Viene dichiarata come una proprietà e la relativa implementazione è semplicemente una chiamata alla proprietà [Publish](https://msdn.microsoft.com/library/b0fdaad5-25e5-43d0-9c0c-ce37c4aeb68e) dell'evento. Gli utenti della classe possono utilizzare il metodo `Add` dell'evento pubblicato per aggiungere un gestore. L'argomento del metodo `Add` può essere un'espressione lambda. È possibile utilizzare la proprietà `Trigger` dell'evento per generare l'evento passando un argomento alla funzione del gestore. Questo aspetto è illustrato nell'esempio di codice seguente. In questo esempio, l'argomento tipo dedotto per l'evento è una tupla, che rappresenta gli argomenti per l'espressione lambda.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3605.fs)]

L'output è indicato di seguito.

```console
Event1 occurred! Object data: Hello World!
```

Di seguito viene illustrata la funzionalità aggiuntiva fornita dal modulo `Event`. Nell'esempio di codice seguente viene illustrato l'utilizzo di base di `Event.create` per creare un evento e un metodo trigger, aggiungere due gestori eventi sotto forma di espressioni lambda e quindi attivare l'evento per eseguire entrambe le espressioni.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3603.fs)]

Di seguito è riportato l'output del codice precedente.

```console
Event occurred.
Given a value: Event occurred.
```

## <a name="processing-event-streams"></a>Elaborazione di flussi di eventi

Anziché aggiungere semplicemente un gestore eventi per un evento tramite la funzione [Event. Add](https://msdn.microsoft.com/library/10670d3b-8d47-4f6e-b8df-ebc6f64ef4fd) , è possibile usare le funzioni nel modulo `Event` per elaborare flussi di eventi in modi altamente personalizzati. A tale scopo, utilizzare l'operatore pipe (`|>`) insieme all'evento come primo valore in una serie di chiamate di funzione e le funzioni del modulo `Event` come chiamate di funzione successive.

Nell'esempio di codice seguente viene mostrato come configurare un evento per il quale il gestore viene chiamato solo in determinate condizioni.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3604.fs)]

Il [modulo osservabile](https://msdn.microsoft.com/library/16b8610b-b30a-4df7-aa99-d9d352276227) contiene funzioni simili che operano su oggetti osservabili. Gli oggetti osservabili sono simili agli eventi, ma sottoscrivono gli eventi in modo attivo solo se vengono anch'essi sottoscritti.

## <a name="implementing-an-interface-event"></a>Implementazione di un evento di interfaccia

Quando si sviluppano componenti dell'interfaccia utente, spesso si inizia creando un nuovo form o un nuovo controllo che eredita da un form o un controllo esistente. Gli eventi sono definiti di frequente su un'interfaccia e, in tal caso, è necessario implementare l'interfaccia per implementare l'evento. L'interfaccia `System.ComponentModel.INotifyPropertyChanged` definisce un solo evento `System.ComponentModel.INotifyPropertyChanged.PropertyChanged`. Il codice seguente illustra come implementare l'evento definito da questa interfaccia ereditata:

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
        this.Click |> Event.add(fun evArgs ->
            this.Property1 <- "text2"
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

Se si desidera collegare l'evento nel costruttore, il codice è un po' più complesso perché il collegamento di evento deve trovarsi in un blocco `then` in un costruttore aggiuntivo, come nel seguente esempio:

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
        this.Click |> Event.add(fun evArgs ->
            this.Property1 <- "text2"
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

## <a name="see-also"></a>Vedere anche

- [Members](index.md)
- [Gestione e generazione di eventi](../../../standard/events/index.md)
- [Espressioni lambda: parola chiave `fun`](../functions/lambda-expressions-the-fun-keyword.md)
- [Modulo Control. Event](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.event-module-%5bfsharp%5d)
- [Classe Control.&#60;Event&#62; ' t](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.event%5b%27t%5d-class-%5bfsharp%5d)
- [Control. Event&#60;' Delegate,' args&#62; (classe)](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.event%5b%27delegate%2c%27args%5d-class-%5bfsharp%5d)
