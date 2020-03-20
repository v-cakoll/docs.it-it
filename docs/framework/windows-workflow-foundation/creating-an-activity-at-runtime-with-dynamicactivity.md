---
title: Creazione di un'attività in fase di esecuzione con DynamicActivity
ms.date: 03/30/2017
ms.assetid: 1af85cc6-912d-449e-90c5-c5db3eca5ace
ms.openlocfilehash: 871108fd09e9127b3f9e06174f05a47c7fd7682c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182987"
---
# <a name="creating-an-activity-at-runtime-with-dynamicactivity"></a><span data-ttu-id="59d80-102">Creazione di un'attività in fase di esecuzione con DynamicActivity</span><span class="sxs-lookup"><span data-stu-id="59d80-102">Creating an Activity at Runtime with DynamicActivity</span></span>
<span data-ttu-id="59d80-103"><xref:System.Activities.DynamicActivity> è una classe sealed concreta con costruttore pubblico.</span><span class="sxs-lookup"><span data-stu-id="59d80-103"><xref:System.Activities.DynamicActivity> is a concrete, sealed class with a public constructor.</span></span> <span data-ttu-id="59d80-104"><xref:System.Activities.DynamicActivity> può essere usata per assemblare la funzionalità di attività in fase di esecuzione tramite un unico DOM di attività.</span><span class="sxs-lookup"><span data-stu-id="59d80-104"><xref:System.Activities.DynamicActivity> can be used to assemble activity functionality at runtime using an activity DOM.</span></span>  
  
## <a name="dynamicactivity-features"></a><span data-ttu-id="59d80-105">Funzionalità DynamicActivity</span><span class="sxs-lookup"><span data-stu-id="59d80-105">DynamicActivity Features</span></span>  
 <span data-ttu-id="59d80-106">La classe <xref:System.Activities.DynamicActivity> dispone dell'accesso alle proprietà, agli argomenti e alle variabili di esecuzione, ma non ai servizi in fase di esecuzione quali la pianificazione di attività figlio o il rilevamento.</span><span class="sxs-lookup"><span data-stu-id="59d80-106"><xref:System.Activities.DynamicActivity> has access to execution properties, arguments and variables, but no access to run-time services such as scheduling child activities or tracking.</span></span>  
  
 <span data-ttu-id="59d80-107">Usando gli oggetti <xref:System.Activities.Argument> del flusso di lavoro è possibile impostare le proprietà di primo livello.</span><span class="sxs-lookup"><span data-stu-id="59d80-107">Top-level properties can be set using workflow <xref:System.Activities.Argument> objects.</span></span> <span data-ttu-id="59d80-108">Nel codice imperativo, questi argomenti vengono creati usando le proprietà CLR in un nuovo tipo.</span><span class="sxs-lookup"><span data-stu-id="59d80-108">In imperative code, these arguments are created using CLR properties on a new type.</span></span> <span data-ttu-id="59d80-109">In XAML, vengono dichiarati usando i tag `x:Class` e `x:Member`.</span><span class="sxs-lookup"><span data-stu-id="59d80-109">In XAML, they are declared using `x:Class` and `x:Member` tags.</span></span>  
  
 <span data-ttu-id="59d80-110">Le attività costruite usando la classe <xref:System.Activities.DynamicActivity> si interfacciano con l'utilità di progettazione tramite l'oggetto <xref:System.ComponentModel.ICustomTypeDescriptor>.</span><span class="sxs-lookup"><span data-stu-id="59d80-110">Activities constructed using <xref:System.Activities.DynamicActivity> interface with the designer using <xref:System.ComponentModel.ICustomTypeDescriptor>.</span></span> <span data-ttu-id="59d80-111">Le attività create nell'utilità di progettazione possono essere caricate usando il metodo <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> in modo dinamico, come dimostrato nella procedura riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="59d80-111">Activities created in the designer can be loaded dynamically using <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A>, as demonstrated in the following procedure.</span></span>  
  
#### <a name="to-create-an-activity-at-runtime-using-imperative-code"></a><span data-ttu-id="59d80-112">Per creare un'attività in fase di esecuzione usando il codice imperativo</span><span class="sxs-lookup"><span data-stu-id="59d80-112">To create an activity at runtime using imperative code</span></span>  
  
