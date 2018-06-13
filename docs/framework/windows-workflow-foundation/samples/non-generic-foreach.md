---
title: ForEach non generica
ms.date: 03/30/2017
ms.assetid: 576cd07a-d58d-4536-b514-77bad60bff38
ms.openlocfilehash: c67f6e3c3afb893f7bb5713d64ce2f119eebc157
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33519480"
---
# <a name="non-generic-foreach"></a><span data-ttu-id="c029c-102">ForEach non generica</span><span class="sxs-lookup"><span data-stu-id="c029c-102">Non-Generic ForEach</span></span>
[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]<span data-ttu-id="c029c-103"> viene fornito nella casella degli strumenti un set di attività flusso di controllo, inclusa <xref:System.Activities.Statements.ForEach%601>, che consente di scorrere <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` raccolte.</span><span class="sxs-lookup"><span data-stu-id="c029c-103"> ships in its toolbox a set of Control Flow activities, including <xref:System.Activities.Statements.ForEach%601>, which allows iterating through <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` collections.</span></span>  
  
 <span data-ttu-id="c029c-104"><xref:System.Activities.Statements.ForEach%601> richiede il relativo <xref:System.Activities.Statements.ForEach%601.Values%2A> proprietà sia di tipo <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="c029c-104"><xref:System.Activities.Statements.ForEach%601> requires its <xref:System.Activities.Statements.ForEach%601.Values%2A> property to be of type <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable`.</span></span> <span data-ttu-id="c029c-105">In questo modo gli utenti scorrere le strutture di dati che implementano <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` interfaccia (ad esempio, <xref:System.Collections.ArrayList>).</span><span class="sxs-lookup"><span data-stu-id="c029c-105">This precludes users from iterating over data structures that implement <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` interface (for example, <xref:System.Collections.ArrayList>).</span></span> <span data-ttu-id="c029c-106">La versione non generica dell'oggetto <xref:System.Activities.Statements.ForEach%601> supera questo requisito, a discapito di una maggiore complessità della fase di esecuzione per assicurare la compatibilità dei tipi dei valori nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="c029c-106">The non-generic version of <xref:System.Activities.Statements.ForEach%601> overcomes this requirement, at the expense of more run-time complexity for ensuring the compatibility of the types of the values in the collection.</span></span>  
  
 <span data-ttu-id="c029c-107">In questo esempio viene illustrato come implementare un'attività <xref:System.Activities.Statements.ForEach%601> non generica e la relativa finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="c029c-107">This sample shows how to implement a non-generic <xref:System.Activities.Statements.ForEach%601> activity and its designer.</span></span> <span data-ttu-id="c029c-108">Questa attività può essere usata per scorrere l'oggetto <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="c029c-108">This activity can be used to iterate through <xref:System.Collections.ArrayList>.</span></span>  
  
## <a name="foreach-activity"></a><span data-ttu-id="c029c-109">Attività ForEach</span><span class="sxs-lookup"><span data-stu-id="c029c-109">ForEach Activity</span></span>  
 <span data-ttu-id="c029c-110">L'istruzione `foreach` di C#/VB enumera gli elementi di una raccolta eseguendo un'istruzione incorporata per ogni elemento della raccolta.</span><span class="sxs-lookup"><span data-stu-id="c029c-110">The C#/VB `foreach` statement enumerates the elements of a collection, executing an embedded statement for each element of the collection.</span></span> <span data-ttu-id="c029c-111">Le attività [!INCLUDE[wf1](../../../../includes/wf1-md.md)] equivalenti di `foreach` sono <xref:System.Activities.Statements.ForEach%601> e <xref:System.Activities.Statements.ParallelForEach%601>.</span><span class="sxs-lookup"><span data-stu-id="c029c-111">The [!INCLUDE[wf1](../../../../includes/wf1-md.md)] equivalent activities of `foreach` are <xref:System.Activities.Statements.ForEach%601> and <xref:System.Activities.Statements.ParallelForEach%601>.</span></span> <span data-ttu-id="c029c-112">L'attività <xref:System.Activities.Statements.ForEach%601> contiene un elenco di valori e un corpo.</span><span class="sxs-lookup"><span data-stu-id="c029c-112">The <xref:System.Activities.Statements.ForEach%601> activity contains a list of values and a body.</span></span> <span data-ttu-id="c029c-113">In fase di esecuzione, viene scorso l'elenco e il corpo viene eseguito per ogni valore dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="c029c-113">At runtime, the list is iterated and the body is executed for each value in the list.</span></span>  
  
 <span data-ttu-id="c029c-114">Nella maggior parte dei casi, la versione generica dell'attività deve essere la soluzione preferita, poiché concerne la maggioranza degli scenari in cui verrà usata e fornisce il controllo dei tipi in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="c029c-114">For most cases, the generic version of the activity should be the preferred solution, because it covers most of the scenarios in which it would be used, and provides type checking at compile time.</span></span> <span data-ttu-id="c029c-115">La versione non generica può essere usata per scorrere i tipi che implementano l'interfaccia <xref:System.Collections.IEnumerable> non generica.</span><span class="sxs-lookup"><span data-stu-id="c029c-115">The non-generic version can be used for iterating through types that implement the non-generic <xref:System.Collections.IEnumerable> interface.</span></span>  
  
## <a name="class-definition"></a><span data-ttu-id="c029c-116">Definizione della classe</span><span class="sxs-lookup"><span data-stu-id="c029c-116">Class Definition</span></span>  
 <span data-ttu-id="c029c-117">Nell'esempio di codice seguente viene illustrata la definizione di un'attività `ForEach` non generica.</span><span class="sxs-lookup"><span data-stu-id="c029c-117">The following code example shows the definition of a non-generic `ForEach` activity.</span></span>  
  
```  
[ContentProperty("Body")]  
public class ForEach : NativeActivity  
{  
    [RequiredArgument]  
    [DefaultValue(null)]  
    InArgument<IEnumerable> Values { get; set; }  
  
