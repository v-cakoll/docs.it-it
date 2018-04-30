---
title: Serializzazione di flussi di lavoro e attività da e verso XAML
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 37685b32-24e3-4d72-88d8-45d5fcc49ec2
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a36b8a6bdf1a024f4ddee91bd937afac516e391f
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2018
---
# <a name="serializing-workflows-and-activities-to-and-from-xaml"></a><span data-ttu-id="4812d-102">Serializzazione di flussi di lavoro e attività da e verso XAML</span><span class="sxs-lookup"><span data-stu-id="4812d-102">Serializing Workflows and Activities to and from XAML</span></span>
<span data-ttu-id="4812d-103">Oltre alla compilazione in tipi contenuti in assembly, le definizioni di flusso di lavoro possono essere serializzate anche in XAML.</span><span class="sxs-lookup"><span data-stu-id="4812d-103">In addition to being compiled into types that are contained in assemblies, workflow definitions can also be serialized to XAML.</span></span> <span data-ttu-id="4812d-104">Queste definizioni serializzate possono essere ricaricate per la modifica o l'ispezione, passate a un sistema di compilazione per la compilazione o caricate e richiamate.</span><span class="sxs-lookup"><span data-stu-id="4812d-104">These serialized definitions can be reloaded for editing or inspection, passed to a build system for compilation, or loaded and invoked.</span></span> <span data-ttu-id="4812d-105">In questo argomento viene fornita una panoramica della serializzazione di definizioni del flusso di lavoro e dell'utilizzo di definizioni del flusso di lavoro XAML.</span><span class="sxs-lookup"><span data-stu-id="4812d-105">This topic provides an overview of serializing workflow definitions and working with XAML workflow definitions.</span></span>  
  
