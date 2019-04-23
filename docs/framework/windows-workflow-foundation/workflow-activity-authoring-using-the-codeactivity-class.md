---
title: Creazione di attività del flusso di lavoro tramite la classe CodeActivity
ms.date: 03/30/2017
ms.assetid: cfe315c1-f86d-43ec-b9ce-2f8c469b1106
ms.openlocfilehash: 549acec8b8101312d48bd20e63a4a988b798ff38
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59767396"
---
# <a name="workflow-activity-authoring-using-the-codeactivity-class"></a><span data-ttu-id="b796b-102">Creazione di attività del flusso di lavoro tramite la classe CodeActivity</span><span class="sxs-lookup"><span data-stu-id="b796b-102">Workflow Activity Authoring Using the CodeActivity Class</span></span>
<span data-ttu-id="b796b-103">Le attività create ereditando dall'oggetto <xref:System.Activities.CodeActivity> possono implementare il comportamento imperativo di base eseguendo l'override del metodo <xref:System.Activities.CodeActivity.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="b796b-103">Activities created by inheriting from <xref:System.Activities.CodeActivity> can implement basic imperative behavior by overriding the <xref:System.Activities.CodeActivity.Execute%2A> method.</span></span>

## <a name="using-codeactivitycontext"></a><span data-ttu-id="b796b-104">Uso di CodeActivityContext</span><span class="sxs-lookup"><span data-stu-id="b796b-104">Using CodeActivityContext</span></span>
 <span data-ttu-id="b796b-105">L'accesso a funzionalità dell'esecuzione del flusso di lavoro può essere eseguito dall'interno del metodo <xref:System.Activities.CodeActivity.Execute%2A> tramite i membri del parametro `context`, di tipo <xref:System.Activities.CodeActivityContext>.</span><span class="sxs-lookup"><span data-stu-id="b796b-105">Features of the workflow runtime can be accessed from within the <xref:System.Activities.CodeActivity.Execute%2A> method by using members of the `context` parameter, of type <xref:System.Activities.CodeActivityContext>.</span></span> <span data-ttu-id="b796b-106">Tra le funzionalità disponibili tramite l'oggetto <xref:System.Activities.CodeActivityContext> sono incluse le seguenti:</span><span class="sxs-lookup"><span data-stu-id="b796b-106">The features available through <xref:System.Activities.CodeActivityContext> include the following:</span></span>

-   <span data-ttu-id="b796b-107">Recupero e impostazione di valori di variabili e di argomenti.</span><span class="sxs-lookup"><span data-stu-id="b796b-107">Getting and setting the values of variables and arguments.</span></span>

-   <span data-ttu-id="b796b-108">Funzionalità di rilevamento personalizzate tramite <xref:System.Activities.CodeActivityContext.Track%2A>.</span><span class="sxs-lookup"><span data-stu-id="b796b-108">Custom tracking features using <xref:System.Activities.CodeActivityContext.Track%2A>.</span></span>

-   <span data-ttu-id="b796b-109">Accesso alle proprietà di esecuzione dell'attività tramite il metodo <xref:System.Activities.CodeActivityContext.GetProperty%2A>.</span><span class="sxs-lookup"><span data-stu-id="b796b-109">Access to the activity’s execution properties using <xref:System.Activities.CodeActivityContext.GetProperty%2A>.</span></span>

#### <a name="to-create-a-custom-activity-that-inherits-from-codeactivity"></a><span data-ttu-id="b796b-110">Per creare un'attività personalizzata che eredita da CodeActivity</span><span class="sxs-lookup"><span data-stu-id="b796b-110">To create a custom activity that inherits from CodeActivity</span></span>

1. <span data-ttu-id="b796b-111">Open Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="b796b-111">Open Visual Studio 2010.</span></span>

2. <span data-ttu-id="b796b-112">Selezionare **File**, **nuove**e quindi **progetto**.</span><span class="sxs-lookup"><span data-stu-id="b796b-112">Select **File**, **New**, and then **Project**.</span></span> <span data-ttu-id="b796b-113">Selezionare **Workflow 4.0** sotto **Visual c#** nel **tipi di progetto** finestra e selezionare il **v2010** nodo.</span><span class="sxs-lookup"><span data-stu-id="b796b-113">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="b796b-114">Selezionare **libreria di attività** nel **modelli** finestra.</span><span class="sxs-lookup"><span data-stu-id="b796b-114">Select **Activity Library** in the **Templates** window.</span></span> <span data-ttu-id="b796b-115">Assegnare al nuovo progetto il nome HelloActivity.</span><span class="sxs-lookup"><span data-stu-id="b796b-115">Name the new project HelloActivity.</span></span>

3. <span data-ttu-id="b796b-116">Fare doppio clic su Activity1.xaml nel progetto HelloActivity e selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="b796b-116">Right-click Activity1.xaml in the HelloActivity project and select **Delete**.</span></span>

4. <span data-ttu-id="b796b-117">Pulsante destro del mouse sul progetto HelloActivity e selezionare **Add** e quindi **classe**.</span><span class="sxs-lookup"><span data-stu-id="b796b-117">Right-click the HelloActivity project and select **Add** , and then **Class**.</span></span> <span data-ttu-id="b796b-118">Assegnare alla nuova classe il nome HelloActivity.cs.</span><span class="sxs-lookup"><span data-stu-id="b796b-118">Name the new class HelloActivity.cs.</span></span>

5. <span data-ttu-id="b796b-119">Nel file HelloActivity.cs aggiungere le seguenti istruzioni `using`.</span><span class="sxs-lookup"><span data-stu-id="b796b-119">In the HelloActivity.cs file, add the following `using` directives.</span></span>

    ```csharp
    using System.Activities;
    using System.Activities.Statements;
    ```

6. <span data-ttu-id="b796b-120">Assicurarsi che la nuova classe erediti dall'oggetto <xref:System.Activities.CodeActivity> aggiungendo una classe base alla dichiarazione di classe.</span><span class="sxs-lookup"><span data-stu-id="b796b-120">Make the new class inherit from <xref:System.Activities.CodeActivity> by adding a base class to the class declaration.</span></span>

    ```csharp
    class HelloActivity : CodeActivity
    ```

7. <span data-ttu-id="b796b-121">Aggiungere la funzionalità alla classe aggiungendo un metodo <xref:System.Activities.CodeActivity.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="b796b-121">Add functionality to the class by adding an <xref:System.Activities.CodeActivity.Execute%2A> method.</span></span>

    ```csharp
    protected override void Execute(CodeActivityContext context)
    {
        Console.WriteLine("Hello World!");
    }
    ```

8. <span data-ttu-id="b796b-122">Usare l'oggetto <xref:System.Activities.CodeActivityContext> per creare un record di rilevamento.</span><span class="sxs-lookup"><span data-stu-id="b796b-122">Use the <xref:System.Activities.CodeActivityContext> to create a tracking record.</span></span>

    ```csharp
    protected override void Execute(CodeActivityContext context)
    {
        Console.WriteLine("Hello World!");
        CustomTrackingRecord record = new CustomTrackingRecord("MyRecord");
        record.Data.Add(new KeyValuePair<String, Object>("ExecutionTime", DateTime.Now));
        context.Track(record);
    }
    ```
