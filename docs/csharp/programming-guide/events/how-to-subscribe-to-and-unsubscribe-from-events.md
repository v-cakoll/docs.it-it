---
title: Come sottoscrivere e annullare la sottoscrizione agli eventi - Guida per programmatori C
ms.date: 07/20/2015
helpviewer_keywords:
- event handlers [C#], creating
- Code Editor, event handlers
- events [C#], creating using the IDE
ms.assetid: 6319f39f-282c-4173-8a62-6c4657cf51cd
ms.openlocfilehash: 3df357cb15f7f77cefbf360dd9615ce246afe2ea
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75705327"
---
# <a name="how-to-subscribe-to-and-unsubscribe-from-events-c-programming-guide"></a><span data-ttu-id="1a2f7-102">Come sottoscrivere e annullare la sottoscrizione agli eventi (Guida per programmatori C</span><span class="sxs-lookup"><span data-stu-id="1a2f7-102">How to subscribe to and unsubscribe from events (C# Programming Guide)</span></span>
<span data-ttu-id="1a2f7-103">Si sottoscrive un evento pubblicato da un'altra classe quando si vuole scrivere codice personalizzato che viene chiamato quando viene generato tale evento.</span><span class="sxs-lookup"><span data-stu-id="1a2f7-103">You subscribe to an event that is published by another class when you want to write custom code that is called when that event is raised.</span></span> <span data-ttu-id="1a2f7-104">È ad esempio possibile sottoscrivere l'evento `click` di un pulsante perché l'applicazione esegua un'operazione utile quando l'utente fa clic sul pulsante in questione.</span><span class="sxs-lookup"><span data-stu-id="1a2f7-104">For example, you might subscribe to a button's `click` event in order to make your application do something useful when the user clicks the button.</span></span>  
  
### <a name="to-subscribe-to-events-by-using-the-visual-studio-ide"></a><span data-ttu-id="1a2f7-105">Per sottoscrivere gli eventi usando l'IDE di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1a2f7-105">To subscribe to events by using the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="1a2f7-106">Se la finestra **Proprietà** non viene visualizzata, nella visualizzazione **Progettazione** fare clic con il pulsante destro del mouse sul modulo o sul controllo per cui si vuole creare un gestore eventi e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="1a2f7-106">If you cannot see the **Properties** window, in **Design** view, right-click the form or control for which you want to create an event handler, and select **Properties**.</span></span>  
  
2. <span data-ttu-id="1a2f7-107">Nella parte superiore della finestra **Proprietà** fare clic sull'icona **Eventi**.</span><span class="sxs-lookup"><span data-stu-id="1a2f7-107">On top of the **Properties** window, click the **Events** icon.</span></span>  
  
3. <span data-ttu-id="1a2f7-108">Fare doppio clic sull'evento che si vuole creare, ad esempio sull'evento `Load`.</span><span class="sxs-lookup"><span data-stu-id="1a2f7-108">Double-click the event that you want to create, for example the `Load` event.</span></span>  
  
     <span data-ttu-id="1a2f7-109">Visual C# crea un metodo del gestore eventi vuoto e lo aggiunge al codice.</span><span class="sxs-lookup"><span data-stu-id="1a2f7-109">Visual C# creates an empty event handler method and adds it to your code.</span></span> <span data-ttu-id="1a2f7-110">In alternativa, è possibile aggiungere manualmente il codice nella visualizzazione **Codice**.</span><span class="sxs-lookup"><span data-stu-id="1a2f7-110">Alternatively you can add the code manually in **Code** view.</span></span> <span data-ttu-id="1a2f7-111">Ad esempio, le righe di codice seguenti dichiarano un metodo del gestore eventi che verrà chiamato quando la classe `Form` genera l'evento `Load`.</span><span class="sxs-lookup"><span data-stu-id="1a2f7-111">For example, the following lines of code declare an event handler method that will be called when the `Form` class raises the `Load` event.</span></span>  
  
     [!code-csharp[csProgGuideEvents#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#11)]  
  
     <span data-ttu-id="1a2f7-112">La riga di codice necessaria per sottoscrivere l'evento viene generata automaticamente nel metodo `InitializeComponent` nel file Form1.Designer.cs del progetto.</span><span class="sxs-lookup"><span data-stu-id="1a2f7-112">The line of code that is required to subscribe to the event is also automatically generated in the `InitializeComponent` method in the Form1.Designer.cs file in your project.</span></span> <span data-ttu-id="1a2f7-113">La riga ha un aspetto simile a quanto riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="1a2f7-113">It resembles this:</span></span>  
  
    ```csharp
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
### <a name="to-subscribe-to-events-programmatically"></a><span data-ttu-id="1a2f7-114">Per sottoscrivere gli eventi a livello di codice</span><span class="sxs-lookup"><span data-stu-id="1a2f7-114">To subscribe to events programmatically</span></span>  
  
1. <span data-ttu-id="1a2f7-115">Definire un metodo del gestore eventi la cui firma corrisponda alla firma del delegato per l'evento.</span><span class="sxs-lookup"><span data-stu-id="1a2f7-115">Define an event handler method whose signature matches the delegate signature for the event.</span></span> <span data-ttu-id="1a2f7-116">Se ad esempio l'evento è basato sul tipo di delegato <xref:System.EventHandler>, il codice riportato di seguito rappresenta lo stub del metodo:</span><span class="sxs-lookup"><span data-stu-id="1a2f7-116">For example, if the event is based on the <xref:System.EventHandler> delegate type, the following code represents the method stub:</span></span>  
  
    ```csharp
    void HandleCustomEvent(object sender, CustomEventArgs a)  
    {  
       // Do something useful here.  
    }  
    ```  
  
2. <span data-ttu-id="1a2f7-117">Usare l'operatore di assegnazione di addizione (`+=`) per associare un gestore all'evento.</span><span class="sxs-lookup"><span data-stu-id="1a2f7-117">Use the addition assignment operator (`+=`) to attach an event handler to the event.</span></span> <span data-ttu-id="1a2f7-118">Nell'esempio seguente si supponga che a un oggetto denominato `publisher` sia associato un evento denominato `RaiseCustomEvent`.</span><span class="sxs-lookup"><span data-stu-id="1a2f7-118">In the following example, assume that an object named `publisher` has an event named `RaiseCustomEvent`.</span></span> <span data-ttu-id="1a2f7-119">Si noti che per la classe subscriber è necessario un riferimento alla classe publisher per sottoscrivere gli eventi corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="1a2f7-119">Note that the subscriber class needs a reference to the publisher class in order to subscribe to its events.</span></span>  
  
    ```csharp
    publisher.RaiseCustomEvent += HandleCustomEvent;  
    ```  
  
     <span data-ttu-id="1a2f7-120">Si noti che la sintassi precedente è nuova in C# 2.0.</span><span class="sxs-lookup"><span data-stu-id="1a2f7-120">Note that the previous syntax is new in C# 2.0.</span></span> <span data-ttu-id="1a2f7-121">Equivale esattamente alla sintassi di C# 1.0, in cui è necessario creare in modo esplicito il delegato incapsulante tramite la parola chiave `new`:</span><span class="sxs-lookup"><span data-stu-id="1a2f7-121">It is exactly equivalent to the C# 1.0 syntax in which the encapsulating delegate must be explicitly created by using the `new` keyword:</span></span>  
  
    ```csharp
    publisher.RaiseCustomEvent += new CustomEventHandler(HandleCustomEvent);  
    ```  
  
     <span data-ttu-id="1a2f7-122">È anche possibile usare un'[espressione lambda](../statements-expressions-operators/lambda-expressions.md) per specificare un gestore eventi:</span><span class="sxs-lookup"><span data-stu-id="1a2f7-122">You also can use a [lambda expression](../statements-expressions-operators/lambda-expressions.md) to specify an event handler:</span></span>
  
    ```csharp
    public Form1()  
    {  
        InitializeComponent();  
        this.Click += (s,e) =>
            {
                MessageBox.Show(((MouseEventArgs)e).Location.ToString());
            };
    }  
    ```  
  
### <a name="to-subscribe-to-events-by-using-an-anonymous-method"></a><span data-ttu-id="1a2f7-123">Per sottoscrivere gli eventi usando un metodo anonimo</span><span class="sxs-lookup"><span data-stu-id="1a2f7-123">To subscribe to events by using an anonymous method</span></span>  
  
- <span data-ttu-id="1a2f7-124">Se non è necessario annullare la sottoscrizione di un evento in un secondo momento, è possibile usare l'operatore di assegnazione di addizione (`+=`) per associare un metodo anonimo all'evento.</span><span class="sxs-lookup"><span data-stu-id="1a2f7-124">If you will not have to unsubscribe to an event later, you can use the addition assignment operator (`+=`) to attach an anonymous method to the event.</span></span> <span data-ttu-id="1a2f7-125">Nell'esempio seguente si supponga che a un oggetto denominato `publisher` sia associato un evento denominato `RaiseCustomEvent` e che sia stata definita una classe `CustomEventArgs` con informazioni specializzate sull'evento.</span><span class="sxs-lookup"><span data-stu-id="1a2f7-125">In the following example, assume that an object named `publisher` has an event named `RaiseCustomEvent` and that a `CustomEventArgs` class has also been defined to carry some kind of specialized event information.</span></span> <span data-ttu-id="1a2f7-126">Si noti che per la classe subscriber è necessario un riferimento alla classe `publisher` per sottoscrivere gli eventi corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="1a2f7-126">Note that the subscriber class needs a reference to `publisher` in order to subscribe to its events.</span></span>  
  
    ```csharp
    publisher.RaiseCustomEvent += delegate(object o, CustomEventArgs e)  
    {  
      string s = o.ToString() + " " + e.ToString();  
      Console.WriteLine(s);  
    };  
    ```  
  
     <span data-ttu-id="1a2f7-127">È importante notare che non si può annullare facilmente la sottoscrizione di un evento se per la sottoscrizione è stata usata una funzione anonima.</span><span class="sxs-lookup"><span data-stu-id="1a2f7-127">It is important to notice that you cannot easily unsubscribe from an event if you used an anonymous function to subscribe to it.</span></span> <span data-ttu-id="1a2f7-128">Per annullare la sottoscrizione in questo scenario, è necessario tornare al codice in cui è stato sottoscritto l'evento, archiviare il metodo anonimo in una variabile del delegato e quindi aggiungere il delegato all'evento.</span><span class="sxs-lookup"><span data-stu-id="1a2f7-128">To unsubscribe in this scenario, it is necessary to go back to the code where you subscribe to the event, store the anonymous method in a delegate variable, and then add the delegate to the event.</span></span> <span data-ttu-id="1a2f7-129">In generale è consigliabile non usare funzioni anonime per sottoscrivere eventi se si prevede di dover annullare la sottoscrizione all'evento in un punto successivo nel codice.</span><span class="sxs-lookup"><span data-stu-id="1a2f7-129">In general, we recommend that you do not use anonymous functions to subscribe to events if you will have to unsubscribe from the event at some later point in your code.</span></span> <span data-ttu-id="1a2f7-130">Per altre informazioni sulle funzioni anonime, vedere [Funzioni anonime](../statements-expressions-operators/anonymous-functions.md).</span><span class="sxs-lookup"><span data-stu-id="1a2f7-130">For more information about anonymous functions, see [Anonymous Functions](../statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="unsubscribing"></a><span data-ttu-id="1a2f7-131">Annullamento della sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="1a2f7-131">Unsubscribing</span></span>  
 <span data-ttu-id="1a2f7-132">Per evitare che il gestore eventi venga chiamato al momento della generazione dell'evento, annullare la sottoscrizione all'evento stesso.</span><span class="sxs-lookup"><span data-stu-id="1a2f7-132">To prevent your event handler from being invoked when the event is raised, unsubscribe from the event.</span></span> <span data-ttu-id="1a2f7-133">Per evitare di perdere risorse, è necessario annullare la sottoscrizione agli eventi prima di eliminare un oggetto sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="1a2f7-133">In order to prevent resource leaks, you should unsubscribe from events before you dispose of a subscriber object.</span></span> <span data-ttu-id="1a2f7-134">Finché non si annulla la sottoscrizione di un evento, il delegato multicast sottostante all'evento nell'oggetto publisher contiene un riferimento al delegato che incapsula il gestore eventi del sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="1a2f7-134">Until you unsubscribe from an event, the multicast delegate that underlies the event in the publishing object has a reference to the delegate that encapsulates the subscriber's event handler.</span></span> <span data-ttu-id="1a2f7-135">Finché l'oggetto publisher include tale riferimento, l'oggetto subscriber non verrà eliminato dal processo di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="1a2f7-135">As long as the publishing object holds that reference, garbage collection will not delete your subscriber object.</span></span>  
  
#### <a name="to-unsubscribe-from-an-event"></a><span data-ttu-id="1a2f7-136">Per annullare la sottoscrizione di un evento</span><span class="sxs-lookup"><span data-stu-id="1a2f7-136">To unsubscribe from an event</span></span>  
  
- <span data-ttu-id="1a2f7-137">Usare l'operatore di assegnazione di sottrazione (`-=`):</span><span class="sxs-lookup"><span data-stu-id="1a2f7-137">Use the subtraction assignment operator (`-=`) to unsubscribe from an event:</span></span>  
  
    ```csharp
    publisher.RaiseCustomEvent -= HandleCustomEvent;  
    ```  
  
     <span data-ttu-id="1a2f7-138">Quando tutti i sottoscrittori hanno annullato la sottoscrizione a un evento, l'istanza dell'evento nella classe publisher viene impostata su `null`.</span><span class="sxs-lookup"><span data-stu-id="1a2f7-138">When all subscribers have unsubscribed from an event, the event instance in the publisher class is set to `null`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a2f7-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a2f7-139">See also</span></span>

- [<span data-ttu-id="1a2f7-140">Events</span><span class="sxs-lookup"><span data-stu-id="1a2f7-140">Events</span></span>](./index.md)
- [<span data-ttu-id="1a2f7-141">Evento</span><span class="sxs-lookup"><span data-stu-id="1a2f7-141">event</span></span>](../../language-reference/keywords/event.md)
- [<span data-ttu-id="1a2f7-142">Come pubblicare eventi conformi alle linee guida di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1a2f7-142">How to publish events that conform to .NET Framework Guidelines</span></span>](./how-to-publish-events-that-conform-to-net-framework-guidelines.md)
- [<span data-ttu-id="1a2f7-143">- e - - operatori</span><span class="sxs-lookup"><span data-stu-id="1a2f7-143">- and -= operators</span></span>](../../language-reference/operators/subtraction-operator.md)
- [<span data-ttu-id="1a2f7-144">Operatori + e +=</span><span class="sxs-lookup"><span data-stu-id="1a2f7-144">+ and += operators</span></span>](../../language-reference/operators/addition-operator.md)