1. <span data-ttu-id="59d80-113">OpenVisual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="59d80-113">OpenVisual Studio 2010.</span></span>  
  
2. <span data-ttu-id="59d80-114">Selezionare **File**, **Nuovo**, **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="59d80-114">Select **File**, **New**, **Project**.</span></span> <span data-ttu-id="59d80-115">Selezionare **Flusso di lavoro 4.0** in **Visual C,** nella finestra **Tipi** progetto, quindi selezionare il nodo **v2010.**</span><span class="sxs-lookup"><span data-stu-id="59d80-115">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="59d80-116">Selezionare **Applicazione console flusso di lavoro sequenziale** nella finestra **Modelli.Select** Sequential Workflow Console Application in the Templates window.</span><span class="sxs-lookup"><span data-stu-id="59d80-116">Select **Sequential Workflow Console Application** in the **Templates** window.</span></span> <span data-ttu-id="59d80-117">Assegnare il nome DynamicActivitySample al nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="59d80-117">Name the new project DynamicActivitySample.</span></span>  
  
3. <span data-ttu-id="59d80-118">Fare clic con il pulsante destro del mouse su Workflow1.xaml nel progetto HelloActivity e selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="59d80-118">Right-click Workflow1.xaml in the HelloActivity project and select **Delete**.</span></span>  
  
4. <span data-ttu-id="59d80-119">Aprire Program.cs.</span><span class="sxs-lookup"><span data-stu-id="59d80-119">Open Program.cs.</span></span> <span data-ttu-id="59d80-120">Aggiungere la seguente direttiva all'inizio del file.</span><span class="sxs-lookup"><span data-stu-id="59d80-120">Add the following directive to the top of the file.</span></span>  
  
    ```csharp  
    using System.Collections.Generic;  
    ```  
  
5. <span data-ttu-id="59d80-121">Sostituire il contenuto del metodo `Main` con il codice seguente che crea un'attività <xref:System.Activities.Statements.Sequence> che contiene una singola attività <xref:System.Activities.Statements.WriteLine> e la assegna alla proprietà <xref:System.Activities.DynamicActivity.Implementation%2A> di una nuova attività dinamica.</span><span class="sxs-lookup"><span data-stu-id="59d80-121">Replace the contents of the `Main` method with the following code, which creates a <xref:System.Activities.Statements.Sequence> activity that contains a single <xref:System.Activities.Statements.WriteLine> activity and assigns it to the <xref:System.Activities.DynamicActivity.Implementation%2A> property of a new dynamic activity.</span></span>  
  
    ```csharp  
    //Define the input argument for the activity  
    var textOut = new InArgument<string>();  
    //Create the activity, property, and implementation  
                Activity dynamicWorkflow = new DynamicActivity()  
                {  
                    Properties =
                    {  
                        new DynamicActivityProperty  
                        {  
                            Name = "Text",  
                            Type = typeof(InArgument<String>),  
                            Value = textOut  
                        }  
                    },  
                    Implementation = () => new Sequence()  
                    {  
                        Activities =
                        {  
                            new WriteLine()  
                            {  
                                Text = new InArgument<string>(env => textOut.Get(env))  
                            }  
                        }  
                    }  
                };  
    //Execute the activity with a parameter dictionary  
                WorkflowInvoker.Invoke(dynamicWorkflow, new Dictionary<string, object> { { "Text", "Hello World!" } });  
                Console.ReadLine();  
    ```  
  
6. <span data-ttu-id="59d80-122">Eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="59d80-122">Execute the application.</span></span> <span data-ttu-id="59d80-123">Una finestra della console con il testo "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="59d80-123">A console window with the text "Hello World!"</span></span> <span data-ttu-id="59d80-124">Visualizza.</span><span class="sxs-lookup"><span data-stu-id="59d80-124">displays.</span></span>  
  
#### <a name="to-create-an-activity-at-runtime-using-xaml"></a><span data-ttu-id="59d80-125">Per creare un'attività in fase di esecuzione usando il codice XAML</span><span class="sxs-lookup"><span data-stu-id="59d80-125">To create an activity at runtime using XAML</span></span>  
  
1. <span data-ttu-id="59d80-126">Aprire Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="59d80-126">Open Visual Studio 2010.</span></span>  
  
