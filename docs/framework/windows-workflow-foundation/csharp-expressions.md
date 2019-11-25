---
title: Espressioni C#
ms.date: 03/30/2017
ms.assetid: 29110be7-f4e3-407e-8dbe-78102eb21115
ms.openlocfilehash: d1728758a4f1af76c2d08695a83c0f9acc3dde3e
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2019
ms.locfileid: "74140091"
---
# <a name="c-expressions"></a>Espressioni C#
A partire da .NET Framework 4,5 C# , le espressioni sono supportate in Windows Workflow Foundation (WF). I C# nuovi progetti di flusso di lavoro creati in Visual Studio 2012 destinati C# a .NET Framework 4,5 usano espressioni e Visual Basic i progetti di flusso di lavoro usano espressioni di Visual Basic. È possibile eseguire la migrazione di progetti di flusso di lavoro .NET Framework 4 esistenti che utilizzano espressioni Visual Basic a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] indipendentemente dal linguaggio del progetto e sono supportati. In questo argomento viene fornita una panoramica sulle espressioni C# in [!INCLUDE[wf1](../../../includes/wf1-md.md)].

## <a name="using-c-expressions-in-workflows"></a>Utilizzo delle espressioni C# nei flussi di lavoro

- [Utilizzo C# di espressioni nel Progettazione flussi di lavoro](csharp-expressions.md#WFDesigner)

  - [Compatibilità con le versioni precedenti](csharp-expressions.md#BackwardCompat)

- [Utilizzo C# di espressioni nei flussi di lavoro di codice](csharp-expressions.md#CodeWorkflows)

- [Utilizzo C# di espressioni nei flussi di lavoro XAML](csharp-expressions.md#XamlWorkflows)

  - [XAML compilato](csharp-expressions.md#CompiledXaml)

  - [XAML separato](csharp-expressions.md#LooseXaml)

- [Utilizzo C# di espressioni nei servizi flusso di lavoro xamlx](csharp-expressions.md#WFServices)

### <a name="WFDesigner"></a>Utilizzo C# di espressioni nel Progettazione flussi di lavoro

A partire da .NET Framework 4,5 C# , le espressioni sono supportate in Windows Workflow Foundation (WF). C#i progetti di flusso di lavoro creati in Visual Studio 2012 destinati C# a .NET Framework 4,5 usano espressioni, mentre i progetti di flusso di lavoro Visual Basic usano espressioni di Visual Basic. Per specificare l'espressione C# desiderata, digitarla nella casella **immettere un' C# espressione**. Questa etichetta viene visualizzata nella finestra delle proprietà quando l'attività viene selezionata nella finestra di progettazione o sull'attività in Progettazione flussi di lavoro. Nell'esempio seguente, due attività `WriteLine` sono contenute in `Sequence` all'interno di `NoPersistScope`.

![Screenshot che mostra un'attività Sequence creata automaticamente.](./media/csharp-expressions/auto-surround-sequence-activity.png)

> [!NOTE]
> C#le espressioni sono supportate solo in Visual Studio e non sono supportate nella finestra di progettazione del flusso di lavoro riallocata. Per ulteriori informazioni sulle nuove funzionalità di WF45 supportate nella finestra di progettazione riallocata, vedere [supporto per le nuove funzionalità di Workflow Foundation 4,5 nella progettazione flussi di lavoro riallocata](wf-features-in-the-rehosted-workflow-designer.md).

#### <a name="BackwardCompat"></a>Compatibilità con le versioni precedenti

Sono supportate le espressioni Visual Basic nei C# progetti di flusso di lavoro .NET Framework 4 esistenti di cui è stata eseguita la migrazione a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]. Quando le espressioni Visual Basic vengono visualizzate nella finestra di progettazione del flusso di lavoro, il testo dell'espressione Visual Basic esistente viene sostituito con il **valore impostato in XAML**, a meno che l' C# espressione Visual Basic non sia una sintassi valida. Se l'espressione Visual Basic è una sintassi C# valida, l'espressione viene visualizzata. Per aggiornare le espressioni Visual Basic a C#, è possibile modificarle nella finestra di progettazione del flusso di lavoro e specificare l'espressione C# equivalente. Non è obbligatorio aggiornare le espressioni Visual Basic a C#, ma una volta che le espressioni vengono aggiornate nella finestra di progettazione del flusso di lavoro, vengono convertite in C# e non possono essere ripristinate in Visual Basic.

### <a name="CodeWorkflows"></a>Utilizzo C# di espressioni nei flussi di lavoro di codice

Le espressioni C# sono supportate nei flussi di lavoro basati sul codice di [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], ma prima di poter richiamare il flusso di lavoro, le espressioni C# devono essere compilate usando <xref:System.Activities.XamlIntegration.TextExpressionCompiler.Compile%2A?displayProperty=nameWithType>. Gli autori di flusso di lavoro possono usare `CSharpValue` per rappresentare l'elemento r-value di un'espressione e `CSharpReference` per rappresentare l'elemento l-value di un'espressione. Nell'esempio seguente viene creato un flusso di lavoro costituito da un'attività `Assign` e da un'attività `WriteLine` contenuta in un'attività `Sequence`. `CSharpReference` viene specificato per l'argomento di `To` di `Assign` e rappresenta l'elemento l-value dell'espressione. `CSharpValue` viene specificato per l'argomento `Value` di `Assign` e per l'argomento `Text` di `WriteLine` e rappresenta l'elemento r-value delle due espressioni.

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

Dopo aver costruito il flusso di lavoro, le espressioni C# vengono compilate chiamando il metodo di supporto `CompileExpressions`, quindi viene richiamato il flusso di lavoro. Nell'esempio seguente viene indicato il metodo `CompileExpressions`:

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
> Se le C# espressioni non vengono compilate, viene generata un'<xref:System.NotSupportedException> quando il flusso di lavoro viene richiamato con un messaggio simile al seguente: `Expression Activity type 'CSharpValue`1' richiede la compilazione per l'esecuzione.  Verificare che il flusso di lavoro sia stato compilato.

Se il flusso di lavoro basato sul codice personalizzato usa `DynamicActivity`, sono richieste alcune modifiche al metodo `CompileExpressions`, come illustrato nell'esempio di codice riportato di seguito.

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

Esistono numerose differenze nell'overload di `CompileExpressions` che compila le espressioni C# in un'attività dinamica.

- Il parametro per `CompileExpressions` è `DynamicActivity`.

- Il nome del tipo e lo spazio dei nomi vengono recuperati usando la proprietà `DynamicActivity.Name`.

- `TextExpressionCompilerSettings.ForImplementation` è impostato su `true`.

- `CompiledExpressionInvoker.SetCompiledExpressionRootForImplementation` viene chiamato al posto di `CompiledExpressionInvoker.SetCompiledExpressionRoot`.

Per ulteriori informazioni sull'utilizzo di espressioni nel codice, vedere [creazione di flussi di lavoro, attività ed espressioni tramite codice imperativo](authoring-workflows-activities-and-expressions-using-imperative-code.md).

### <a name="XamlWorkflows"></a>Utilizzo C# di espressioni nei flussi di lavoro XAML

Le espressioni C# sono supportate nei flussi di lavoro XAML. I flussi di lavoro XAML compilato vengono compilati in un tipo e i flussi di lavoro XAML separato vengono caricati dal runtime e compilati in un albero delle attività quando il flusso di lavoro viene eseguito.

- [XAML compilato](csharp-expressions.md#CompiledXaml)

- [XAML separato](csharp-expressions.md#LooseXaml)

#### <a name="CompiledXaml"></a>XAML compilato

Le espressioni C# sono supportate nei flussi di lavoro XAML compilato che vengono compilati in un tipo come parte di un progetto di flusso di lavoro C# destinato a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]. XAML compilato è il tipo predefinito di creazione del flusso di lavoro in Visual Studio C# e i progetti di flusso di lavoro creati in Visual C# studio che hanno come destinazione [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] usare espressioni.

#### <a name="LooseXaml"></a>XAML separato

Le espressioni C# sono supportate nei flussi di lavoro XAML separato. Il programma host del flusso di lavoro che carica e richiama il flusso di lavoro XAML separato deve essere destinato a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] e <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> deve essere impostato su `true` (l'impostazione predefinita è `false`). Per impostare <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> su `true`, creare un'istanza di <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> con la relativa proprietà <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> impostata su `true` e passarla come parametro a <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType>. Se `CompileExpressions` non è impostato su `true`, verrà generata un'<xref:System.NotSupportedException> con un messaggio simile al seguente: `Expression Activity type 'CSharpValue`1' richiede la compilazione per poter essere eseguita.  Verificare che il flusso di lavoro sia stato compilato.

```csharp
ActivityXamlServicesSettings settings = new ActivityXamlServicesSettings
{
    CompileExpressions = true
};

DynamicActivity<int> wf = ActivityXamlServices.Load(new StringReader(serializedAB), settings) as DynamicActivity<int>;
```

Per ulteriori informazioni sull'utilizzo dei flussi di lavoro XAML, vedere [serializzazione di flussi di lavoro e attività da e verso XAML](serializing-workflows-and-activities-to-and-from-xaml.md).

### <a name="WFServices"></a>Utilizzo C# di espressioni nei servizi flusso di lavoro xamlx

Le espressioni C# sono supporte nei servizi flusso di lavoro XAMLX. Quando un servizio flusso di lavoro è ospitato in IIS o WAS non sono necessarie ulteriori attività, ma se il servizio flusso di lavoro XAML è indipendente, è necessario compilare le espressioni C#. Per compilare le C# espressioni in un servizio del flusso di lavoro xamlx indipendente, caricare innanzitutto il file xamlx in un `WorkflowService`, quindi passare l'`Body` della `WorkflowService` al metodo `CompileExpressions` descritto nella sezione [using C# Expressions in code workflows](csharp-expressions.md#CodeWorkflows) . Nell'esempio seguente, viene caricato un servizio flusso di lavoro XAMLX, vengono compilate espressioni C# e quindi viene aperto il servizio flusso di lavoro in attesa di richieste.

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

Se le espressioni C# non sono compilate, l'operazione `Open` viene eseguita, ma il flusso di lavoro non verrà richiamato. Il `CompileExpressions` metodo seguente è lo stesso del metodo della sezione precedente [using C# Expressions in code workflows](csharp-expressions.md#CodeWorkflows) .

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
