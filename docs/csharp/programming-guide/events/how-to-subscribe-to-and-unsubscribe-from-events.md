---
title: 'Procedura: Sottoscrivere e annullare la sottoscrizione di eventi - Guida per programmatori C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- event handlers [C#], creating
- Code Editor, event handlers
- events [C#], creating using the IDE
ms.assetid: 6319f39f-282c-4173-8a62-6c4657cf51cd
ms.openlocfilehash: 4d06899303110d0b06729f2a02c47b9096bec724
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981803"
---
# <a name="how-to-subscribe-to-and-unsubscribe-from-events-c-programming-guide"></a><span data-ttu-id="09da0-102">Procedura: Sottoscrivere e annullare la sottoscrizione di eventi (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="09da0-102">How to: Subscribe to and Unsubscribe from Events (C# Programming Guide)</span></span>
<span data-ttu-id="09da0-103">Si sottoscrive un evento pubblicato da un'altra classe quando si vuole scrivere codice personalizzato che viene chiamato quando viene generato tale evento.</span><span class="sxs-lookup"><span data-stu-id="09da0-103">You subscribe to an event that is published by another class when you want to write custom code that is called when that event is raised.</span></span> <span data-ttu-id="09da0-104">È ad esempio possibile sottoscrivere l'evento `click` di un pulsante perché l'applicazione esegua un'operazione utile quando l'utente fa clic sul pulsante in questione.</span><span class="sxs-lookup"><span data-stu-id="09da0-104">For example, you might subscribe to a button's `click` event in order to make your application do something useful when the user clicks the button.</span></span>  
  
### <a name="to-subscribe-to-events-by-using-the-visual-studio-ide"></a><span data-ttu-id="09da0-105">Per sottoscrivere gli eventi usando l'IDE di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="09da0-105">To subscribe to events by using the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="09da0-106">Se la finestra **Proprietà** non viene visualizzata, nella visualizzazione **Progettazione** fare clic con il pulsante destro del mouse sul modulo o sul controllo per cui si vuole creare un gestore eventi e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="09da0-106">If you cannot see the **Properties** window, in **Design** view, right-click the form or control for which you want to create an event handler, and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="09da0-107">Nella parte superiore della finestra **Proprietà** fare clic sull'icona **Eventi**.</span><span class="sxs-lookup"><span data-stu-id="09da0-107">On top of the **Properties** window, click the **Events** icon.</span></span>  
  
3.  <span data-ttu-id="09da0-108">Fare doppio clic sull'evento che si vuole creare, ad esempio sull'evento `Load`.</span><span class="sxs-lookup"><span data-stu-id="09da0-108">Double-click the event that you want to create, for example the `Load` event.</span></span>  
  
     <span data-ttu-id="09da0-109">Visual C# crea un metodo del gestore eventi vuoto e lo aggiunge al codice.</span><span class="sxs-lookup"><span data-stu-id="09da0-109">Visual C# creates an empty event handler method and adds it to your code.</span></span> <span data-ttu-id="09da0-110">In alternativa, è possibile aggiungere manualmente il codice nella visualizzazione **Codice**.</span><span class="sxs-lookup"><span data-stu-id="09da0-110">Alternatively you can add the code manually in **Code** view.</span></span> <span data-ttu-id="09da0-111">Ad esempio, le righe di codice seguenti dichiarano un metodo del gestore eventi che verrà chiamato quando la classe `Form` genera l'evento `Load`.</span><span class="sxs-lookup"><span data-stu-id="09da0-111">For example, the following lines of code declare an event handler method that will be called when the `Form` class raises the `Load` event.</span></span>  
  
     [!code-csharp[csProgGuideEvents#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#11)]  
  
     <span data-ttu-id="09da0-112">La riga di codice necessaria per sottoscrivere l'evento viene generata automaticamente nel metodo `InitializeComponent` nel file Form1.Designer.cs del progetto.</span><span class="sxs-lookup"><span data-stu-id="09da0-112">The line of code that is required to subscribe to the event is also automatically generated in the `InitializeComponent` method in the Form1.Designer.cs file in your project.</span></span> <span data-ttu-id="09da0-113">La riga ha un aspetto simile a quanto riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="09da0-113">It resembles this:</span></span>  
  
    ```csharp
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
### <a name="to-subscribe-to-events-programmatically"></a><span data-ttu-id="09da0-114">Per sottoscrivere gli eventi a livello di codice</span><span class="sxs-lookup"><span data-stu-id="09da0-114">To subscribe to events programmatically</span></span>  
  
1.  <span data-ttu-id="09da0-115">Definire un metodo del gestore eventi la cui firma corrisponda alla firma del delegato per l'evento.</span><span class="sxs-lookup"><span data-stu-id="09da0-115">Define an event handler method whose signature matches the delegate signature for the event.</span></span> <span data-ttu-id="09da0-116">Se ad esempio l'evento è basato sul tipo di delegato <xref:System.EventHandler>, il codice riportato di seguito rappresenta lo stub del metodo:</span><span class="sxs-lookup"><span data-stu-id="09da0-116">For example, if the event is based on the <xref:System.EventHandler> delegate type, the following code represents the method stub:</span></span>  
  
    ```csharp
    void HandleCustomEvent(object sender, CustomEventArgs a)  
    {  
       // Do something useful here.  
    }  
    ```  
  
2.  <span data-ttu-id="09da0-117">Usare l'operatore di assegnazione di addizione (`+=`) per associare il gestore eventi all'evento.</span><span class="sxs-lookup"><span data-stu-id="09da0-117">Use the addition assignment operator (`+=`) to attach your event handler to the event.</span></span> <span data-ttu-id="09da0-118">Nell'esempio seguente si supponga che a un oggetto denominato `publisher` sia associato un evento denominato `RaiseCustomEvent`.</span><span class="sxs-lookup"><span data-stu-id="09da0-118">In the following example, assume that an object named `publisher` has an event named `RaiseCustomEvent`.</span></span> <span data-ttu-id="09da0-119">Si noti che per la classe subscriber è necessario un riferimento alla classe publisher per sottoscrivere gli eventi corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="09da0-119">Note that the subscriber class needs a reference to the publisher class in order to subscribe to its events.</span></span>  
  
    ```csharp
    publisher.RaiseCustomEvent += HandleCustomEvent;  
    ```  
  
     <span data-ttu-id="09da0-120">Si noti che la sintassi precedente è nuova in C# 2.0.</span><span class="sxs-lookup"><span data-stu-id="09da0-120">Note that the previous syntax is new in C# 2.0.</span></span> <span data-ttu-id="09da0-121">Equivale esattamente alla sintassi di C# 1.0, in cui è necessario creare in modo esplicito il delegato incapsulante tramite la parola chiave `new`:</span><span class="sxs-lookup"><span data-stu-id="09da0-121">It is exactly equivalent to the C# 1.0 syntax in which the encapsulating delegate must be explicitly created by using the `new` keyword:</span></span>  
  
    ```csharp
    publisher.RaiseCustomEvent += new CustomEventHandler(HandleCustomEvent);  
    ```  
  
     <span data-ttu-id="09da0-122">È possibile aggiungere un gestore eventi anche tramite un'espressione lambda:</span><span class="sxs-lookup"><span data-stu-id="09da0-122">An event handler can also be added by using a lambda expression:</span></span>  
  
    ```csharp
    public Form1()  
    {  
        InitializeComponent();  
        // Use a lambda expression to define an event handler.  
        this.Click += (s,e) => { MessageBox.Show(  
           ((MouseEventArgs)e).Location.ToString());};  
    }  
    ```  
  
     <span data-ttu-id="09da0-123">Per altre informazioni, vedere [Procedura: Usare espressioni lambda all'esterno di LINQ](../../../csharp/programming-guide/statements-expressions-operators/how-to-use-lambda-expressions-outside-linq.md).</span><span class="sxs-lookup"><span data-stu-id="09da0-123">For more information, see [How to: Use Lambda Expressions Outside LINQ](../../../csharp/programming-guide/statements-expressions-operators/how-to-use-lambda-expressions-outside-linq.md).</span></span>  
  
### <a name="to-subscribe-to-events-by-using-an-anonymous-method"></a><span data-ttu-id="09da0-124">Per sottoscrivere gli eventi usando un metodo anonimo</span><span class="sxs-lookup"><span data-stu-id="09da0-124">To subscribe to events by using an anonymous method</span></span>  
  
-   <span data-ttu-id="09da0-125">Se non è necessario annullare la sottoscrizione di un evento in un secondo momento, è possibile usare l'operatore di assegnazione di addizione (`+=`) per associare un metodo anonimo all'evento.</span><span class="sxs-lookup"><span data-stu-id="09da0-125">If you will not have to unsubscribe to an event later, you can use the addition assignment operator (`+=`) to attach an anonymous method to the event.</span></span> <span data-ttu-id="09da0-126">Nell'esempio seguente si supponga che a un oggetto denominato `publisher` sia associato un evento denominato `RaiseCustomEvent` e che sia stata definita una classe `CustomEventArgs` con informazioni specializzate sull'evento.</span><span class="sxs-lookup"><span data-stu-id="09da0-126">In the following example, assume that an object named `publisher` has an event named `RaiseCustomEvent` and that a `CustomEventArgs` class has also been defined to carry some kind of specialized event information.</span></span> <span data-ttu-id="09da0-127">Si noti che per la classe subscriber è necessario un riferimento alla classe `publisher` per sottoscrivere gli eventi corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="09da0-127">Note that the subscriber class needs a reference to `publisher` in order to subscribe to its events.</span></span>  
  
    ```csharp
    publisher.RaiseCustomEvent += delegate(object o, CustomEventArgs e)  
    {  
      string s = o.ToString() + " " + e.ToString();  
      Console.WriteLine(s);  
    };  
    ```  
  
     <span data-ttu-id="09da0-128">È importante notare che non si può annullare facilmente la sottoscrizione di un evento se per la sottoscrizione è stata usata una funzione anonima.</span><span class="sxs-lookup"><span data-stu-id="09da0-128">It is important to notice that you cannot easily unsubscribe from an event if you used an anonymous function to subscribe to it.</span></span> <span data-ttu-id="09da0-129">Per annullare la sottoscrizione in questo scenario, è necessario tornare al codice in cui è stato sottoscritto l'evento, archiviare il metodo anonimo in una variabile del delegato e quindi aggiungere il delegato all'evento.</span><span class="sxs-lookup"><span data-stu-id="09da0-129">To unsubscribe in this scenario, it is necessary to go back to the code where you subscribe to the event, store the anonymous method in a delegate variable, and then add the delegate to the event.</span></span> <span data-ttu-id="09da0-130">In generale è consigliabile non usare funzioni anonime per sottoscrivere eventi se si prevede di dover annullare la sottoscrizione all'evento in un punto successivo nel codice.</span><span class="sxs-lookup"><span data-stu-id="09da0-130">In general, we recommend that you do not use anonymous functions to subscribe to events if you will have to unsubscribe from the event at some later point in your code.</span></span> <span data-ttu-id="09da0-131">Per altre informazioni sulle funzioni anonime, vedere [Funzioni anonime](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span><span class="sxs-lookup"><span data-stu-id="09da0-131">For more information about anonymous functions, see [Anonymous Functions](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="unsubscribing"></a><span data-ttu-id="09da0-132">Annullamento della sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="09da0-132">Unsubscribing</span></span>  
 <span data-ttu-id="09da0-133">Per evitare che il gestore eventi venga chiamato al momento della generazione dell'evento, annullare la sottoscrizione all'evento stesso.</span><span class="sxs-lookup"><span data-stu-id="09da0-133">To prevent your event handler from being invoked when the event is raised, unsubscribe from the event.</span></span> <span data-ttu-id="09da0-134">Per evitare di perdere risorse, è necessario annullare la sottoscrizione agli eventi prima di eliminare un oggetto sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="09da0-134">In order to prevent resource leaks, you should unsubscribe from events before you dispose of a subscriber object.</span></span> <span data-ttu-id="09da0-135">Finché non si annulla la sottoscrizione di un evento, il delegato multicast sottostante all'evento nell'oggetto publisher contiene un riferimento al delegato che incapsula il gestore eventi del sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="09da0-135">Until you unsubscribe from an event, the multicast delegate that underlies the event in the publishing object has a reference to the delegate that encapsulates the subscriber's event handler.</span></span> <span data-ttu-id="09da0-136">Finché l'oggetto publisher include tale riferimento, l'oggetto subscriber non verrà eliminato dal processo di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="09da0-136">As long as the publishing object holds that reference, garbage collection will not delete your subscriber object.</span></span>  
  
#### <a name="to-unsubscribe-from-an-event"></a><span data-ttu-id="09da0-137">Per annullare la sottoscrizione di un evento</span><span class="sxs-lookup"><span data-stu-id="09da0-137">To unsubscribe from an event</span></span>  
  
-   <span data-ttu-id="09da0-138">Usare l'operatore di assegnazione di sottrazione (`-=`):</span><span class="sxs-lookup"><span data-stu-id="09da0-138">Use the subtraction assignment operator (`-=`) to unsubscribe from an event:</span></span>  
  
    ```csharp
    publisher.RaiseCustomEvent -= HandleCustomEvent;  
    ```  
  
     <span data-ttu-id="09da0-139">Quando tutti i sottoscrittori hanno annullato la sottoscrizione a un evento, l'istanza dell'evento nella classe publisher viene impostata su `null`.</span><span class="sxs-lookup"><span data-stu-id="09da0-139">When all subscribers have unsubscribed from an event, the event instance in the publisher class is set to `null`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09da0-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09da0-140">See also</span></span>

- [<span data-ttu-id="09da0-141">Eventi</span><span class="sxs-lookup"><span data-stu-id="09da0-141">Events</span></span>](../../../csharp/programming-guide/events/index.md)
- [<span data-ttu-id="09da0-142">event</span><span class="sxs-lookup"><span data-stu-id="09da0-142">event</span></span>](../../../csharp/language-reference/keywords/event.md)
- [<span data-ttu-id="09da0-143">Procedura: Pubblicare eventi conformi alle linee guida di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="09da0-143">How to: Publish Events that Conform to .NET Framework Guidelines</span></span>](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md)
- [<span data-ttu-id="09da0-144">Operatore = (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="09da0-144">-= Operator (C# Reference)</span></span>](../../language-reference/operators/subtraction-assignment-operator.md)
- [<span data-ttu-id="09da0-145">Operatore +=</span><span class="sxs-lookup"><span data-stu-id="09da0-145">+= Operator</span></span>](../../../csharp/language-reference/operators/addition-assignment-operator.md)
