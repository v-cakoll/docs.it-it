---
title: Introduzione agli eventi
description: Questa panoramica offre informazioni sugli eventi di .NET Core e sugli obiettivi di progettazione del linguaggio per gli eventi.
ms.date: 06/20/2016
ms.assetid: 9b8d2a00-1584-4a5b-8994-5003d54d8e0c
ms.openlocfilehash: 4e660f85eecfd5668919baf21a0d26f858faf5a6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79146114"
---
# <a name="introduction-to-events"></a><span data-ttu-id="55f5f-103">Introduzione agli eventi</span><span class="sxs-lookup"><span data-stu-id="55f5f-103">Introduction to events</span></span>

[<span data-ttu-id="55f5f-104">Indietro</span><span class="sxs-lookup"><span data-stu-id="55f5f-104">Previous</span></span>](delegates-patterns.md)

<span data-ttu-id="55f5f-105">Analogamente ai delegati, gli eventi sono un meccanismo di *associazione tardiva*.</span><span class="sxs-lookup"><span data-stu-id="55f5f-105">Events are, like delegates, a *late binding* mechanism.</span></span> <span data-ttu-id="55f5f-106">In effetti, gli eventi hanno alla base il supporto del linguaggio per i delegati.</span><span class="sxs-lookup"><span data-stu-id="55f5f-106">In fact, events are built on the language support for delegates.</span></span>

<span data-ttu-id="55f5f-107">Gli eventi rappresentano il modo in cui un oggetto comunica a tutti i componenti del sistema interessati che è avvenuto qualcosa.</span><span class="sxs-lookup"><span data-stu-id="55f5f-107">Events are a way for an object to broadcast (to all interested components in the system) that something has happened.</span></span> <span data-ttu-id="55f5f-108">Qualsiasi altro componente può sottoscrivere l'evento e ricevere una notifica quando tale evento viene generato.</span><span class="sxs-lookup"><span data-stu-id="55f5f-108">Any other component can subscribe to the event, and be notified when an event is raised.</span></span>

<span data-ttu-id="55f5f-109">Probabilmente in altri programmi creati in passato gli eventi sono già stati usati.</span><span class="sxs-lookup"><span data-stu-id="55f5f-109">You've probably used events in some of your programming.</span></span> <span data-ttu-id="55f5f-110">Molti sistemi grafici dispongono di un modello di eventi per segnalare l'interazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="55f5f-110">Many graphical systems have an event model to report user interaction.</span></span> <span data-ttu-id="55f5f-111">Questi eventi segnalano il movimento del mouse, la pressione di pulsanti e interazioni analoghe.</span><span class="sxs-lookup"><span data-stu-id="55f5f-111">These events would report mouse movement, button presses and similar interactions.</span></span> <span data-ttu-id="55f5f-112">Questo è uno degli scenari più comuni di uso degli eventi, ma sicuramente non l'unico.</span><span class="sxs-lookup"><span data-stu-id="55f5f-112">That's one of the most common, but certainly not the only scenario where events are used.</span></span>

<span data-ttu-id="55f5f-113">È possibile definire gli eventi che devono essere generati per le classi.</span><span class="sxs-lookup"><span data-stu-id="55f5f-113">You can define events that should be raised for your classes.</span></span> <span data-ttu-id="55f5f-114">Una considerazione importante per l'uso degli eventi è che per un evento specifico potrebbe non essere registrato alcun oggetto.</span><span class="sxs-lookup"><span data-stu-id="55f5f-114">One important consideration when working with events is that there may not be any object registered for a particular event.</span></span> <span data-ttu-id="55f5f-115">È necessario scrivere il codice in modo che vengano generati eventi solo se è configurato un listener.</span><span class="sxs-lookup"><span data-stu-id="55f5f-115">You must write your code so that it does not raise events when no listeners are configured.</span></span>

<span data-ttu-id="55f5f-116">La sottoscrizione di un evento crea anche un accoppiamento tra due oggetti, l'origine evento e il sink di evento.</span><span class="sxs-lookup"><span data-stu-id="55f5f-116">Subscribing to an event also creates a coupling between two objects (the event source, and the event sink).</span></span> <span data-ttu-id="55f5f-117">È necessario assicurarsi che il sink di evento annulli la sottoscrizione dall'origine evento quando non è più interessato agli eventi.</span><span class="sxs-lookup"><span data-stu-id="55f5f-117">You need to ensure that the event sink unsubscribes from the event source when no longer interested in events.</span></span>

## <a name="design-goals-for-event-support"></a><span data-ttu-id="55f5f-118">Obiettivi di progettazione per il supporto degli eventi</span><span class="sxs-lookup"><span data-stu-id="55f5f-118">Design goals for event support</span></span>

<span data-ttu-id="55f5f-119">La progettazione del linguaggio per gli eventi si rivolge a questi obiettivi:The language design for events targets these goals:</span><span class="sxs-lookup"><span data-stu-id="55f5f-119">The language design for events targets these goals:</span></span>

