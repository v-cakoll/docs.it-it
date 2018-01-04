---
title: ForEach non generica
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 576cd07a-d58d-4536-b514-77bad60bff38
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 090aeda13081dc87b37cf0a18955cbd239720870
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="non-generic-foreach"></a>ForEach non generica
[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]Nella casella degli strumenti è disponibile un set di attività flusso di controllo, tra cui <xref:System.Activities.Statements.ForEach%601>, che consente di scorrere <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` raccolte.  
  
 <xref:System.Activities.Statements.ForEach%601>richiede la <xref:System.Activities.Statements.ForEach%601.Values%2A> proprietà sia di tipo <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable`. In questo modo gli utenti scorrere le strutture di dati che implementano <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` interfaccia (ad esempio, <xref:System.Collections.ArrayList>). La versione non generica dell'oggetto <xref:System.Activities.Statements.ForEach%601> supera questo requisito, a discapito di una maggiore complessità della fase di esecuzione per assicurare la compatibilità dei tipi dei valori nella raccolta.  
  
 In questo esempio viene illustrato come implementare un'attività <xref:System.Activities.Statements.ForEach%601> non generica e la relativa finestra di progettazione. Questa attività può essere usata per scorrere l'oggetto <xref:System.Collections.ArrayList>.  
  
## <a name="foreach-activity"></a>Attività ForEach  
 L'istruzione `foreach` di C#/VB enumera gli elementi di una raccolta eseguendo un'istruzione incorporata per ogni elemento della raccolta. Le attività [!INCLUDE[wf1](../../../../includes/wf1-md.md)] equivalenti di `foreach` sono <xref:System.Activities.Statements.ForEach%601> e <xref:System.Activities.Statements.ParallelForEach%601>. L'attività <xref:System.Activities.Statements.ForEach%601> contiene un elenco di valori e un corpo. In fase di esecuzione, viene scorso l'elenco e il corpo viene eseguito per ogni valore dell'elenco.  
  
 Nella maggior parte dei casi, la versione generica dell'attività deve essere la soluzione preferita, poiché concerne la maggioranza degli scenari in cui verrà usata e fornisce il controllo dei tipi in fase di compilazione. La versione non generica può essere usata per scorrere i tipi che implementano l'interfaccia <xref:System.Collections.IEnumerable> non generica.  
  
## <a name="class-definition"></a>Definizione della classe  
 Nell'esempio di codice seguente viene illustrata la definizione di un'attività `ForEach` non generica.  
  
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
  
 Body (facoltativo)  
 Oggetto <xref:System.Activities.ActivityAction> di tipo <xref:System.Object> eseguito per ogni elemento della raccolta. Ogni singolo elemento viene passato al corpo tramite la proprietà `Argument`.  
  
 Values (facoltativo)  
 Raccolta di elementi che vengono scorsi. In fase di esecuzione si verifica che tutti gli elementi della raccolta siano di tipi compatibili.  
  
## <a name="example-of-using-foreach"></a>Esempio di utilizzo di ForEach  
 Nel codice seguente viene illustrato come usare l'attività ForEach in un'applicazione.  
  
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
  
|Condizione|Messaggio|Gravità|Tipo di eccezione|  
|---------------|-------------|--------------|--------------------|  
|I valori sono `null`|Valore non specificato per un argomento di attività 'Values' obbligatorio.|Errore|<xref:System.InvalidOperationException>|  
  
## <a name="foreach-designer"></a>Finestra di progettazione ForEach  
 L'aspetto dell'ActivityDesigner per l'esempio è simile a quello della finestra di progettazione fornita per l'attività <xref:System.Activities.Statements.ForEach%601> incorporata. Verrà visualizzata la finestra di progettazione nella casella degli strumenti di **esempi**, **attività Non generiche** categoria. La finestra di progettazione è denominata **ForEachWithBodyFactory** nella casella degli strumenti, poiché l'attività espone un <xref:System.Activities.Presentation.IActivityTemplateFactory> nella casella degli strumenti, che crea l'attività con configurato correttamente <xref:System.Activities.ActivityAction>.  
  
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
  
#### <a name="to-run-this-sample"></a>Per eseguire l'esempio  
  
1.  Impostare il progetto scelto come progetto di avvio della soluzione:  
  
    1.  **CodeTestClient** viene illustrato come utilizzare l'attività tramite codice.  
  
    2.  **DesignerTestClient** viene illustrato come utilizzare l'attività all'interno di progettazione.  
  
2.  Compilare ed eseguire il progetto.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NonGenericForEach`
