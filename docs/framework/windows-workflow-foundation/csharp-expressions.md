---
title: Espressioni C#
ms.date: 03/30/2017
ms.assetid: 29110be7-f4e3-407e-8dbe-78102eb21115
ms.openlocfilehash: 819f52c345983ca81794b8b1f33b6e2ba96b3922
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/04/2018
ms.locfileid: "48584164"
---
# <a name="c-expressions"></a><span data-ttu-id="84649-102">Espressioni C#</span><span class="sxs-lookup"><span data-stu-id="84649-102">C# Expressions</span></span>
<span data-ttu-id="84649-103">A partire da [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], le espressioni c# sono supportate in Windows Workflow Foundation (WF).</span><span class="sxs-lookup"><span data-stu-id="84649-103">Starting with [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], C# expressions are supported in Windows Workflow Foundation (WF).</span></span> <span data-ttu-id="84649-104">I nuovi progetti di flusso di lavoro c# creati in Visual Studio 2012 che hanno come destinazione [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] usano le espressioni c# e progetti di flusso di lavoro di Visual Basic usano le espressioni Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="84649-104">New C# workflow projects created in Visual Studio 2012 that target [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] use C# expressions, and Visual Basic workflow projects use Visual Basic expressions.</span></span> <span data-ttu-id="84649-105">I progetti di flusso di lavoro [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] esistenti che usano espressioni Visual Basic possono essere migrati a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], indipendentemente dal linguaggio del progetto, e sono supportati.</span><span class="sxs-lookup"><span data-stu-id="84649-105">Existing [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] workflow projects that use Visual Basic expressions can be migrated to [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] regardless of the project language and are supported.</span></span> <span data-ttu-id="84649-106">In questo argomento viene fornita una panoramica sulle espressioni C# in [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="84649-106">This topic provides an overview of C# expressions in [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span></span>

## <a name="using-c-expressions-in-workflows"></a><span data-ttu-id="84649-107">Utilizzo delle espressioni C# nei flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="84649-107">Using C# expressions in workflows</span></span>