- <span data-ttu-id="55f5f-120">Abilitare un accoppiamento minimo tra un'origine eventi e un sink di evento.</span><span class="sxs-lookup"><span data-stu-id="55f5f-120">Enable very minimal coupling between an event source and an event sink.</span></span> <span data-ttu-id="55f5f-121">È possibile che questi due componenti non siano stati scritti dalla stessa organizzazione. È persino possibile che l'aggiornamento di questi componenti avvenga secondo pianificazioni completamente diverse.</span><span class="sxs-lookup"><span data-stu-id="55f5f-121">These two components may not be written by the same organization, and may even be updated on totally different schedules.</span></span>

- <span data-ttu-id="55f5f-122">Dovrebbe essere molto semplice sottoscrivere un evento e annullare la sottoscrizione dello stesso evento.</span><span class="sxs-lookup"><span data-stu-id="55f5f-122">It should be very simple to subscribe to an event, and to unsubscribe from that same event.</span></span>

- <span data-ttu-id="55f5f-123">Le origini eventi devono supportare più sottoscrittori di eventi.</span><span class="sxs-lookup"><span data-stu-id="55f5f-123">Event sources should support multiple event subscribers.</span></span> <span data-ttu-id="55f5f-124">nonché la completa mancanza di sottoscrittori associati.</span><span class="sxs-lookup"><span data-stu-id="55f5f-124">It should also support having no event subscribers attached.</span></span>

<span data-ttu-id="55f5f-125">Come si può notare, gli obiettivi per gli eventi sono molto simili agli obiettivi per i delegati.</span><span class="sxs-lookup"><span data-stu-id="55f5f-125">You can see that the goals for events are very similar to the goals for delegates.</span></span>
<span data-ttu-id="55f5f-126">Ecco perché il supporto del linguaggio per gli eventi si basa sul supporto del linguaggio per i delegati.</span><span class="sxs-lookup"><span data-stu-id="55f5f-126">That's why the event language support is built on the delegate language support.</span></span>

## <a name="language-support-for-events"></a><span data-ttu-id="55f5f-127">Supporto linguistico per gli eventi</span><span class="sxs-lookup"><span data-stu-id="55f5f-127">Language support for events</span></span>

<span data-ttu-id="55f5f-128">La sintassi per la definizione di eventi e la sottoscrizione o l'annullamento della sottoscrizione di eventi è un'estensione della sintassi per i delegati.</span><span class="sxs-lookup"><span data-stu-id="55f5f-128">The syntax for defining events, and subscribing or unsubscribing from events is an extension of the syntax for delegates.</span></span>

<span data-ttu-id="55f5f-129">Per definire un evento si usa la parola chiave `event`:</span><span class="sxs-lookup"><span data-stu-id="55f5f-129">To define an event you use the `event` keyword:</span></span>

```csharp
public event EventHandler<FileListArgs> Progress;
```

<span data-ttu-id="55f5f-130">Il tipo di evento (`EventHandler<FileListArgs>` in questo esempio) deve essere un tipo di delegato.</span><span class="sxs-lookup"><span data-stu-id="55f5f-130">The type of the event (`EventHandler<FileListArgs>` in this example) must be a delegate type.</span></span> <span data-ttu-id="55f5f-131">Quando si dichiara un evento, è necessario seguire un certo numero di convenzioni.</span><span class="sxs-lookup"><span data-stu-id="55f5f-131">There are a number of conventions that you should follow when declaring an event.</span></span> <span data-ttu-id="55f5f-132">In genere, il tipo di delegato di un evento restituisce void.</span><span class="sxs-lookup"><span data-stu-id="55f5f-132">Typically, the event delegate type has a void return.</span></span>
<span data-ttu-id="55f5f-133">Le dichiarazioni di eventi devono essere un verbo o una frase verbale.</span><span class="sxs-lookup"><span data-stu-id="55f5f-133">Event declarations should be a verb, or a verb phrase.</span></span>
<span data-ttu-id="55f5f-134">Usa il tempo passato quando l'evento riporta qualcosa che è accaduto.</span><span class="sxs-lookup"><span data-stu-id="55f5f-134">Use past tense when the event reports something that has happened.</span></span> <span data-ttu-id="55f5f-135">Usare il presente (ad esempio, `Closing`) per segnalare qualcosa che sta per verificarsi.</span><span class="sxs-lookup"><span data-stu-id="55f5f-135">Use a present tense verb (for example, `Closing`) to report something that is about to happen.</span></span> <span data-ttu-id="55f5f-136">L'uso del presente indica spesso che la classe supporta un determinato tipo di comportamento di personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="55f5f-136">Often, using present tense indicates that your class supports some kind of customization behavior.</span></span> <span data-ttu-id="55f5f-137">Uno degli scenari più comuni riguarda il supporto dell'annullamento.</span><span class="sxs-lookup"><span data-stu-id="55f5f-137">One of the most common scenarios is to support cancellation.</span></span> <span data-ttu-id="55f5f-138">Un evento `Closing`, ad esempio, può includere un argomento che indica se l'operazione di chiusura deve continuare o meno.</span><span class="sxs-lookup"><span data-stu-id="55f5f-138">For example, a `Closing` event may include an argument that would indicate if the close operation should continue, or not.</span></span>  <span data-ttu-id="55f5f-139">Altri scenari possono consentire ai chiamanti di modificare il comportamento tramite l'aggiornamento delle proprietà degli argomenti dell'evento.</span><span class="sxs-lookup"><span data-stu-id="55f5f-139">Other scenarios may enable callers to modify behavior by updating properties of the event arguments.</span></span> <span data-ttu-id="55f5f-140">È possibile generare un evento per proporre l'azione successiva che un algoritmo deve eseguire.</span><span class="sxs-lookup"><span data-stu-id="55f5f-140">You may raise an event to indicate a proposed next action an algorithm will take.</span></span> <span data-ttu-id="55f5f-141">Il gestore eventi può imporre un'azione diversa modificando le proprietà dell'argomento dell'evento.</span><span class="sxs-lookup"><span data-stu-id="55f5f-141">The event handler may mandate a different action by modifying  properties of the event argument.</span></span>