    [DefaultValue(null)]  
    [DependsOn("Values")]  
    ActivityAction<object> Body { get; set; }   
}  
```  
  
 <span data-ttu-id="c029c-118">Body (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="c029c-118">Body (optional)</span></span>  
 <span data-ttu-id="c029c-119">Oggetto <xref:System.Activities.ActivityAction> di tipo <xref:System.Object> eseguito per ogni elemento della raccolta.</span><span class="sxs-lookup"><span data-stu-id="c029c-119">The <xref:System.Activities.ActivityAction> of type <xref:System.Object>, which is executed for each element in the collection.</span></span> <span data-ttu-id="c029c-120">Ogni singolo elemento viene passato al corpo tramite la proprietà `Argument`.</span><span class="sxs-lookup"><span data-stu-id="c029c-120">Each individual element is passed into the Body through its `Argument` property.</span></span>  
  
 <span data-ttu-id="c029c-121">Values (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="c029c-121">Values (optional)</span></span>  
 <span data-ttu-id="c029c-122">Raccolta di elementi che vengono scorsi.</span><span class="sxs-lookup"><span data-stu-id="c029c-122">The collection of elements that are iterated over.</span></span> <span data-ttu-id="c029c-123">In fase di esecuzione si verifica che tutti gli elementi della raccolta siano di tipi compatibili.</span><span class="sxs-lookup"><span data-stu-id="c029c-123">Ensuring that all elements of the collection are of compatible types is done at run-time.</span></span>  
  
## <a name="example-of-using-foreach"></a><span data-ttu-id="c029c-124">Esempio di utilizzo di ForEach</span><span class="sxs-lookup"><span data-stu-id="c029c-124">Example of Using ForEach</span></span>  
 <span data-ttu-id="c029c-125">Nel codice seguente viene illustrato come usare l'attività ForEach in un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c029c-125">The following code demonstrates how to use the ForEach activity in an application.</span></span>  
  
```  
string[] names = { "bill", "steve", "ray" };  
  
DelegateInArgument<object> iterationVariable = new DelegateInArgument<object>() { Name = "iterationVariable" };  
  
Activity sampleUsage =  
    new ForEach  
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
  