2. <span data-ttu-id="59d80-127">Selezionare **File**, **Nuovo**, **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="59d80-127">Select **File**, **New**, **Project**.</span></span> <span data-ttu-id="59d80-128">Selezionare **Flusso di lavoro 4.0** in **Visual C,** nella finestra **Tipi** progetto, quindi selezionare il nodo **v2010.**</span><span class="sxs-lookup"><span data-stu-id="59d80-128">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="59d80-129">Selezionare **Applicazione console flusso di lavoro** nella finestra Modelli.Select Workflow Console Application in the **Templates** window.</span><span class="sxs-lookup"><span data-stu-id="59d80-129">Select  **Workflow Console Application** in the **Templates** window.</span></span> <span data-ttu-id="59d80-130">Assegnare il nome DynamicActivitySample al nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="59d80-130">Name the new project DynamicActivitySample.</span></span>  
  
3. <span data-ttu-id="59d80-131">Aprire Workflow1.xaml nel progetto HelloActivity.</span><span class="sxs-lookup"><span data-stu-id="59d80-131">Open Workflow1.xaml in the HelloActivity project.</span></span> <span data-ttu-id="59d80-132">Fare clic sull'opzione **Argomenti** nella parte inferiore della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="59d80-132">Click the **Arguments** option at the bottom of the designer.</span></span> <span data-ttu-id="59d80-133">Creare un nuovo argomento `In` denominato `TextToWrite` di tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="59d80-133">Create a new `In` argument called `TextToWrite` of type `String`.</span></span>  
  
4. <span data-ttu-id="59d80-134">Trascinare un **WriteLine** attività dal **Primitives** sezione della casella degli strumenti nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="59d80-134">Drag a **WriteLine** activity from the **Primitives** section of the toolbox onto the designer surface.</span></span> <span data-ttu-id="59d80-135">Assegnare `TextToWrite` il valore alla proprietà **Text** dell'attività.</span><span class="sxs-lookup"><span data-stu-id="59d80-135">Assign the value `TextToWrite` to the **Text** property of the activity.</span></span>  
  
5. <span data-ttu-id="59d80-136">Aprire Program.cs.</span><span class="sxs-lookup"><span data-stu-id="59d80-136">Open Program.cs.</span></span> <span data-ttu-id="59d80-137">Aggiungere la seguente direttiva all'inizio del file.</span><span class="sxs-lookup"><span data-stu-id="59d80-137">Add the following directive to the top of the file.</span></span>  
  
    ```csharp  
    using System.Activities.XamlIntegration;  
    ```  
  
6. <span data-ttu-id="59d80-138">Sostituire il contenuto del metodo `Main` con il codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="59d80-138">Replace the contents of the `Main` method with the following code.</span></span>  
  
    ```csharp  
    Activity act2 = ActivityXamlServices.Load(@"Workflow1.xaml");  
                    results = WorkflowInvoker.Invoke(act2, new Dictionary<string, object> { { "TextToWrite", "HelloWorld!" } });  
    Console.ReadLine();  
    ```  
  
7. <span data-ttu-id="59d80-139">Eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="59d80-139">Execute the application.</span></span> <span data-ttu-id="59d80-140">Una finestra della console con il testo "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="59d80-140">A console window with the text "Hello World!"</span></span> <span data-ttu-id="59d80-141">Viene visualizzato .</span><span class="sxs-lookup"><span data-stu-id="59d80-141">appears.</span></span>  
  
8. <span data-ttu-id="59d80-142">Fare clic con il pulsante destro del mouse sul file Workflow1.xaml in **Esplora soluzioni** e selezionare **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="59d80-142">Right-click the Workflow1.xaml file in the **Solution Explorer** and select **View Code**.</span></span> <span data-ttu-id="59d80-143">Si noti che la classe di attività viene creata con `x:Class` e la proprietà viene creata con `x:Property`.</span><span class="sxs-lookup"><span data-stu-id="59d80-143">Note that the activity class is created with `x:Class` and the property is created with `x:Property`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59d80-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="59d80-144">See also</span></span>

- [<span data-ttu-id="59d80-145">Creazione di flussi di lavoro, attività ed espressioni tramite codice imperativo</span><span class="sxs-lookup"><span data-stu-id="59d80-145">Authoring Workflows, Activities, and Expressions Using Imperative Code</span></span>](authoring-workflows-activities-and-expressions-using-imperative-code.md)
