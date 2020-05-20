---
title: Creazione di un'attività in fase di esecuzione con DynamicActivity
description: DynamicActivity è una classe concreta e sealed con un costruttore pubblico. Usare la classe per assemblare la funzionalità di attività in fase di esecuzione usando un DOM attività.
ms.date: 03/30/2017
ms.assetid: 1af85cc6-912d-449e-90c5-c5db3eca5ace
ms.openlocfilehash: 17ee14be7df4801018c7afd2e91f1fb07c34e8e1
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421540"
---
# <a name="creating-an-activity-at-runtime-with-dynamicactivity"></a><span data-ttu-id="198b8-104">Creazione di un'attività in fase di esecuzione con DynamicActivity</span><span class="sxs-lookup"><span data-stu-id="198b8-104">Creating an Activity at Runtime with DynamicActivity</span></span>
<span data-ttu-id="198b8-105"><xref:System.Activities.DynamicActivity> è una classe sealed concreta con costruttore pubblico.</span><span class="sxs-lookup"><span data-stu-id="198b8-105"><xref:System.Activities.DynamicActivity> is a concrete, sealed class with a public constructor.</span></span> <span data-ttu-id="198b8-106"><xref:System.Activities.DynamicActivity> può essere usata per assemblare la funzionalità di attività in fase di esecuzione tramite un unico DOM di attività.</span><span class="sxs-lookup"><span data-stu-id="198b8-106"><xref:System.Activities.DynamicActivity> can be used to assemble activity functionality at runtime using an activity DOM.</span></span>  
  
## <a name="dynamicactivity-features"></a><span data-ttu-id="198b8-107">Funzionalità DynamicActivity</span><span class="sxs-lookup"><span data-stu-id="198b8-107">DynamicActivity Features</span></span>  
 <span data-ttu-id="198b8-108">La classe <xref:System.Activities.DynamicActivity> dispone dell'accesso alle proprietà, agli argomenti e alle variabili di esecuzione, ma non ai servizi in fase di esecuzione quali la pianificazione di attività figlio o il rilevamento.</span><span class="sxs-lookup"><span data-stu-id="198b8-108"><xref:System.Activities.DynamicActivity> has access to execution properties, arguments and variables, but no access to run-time services such as scheduling child activities or tracking.</span></span>  
  
 <span data-ttu-id="198b8-109">Usando gli oggetti <xref:System.Activities.Argument> del flusso di lavoro è possibile impostare le proprietà di primo livello.</span><span class="sxs-lookup"><span data-stu-id="198b8-109">Top-level properties can be set using workflow <xref:System.Activities.Argument> objects.</span></span> <span data-ttu-id="198b8-110">Nel codice imperativo, questi argomenti vengono creati usando le proprietà CLR in un nuovo tipo.</span><span class="sxs-lookup"><span data-stu-id="198b8-110">In imperative code, these arguments are created using CLR properties on a new type.</span></span> <span data-ttu-id="198b8-111">In XAML, vengono dichiarati usando i tag `x:Class` e `x:Member`.</span><span class="sxs-lookup"><span data-stu-id="198b8-111">In XAML, they are declared using `x:Class` and `x:Member` tags.</span></span>  
  
 <span data-ttu-id="198b8-112">Le attività costruite usando la classe <xref:System.Activities.DynamicActivity> si interfacciano con l'utilità di progettazione tramite l'oggetto <xref:System.ComponentModel.ICustomTypeDescriptor>.</span><span class="sxs-lookup"><span data-stu-id="198b8-112">Activities constructed using <xref:System.Activities.DynamicActivity> interface with the designer using <xref:System.ComponentModel.ICustomTypeDescriptor>.</span></span> <span data-ttu-id="198b8-113">Le attività create nell'utilità di progettazione possono essere caricate usando il metodo <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> in modo dinamico, come dimostrato nella procedura riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="198b8-113">Activities created in the designer can be loaded dynamically using <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A>, as demonstrated in the following procedure.</span></span>  
  
