---
title: DynamicActivityCreation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d8ebe82f-98c8-4452-aed7-2c60a512b097
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 02dc1dfda28aae15889c0239f2913a8240869a76
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2017
---
# <a name="dynamicactivity-creation"></a><span data-ttu-id="55a17-102">DynamicActivityCreation</span><span class="sxs-lookup"><span data-stu-id="55a17-102">DynamicActivity Creation</span></span>
<span data-ttu-id="55a17-103">In questo esempio vengono illustrati due modi diversi per creare un'attività in fase di esecuzione usando l'attività <xref:System.Activities.DynamicActivity>.</span><span class="sxs-lookup"><span data-stu-id="55a17-103">This sample demonstrates two different ways to create an activity at runtime using the <xref:System.Activities.DynamicActivity> activity.</span></span>  
  
 <span data-ttu-id="55a17-104">In questo esempio, un'attività viene creata in fase di esecuzione con un corpo contenente un'attività <xref:System.Activities.Statements.Sequence> che contiene le attività <xref:System.Activities.Statements.ForEach%601> e <xref:System.Activities.Statements.Assign%601>.</span><span class="sxs-lookup"><span data-stu-id="55a17-104">In this sample, an activity is created at runtime with a body that contains a <xref:System.Activities.Statements.Sequence> activity that contains <xref:System.Activities.Statements.ForEach%601> and <xref:System.Activities.Statements.Assign%601> activities.</span></span> <span data-ttu-id="55a17-105">Un elenco di input di Integer viene passato all'attività e impostato come proprietà.</span><span class="sxs-lookup"><span data-stu-id="55a17-105">An input list of integers is passed into the activity and set as a property.</span></span> <span data-ttu-id="55a17-106">L'attività <xref:System.Activities.Statements.ForEach%601> scorre quindi l'elenco di valori e lo accumula.</span><span class="sxs-lookup"><span data-stu-id="55a17-106">The <xref:System.Activities.Statements.ForEach%601> activity then iterates over the list of values and accumulates it.</span></span> <span data-ttu-id="55a17-107">Nell'attività <xref:System.Activities.Statements.Assign%601>, il valore medio è calcolato dividendo l'accumulatore per il numero di elementi nell'elenco e assegnandolo alla media.</span><span class="sxs-lookup"><span data-stu-id="55a17-107">In the <xref:System.Activities.Statements.Assign%601> activity, the average value is calculated by dividing the accumulator by the number of elements in the list and assign it to the average.</span></span>  
  
 <span data-ttu-id="55a17-108">Nell'esempio viene illustrato l'uso di un'attività <xref:System.Activities.DynamicActivity> che consente l'ingresso di variabili come argomenti di input e restituisce valori come argomenti di output.</span><span class="sxs-lookup"><span data-stu-id="55a17-108">The sample demonstrates the usage of a <xref:System.Activities.DynamicActivity> activity that flows in variables as input arguments and returning values as output arguments.</span></span> <span data-ttu-id="55a17-109">L'attività dispone di un argomento di input denominato `Numbers`, ovvero un elenco di Integer.</span><span class="sxs-lookup"><span data-stu-id="55a17-109">The activity has one input argument named `Numbers` that is a list of integers.</span></span> <span data-ttu-id="55a17-110">L'attività <xref:System.Activities.Statements.ForEach%601> scorre l'elenco di valori e lo accumula.</span><span class="sxs-lookup"><span data-stu-id="55a17-110">The <xref:System.Activities.Statements.ForEach%601> activity iterates over the list of values and accumulates it.</span></span> <span data-ttu-id="55a17-111">Nell'attività <xref:System.Activities.Statements.Assign%601>, il valore medio è calcolato dividendo l'accumulatore per il numero di elementi nell'elenco e assegnandolo alla media.</span><span class="sxs-lookup"><span data-stu-id="55a17-111">In the <xref:System.Activities.Statements.Assign%601> activity, the average value is calculated by dividing the accumulator by the number of elements in the list and assigning it to the average.</span></span> <span data-ttu-id="55a17-112">La media viene restituita come argomento di output denominato `Average`.</span><span class="sxs-lookup"><span data-stu-id="55a17-112">The average is returned as an output argument named `Average`.</span></span>  
  
 <span data-ttu-id="55a17-113">Quando l'attività dinamica viene creata a livello di codice, l'input e l'output vengono dichiarati come mostrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="55a17-113">When the dynamic activity is created programmatically, the input and output are declared as shown in the following code example.</span></span>  
  