## <a name="working-with-xaml-workflow-definitions"></a><span data-ttu-id="4812d-106">Uso di definizioni del flusso di lavoro XAML</span><span class="sxs-lookup"><span data-stu-id="4812d-106">Working with XAML Workflow Definitions</span></span>  
 <span data-ttu-id="4812d-107">Per creare una definizione di flusso di lavoro per la serializzazione, viene usata la classe <xref:System.Activities.ActivityBuilder>.</span><span class="sxs-lookup"><span data-stu-id="4812d-107">To create a workflow definition for serialization, the <xref:System.Activities.ActivityBuilder> class is used.</span></span> <span data-ttu-id="4812d-108">La creazione di un oggetto <xref:System.Activities.ActivityBuilder> è molto simile alla creazione di <xref:System.Activities.DynamicActivity>.</span><span class="sxs-lookup"><span data-stu-id="4812d-108">Creating an <xref:System.Activities.ActivityBuilder> is very similar to creating a <xref:System.Activities.DynamicActivity>.</span></span> <span data-ttu-id="4812d-109">Vengono specificati gli argomenti desiderati e vengono configurate le attività che costituiscono il comportamento.</span><span class="sxs-lookup"><span data-stu-id="4812d-109">Any desired arguments are specified, and the activities that constitute the behavior are configured.</span></span> <span data-ttu-id="4812d-110">Nell'esempio seguente viene creata un'attività `Add` che accetta due argomenti di input, li somma e restituisce il risultato.</span><span class="sxs-lookup"><span data-stu-id="4812d-110">In the following example, an `Add` activity is created that takes two input arguments, adds them together, and returns the result.</span></span> <span data-ttu-id="4812d-111">Poiché questa attività restituisce un risultato, viene usata la classe <xref:System.Activities.ActivityBuilder%601> generica.</span><span class="sxs-lookup"><span data-stu-id="4812d-111">Because this activity returns a result, the generic <xref:System.Activities.ActivityBuilder%601> class is used.</span></span>  
  
 [!code-csharp[CFX_WorkflowApplicationExample#41](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#41)]  
  
 <span data-ttu-id="4812d-112">Ognuna delle istanze di <xref:System.Activities.DynamicActivityProperty> rappresenta uno degli argomenti di input per il flusso di lavoro e <xref:System.Activities.ActivityBuilder.Implementation%2A> contiene le attività che costituiscono la logica del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="4812d-112">Each of the <xref:System.Activities.DynamicActivityProperty> instances represents one of the input arguments to the workflow, and the <xref:System.Activities.ActivityBuilder.Implementation%2A> contains the activities that make up the logic of the workflow.</span></span> <span data-ttu-id="4812d-113">Si noti che le espressioni r-value in questo esempio sono espressioni di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4812d-113">Note that the r-value expressions in this example are Visual Basic expressions.</span></span> <span data-ttu-id="4812d-114">Le espressioni lambda non sono serializzabili nel formato XAML a meno che non si utilizzi <xref:System.Activities.Expressions.ExpressionServices.Convert%2A>.</span><span class="sxs-lookup"><span data-stu-id="4812d-114">Lambda expressions are not serializable to XAML unless <xref:System.Activities.Expressions.ExpressionServices.Convert%2A> is used.</span></span> <span data-ttu-id="4812d-115">Se i flussi di lavoro serializzati sono progettati per essere aperti o modificati nella finestra di progettazione del flusso di lavoro, dovranno essere usate le espressioni di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4812d-115">If the serialized workflows are intended to be opened or edited in the workflow designer then Visual Basic expressions should be used.</span></span> <span data-ttu-id="4812d-116">Per altre informazioni, vedere [creazione di flussi di lavoro, attività ed espressioni tramite codice imperativo](../../../docs/framework/windows-workflow-foundation/authoring-workflows-activities-and-expressions-using-imperative-code.md).</span><span class="sxs-lookup"><span data-stu-id="4812d-116">For more information, see [Authoring Workflows, Activities, and Expressions Using Imperative Code](../../../docs/framework/windows-workflow-foundation/authoring-workflows-activities-and-expressions-using-imperative-code.md).</span></span>  
  
 <span data-ttu-id="4812d-117">Per serializzare la definizione del flusso di lavoro rappresentata dall'istanza di <xref:System.Activities.ActivityBuilder> in XAML, usare <xref:System.Activities.XamlIntegration.ActivityXamlServices> per creare un oggetto <xref:System.Xaml.XamlWriter>, quindi usare <xref:System.Xaml.XamlServices> per serializzare la definizione del flusso di lavoro tramite <xref:System.Xaml.XamlWriter>.</span><span class="sxs-lookup"><span data-stu-id="4812d-117">To serialize the workflow definition represented by the <xref:System.Activities.ActivityBuilder> instance to XAML, use <xref:System.Activities.XamlIntegration.ActivityXamlServices> to create a <xref:System.Xaml.XamlWriter>, and then use <xref:System.Xaml.XamlServices> to serialize the workflow definition by using the <xref:System.Xaml.XamlWriter>.</span></span> <span data-ttu-id="4812d-118"><xref:System.Activities.XamlIntegration.ActivityXamlServices> contiene metodi per eseguire il mapping delle istanze di <xref:System.Activities.ActivityBuilder> in e da XAML e per caricare i flussi di lavoro XAML e restituire un oggetto <xref:System.Activities.DynamicActivity> che può essere richiamato.</span><span class="sxs-lookup"><span data-stu-id="4812d-118"><xref:System.Activities.XamlIntegration.ActivityXamlServices> has methods to map <xref:System.Activities.ActivityBuilder> instances to and from XAML, and to load XAML workflows and return a <xref:System.Activities.DynamicActivity> that can be invoked.</span></span> <span data-ttu-id="4812d-119">Nell'esempio seguente l'istanza di <xref:System.Activities.ActivityBuilder> dall'esempio precedente viene serializzata in una stringa e inoltre salvata in un file.</span><span class="sxs-lookup"><span data-stu-id="4812d-119">In the following example, the <xref:System.Activities.ActivityBuilder> instance from the previous example is serialized to a string, and also saved to a file.</span></span>  
  
```csharp  
// Serialize the workflow to XAML and store it in a string.  
StringBuilder sb = new StringBuilder();  
StringWriter tw = new StringWriter(sb);  
XamlWriter xw = ActivityXamlServices.CreateBuilderWriter(new XamlXmlWriter(tw, new XamlSchemaContext()));  
XamlServices.Save(xw , ab);  
string serializedAB = sb.ToString();  
  
// Display the XAML to the console.  
Console.WriteLine(serializedAB);  
  
// Serialize the workflow to XAML and save it to a file.  
StreamWriter sw = File.CreateText(@"C:\Workflows\add.xaml");  
XamlWriter xw2 = ActivityXamlServices.CreateBuilderWriter(new XamlXmlWriter(sw, new XamlSchemaContext()));  
XamlServices.Save(xw2, ab);  
sw.Close();  
```  
  
 <span data-ttu-id="4812d-120">L'esempio seguente rappresenta il flusso di lavoro serializzato.</span><span class="sxs-lookup"><span data-stu-id="4812d-120">The following example represents the serialized workflow.</span></span>  
  
```xaml  
<Activity   
  x:TypeArguments="x:Int32"   
  x:Class="Add"   
  xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"   
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <x:Members>  
    <x:Property Name="Operand1" Type="InArgument(x:Int32)" />  
    <x:Property Name="Operand2" Type="InArgument(x:Int32)" />  
  </x:Members>  
  <Sequence>  
    <WriteLine Text="[Operand1.ToString() + " + " + Operand2.ToString()]" />  
    <Assign x:TypeArguments="x:Int32" Value="[Operand1 + Operand2]">  
      <Assign.To>  
        <OutArgument x:TypeArguments="x:Int32">  
          <ArgumentReference x:TypeArguments="x:Int32" ArgumentName="Result" />  
          </OutArgument>  
      </Assign.To>  
    </Assign>  
  </Sequence>  
</Activity>  
```  
  
 <span data-ttu-id="4812d-121">Per caricare un flusso di lavoro serializzato il <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> viene usato il metodo.</span><span class="sxs-lookup"><span data-stu-id="4812d-121">To load a serialized workflow, the <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> method is used.</span></span> <span data-ttu-id="4812d-122">che accetta la definizione di flusso di lavoro serializzata e restituisce un oggetto <xref:System.Activities.DynamicActivity> che rappresenta la definizione di flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="4812d-122">This takes the serialized workflow definition and returns a <xref:System.Activities.DynamicActivity> that represents the workflow definition.</span></span> <span data-ttu-id="4812d-123">Notare che XAML non viene deserializzato fino a che <xref:System.Activities.Activity.CacheMetadata%2A> non viene chiamato nel corpo di <xref:System.Activities.DynamicActivity> durante il processo di convalida.</span><span class="sxs-lookup"><span data-stu-id="4812d-123">Note that the XAML is not deserialized until <xref:System.Activities.Activity.CacheMetadata%2A> is called on the body of the <xref:System.Activities.DynamicActivity> during the validation process.</span></span> <span data-ttu-id="4812d-124">Se la convalida non viene chiamata in modo esplicito, viene quindi eseguita quando viene richiamato il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="4812d-124">If validation is not explicitly called then it is performed when the workflow is invoked.</span></span> <span data-ttu-id="4812d-125">Se la definizione di flusso di lavoro XAML non è valida, verrà generata un'eccezione <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="4812d-125">If the XAML workflow definition is invalid, then an <xref:System.ArgumentException> exception is thrown.</span></span> <span data-ttu-id="4812d-126">Qualsiasi eccezione generata da <xref:System.Activities.Activity.CacheMetadata%2A> usa caratteri di escape dalla chiamata a <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> e deve essere gestite dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="4812d-126">Any exceptions thrown from <xref:System.Activities.Activity.CacheMetadata%2A> escape from the call to <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> and must be handled by the caller.</span></span> <span data-ttu-id="4812d-127">Nell'esempio seguente il flusso di lavoro serializzato dall'esempio precedente viene caricato e richiamato tramite <xref:System.Activities.WorkflowInvoker>.</span><span class="sxs-lookup"><span data-stu-id="4812d-127">In the following example, the serialized workflow from the previous example is loaded and invoked by using <xref:System.Activities.WorkflowInvoker>.</span></span>  
  
 [!code-csharp[CFX_WorkflowApplicationExample#43](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#43)]  
  
 <span data-ttu-id="4812d-128">Quando questo flusso di lavoro viene richiamato, nella console viene visualizzato l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="4812d-128">When this workflow is invoked, the following output is displayed to the console.</span></span>  
  
 <span data-ttu-id="4812d-129">**25 + 15**</span><span class="sxs-lookup"><span data-stu-id="4812d-129">**25 + 15**</span></span>  
<span data-ttu-id="4812d-130">**40**</span><span class="sxs-lookup"><span data-stu-id="4812d-130">**40**</span></span>    
> [!NOTE]
>  <span data-ttu-id="4812d-131">Per ulteriori informazioni sui flussi di lavoro con gli argomenti di input e outpui di chiamata, vedere [utilizzo di WorkflowInvoker e WorkflowApplication](../../../docs/framework/windows-workflow-foundation/using-workflowinvoker-and-workflowapplication.md) e <xref:System.Activities.WorkflowInvoker.Invoke%2A>.</span><span class="sxs-lookup"><span data-stu-id="4812d-131">For more information about invoking workflows with input and output arguments, see [Using WorkflowInvoker and WorkflowApplication](../../../docs/framework/windows-workflow-foundation/using-workflowinvoker-and-workflowapplication.md) and <xref:System.Activities.WorkflowInvoker.Invoke%2A>.</span></span>  
  
 <span data-ttu-id="4812d-132">Se il flusso di lavoro serializzato contiene le espressioni c#, quindi un <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> istanza con relativo <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> proprietà impostata su `true` deve essere passato come parametro a <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType>, in caso contrario un <xref:System.NotSupportedException> verrà generata un'eccezione con un messaggio simile al Dopo: `Expression Activity type 'CSharpValue`1' richiede la compilazione per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4812d-132">If the serialized workflow contains C# expressions, then an <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> instance with its <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> property set to `true` must be passed as a parameter to <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType>, otherwise a <xref:System.NotSupportedException> will be thrown with a message similar to the following: `Expression Activity type 'CSharpValue`1' requires compilation in order to run.</span></span>  <span data-ttu-id="4812d-133">Verificare che il flusso di lavoro è stato compilato.'</span><span class="sxs-lookup"><span data-stu-id="4812d-133">Please ensure that the workflow has been compiled.\`</span></span>  
  
```csharp  
ActivityXamlServicesSettings settings = new ActivityXamlServicesSettings  
{  
    CompileExpressions = true  
};  
  
DynamicActivity<int> wf = ActivityXamlServices.Load(new StringReader(serializedAB), settings) as DynamicActivity<int>;  
```  
  
 <span data-ttu-id="4812d-134">Per altre informazioni, vedere [espressioni c#](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="4812d-134">For more information, see [C# Expressions](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md).</span></span>  
  
 <span data-ttu-id="4812d-135">È anche possibile caricare una definizione di flusso di lavoro serializzato in un <xref:System.Activities.ActivityBuilder> istanza utilizzando il <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.CreateBuilderReader%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="4812d-135">A serialized workflow definition can also be loaded into an <xref:System.Activities.ActivityBuilder> instance by using the <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.CreateBuilderReader%2A> method.</span></span> <span data-ttu-id="4812d-136">Una volte che un flusso di lavoro serializzato è stato caricato in un'istanza di <xref:System.Activities.ActivityBuilder>, può essere controllato e modificato.</span><span class="sxs-lookup"><span data-stu-id="4812d-136">After a serialized workflow is loaded into an <xref:System.Activities.ActivityBuilder> instance it can be inspected and modified.</span></span> <span data-ttu-id="4812d-137">Ciò si rivela utile per gli autori di finestre di progettazione flussi di lavoro personalizzati crea e fornisce un meccanismo per salvare e ricaricare definizioni di flusso di lavoro durante il processo di progettazione.</span><span class="sxs-lookup"><span data-stu-id="4812d-137">This is useful for custom workflow designer authors and provides a mechanism for saving and reloading workflow definitions during the design process.</span></span> <span data-ttu-id="4812d-138">Nell'esempio seguente la definizione di flusso di lavoro serializzato dall'esempio precedente viene caricata e le relative proprietà vengono controllate.</span><span class="sxs-lookup"><span data-stu-id="4812d-138">In the following example, the serialized workflow definition from the previous example is loaded and its properties are inspected.</span></span>  
  
 [!code-csharp[CFX_WorkflowApplicationExample#44](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#44)]
