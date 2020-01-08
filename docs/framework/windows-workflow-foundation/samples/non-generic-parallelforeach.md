---
title: ActivityDesigner ParallelForEach non generico
ms.date: 03/30/2017
ms.assetid: de17e7a2-257b-48b3-91a1-860e2e9bf6e6
ms.openlocfilehash: ea7f57b8812dca3dfcb4908730dd788182d50c5c
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347609"
---
# <a name="non-generic-parallelforeach"></a><span data-ttu-id="9cea8-102">ActivityDesigner ParallelForEach non generico</span><span class="sxs-lookup"><span data-stu-id="9cea8-102">Non-generic ParallelForEach</span></span>

<span data-ttu-id="9cea8-103">Nella casella degli strumenti di [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] è disponibile un set di attività del flusso di controllo, inclusa <xref:System.Activities.Statements.ParallelForEach%601> che consente di scorrere le raccolte <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="9cea8-103">[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] ships in its toolbox a set of Control Flow activities, including <xref:System.Activities.Statements.ParallelForEach%601>, which allows iterating through <xref:System.Collections.Generic.IEnumerable%601> collections.</span></span>

<span data-ttu-id="9cea8-104"><xref:System.Activities.Statements.ParallelForEach%601> richiede che la proprietà <xref:System.Activities.Statements.ParallelForEach%601.Values%2A> sia di tipo <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="9cea8-104"><xref:System.Activities.Statements.ParallelForEach%601> requires its <xref:System.Activities.Statements.ParallelForEach%601.Values%2A> property to be of type  <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="9cea8-105">In questo modo, gli utenti non possono scorrere le strutture di dati che implementano l'interfaccia <xref:System.Collections.Generic.IEnumerable%601> (ad esempio l'oggetto <xref:System.Collections.ArrayList>).</span><span class="sxs-lookup"><span data-stu-id="9cea8-105">This precludes users from iterating over data structures that implement <xref:System.Collections.Generic.IEnumerable%601> interface (for example, <xref:System.Collections.ArrayList>).</span></span> <span data-ttu-id="9cea8-106">La versione non generica dell'oggetto <xref:System.Activities.Statements.ParallelForEach%601> supera questo requisito, a discapito di una maggiore complessità della fase di esecuzione per assicurare la compatibilità dei tipi dei valori nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="9cea8-106">The non-generic version of <xref:System.Activities.Statements.ParallelForEach%601> overcomes this requirement, at the expense of more run-time complexity for ensuring the compatibility of the types of the values in the collection.</span></span>

<span data-ttu-id="9cea8-107">In questo esempio viene illustrato come implementare un'attività <xref:System.Activities.Statements.ParallelForEach%601> non generica e la relativa finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="9cea8-107">This sample shows how to implement a non-generic <xref:System.Activities.Statements.ParallelForEach%601> activity and its designer.</span></span> <span data-ttu-id="9cea8-108">Questa attività può essere usata per scorrere l'oggetto <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="9cea8-108">This activity can be used to iterate through <xref:System.Collections.ArrayList>.</span></span>

## <a name="parallelforeach-activity"></a><span data-ttu-id="9cea8-109">Attività ActivityDesigner ParallelForEach</span><span class="sxs-lookup"><span data-stu-id="9cea8-109">ParallelForEach activity</span></span>

<span data-ttu-id="9cea8-110">L' C#istruzione/Visual Basic `foreach` enumera gli elementi di una raccolta, eseguendo un'istruzione incorporata per ogni elemento della raccolta.</span><span class="sxs-lookup"><span data-stu-id="9cea8-110">The C#/Visual Basic `foreach` statement enumerates the elements of a collection, executing an embedded statement for each element of the collection.</span></span> <span data-ttu-id="9cea8-111">Le attività equivalenti di [!INCLUDE[wf1](../../../../includes/wf1-md.md)] sono <xref:System.Activities.Statements.ForEach%601> e <xref:System.Activities.Statements.ParallelForEach%601>.</span><span class="sxs-lookup"><span data-stu-id="9cea8-111">The [!INCLUDE[wf1](../../../../includes/wf1-md.md)] equivalent activities are <xref:System.Activities.Statements.ForEach%601> and <xref:System.Activities.Statements.ParallelForEach%601>.</span></span> <span data-ttu-id="9cea8-112">L'attività <xref:System.Activities.Statements.ForEach%601> contiene un elenco di valori e un corpo.</span><span class="sxs-lookup"><span data-stu-id="9cea8-112">The <xref:System.Activities.Statements.ForEach%601> activity contains a list of values and a body.</span></span> <span data-ttu-id="9cea8-113">In fase di esecuzione, viene scorso l'elenco e il corpo viene eseguito per ogni valore dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="9cea8-113">At runtime, the list is iterated and the body is executed for each value in the list.</span></span>