#### <a name="to-create-an-activity-at-runtime-using-imperative-code"></a><span data-ttu-id="198b8-114">Per creare un'attività in fase di esecuzione usando il codice imperativo</span><span class="sxs-lookup"><span data-stu-id="198b8-114">To create an activity at runtime using imperative code</span></span>  
  
1. <span data-ttu-id="198b8-115">OpenVisual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="198b8-115">OpenVisual Studio 2010.</span></span>  
  
2. <span data-ttu-id="198b8-116">Selezionare **file**, **nuovo**, **progetto**.</span><span class="sxs-lookup"><span data-stu-id="198b8-116">Select **File**, **New**, **Project**.</span></span> <span data-ttu-id="198b8-117">Selezionare **Workflow 4,0** in **Visual C#** nella finestra **Tipi progetto** e selezionare il nodo **v2010** .</span><span class="sxs-lookup"><span data-stu-id="198b8-117">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="198b8-118">Selezionare **applicazione console flusso di lavoro sequenziale** nella finestra **modelli** .</span><span class="sxs-lookup"><span data-stu-id="198b8-118">Select **Sequential Workflow Console Application** in the **Templates** window.</span></span> <span data-ttu-id="198b8-119">Assegnare il nome DynamicActivitySample al nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="198b8-119">Name the new project DynamicActivitySample.</span></span>  
  
3. <span data-ttu-id="198b8-120">Fare clic con il pulsante destro del mouse su Workflow1. XAML nel progetto HelloActivity e selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="198b8-120">Right-click Workflow1.xaml in the HelloActivity project and select **Delete**.</span></span>  
  
4. <span data-ttu-id="198b8-121">Aprire Program.cs.</span><span class="sxs-lookup"><span data-stu-id="198b8-121">Open Program.cs.</span></span> <span data-ttu-id="198b8-122">Aggiungere la seguente direttiva all'inizio del file.</span><span class="sxs-lookup"><span data-stu-id="198b8-122">Add the following directive to the top of the file.</span></span>  
  
    ```csharp  
    using System.Collections.Generic;  
    ```  
  
5. <span data-ttu-id="198b8-123">Sostituire il contenuto del metodo `Main` con il codice seguente che crea un'attività <xref:System.Activities.Statements.Sequence> che contiene una singola attività <xref:System.Activities.Statements.WriteLine> e la assegna alla proprietà <xref:System.Activities.DynamicActivity.Implementation%2A> di una nuova attività dinamica.</span><span class="sxs-lookup"><span data-stu-id="198b8-123">Replace the contents of the `Main` method with the following code, which creates a <xref:System.Activities.Statements.Sequence> activity that contains a single <xref:System.Activities.Statements.WriteLine> activity and assigns it to the <xref:System.Activities.DynamicActivity.Implementation%2A> property of a new dynamic activity.</span></span>  
  
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
  
6. <span data-ttu-id="198b8-124">Eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="198b8-124">Execute the application.</span></span> <span data-ttu-id="198b8-125">Una finestra della console con il testo "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="198b8-125">A console window with the text "Hello World!"</span></span> <span data-ttu-id="198b8-126">Visualizza.</span><span class="sxs-lookup"><span data-stu-id="198b8-126">displays.</span></span>  
  
#### <a name="to-create-an-activity-at-runtime-using-xaml"></a><span data-ttu-id="198b8-127">Per creare un'attività in fase di esecuzione usando il codice XAML</span><span class="sxs-lookup"><span data-stu-id="198b8-127">To create an activity at runtime using XAML</span></span>  
  
1. <span data-ttu-id="198b8-128">Aprire Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="198b8-128">Open Visual Studio 2010.</span></span>  
  