-   [<span data-ttu-id="84649-108">Utilizzo delle espressioni c# nella finestra di progettazione del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="84649-108">Using C# expressions in the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md#WFDesigner)

    -   [<span data-ttu-id="84649-109">Con le versioni precedenti la compatibilità</span><span class="sxs-lookup"><span data-stu-id="84649-109">Backwards compatibility</span></span>](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md#BackwardCompat)

-   [<span data-ttu-id="84649-110">Utilizzo delle espressioni c# nei flussi di lavoro di codice</span><span class="sxs-lookup"><span data-stu-id="84649-110">Using C# expressions in code workflows</span></span>](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md#CodeWorkflows)

-   [<span data-ttu-id="84649-111">Utilizzo delle espressioni c# nei flussi di lavoro XAML</span><span class="sxs-lookup"><span data-stu-id="84649-111">Using C# expressions in XAML workflows</span></span>](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md#XamlWorkflows)

    -   [<span data-ttu-id="84649-112">Xaml compilato</span><span class="sxs-lookup"><span data-stu-id="84649-112">Compiled Xaml</span></span>](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md#CompiledXaml)

    -   [<span data-ttu-id="84649-113">Xaml separato</span><span class="sxs-lookup"><span data-stu-id="84649-113">Loose Xaml</span></span>](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md#LooseXaml)

-   [<span data-ttu-id="84649-114">Utilizzo delle espressioni c# nei servizi del flusso di lavoro XAMLX</span><span class="sxs-lookup"><span data-stu-id="84649-114">Using C# expressions in XAMLX workflow services</span></span>](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md#WFServices)

###  <a name="WFDesigner"></a> <span data-ttu-id="84649-115">Utilizzo delle espressioni c# nella finestra di progettazione del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="84649-115">Using C# expressions in the Workflow Designer</span></span>
 <span data-ttu-id="84649-116">A partire da [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], le espressioni c# sono supportate in Windows Workflow Foundation (WF).</span><span class="sxs-lookup"><span data-stu-id="84649-116">Starting with [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], C# expressions are supported in Windows Workflow Foundation (WF).</span></span> <span data-ttu-id="84649-117">Progetti di flusso di lavoro c# creati in Visual Studio 2012 che hanno come destinazione [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] usano le espressioni c# mentre i progetti di flusso di lavoro di Visual Basic usano le espressioni Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="84649-117">C# workflow projects created in Visual Studio 2012 that target [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] use C# expressions, while Visual Basic workflow projects use Visual Basic expressions.</span></span> <span data-ttu-id="84649-118">Per specificare l'espressione c# desiderata, digitarla nella casella **immettere un'espressione c#**.</span><span class="sxs-lookup"><span data-stu-id="84649-118">To specify the desired C# expression, type it into the box labeled **Enter a C# expression**.</span></span> <span data-ttu-id="84649-119">Questa etichetta viene visualizzata nella finestra delle proprietà quando l'attività viene selezionata nella finestra di progettazione o sull'attività in Progettazione flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="84649-119">This label is displayed in the properties window when the activity is selected in the designer, or on the activity in the workflow designer.</span></span> <span data-ttu-id="84649-120">Nell'esempio seguente, due attività `WriteLine` sono contenute in `Sequence` all'interno di `NoPersistScope`.</span><span class="sxs-lookup"><span data-stu-id="84649-120">In the following example, two `WriteLine` activities are contained within a `Sequence` inside a `NoPersistScope`.</span></span>

 <span data-ttu-id="84649-121">![Attività sequence creata automaticamente](../../../docs/framework/windows-workflow-foundation/media/autosurround2.png "AutoSurround2")</span><span class="sxs-lookup"><span data-stu-id="84649-121">![Automatically created sequence activity](../../../docs/framework/windows-workflow-foundation/media/autosurround2.png "AutoSurround2")</span></span>

> [!NOTE]
>  <span data-ttu-id="84649-122">Le espressioni c# sono supportate solo in Visual Studio e non sono supportate nella finestra di progettazione del flusso di lavoro ospitata nuovamente.</span><span class="sxs-lookup"><span data-stu-id="84649-122">C# expressions are supported only in Visual Studio, and are not supported in the re-hosted workflow designer.</span></span> <span data-ttu-id="84649-123">Per altre informazioni sulle nuove funzionalità WF45 supportate nella finestra di progettazione ospitata nuovamente, vedere [supporto per nuove funzionalità di Workflow Foundation 4.5 in Progettazione flussi di lavoro riallocate](../../../docs/framework/windows-workflow-foundation/wf-features-in-the-rehosted-workflow-designer.md).</span><span class="sxs-lookup"><span data-stu-id="84649-123">For more information about new WF45 features supported in the re-hosted designer, see [Support for New Workflow Foundation 4.5 Features in the Rehosted Workflow Designer](../../../docs/framework/windows-workflow-foundation/wf-features-in-the-rehosted-workflow-designer.md).</span></span>

####  <a name="BackwardCompat"></a> <span data-ttu-id="84649-124">Con le versioni precedenti la compatibilità</span><span class="sxs-lookup"><span data-stu-id="84649-124">Backwards compatibility</span></span>
 <span data-ttu-id="84649-125">Sono supportate le espressioni Visual Basic dei progetti di flusso di lavoro C# di [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] esistenti che sono stati migrati a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="84649-125">Visual Basic expressions in existing [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] C# workflow projects that have been migrated to [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] are supported.</span></span> <span data-ttu-id="84649-126">Se le espressioni Visual Basic vengono visualizzate nella finestra di progettazione del flusso di lavoro, il testo dell'espressione Visual Basic esistente viene sostituito con **valore impostato in XAML**, a meno che l'espressione Visual Basic è una sintassi c# valida.</span><span class="sxs-lookup"><span data-stu-id="84649-126">When the Visual Basic expressions are viewed in the workflow designer, the text of the existing Visual Basic expression is replaced with **Value was set in XAML**, unless the Visual Basic expression is valid C# syntax.</span></span> <span data-ttu-id="84649-127">Se l'espressione Visual Basic è una sintassi C# valida, l'espressione viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="84649-127">If the Visual Basic expression is valid C# syntax, then the expression is displayed.</span></span> <span data-ttu-id="84649-128">Per aggiornare le espressioni Visual Basic a C#, è possibile modificarle nella finestra di progettazione del flusso di lavoro e specificare l'espressione C# equivalente.</span><span class="sxs-lookup"><span data-stu-id="84649-128">To update the Visual Basic expressions to C#, you can edit them in the workflow designer and specify the equivalent C# expression.</span></span> <span data-ttu-id="84649-129">Non è obbligatorio aggiornare le espressioni Visual Basic a C#, ma una volta che le espressioni vengono aggiornate nella finestra di progettazione del flusso di lavoro, vengono convertite in C# e non possono essere ripristinate in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="84649-129">It is not required to update the Visual Basic expressions to C#, but once the expressions are updated in the workflow designer they are converted to C# and may not be reverted to Visual Basic.</span></span>

###  <a name="CodeWorkflows"></a> <span data-ttu-id="84649-130">Utilizzo delle espressioni c# nei flussi di lavoro di codice</span><span class="sxs-lookup"><span data-stu-id="84649-130">Using C# expressions in code workflows</span></span>
 <span data-ttu-id="84649-131">Le espressioni C# sono supportate nei flussi di lavoro basati sul codice di [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], ma prima di poter richiamare il flusso di lavoro, le espressioni C# devono essere compilate usando <xref:System.Activities.XamlIntegration.TextExpressionCompiler.Compile%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="84649-131">C# expressions are supported in [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] code based workflows, but before the workflow can be invoked the C# expressions must be compiled using <xref:System.Activities.XamlIntegration.TextExpressionCompiler.Compile%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="84649-132">Gli autori di flusso di lavoro possono usare `CSharpValue` per rappresentare l'elemento r-value di un'espressione e `CSharpReference` per rappresentare l'elemento l-value di un'espressione.</span><span class="sxs-lookup"><span data-stu-id="84649-132">Workflow authors can use `CSharpValue` to represent the r-value of an expression, and `CSharpReference` to represent the l-value of an expression.</span></span> <span data-ttu-id="84649-133">Nell'esempio seguente viene creato un flusso di lavoro costituito da un'attività `Assign` e da un'attività `WriteLine` contenuta in un'attività `Sequence`.</span><span class="sxs-lookup"><span data-stu-id="84649-133">In the following example, a workflow is created with an `Assign` activity and a `WriteLine` activity contained in a `Sequence` activity.</span></span> <span data-ttu-id="84649-134">`CSharpReference` viene specificato per l'argomento di `To` di `Assign` e rappresenta l'elemento l-value dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="84649-134">A `CSharpReference` is specified for the `To` argument of the `Assign`, and represents the l-value of the expression.</span></span> <span data-ttu-id="84649-135">`CSharpValue` viene specificato per l'argomento `Value` di `Assign` e per l'argomento `Text` di `WriteLine` e rappresenta l'elemento r-value delle due espressioni.</span><span class="sxs-lookup"><span data-stu-id="84649-135">A `CSharpValue` is specified for the `Value` argument of the `Assign`, and for the `Text` argument of the `WriteLine`, and represents the r-value for those two expressions.</span></span>

```csharp
Variable<int> n = new Variable<int>
{
    Name = "n"
};

Activity wf = new Sequence
{
    Variables = { n },
    Activities =
    {
        new Assign<int>
        {
            To = new CSharpReference<int>("n"),
            Value = new CSharpValue<int>("new Random().Next(1, 101)")
        },
        new WriteLine
        {
            Text = new CSharpValue<string>("\"The number is \" + n")
        }
    }
};

CompileExpressions(wf);

WorkflowInvoker.Invoke(wf);
```

 <span data-ttu-id="84649-136">Dopo aver costruito il flusso di lavoro, le espressioni C# vengono compilate chiamando il metodo di supporto `CompileExpressions`, quindi viene richiamato il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="84649-136">After the workflow is constructed, the C# expressions are compiled by calling the `CompileExpressions` helper method and then the workflow is invoked.</span></span> <span data-ttu-id="84649-137">Nell'esempio seguente viene indicato il metodo `CompileExpressions`:</span><span class="sxs-lookup"><span data-stu-id="84649-137">The following example is the `CompileExpressions` method.</span></span>

```csharp
static void CompileExpressions(Activity activity)
{
    // activityName is the Namespace.Type of the activity that contains the
    // C# expressions.
    string activityName = activity.GetType().ToString();

    // Split activityName into Namespace and Type.Append _CompiledExpressionRoot to the type name
    // to represent the new type that represents the compiled expressions.
    // Take everything after the last . for the type name.
    string activityType = activityName.Split('.').Last() + "_CompiledExpressionRoot";
    // Take everything before the last . for the namespace.
    string activityNamespace = string.Join(".", activityName.Split('.').Reverse().Skip(1).Reverse());

    // Create a TextExpressionCompilerSettings.
    TextExpressionCompilerSettings settings = new TextExpressionCompilerSettings
    {
        Activity = activity,
        Language = "C#",
        ActivityName = activityType,
        ActivityNamespace = activityNamespace,
        RootNamespace = null,
        GenerateAsPartialClass = false,
        AlwaysGenerateSource = true,
        ForImplementation = false
    };

    // Compile the C# expression.
    TextExpressionCompilerResults results =
        new TextExpressionCompiler(settings).Compile();

    // Any compilation errors are contained in the CompilerMessages.
    if (results.HasErrors)
    {
        throw new Exception("Compilation failed.");
    }

    // Create an instance of the new compiled expression type.
    ICompiledExpressionRoot compiledExpressionRoot =
        Activator.CreateInstance(results.ResultType,
            new object[] { activity }) as ICompiledExpressionRoot;

    // Attach it to the activity.
    CompiledExpressionInvoker.SetCompiledExpressionRoot(
        activity, compiledExpressionRoot);
}
```

> [!NOTE]
>  <span data-ttu-id="84649-138">Se non vengono compilate le espressioni c#, un <xref:System.NotSupportedException> viene generata quando il flusso di lavoro viene richiamato con un messaggio simile al seguente: `Expression Activity type 'CSharpValue`1' richiede la compilazione per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="84649-138">If the C# expressions are not compiled, a <xref:System.NotSupportedException> is thrown when the workflow is invoked with a message similar to the following: `Expression Activity type 'CSharpValue`1' requires compilation in order to run.</span></span>  <span data-ttu-id="84649-139">Assicurarsi che il flusso di lavoro è stata compilata.'</span><span class="sxs-lookup"><span data-stu-id="84649-139">Please ensure that the workflow has been compiled.\`</span></span>

 <span data-ttu-id="84649-140">Se il flusso di lavoro basato sul codice personalizzato usa `DynamicActivity`, sono richieste alcune modifiche al metodo `CompileExpressions`, come illustrato nell'esempio di codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="84649-140">If your custom code based workflow uses `DynamicActivity`, then some changes to the `CompileExpressions` method are required, as demonstrated in the following code example.</span></span>

```csharp
static void CompileExpressions(DynamicActivity dynamicActivity)
{
    // activityName is the Namespace.Type of the activity that contains the
    // C# expressions. For Dynamic Activities this can be retrieved using the
    // name property , which must be in the form Namespace.Type.
    string activityName = dynamicActivity.Name;

    // Split activityName into Namespace and Type.Append _CompiledExpressionRoot to the type name
    // to represent the new type that represents the compiled expressions.
    // Take everything after the last . for the type name.
    string activityType = activityName.Split('.').Last() + "_CompiledExpressionRoot";
    // Take everything before the last . for the namespace.
    string activityNamespace = string.Join(".", activityName.Split('.').Reverse().Skip(1).Reverse());

    // Create a TextExpressionCompilerSettings.
    TextExpressionCompilerSettings settings = new TextExpressionCompilerSettings
    {
        Activity = dynamicActivity,
        Language = "C#",
        ActivityName = activityType,
        ActivityNamespace = activityNamespace,
        RootNamespace = null,
        GenerateAsPartialClass = false,
        AlwaysGenerateSource = true,
        ForImplementation = true
    };

    // Compile the C# expression.
    TextExpressionCompilerResults results =
        new TextExpressionCompiler(settings).Compile();

    // Any compilation errors are contained in the CompilerMessages.
    if (results.HasErrors)
    {
        throw new Exception("Compilation failed.");
    }

    // Create an instance of the new compiled expression type.
    ICompiledExpressionRoot compiledExpressionRoot =
        Activator.CreateInstance(results.ResultType,
            new object[] { dynamicActivity }) as ICompiledExpressionRoot;

    // Attach it to the activity.
    CompiledExpressionInvoker.SetCompiledExpressionRootForImplementation(
        dynamicActivity, compiledExpressionRoot);
}
```

 <span data-ttu-id="84649-141">Esistono numerose differenze nell'overload di `CompileExpressions` che compila le espressioni C# in un'attività dinamica.</span><span class="sxs-lookup"><span data-stu-id="84649-141">There are several differences in the `CompileExpressions` overload that compiles the C# expressions in a dynamic activity.</span></span>

-   <span data-ttu-id="84649-142">Il parametro per `CompileExpressions` è `DynamicActivity`.</span><span class="sxs-lookup"><span data-stu-id="84649-142">The parameter to `CompileExpressions` is a `DynamicActivity`.</span></span>

-   <span data-ttu-id="84649-143">Il nome del tipo e lo spazio dei nomi vengono recuperati usando la proprietà `DynamicActivity.Name`.</span><span class="sxs-lookup"><span data-stu-id="84649-143">The type name and namespace are retrieved using the `DynamicActivity.Name` property.</span></span>

-   <span data-ttu-id="84649-144">`TextExpressionCompilerSettings.ForImplementation` è impostato su `true`.</span><span class="sxs-lookup"><span data-stu-id="84649-144">`TextExpressionCompilerSettings.ForImplementation` is set to `true`.</span></span>

-   <span data-ttu-id="84649-145">`CompiledExpressionInvoker.SetCompiledExpressionRootForImplementation` viene chiamato al posto di `CompiledExpressionInvoker.SetCompiledExpressionRoot`.</span><span class="sxs-lookup"><span data-stu-id="84649-145">`CompiledExpressionInvoker.SetCompiledExpressionRootForImplementation` is called instead of `CompiledExpressionInvoker.SetCompiledExpressionRoot`.</span></span>

 <span data-ttu-id="84649-146">Per altre informazioni sull'utilizzo delle espressioni nel codice, vedere [creazione di flussi di lavoro, attività e le espressioni tramite codice imperativo](../../../docs/framework/windows-workflow-foundation/authoring-workflows-activities-and-expressions-using-imperative-code.md).</span><span class="sxs-lookup"><span data-stu-id="84649-146">For more information about working with expressions in code, see [Authoring Workflows, Activities, and Expressions Using Imperative Code](../../../docs/framework/windows-workflow-foundation/authoring-workflows-activities-and-expressions-using-imperative-code.md).</span></span>

###  <a name="XamlWorkflows"></a> <span data-ttu-id="84649-147">Utilizzo delle espressioni c# nei flussi di lavoro XAML</span><span class="sxs-lookup"><span data-stu-id="84649-147">Using C# expressions in XAML workflows</span></span>
 <span data-ttu-id="84649-148">Le espressioni C# sono supportate nei flussi di lavoro XAML.</span><span class="sxs-lookup"><span data-stu-id="84649-148">C# expressions are supported in XAML workflows.</span></span> <span data-ttu-id="84649-149">I flussi di lavoro XAML compilato vengono compilati in un tipo e i flussi di lavoro XAML separato vengono caricati dal runtime e compilati in un albero delle attività quando il flusso di lavoro viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="84649-149">Compiled XAML workflows are compiled into a type, and loose XAML workflows are loaded by the runtime and compiled into an activity tree when the workflow is executed.</span></span>

-   [<span data-ttu-id="84649-150">Xaml compilato</span><span class="sxs-lookup"><span data-stu-id="84649-150">Compiled Xaml</span></span>](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md#CompiledXaml)

-   [<span data-ttu-id="84649-151">Xaml separato</span><span class="sxs-lookup"><span data-stu-id="84649-151">Loose Xaml</span></span>](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md#LooseXaml)

####  <a name="CompiledXaml"></a> <span data-ttu-id="84649-152">Xaml compilato</span><span class="sxs-lookup"><span data-stu-id="84649-152">Compiled Xaml</span></span>
 <span data-ttu-id="84649-153">Le espressioni C# sono supportate nei flussi di lavoro XAML compilato che vengono compilati in un tipo come parte di un progetto di flusso di lavoro C# destinato a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="84649-153">C# expressions are supported in compiled XAML workflows that are compiled to a type as part of a C# workflow project that targets [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)].</span></span> <span data-ttu-id="84649-154">XAML compilato è il tipo predefinito del flusso di lavoro di creazione in Visual Studio e i progetti di flusso di lavoro c# creati in Visual Studio che hanno come destinazione [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] usano espressioni c#.</span><span class="sxs-lookup"><span data-stu-id="84649-154">Compiled XAML is the default type of workflow authoring in Visual Studio, and C# workflow projects created in Visual Studio that target [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] use C# expressions.</span></span>

####  <a name="LooseXaml"></a> <span data-ttu-id="84649-155">Xaml separato</span><span class="sxs-lookup"><span data-stu-id="84649-155">Loose Xaml</span></span>
 <span data-ttu-id="84649-156">Le espressioni C# sono supportate nei flussi di lavoro XAML separato.</span><span class="sxs-lookup"><span data-stu-id="84649-156">C# expressions are supported in loose XAML workflows.</span></span> <span data-ttu-id="84649-157">Il programma host del flusso di lavoro che carica e richiama il flusso di lavoro XAML separato deve essere destinato a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] e <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> deve essere impostato su `true` (l'impostazione predefinita è `false`).</span><span class="sxs-lookup"><span data-stu-id="84649-157">The workflow host program that loads and invokes the loose XAML workflow must target [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], and <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> must be set to `true` (the default is `false`).</span></span> <span data-ttu-id="84649-158">Per impostare <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> su `true`, creare un'istanza di <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> con la relativa proprietà <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> impostata su `true` e passarla come parametro a <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="84649-158">To set <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> to `true`, create an <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> instance with its <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> property set to `true`, and pass it as a parameter to <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="84649-159">Se `CompileExpressions` non è impostata su `true`, un <xref:System.NotSupportedException> verrà generato con un messaggio simile al seguente: `Expression Activity type 'CSharpValue`1' richiede la compilazione per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="84649-159">If `CompileExpressions` Is not set to `true`, a <xref:System.NotSupportedException> will be thrown with a message similar to the following: `Expression Activity type 'CSharpValue`1' requires compilation in order to run.</span></span>  <span data-ttu-id="84649-160">Assicurarsi che il flusso di lavoro è stata compilata.'</span><span class="sxs-lookup"><span data-stu-id="84649-160">Please ensure that the workflow has been compiled.\`</span></span>

```csharp
ActivityXamlServicesSettings settings = new ActivityXamlServicesSettings
{
    CompileExpressions = true
};

DynamicActivity<int> wf = ActivityXamlServices.Load(new StringReader(serializedAB), settings) as DynamicActivity<int>;
```

 <span data-ttu-id="84649-161">Per altre informazioni sull'utilizzo dei flussi di lavoro XAML, vedere [serializzazione di flussi di lavoro e attività da e verso XAML](../../../docs/framework/windows-workflow-foundation/serializing-workflows-and-activities-to-and-from-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="84649-161">For more information about working with XAML workflows, see [Serializing Workflows and Activities to and from XAML](../../../docs/framework/windows-workflow-foundation/serializing-workflows-and-activities-to-and-from-xaml.md).</span></span>

###  <a name="WFServices"></a> <span data-ttu-id="84649-162">Utilizzo delle espressioni c# nei servizi del flusso di lavoro XAMLX</span><span class="sxs-lookup"><span data-stu-id="84649-162">Using C# expressions in XAMLX workflow services</span></span>
 <span data-ttu-id="84649-163">Le espressioni C# sono supporte nei servizi flusso di lavoro XAMLX.</span><span class="sxs-lookup"><span data-stu-id="84649-163">C# expressions are supported in XAMLX workflow services.</span></span> <span data-ttu-id="84649-164">Quando un servizio flusso di lavoro è ospitato in IIS o WAS non sono necessarie ulteriori attività, ma se il servizio flusso di lavoro XAML è indipendente, è necessario compilare le espressioni C#.</span><span class="sxs-lookup"><span data-stu-id="84649-164">When a workflow service is hosted in IIS or WAS then no additional steps are required, but if the XAML workflow service is self-hosted, then the C# expressions must be compiled.</span></span> <span data-ttu-id="84649-165">Per compilare le espressioni c# in un servizio del flusso di lavoro XAMLX indipendente, innanzitutto caricare il file XAMLX in una `WorkflowService`e quindi passare il `Body` delle `WorkflowService` per il `CompileExpressions` metodo descritto nella precedente [con c# espressioni nei flussi di lavoro di codice](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md#CodeWorkflows) sezione.</span><span class="sxs-lookup"><span data-stu-id="84649-165">To compile the C# expressions in a self-hosted XAMLX workflow service, first load the XAMLX file into a `WorkflowService`, and then pass the `Body` of the `WorkflowService` to the `CompileExpressions` method described in the previous [Using C# expressions in code workflows](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md#CodeWorkflows) section.</span></span> <span data-ttu-id="84649-166">Nell'esempio seguente, viene caricato un servizio flusso di lavoro XAMLX, vengono compilate espressioni C# e quindi viene aperto il servizio flusso di lavoro in attesa di richieste.</span><span class="sxs-lookup"><span data-stu-id="84649-166">In the following example, a XAMLX workflow service is loaded, the C# expressions are compiled, and then the workflow service is opened and waits for requests.</span></span>

```csharp
// Load the XAMLX workflow service.
WorkflowService workflow1 =
    (WorkflowService)XamlServices.Load(xamlxPath);

// Compile the C# expressions in the workflow by passing the Body to CompileExpressions.
CompileExpressions(workflow1.Body);

// Initialize the WorkflowServiceHost.
var host = new WorkflowServiceHost(workflow1, new Uri("http://localhost:8293/Service1.xamlx"));

// Enable Metadata publishing/
ServiceMetadataBehavior smb = new ServiceMetadataBehavior();
smb.HttpGetEnabled = true;
smb.MetadataExporter.PolicyVersion = PolicyVersion.Policy15;
host.Description.Behaviors.Add(smb);

// Open the WorkflowServiceHost and wait for requests.
host.Open();
Console.WriteLine("Press enter to quit");
Console.ReadLine();
```

 <span data-ttu-id="84649-167">Se le espressioni C# non sono compilate, l'operazione `Open` viene eseguita, ma il flusso di lavoro non verrà richiamato.</span><span class="sxs-lookup"><span data-stu-id="84649-167">If the C# expressions are not compiled, the `Open` operation succeeds but the workflow will fail when it is invoked.</span></span> <span data-ttu-id="84649-168">Quanto segue `CompileExpressions` metodo è quello utilizzato per il metodo precedente [espressioni con c# nei flussi di lavoro di codice](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md#CodeWorkflows) sezione.</span><span class="sxs-lookup"><span data-stu-id="84649-168">The following `CompileExpressions` method is the same as the method from the previous [Using C# expressions in code workflows](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md#CodeWorkflows) section.</span></span>

```csharp
static void CompileExpressions(Activity activity)
{
    // activityName is the Namespace.Type of the activity that contains the
    // C# expressions.
    string activityName = activity.GetType().ToString();

    // Split activityName into Namespace and Type.Append _CompiledExpressionRoot to the type name
    // to represent the new type that represents the compiled expressions.
    // Take everything after the last . for the type name.
    string activityType = activityName.Split('.').Last() + "_CompiledExpressionRoot";
    // Take everything before the last . for the namespace.
    string activityNamespace = string.Join(".", activityName.Split('.').Reverse().Skip(1).Reverse());

    // Create a TextExpressionCompilerSettings.
    TextExpressionCompilerSettings settings = new TextExpressionCompilerSettings
    {
        Activity = activity,
        Language = "C#",
        ActivityName = activityType,
        ActivityNamespace = activityNamespace,
        RootNamespace = null,
        GenerateAsPartialClass = false,
        AlwaysGenerateSource = true,
        ForImplementation = false
    };

    // Compile the C# expression.
    TextExpressionCompilerResults results =
        new TextExpressionCompiler(settings).Compile();

    // Any compilation errors are contained in the CompilerMessages.
    if (results.HasErrors)
    {
        throw new Exception("Compilation failed.");
    }

    // Create an instance of the new compiled expression type.
    ICompiledExpressionRoot compiledExpressionRoot =
        Activator.CreateInstance(results.ResultType,
            new object[] { activity }) as ICompiledExpressionRoot;

    // Attach it to the activity.
    CompiledExpressionInvoker.SetCompiledExpressionRoot(
        activity, compiledExpressionRoot);
}
```
