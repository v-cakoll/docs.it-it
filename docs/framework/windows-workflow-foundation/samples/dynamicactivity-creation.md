---
title: DynamicActivityCreation
ms.date: 03/30/2017
ms.assetid: d8ebe82f-98c8-4452-aed7-2c60a512b097
ms.openlocfilehash: 270066fafd5c71b2a720ca305433159c172872aa
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43777487"
---
# <a name="dynamicactivity-creation"></a>DynamicActivityCreation
In questo esempio vengono illustrati due modi diversi per creare un'attività in fase di esecuzione usando l'attività <xref:System.Activities.DynamicActivity>.  
  
 In questo esempio, un'attività viene creata in fase di esecuzione con un corpo contenente un'attività <xref:System.Activities.Statements.Sequence> che contiene le attività <xref:System.Activities.Statements.ForEach%601> e <xref:System.Activities.Statements.Assign%601>. Un elenco di input di Integer viene passato all'attività e impostato come proprietà. L'attività <xref:System.Activities.Statements.ForEach%601> scorre quindi l'elenco di valori e lo accumula. Nell'attività <xref:System.Activities.Statements.Assign%601>, il valore medio è calcolato dividendo l'accumulatore per il numero di elementi nell'elenco e assegnandolo alla media.  
  
 Nell'esempio viene illustrato l'uso di un'attività <xref:System.Activities.DynamicActivity> che consente l'ingresso di variabili come argomenti di input e restituisce valori come argomenti di output. L'attività dispone di un argomento di input denominato `Numbers`, ovvero un elenco di Integer. L'attività <xref:System.Activities.Statements.ForEach%601> scorre l'elenco di valori e lo accumula. Nell'attività <xref:System.Activities.Statements.Assign%601>, il valore medio è calcolato dividendo l'accumulatore per il numero di elementi nell'elenco e assegnandolo alla media. La media viene restituita come argomento di output denominato `Average`.  
  
 Quando l'attività dinamica viene creata a livello di codice, l'input e l'output vengono dichiarati come mostrato nell'esempio di codice seguente.  
  
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
  
 Nell'esempio di codice seguente viene illustrata la definizione completa dell'oggetto `DynamicActivity` che calcola la media dei valori in un elenco.  
  
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
  
 Se creati in XAML, l'input e l'output vengono dichiarati come mostrato nell'esempio seguente.  
  
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
  
 Il codice XAML può essere creato in modo visivo tramite [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)]. Se è incluso in un progetto di Visual Studio, assicurarsi di impostare il "Compila azione" su "None" per impedire che in fase di compilazione. Il codice XAML può quindi essere caricato dinamicamente usando la chiamata seguente.  
  
```  
Activity act2 = ActivityXamlServices.Load(@"FindAverage.xaml");  
```  
  
 L'istanza <xref:System.Activities.DynamicActivity> creata a livello di codice o tramite il caricamento di un flusso di lavoro XAML può essere usata come mostrato nell'esempio di codice seguente. Si noti che il "atto" passato per il `WorkflowInvoker.Invoke` è il "atto" <xref:System.Activities.Activity> definito nel primo esempio di codice.  
  
```  
IDictionary<string, object> results = WorkflowInvoker.Invoke(act, new Dictionary<string, object> { { "Numbers", numbers } });  
  
Console.WriteLine("The average calculated using the code activity is = " + results["Average"]);  
```  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione DynamicActivityCreation.sln.  
  
2.  Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
3.  Per eseguire la soluzione, premere CTRL+F5.  
  
## <a name="command-line-arguments"></a>Argomenti della riga di comando  
 In questo esempio sono accettati gli argomenti della riga di comando. Gli utenti possono fornire un elenco di numeri affinché l'attività calcoli la media. L'elenco di numeri da usare viene passato come elenco di numeri separati da uno spazio. Ad esempio per calcolare la media di 5, 10 e 32, richiamare l'esempio usando la riga di comando seguente.  
  
 **DynamicActivityCreation 32 10 5**  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\DynamicActivity\DynamicActivityCreation`