2. <span data-ttu-id="198b8-129">Selezionare **file**, **nuovo**, **progetto**.</span><span class="sxs-lookup"><span data-stu-id="198b8-129">Select **File**, **New**, **Project**.</span></span> <span data-ttu-id="198b8-130">Selezionare **Workflow 4,0** in **Visual C#** nella finestra **Tipi progetto** e selezionare il nodo **v2010** .</span><span class="sxs-lookup"><span data-stu-id="198b8-130">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="198b8-131">Selezionare **applicazione console flusso di lavoro** nella finestra **modelli** .</span><span class="sxs-lookup"><span data-stu-id="198b8-131">Select  **Workflow Console Application** in the **Templates** window.</span></span> <span data-ttu-id="198b8-132">Assegnare il nome DynamicActivitySample al nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="198b8-132">Name the new project DynamicActivitySample.</span></span>  
  
3. <span data-ttu-id="198b8-133">Aprire Workflow1.xaml nel progetto HelloActivity.</span><span class="sxs-lookup"><span data-stu-id="198b8-133">Open Workflow1.xaml in the HelloActivity project.</span></span> <span data-ttu-id="198b8-134">Fare clic sull'opzione **argomenti** nella parte inferiore della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="198b8-134">Click the **Arguments** option at the bottom of the designer.</span></span> <span data-ttu-id="198b8-135">Creare un nuovo argomento `In` denominato `TextToWrite` di tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="198b8-135">Create a new `In` argument called `TextToWrite` of type `String`.</span></span>  
  
4. <span data-ttu-id="198b8-136">Trascinare un'attività **WriteLine** dalla sezione **primitive** della casella degli strumenti nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="198b8-136">Drag a **WriteLine** activity from the **Primitives** section of the toolbox onto the designer surface.</span></span> <span data-ttu-id="198b8-137">Assegnare il valore `TextToWrite` alla proprietà **Text** dell'attività.</span><span class="sxs-lookup"><span data-stu-id="198b8-137">Assign the value `TextToWrite` to the **Text** property of the activity.</span></span>  
  
5. <span data-ttu-id="198b8-138">Aprire Program.cs.</span><span class="sxs-lookup"><span data-stu-id="198b8-138">Open Program.cs.</span></span> <span data-ttu-id="198b8-139">Aggiungere la seguente direttiva all'inizio del file.</span><span class="sxs-lookup"><span data-stu-id="198b8-139">Add the following directive to the top of the file.</span></span>  
  
    ```csharp  
    using System.Activities.XamlIntegration;  
    ```  
  
6. <span data-ttu-id="198b8-140">Sostituire il contenuto del metodo `Main` con il codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="198b8-140">Replace the contents of the `Main` method with the following code.</span></span>  
  
    ```csharp  
    Activity act2 = ActivityXamlServices.Load(@"Workflow1.xaml");  
                    results = WorkflowInvoker.Invoke(act2, new Dictionary<string, object> { { "TextToWrite", "HelloWorld!" } });  
    Console.ReadLine();  
    ```  
  
7. <span data-ttu-id="198b8-141">Eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="198b8-141">Execute the application.</span></span> <span data-ttu-id="198b8-142">Una finestra della console con il testo "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="198b8-142">A console window with the text "Hello World!"</span></span> <span data-ttu-id="198b8-143">Viene visualizzato .</span><span class="sxs-lookup"><span data-stu-id="198b8-143">appears.</span></span>  
  
8. <span data-ttu-id="198b8-144">Fare clic con il pulsante destro del mouse sul file Workflow1. XAML nella **Esplora soluzioni** e selezionare **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="198b8-144">Right-click the Workflow1.xaml file in the **Solution Explorer** and select **View Code**.</span></span> <span data-ttu-id="198b8-145">Si noti che la classe di attività viene creata con `x:Class` e la proprietà viene creata con `x:Property`.</span><span class="sxs-lookup"><span data-stu-id="198b8-145">Note that the activity class is created with `x:Class` and the property is created with `x:Property`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="198b8-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="198b8-146">See also</span></span>

- [<span data-ttu-id="198b8-147">Creazione di flussi di lavoro, attività ed espressioni tramite codice imperativo</span><span class="sxs-lookup"><span data-stu-id="198b8-147">Authoring Workflows, Activities, and Expressions Using Imperative Code</span></span>](authoring-workflows-activities-and-expressions-using-imperative-code.md)