|<span data-ttu-id="c029c-126">Condizione</span><span class="sxs-lookup"><span data-stu-id="c029c-126">Condition</span></span>|<span data-ttu-id="c029c-127">Messaggio</span><span class="sxs-lookup"><span data-stu-id="c029c-127">Message</span></span>|<span data-ttu-id="c029c-128">Gravità</span><span class="sxs-lookup"><span data-stu-id="c029c-128">Severity</span></span>|<span data-ttu-id="c029c-129">Tipo di eccezione</span><span class="sxs-lookup"><span data-stu-id="c029c-129">Exception Type</span></span>|  
|---------------|-------------|--------------|--------------------|  
|<span data-ttu-id="c029c-130">I valori sono `null`</span><span class="sxs-lookup"><span data-stu-id="c029c-130">Values is `null`</span></span>|<span data-ttu-id="c029c-131">Valore non specificato per un argomento di attività 'Values' obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c029c-131">Value for a required activity argument 'Values' was not supplied.</span></span>|<span data-ttu-id="c029c-132">Errore</span><span class="sxs-lookup"><span data-stu-id="c029c-132">Error</span></span>|<xref:System.InvalidOperationException>|  
  
## <a name="foreach-designer"></a><span data-ttu-id="c029c-133">Finestra di progettazione ForEach</span><span class="sxs-lookup"><span data-stu-id="c029c-133">ForEach Designer</span></span>  
 <span data-ttu-id="c029c-134">L'aspetto dell'ActivityDesigner per l'esempio è simile a quello della finestra di progettazione fornita per l'attività <xref:System.Activities.Statements.ForEach%601> incorporata.</span><span class="sxs-lookup"><span data-stu-id="c029c-134">The activity designer for the sample is similar in appearance to the designer provided for the built-in <xref:System.Activities.Statements.ForEach%601> activity.</span></span> <span data-ttu-id="c029c-135">Verrà visualizzata la finestra di progettazione nella casella degli strumenti di **esempi**, **attività Non generiche** categoria.</span><span class="sxs-lookup"><span data-stu-id="c029c-135">The designer appears in the toolbox in the **Samples**, **Non-Generic Activities** category.</span></span> <span data-ttu-id="c029c-136">La finestra di progettazione è denominata **ForEachWithBodyFactory** nella casella degli strumenti, poiché l'attività espone un <xref:System.Activities.Presentation.IActivityTemplateFactory> nella casella degli strumenti, che crea l'attività con configurato correttamente <xref:System.Activities.ActivityAction>.</span><span class="sxs-lookup"><span data-stu-id="c029c-136">The designer is named **ForEachWithBodyFactory** in the toolbox, because the activity exposes an <xref:System.Activities.Presentation.IActivityTemplateFactory> in the toolbox, which creates the activity with a properly configured <xref:System.Activities.ActivityAction>.</span></span>  
  
```  
public sealed class ForEachWithBodyFactory : IActivityTemplateFactory  
{  
    public Activity Create(DependencyObject target)  
    {  
        return new Microsoft.Samples.Activities.Statements.ForEach()  
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
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="c029c-137">Per eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="c029c-137">To run this sample</span></span>  
  
1.  <span data-ttu-id="c029c-138">Impostare il progetto scelto come progetto di avvio della soluzione:</span><span class="sxs-lookup"><span data-stu-id="c029c-138">Set the project of your choice as the start-up project of the solution:</span></span>  
  
    1.  <span data-ttu-id="c029c-139">**CodeTestClient** viene illustrato come utilizzare l'attività tramite codice.</span><span class="sxs-lookup"><span data-stu-id="c029c-139">**CodeTestClient** shows how to use the activity using code.</span></span>  
  
    2.  <span data-ttu-id="c029c-140">**DesignerTestClient** viene illustrato come utilizzare l'attività all'interno di progettazione.</span><span class="sxs-lookup"><span data-stu-id="c029c-140">**DesignerTestClient** shows how to use the activity within the designer.</span></span>  
  
2.  <span data-ttu-id="c029c-141">Compilare ed eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="c029c-141">Build and run the project.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c029c-142">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="c029c-142">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c029c-143">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="c029c-143">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c029c-144">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="c029c-144">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c029c-145">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="c029c-145">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NonGenericForEach`