<span data-ttu-id="9cea8-114">L'oggetto <xref:System.Activities.Statements.ParallelForEach%601> dispone di una proprietà <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> in modo che l'attività <xref:System.Activities.Statements.ParallelForEach%601> possa essere completata in fretta se la valutazione della proprietà <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="9cea8-114"><xref:System.Activities.Statements.ParallelForEach%601> has a <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A>, so that the <xref:System.Activities.Statements.ParallelForEach%601> activity could complete early if the evaluation of the <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> returns `true`.</span></span> <span data-ttu-id="9cea8-115">La proprietà <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> viene valutata al termine di ogni iterazione.</span><span class="sxs-lookup"><span data-stu-id="9cea8-115">The <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> is evaluated after each iteration is completed.</span></span>

<span data-ttu-id="9cea8-116">Nella maggior parte dei casi, la versione generica dell'attività deve essere la soluzione preferita, poiché concerne la maggioranza degli scenari in cui viene usata e fornisce il controllo dei tipi in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="9cea8-116">For most cases, the generic version of the activity should be the preferred solution, because it covers most of the scenarios in which it is used and provides type checking at compile time.</span></span> <span data-ttu-id="9cea8-117">La versione non generica può essere usata per scorrere i tipi che implementano l'interfaccia <xref:System.Collections.IEnumerable> non generica.</span><span class="sxs-lookup"><span data-stu-id="9cea8-117">The non-generic version can be used for iterating through types that implement the non-generic <xref:System.Collections.IEnumerable> interface.</span></span>

## <a name="class-definition"></a><span data-ttu-id="9cea8-118">Definizione di classe</span><span class="sxs-lookup"><span data-stu-id="9cea8-118">Class definition</span></span>

<span data-ttu-id="9cea8-119">Nell'esempio di codice seguente viene illustrata la definizione di un'attività `ParallelForEach` non generica.</span><span class="sxs-lookup"><span data-stu-id="9cea8-119">The following code example shows the definition of a non-generic `ParallelForEach` activity is.</span></span>

```csharp
[ContentProperty("Body")]
public class ParallelForEach : NativeActivity
{
    [RequiredArgument]
    [DefaultValue(null)]
    InArgument<IEnumerable> Values { get; set; }

    [DefaultValue(null)]
    [DependsOn("Values")]
    public Activity<bool> CompletionCondition
    [DefaultValue(null)]
    [DependsOn("CompletionCondition")]
    ActivityAction<object> Body { get; set; }
}
```

<span data-ttu-id="9cea8-120">Corpo (facoltativo) </span><span class="sxs-lookup"><span data-stu-id="9cea8-120">Body (optional)</span></span>\
<span data-ttu-id="9cea8-121">Oggetto <xref:System.Activities.ActivityAction> di tipo <xref:System.Object> eseguito per ogni elemento della raccolta.</span><span class="sxs-lookup"><span data-stu-id="9cea8-121">The <xref:System.Activities.ActivityAction> of type <xref:System.Object>, which is executed for each element in the collection.</span></span> <span data-ttu-id="9cea8-122">Ogni singolo elemento viene passato al corpo tramite la proprietà Argument.</span><span class="sxs-lookup"><span data-stu-id="9cea8-122">Each individual element is passed into the Body through its Argument property.</span></span>

<span data-ttu-id="9cea8-123">Valori (facoltativo) </span><span class="sxs-lookup"><span data-stu-id="9cea8-123">Values (optional)</span></span>\
<span data-ttu-id="9cea8-124">Raccolta di elementi che vengono scorsi.</span><span class="sxs-lookup"><span data-stu-id="9cea8-124">The collection of elements that are iterated over.</span></span> <span data-ttu-id="9cea8-125">In fase di esecuzione si verifica che tutti gli elementi della raccolta siano di tipi compatibili.</span><span class="sxs-lookup"><span data-stu-id="9cea8-125">Ensuring that all elements of the collection are of compatible types is done at run-time.</span></span>

<span data-ttu-id="9cea8-126">CompletionCondition (facoltativo) </span><span class="sxs-lookup"><span data-stu-id="9cea8-126">CompletionCondition (optional)</span></span>\
<span data-ttu-id="9cea8-127">La proprietà <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> viene valutata al termine di qualsiasi iterazione.</span><span class="sxs-lookup"><span data-stu-id="9cea8-127">The <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> property is evaluated after any iteration completes.</span></span> <span data-ttu-id="9cea8-128">Se restituisce `true`, le iterazioni in sospeso pianificate vengono annullate.</span><span class="sxs-lookup"><span data-stu-id="9cea8-128">If it evaluates to `true`, then the scheduled pending iterations are canceled.</span></span> <span data-ttu-id="9cea8-129">Se questa proprietà non è impostata, tutte le attività nella raccolta di rami vengono eseguite fino al completamento.</span><span class="sxs-lookup"><span data-stu-id="9cea8-129">If this property is not set, all activities in the Branches collection execute until completion.</span></span>