```csharp  
DynamicActivity act = new DynamicActivity()  
{  
    DisplayName = "Find average",  
    Properties =   
    {  
        // Input argument  
        new DynamicActivityProperty  
        {  
            Name = "Numbers",  
            Type = typeof(InArgument<List<int>>),  
            Value = numbers  
        },  
        // Output argument  
        new DynamicActivityProperty  
        {  
            Name = "Average",  
            Type = typeof(OutArgument<double>),  
            Value = average  
        }  
    },  
};  
```  
  
 <span data-ttu-id="55a17-114">Nell'esempio di codice seguente viene illustrata la definizione completa dell'oggetto `DynamicActivity` che calcola la media dei valori in un elenco.</span><span class="sxs-lookup"><span data-stu-id="55a17-114">The following code example shows the complete definition of the `DynamicActivity` that computes the average of the values in a list.</span></span>  
  
```  
DynamicActivity act = new DynamicActivity()  
{  
    DisplayName = "Find average",  
    Properties =   
    {  
        // Input argument  
        new DynamicActivityProperty  
        {  
            Name = "Numbers",  
            Type = typeof(InArgument<List<int>>),  
            Value = numbers  
        },  
        // Output argument  
        new DynamicActivityProperty  
        {  
            Name = "Average",  
            Type = typeof(OutArgument<double>),  
            Value = average  
        }  
    },  
    Implementation = () =>  
        new Sequence  
        {  
            Variables = { result, accumulator },  
            Activities =  
            {  
                new ForEach<int>  
                {  
                    Values =  new ArgumentValue<IEnumerable<int>> { ArgumentName = "Numbers" },                                  
                    Body = new ActivityAction<int>  
                    {  
                        Argument = iterationVariable,  
                        Handler = new Assign<int>  
                        {  
                            To = accumulator,  
                            Value = new InArgument<int>(env => iterationVariable.Get(env) +  accumulator.Get(env))  
                        }  
                    }  
                },  
  
                // Calculate the average and assign to the output argument.  
                new Assign<double>  
                {  
                    To = new ArgumentReference<double> { ArgumentName = "Average" },  
                    Value = new InArgument<double>(env => accumulator.Get(env) / numbers.Get(env).Count<int>())  
                },  
            }  
        }  
};  
```  
  
 <span data-ttu-id="55a17-115">Se creati in XAML, l'input e l'output vengono dichiarati come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="55a17-115">When created in XAML, the input and output are declared as shown in the following example.</span></span>  
  
```xml  
<Activity x:Class="Microsoft.Samples.DynamicActivityCreation.FindAverage"  
          xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"  
          xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"  
          xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <x:Members>  
    <x:Property Name="Numbers" Type="InArgument(scg:List(x:Int32))" />  
    <x:Property Name="Average" Type="OutArgument(x:Double)" />  
  </x:Members>  
    ...  
    ...  
</Activity>  
```  
  
 <span data-ttu-id="55a17-116">Il codice XAML può essere creato in modo visivo tramite [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="55a17-116">The XAML can be created visually using the [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)].</span></span> <span data-ttu-id="55a17-117">Se è incluso in un progetto di Visual Studio, assicurarsi di impostare il "Compila azione" su "None" per evitare che si sta compilando.</span><span class="sxs-lookup"><span data-stu-id="55a17-117">If it is included in a Visual Studio project, be sure to set its "Build Action" to "None" to prevent it from being compiled.</span></span> <span data-ttu-id="55a17-118">Il codice XAML può quindi essere caricato dinamicamente usando la chiamata seguente.</span><span class="sxs-lookup"><span data-stu-id="55a17-118">The XAML can then be loaded dynamically using the following call.</span></span>  
  
