---
title: Attività ParallelForEach non generica
ms.date: 03/30/2017
ms.assetid: de17e7a2-257b-48b3-91a1-860e2e9bf6e6
ms.openlocfilehash: 0bdaaac04162cf065d847f5071ba21953f042223
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33519389"
---
# <a name="non-generic-parallelforeach"></a><span data-ttu-id="29074-102">Attività ParallelForEach non generica</span><span class="sxs-lookup"><span data-stu-id="29074-102">Non-Generic ParallelForEach</span></span>
[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]<span data-ttu-id="29074-103"> viene fornito nella casella degli strumenti un set di attività flusso di controllo, inclusa <xref:System.Activities.Statements.ParallelForEach%601>, che consente di scorrere <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` raccolte.</span><span class="sxs-lookup"><span data-stu-id="29074-103"> ships in its toolbox a set of Control Flow activities, including <xref:System.Activities.Statements.ParallelForEach%601>, which allows iterating through <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` collections.</span></span>  
  
 <span data-ttu-id="29074-104"><xref:System.Activities.Statements.ParallelForEach%601> richiede il relativo <xref:System.Activities.Statements.ParallelForEach%601.Values%2A> proprietà sia di tipo <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="29074-104"><xref:System.Activities.Statements.ParallelForEach%601> requires its <xref:System.Activities.Statements.ParallelForEach%601.Values%2A> property to be of type <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable`.</span></span> <span data-ttu-id="29074-105">In questo modo gli utenti scorrere le strutture di dati che implementano <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` interfaccia (ad esempio, <xref:System.Collections.ArrayList>).</span><span class="sxs-lookup"><span data-stu-id="29074-105">This precludes users from iterating over data structures that implement <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` interface (for example, <xref:System.Collections.ArrayList>).</span></span> <span data-ttu-id="29074-106">La versione non generica dell'oggetto <xref:System.Activities.Statements.ParallelForEach%601> supera questo requisito, a discapito di una maggiore complessità della fase di esecuzione per assicurare la compatibilità dei tipi dei valori nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="29074-106">The non-generic version of <xref:System.Activities.Statements.ParallelForEach%601> overcomes this requirement, at the expense of more run-time complexity for ensuring the compatibility of the types of the values in the collection.</span></span>  
  
 <span data-ttu-id="29074-107">In questo esempio viene illustrato come implementare un'attività <xref:System.Activities.Statements.ParallelForEach%601> non generica e la relativa finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="29074-107">This sample shows how to implement a non-generic <xref:System.Activities.Statements.ParallelForEach%601> activity and its designer.</span></span> <span data-ttu-id="29074-108">Questa attività può essere usata per scorrere l'oggetto <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="29074-108">This activity can be used to iterate through <xref:System.Collections.ArrayList>.</span></span>  
  
## <a name="parallelforeach-activity"></a><span data-ttu-id="29074-109">Attività ParallelForEach</span><span class="sxs-lookup"><span data-stu-id="29074-109">ParallelForEach Activity</span></span>  
 <span data-ttu-id="29074-110">L'istruzione `foreach` di C#/VB enumera gli elementi di una raccolta eseguendo un'istruzione incorporata per ogni elemento della raccolta.</span><span class="sxs-lookup"><span data-stu-id="29074-110">The C#/VB `foreach` statement enumerates the elements of a collection, executing an embedded statement for each element of the collection.</span></span> <span data-ttu-id="29074-111">Le attività equivalenti di [!INCLUDE[wf1](../../../../includes/wf1-md.md)] sono <xref:System.Activities.Statements.ForEach%601> e <xref:System.Activities.Statements.ParallelForEach%601>.</span><span class="sxs-lookup"><span data-stu-id="29074-111">The [!INCLUDE[wf1](../../../../includes/wf1-md.md)] equivalent activities are <xref:System.Activities.Statements.ForEach%601> and <xref:System.Activities.Statements.ParallelForEach%601>.</span></span> <span data-ttu-id="29074-112">L'attività <xref:System.Activities.Statements.ForEach%601> contiene un elenco di valori e un corpo.</span><span class="sxs-lookup"><span data-stu-id="29074-112">The <xref:System.Activities.Statements.ForEach%601> activity contains a list of values and a body.</span></span> <span data-ttu-id="29074-113">In fase di esecuzione, viene scorso l'elenco e il corpo viene eseguito per ogni valore dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="29074-113">At runtime, the list is iterated and the body is executed for each value in the list.</span></span>  
  
 <span data-ttu-id="29074-114">L'oggetto <xref:System.Activities.Statements.ParallelForEach%601> dispone di una proprietà <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> in modo che l'attività <xref:System.Activities.Statements.ParallelForEach%601> possa essere completata in fretta se la valutazione della proprietà <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="29074-114"><xref:System.Activities.Statements.ParallelForEach%601> has a <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A>, so that the <xref:System.Activities.Statements.ParallelForEach%601> activity could complete early if the evaluation of the <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> returns `true`.</span></span> <span data-ttu-id="29074-115">La proprietà <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> viene valutata al termine di ogni iterazione.</span><span class="sxs-lookup"><span data-stu-id="29074-115">The <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> is evaluated after each iteration is completed.</span></span>  
  
 <span data-ttu-id="29074-116">Nella maggior parte dei casi, la versione generica dell'attività deve essere la soluzione preferita, poiché concerne la maggioranza degli scenari in cui viene usata e fornisce il controllo dei tipi in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="29074-116">For most cases, the generic version of the activity should be the preferred solution, because it covers most of the scenarios in which it is used and provides type checking at compile time.</span></span> <span data-ttu-id="29074-117">La versione non generica può essere usata per scorrere i tipi che implementano l'interfaccia <xref:System.Collections.IEnumerable> non generica.</span><span class="sxs-lookup"><span data-stu-id="29074-117">The non-generic version can be used for iterating through types that implement the non-generic <xref:System.Collections.IEnumerable> interface.</span></span>  
  
## <a name="class-definition"></a><span data-ttu-id="29074-118">Definizione della classe</span><span class="sxs-lookup"><span data-stu-id="29074-118">Class Definition</span></span>  
 <span data-ttu-id="29074-119">Nell'esempio di codice seguente viene illustrata la definizione di un'attività `ParallelForEach` non generica.</span><span class="sxs-lookup"><span data-stu-id="29074-119">The following code example shows the definition of a non-generic `ParallelForEach` activity is.</span></span>  
  
```  
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
  
 <span data-ttu-id="29074-120">Body (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="29074-120">Body (optional)</span></span>  
 <span data-ttu-id="29074-121">Oggetto <xref:System.Activities.ActivityAction> di tipo <xref:System.Object> eseguito per ogni elemento della raccolta.</span><span class="sxs-lookup"><span data-stu-id="29074-121">The <xref:System.Activities.ActivityAction> of type <xref:System.Object>, which is executed for each element in the collection.</span></span> <span data-ttu-id="29074-122">Ogni singolo elemento viene passato al corpo tramite la proprietà Argument.</span><span class="sxs-lookup"><span data-stu-id="29074-122">Each individual element is passed into the Body through its Argument property.</span></span>  
  
 <span data-ttu-id="29074-123">Values (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="29074-123">Values (optional)</span></span>  
 <span data-ttu-id="29074-124">Raccolta di elementi che vengono scorsi.</span><span class="sxs-lookup"><span data-stu-id="29074-124">The collection of elements that are iterated over.</span></span> <span data-ttu-id="29074-125">In fase di esecuzione si verifica che tutti gli elementi della raccolta siano di tipi compatibili.</span><span class="sxs-lookup"><span data-stu-id="29074-125">Ensuring that all elements of the collection are of compatible types is done at run-time.</span></span>  
  
 <span data-ttu-id="29074-126">CompletionCondition (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="29074-126">CompletionCondition (optional)</span></span>  
 <span data-ttu-id="29074-127">La proprietà <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> viene valutata al termine di qualsiasi iterazione.</span><span class="sxs-lookup"><span data-stu-id="29074-127">The <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> property is evaluated after any iteration completes.</span></span> <span data-ttu-id="29074-128">Se restituisce `true`, le iterazioni in sospeso pianificate vengono annullate.</span><span class="sxs-lookup"><span data-stu-id="29074-128">If it evaluates to `true`, then the scheduled pending iterations are canceled.</span></span> <span data-ttu-id="29074-129">Se questa proprietà non è impostata, tutte le attività nella raccolta di rami vengono eseguite fino al completamento.</span><span class="sxs-lookup"><span data-stu-id="29074-129">If this property is not set, all activities in the Branches collection execute until completion.</span></span>  
  
## <a name="example-of-using-parallelforeach"></a><span data-ttu-id="29074-130">Esempio di utilizzo di ParallelForEach</span><span class="sxs-lookup"><span data-stu-id="29074-130">Example of Using ParallelForEach</span></span>  
 <span data-ttu-id="29074-131">Nel codice seguente viene illustrato come usare l'attività ParallelForEach in un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="29074-131">The following code demonstrates how to use the ParallelForEach activity in an application.</span></span>  
  
```  
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
  
## <a name="parallelforeach-designer"></a><span data-ttu-id="29074-132">Finestra di progettazione ParallelForEachT</span><span class="sxs-lookup"><span data-stu-id="29074-132">ParallelForEach Designer</span></span>  
 <span data-ttu-id="29074-133">L'aspetto dell'ActivityDesigner per l'esempio è simile a quello della finestra di progettazione fornita per l'attività <xref:System.Activities.Statements.ParallelForEach%601> incorporata.</span><span class="sxs-lookup"><span data-stu-id="29074-133">The activity designer for the sample is similar in appearance to the designer provided for the built-in <xref:System.Activities.Statements.ParallelForEach%601> activity.</span></span> <span data-ttu-id="29074-134">Verrà visualizzata la finestra di progettazione nella casella degli strumenti di **esempi**, **attività Non generiche** categoria.</span><span class="sxs-lookup"><span data-stu-id="29074-134">The designer appears in the toolbox in the **Samples**, **Non-Generic Activities** category.</span></span> <span data-ttu-id="29074-135">La finestra di progettazione è denominata **ParallelForEachWithBodyFactory** nella casella degli strumenti, poiché l'attività espone un <xref:System.Activities.Presentation.IActivityTemplateFactory> nella casella degli strumenti che crea l'attività con configurato correttamente <xref:System.Activities.ActivityAction>.</span><span class="sxs-lookup"><span data-stu-id="29074-135">The designer is named **ParallelForEachWithBodyFactory** in the toolbox, because the activity exposes an <xref:System.Activities.Presentation.IActivityTemplateFactory> in the toolbox that creates the activity with a properly configured <xref:System.Activities.ActivityAction>.</span></span>  
  
```  
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
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="29074-136">Per eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="29074-136">To run the sample</span></span>  
  
1.  <span data-ttu-id="29074-137">Impostare il progetto scelto come progetto di avvio della soluzione.</span><span class="sxs-lookup"><span data-stu-id="29074-137">Set the project of your choice as the startup project of the solution.</span></span>  
  
    1.  <span data-ttu-id="29074-138">**CodeTestClient** viene illustrato come utilizzare l'attività tramite codice.</span><span class="sxs-lookup"><span data-stu-id="29074-138">**CodeTestClient** shows how to use the activity using code.</span></span>  
  
    2.  <span data-ttu-id="29074-139">**DesignerTestClient** viene illustrato come utilizzare l'attività all'interno di progettazione.</span><span class="sxs-lookup"><span data-stu-id="29074-139">**DesignerTestClient** shows how to use the activity within the designer.</span></span>  
  
2.  <span data-ttu-id="29074-140">Compilare ed eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="29074-140">Build and run the project.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="29074-141">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="29074-141">The samples may already be installed on your machine.</span></span> <span data-ttu-id="29074-142">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="29074-142">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="29074-143">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="29074-143">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="29074-144">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="29074-144">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NonGenericParallelForEach`