<span data-ttu-id="55f5f-142">Quando si vuole generare l'evento, è possibile chiamare i gestori eventi tramite la sintassi di chiamata dei delegati:</span><span class="sxs-lookup"><span data-stu-id="55f5f-142">When you want to raise the event, you call the event handlers using the delegate invocation syntax:</span></span>

```csharp
Progress?.Invoke(this, new FileListArgs(file));
```

<span data-ttu-id="55f5f-143">Come descritto nella sezione sui [delegati](delegates-patterns.md), l'operatore ?.</span><span class="sxs-lookup"><span data-stu-id="55f5f-143">As discussed in the section on [delegates](delegates-patterns.md), the ?.</span></span>
<span data-ttu-id="55f5f-144">assicura in modo semplice che non venga generato un evento se questo non ha sottoscrittori.</span><span class="sxs-lookup"><span data-stu-id="55f5f-144">operator makes it easy to ensure that you do not attempt to raise the event when there are no subscribers to that event.</span></span>

<span data-ttu-id="55f5f-145">Per sottoscrivere un evento si usa l'operatore `+=`:</span><span class="sxs-lookup"><span data-stu-id="55f5f-145">You subscribe to an event by using the `+=` operator:</span></span>

```csharp
EventHandler<FileListArgs> onProgress = (sender, eventArgs) =>
    Console.WriteLine(eventArgs.FoundFile);

fileLister.Progress += onProgress;
```

<span data-ttu-id="55f5f-146">Il metodo del gestore ha in genere il prefisso 'On' seguito dal nome dell'evento, come illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="55f5f-146">The handler method typically has the prefix 'On' followed by the event name, as shown above.</span></span>

<span data-ttu-id="55f5f-147">Per annullare la sottoscrizione si usa l'operatore `-=`:</span><span class="sxs-lookup"><span data-stu-id="55f5f-147">You unsubscribe using the `-=` operator:</span></span>

```csharp
fileLister.Progress -= onProgress;
```

<span data-ttu-id="55f5f-148">È importante notare che per l'espressione che rappresenta il gestore eventi è stata dichiarata una variabile locale.</span><span class="sxs-lookup"><span data-stu-id="55f5f-148">It's important to note that I declared a local variable for the expression that represents the event handler.</span></span> <span data-ttu-id="55f5f-149">Questo garantisce che l'annullamento della sottoscrizione rimuova il gestore.</span><span class="sxs-lookup"><span data-stu-id="55f5f-149">That ensures the unsubscribe removes the handler.</span></span>
<span data-ttu-id="55f5f-150">Se invece si usa il corpo dell'espressione lambda, si tenta di rimuovere un gestore che non è mai stato associato e non viene quindi eseguita alcuna operazione.</span><span class="sxs-lookup"><span data-stu-id="55f5f-150">If, instead, you used the body of the lambda expression, you are attempting to remove a handler that has never been attached, which does nothing.</span></span>

<span data-ttu-id="55f5f-151">Il prossimo articolo offre altre informazioni sui criteri tipici degli eventi, oltre a diverse varianti di questo esempio.</span><span class="sxs-lookup"><span data-stu-id="55f5f-151">In the next article, you'll learn more about typical event patterns, and different variations on this example.</span></span>

[<span data-ttu-id="55f5f-152">Avanti</span><span class="sxs-lookup"><span data-stu-id="55f5f-152">Next</span></span>](event-pattern.md)