## <a name="example-of-using-parallelforeach"></a><span data-ttu-id="9cea8-130">Esempio di uso di ActivityDesigner ParallelForEach</span><span class="sxs-lookup"><span data-stu-id="9cea8-130">Example of using ParallelForEach</span></span>

<span data-ttu-id="9cea8-131">Nel codice seguente viene illustrato come usare l'attività ParallelForEach in un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9cea8-131">The following code demonstrates how to use the ParallelForEach activity in an application.</span></span>

```csharp
string[] names = { "bill", "steve", "ray" };

DelegateInArgument<object> iterationVariable = new DelegateInArgument<object>() { Name = "iterationVariable" };

Activity sampleUsage =
    new ParallelForEach
    {
       Values = new InArgument<IEnumerable>(c=> names),
       Body = new ActivityAction<object>
       {
           Argument = iterationVariable,
           Handler = new WriteLine
           {
               Text = new InArgument<string>(env => string.Format("Hello {0}",                                                               iterationVariable.Get(env)))
           }
       }
   };
```

## <a name="parallelforeach-designer"></a><span data-ttu-id="9cea8-132">ActivityDesigner ParallelForEach designer</span><span class="sxs-lookup"><span data-stu-id="9cea8-132">ParallelForEach designer</span></span>

<span data-ttu-id="9cea8-133">L'aspetto dell'ActivityDesigner per l'esempio è simile a quello della finestra di progettazione fornita per l'attività <xref:System.Activities.Statements.ParallelForEach%601> incorporata.</span><span class="sxs-lookup"><span data-stu-id="9cea8-133">The activity designer for the sample is similar in appearance to the designer provided for the built-in <xref:System.Activities.Statements.ParallelForEach%601> activity.</span></span> <span data-ttu-id="9cea8-134">La finestra di progettazione viene visualizzata nella casella degli strumenti nella categoria **esempi**, **attività non generiche** .</span><span class="sxs-lookup"><span data-stu-id="9cea8-134">The designer appears in the toolbox in the **Samples**, **Non-Generic Activities** category.</span></span> <span data-ttu-id="9cea8-135">La finestra di progettazione è denominata **ParallelForEachWithBodyFactory** nella casella degli strumenti, poiché l'attività espone un <xref:System.Activities.Presentation.IActivityTemplateFactory> nella casella degli strumenti che crea l'attività con una <xref:System.Activities.ActivityAction>configurata correttamente.</span><span class="sxs-lookup"><span data-stu-id="9cea8-135">The designer is named **ParallelForEachWithBodyFactory** in the toolbox, because the activity exposes an <xref:System.Activities.Presentation.IActivityTemplateFactory> in the toolbox that creates the activity with a properly configured <xref:System.Activities.ActivityAction>.</span></span>

```csharp
public sealed class ParallelForEachWithBodyFactory : IActivityTemplateFactory
{
    public Activity Create(DependencyObject target)
    {
        return new Microsoft.Samples.Activities.Statements.ParallelForEach()
        {
            Body = new ActivityAction<object>()
            {
                Argument = new DelegateInArgument<object>()
                {
                    Name = "item"
                }
            }
        };
    }
}
```

## <a name="to-run-the-sample"></a><span data-ttu-id="9cea8-136">Per eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="9cea8-136">To run the sample</span></span>

1. <span data-ttu-id="9cea8-137">Impostare il progetto scelto come progetto di avvio della soluzione.</span><span class="sxs-lookup"><span data-stu-id="9cea8-137">Set the project of your choice as the startup project of the solution.</span></span>

    1. <span data-ttu-id="9cea8-138">**CodeTestClient** illustra come usare l'attività usando il codice.</span><span class="sxs-lookup"><span data-stu-id="9cea8-138">**CodeTestClient** shows how to use the activity using code.</span></span>

    2. <span data-ttu-id="9cea8-139">**DesignerTestClient** Mostra come usare l'attività all'interno della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="9cea8-139">**DesignerTestClient** shows how to use the activity within the designer.</span></span>

2. <span data-ttu-id="9cea8-140">Compilare ed eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="9cea8-140">Build and run the project.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9cea8-141">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="9cea8-141">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9cea8-142">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="9cea8-142">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="9cea8-143">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="9cea8-143">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9cea8-144">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="9cea8-144">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NonGenericParallelForEach`