```  
Activity act2 = ActivityXamlServices.Load(@"FindAverage.xaml");  
```  
  
 <span data-ttu-id="55a17-119">L'istanza <xref:System.Activities.DynamicActivity> creata a livello di codice o tramite il caricamento di un flusso di lavoro XAML può essere usata come mostrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="55a17-119">The <xref:System.Activities.DynamicActivity> instance created programmatically or through loading a XAML workflow can be used as shown in the following code example.</span></span> <span data-ttu-id="55a17-120">Si noti che "atto" passato al `WorkflowInvoker.Invoke` è il "atto" <xref:System.Activities.Activity> definito nel primo esempio di codice.</span><span class="sxs-lookup"><span data-stu-id="55a17-120">Please note that "act" passed to the `WorkflowInvoker.Invoke` is the "act" <xref:System.Activities.Activity> defined in the first code example.</span></span>  
  
```  
IDictionary<string, object> results = WorkflowInvoker.Invoke(act, new Dictionary<string, object> { { "Numbers", numbers } });  
  
Console.WriteLine("The average calculated using the code activity is = " + results["Average"]);  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="55a17-121">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="55a17-121">To use this sample</span></span>  
  
1.  <span data-ttu-id="55a17-122">In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione DynamicActivityCreation.sln.</span><span class="sxs-lookup"><span data-stu-id="55a17-122">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the DynamicActivityCreation.sln solution file.</span></span>  
  
2.  <span data-ttu-id="55a17-123">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="55a17-123">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="55a17-124">Per eseguire la soluzione, premere CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="55a17-124">To run the solution, press CTRL+F5.</span></span>  
  
## <a name="command-line-arguments"></a><span data-ttu-id="55a17-125">Argomenti della riga di comando</span><span class="sxs-lookup"><span data-stu-id="55a17-125">Command line arguments</span></span>  
 <span data-ttu-id="55a17-126">In questo esempio sono accettati gli argomenti della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="55a17-126">This sample accepts command line arguments.</span></span> <span data-ttu-id="55a17-127">Gli utenti possono fornire un elenco di numeri affinché l'attività calcoli la media.</span><span class="sxs-lookup"><span data-stu-id="55a17-127">Users can provide a list of numbers for the activity to calculate their average.</span></span> <span data-ttu-id="55a17-128">L'elenco di numeri da usare viene passato come elenco di numeri separati da uno spazio.</span><span class="sxs-lookup"><span data-stu-id="55a17-128">The list of numbers to be used is passed as a list of numbers separated by a space.</span></span> <span data-ttu-id="55a17-129">Ad esempio per calcolare la media di 5, 10 e 32, richiamare l'esempio usando la riga di comando seguente.</span><span class="sxs-lookup"><span data-stu-id="55a17-129">For example, to calculate the average of 5, 10, and 32 invoke the sample using the following command line.</span></span>  
  
 <span data-ttu-id="55a17-130">**DynamicActivityCreation 5 10 32**</span><span class="sxs-lookup"><span data-stu-id="55a17-130">**DynamicActivityCreation 5 10 32**</span></span>  
> [!IMPORTANT]
>  <span data-ttu-id="55a17-131">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="55a17-131">The samples may already be installed on your machine.</span></span> <span data-ttu-id="55a17-132">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="55a17-132">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="55a17-133">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="55a17-133">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="55a17-134">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="55a17-134">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\DynamicActivity\DynamicActivityCreation`