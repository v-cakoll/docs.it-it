---
title: "Attività LINQ to Objects"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 403c82e8-7f2b-42f6-93cd-95c35bc76ead
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 811ffe44a65dea13482d600a09989ce42f6580dd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="linq-to-objects-activity"></a><span data-ttu-id="1dff4-102">Attività LINQ to Objects</span><span class="sxs-lookup"><span data-stu-id="1dff4-102">LINQ to Objects Activity</span></span>
<span data-ttu-id="1dff4-103">In questo esempio viene illustrato come creare un'attività per usare LINQ to Objects per eseguire query su elementi di una raccolta.</span><span class="sxs-lookup"><span data-stu-id="1dff4-103">This sample demonstrates how to create an activity to use LINQ to Objects to query elements in a collection.</span></span>  
  
## <a name="activity-details-for-findincollection"></a><span data-ttu-id="1dff4-104">Dettagli dell'attività per FindInCollection</span><span class="sxs-lookup"><span data-stu-id="1dff4-104">Activity Details for FindInCollection</span></span>  
 <span data-ttu-id="1dff4-105">Questa attività consente agli utenti di eseguire query su elementi di raccolte in memoria usando LINQ to Objects.</span><span class="sxs-lookup"><span data-stu-id="1dff4-105">This activity allows users to query elements from collections in memory using LINQ to Objects.</span></span> <span data-ttu-id="1dff4-106">È necessario fornire un predicato LINQ nel formato di un'espressione lambda per filtrare i risultati.</span><span class="sxs-lookup"><span data-stu-id="1dff4-106">You must provide a LINQ predicate in the form of a lambda expression to filter the results.</span></span> <span data-ttu-id="1dff4-107">Questa attività può essere usata unitamente ad attività <xref:System.Activities.Statements.AddToCollection%601>.</span><span class="sxs-lookup"><span data-stu-id="1dff4-107">This activity can be used in conjunction with <xref:System.Activities.Statements.AddToCollection%601> activities.</span></span>  
  
 <span data-ttu-id="1dff4-108">Nella tabella seguente viene descritta la proprietà e i valori restituiti per l'attività.</span><span class="sxs-lookup"><span data-stu-id="1dff4-108">The following table details the property and return values for the activity.</span></span>  
  
|<span data-ttu-id="1dff4-109">Proprietà o valore restituito</span><span class="sxs-lookup"><span data-stu-id="1dff4-109">Property or Return Value</span></span>|<span data-ttu-id="1dff4-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1dff4-110">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="1dff4-111">Proprietà `Collection`</span><span class="sxs-lookup"><span data-stu-id="1dff4-111">`Collection` property</span></span>|<span data-ttu-id="1dff4-112">Proprietà obbligatoria che specifica la raccolta di origine.</span><span class="sxs-lookup"><span data-stu-id="1dff4-112">A required property that specifies the source collection.</span></span>|  
|<span data-ttu-id="1dff4-113">Proprietà `Predicate`</span><span class="sxs-lookup"><span data-stu-id="1dff4-113">`Predicate` property</span></span>|<span data-ttu-id="1dff4-114">Proprietà obbligatoria che specifica il filtro per la raccolta nel formato di un'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="1dff4-114">A required property that specifies the filter for the collection in the form of a lambda expression.</span></span>|  
|<span data-ttu-id="1dff4-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1dff4-115">Return Value</span></span>|<span data-ttu-id="1dff4-116">La raccolta filtrata.</span><span class="sxs-lookup"><span data-stu-id="1dff4-116">The filtered collection.</span></span>|  
  
## <a name="code-sample-that-uses-the-custom-activity"></a><span data-ttu-id="1dff4-117">Esempio di codice che usa l'attività personalizzata</span><span class="sxs-lookup"><span data-stu-id="1dff4-117">Code Sample that uses the Custom Activity</span></span>  
 <span data-ttu-id="1dff4-118">Nell'esempio di codice seguente viene usata l'attività personalizzata `FindInCollection` per trovare tutte le righe in una raccolta di dipendenti la cui proprietà `Role` è impostata su `Manager` e la proprietà `Location` è impostata su `Redmond`.</span><span class="sxs-lookup"><span data-stu-id="1dff4-118">The following code example uses the `FindInCollection` custom activity to find all rows in a collection of employees that have a `Role` property set to `Manager` and the `Location` property set to `Redmond`.</span></span>  
  
```csharp  
// Find all program managers in Redmond in the employees collection.  
  
Activity wf = new FindInCollection<Employee>  
{  
    Collections = new LambdaValue<IEnumerable<Employee>>(c => employees),                
    Predicate = new LambdaValue<Func<Employee, bool>>(c => new Func<Employee, bool>(e => e.Role.Equals("Manager") && e.Location.Equals("Redmond")))  
};  
```  
  
 <span data-ttu-id="1dff4-119">Nel codice seguente viene illustrato come creare un programma flusso di lavoro che usa l'attività FindInCollection personalizzata e le attività <xref:System.Activities.Statements.AddToCollection%601> e <xref:System.Activities.Statements.ForEach%601> per popolare una raccolta con dipendenti, trovare tutti i dipendenti con il ruolo di sviluppatore e che si trovano a Redmond, quindi scorrere l'elenco risultante.</span><span class="sxs-lookup"><span data-stu-id="1dff4-119">The following code shows how to create a workflow program that uses the custom FindInCollection activity, <xref:System.Activities.Statements.AddToCollection%601>, and <xref:System.Activities.Statements.ForEach%601> activities to populate a collection with employees, find all the employees that have developer roles and are located in Redmond, and then iterate through the resulting list.</span></span>  
  
```csharp  
// Create the Linq predicate for the find expression  
  
Func<Employee, bool> predicate = e => e.Role == "DEV" && e.Location.Equals("Redmond");  
  
// Create workflow program  
Activity sampleWorkflow = new Sequence  
{  
    Variables = { employees, devsFromRedmond },  
    Activities =  
    {  
        new Assign<IList<Employee>>  
        {  
            To = employees,  
            Value = new LambdaValue<IList<Employee>>(c => new List<Employee>())  
        },  
        new AddToCollection<Employee>  
        {  
            Collection = new InArgument<ICollection<Employee>>(employees),  
            Item =  new LambdaValue<Employee>(c => new Employee(1, "Employee 1", "DEV", "Redmond"))  
        },  
        new AddToCollection<Employee>  
        {  
            Collection = new InArgument<ICollection<Employee>>(employees),  
            Item =  new LambdaValue<Employee>(c => new Employee(2, "Employee 2", "DEV", "Redmond"))  
        },  
        new AddToCollection<Employee>  
        {  
            Collection = new InArgument<ICollection<Employee>>(employees),  
            Item =  new LambdaValue<Employee>(c => new Employee(3, "Employee 3", "PM", "Redmond"))  
        },  
        new AddToCollection<Employee>  
        {  
            Collection = new InArgument<ICollection<Employee>>(employees),  
            Item =  new LambdaValue<Employee>(c => new Employee(4, "Employee 4", "PM", "China"))  
        },  
        new FindInCollection<Employee>  
        {  
            Collections = new InArgument<IEnumerable<Employee>>(employees),  
            Predicate = new LambdaValue<Func<Employee, bool>>(c => predicate),  
            Result = new OutArgument<IList<Employee>>(devsFromRedmond)  
        },  
        new ForEach<Employee>  
        {  
            Values = new InArgument<IEnumerable<Employee>>(devsFromRedmond),  
            Body = new ActivityAction<Employee>  
            {  
                Argument = iterationVariable,  
                Handler = new WriteLine  
                {  
                    Text = new InArgument<string>(env => iterationVariable.Get(env).ToString())  
                }  
            }  
        }  
    }  
};  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="1dff4-120">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="1dff4-120">To use this sample</span></span>  
  
1.  <span data-ttu-id="1dff4-121">Tramite [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione LinqToObjects.sln.</span><span class="sxs-lookup"><span data-stu-id="1dff4-121">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the LinqToObjects.sln solution file.</span></span>  
  
2.  <span data-ttu-id="1dff4-122">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="1dff4-122">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="1dff4-123">Per eseguire la soluzione, premere F5.</span><span class="sxs-lookup"><span data-stu-id="1dff4-123">To run the solution, press F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1dff4-124">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="1dff4-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="1dff4-125">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="1dff4-125">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="1dff4-126">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1dff4-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1dff4-127">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="1dff4-127">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Linq\LinqToObjects`  
  
## <a name="see-also"></a><span data-ttu-id="1dff4-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1dff4-128">See Also</span></span>  
 [<span data-ttu-id="1dff4-129">Espressioni lambda (Guida per programmatori c#)</span><span class="sxs-lookup"><span data-stu-id="1dff4-129">Lambda Expressions (C# Programming Guide)</span></span>](http://go.microsoft.com/fwlink/?LinkId=150381)  
 [<span data-ttu-id="1dff4-130">LINQ to Objects</span><span class="sxs-lookup"><span data-stu-id="1dff4-130">LINQ to Objects</span></span>](http://go.microsoft.com/fwlink/?LinkID=150380)
