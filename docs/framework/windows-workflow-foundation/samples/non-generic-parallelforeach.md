---
title: Attività ParallelForEach non generica
ms.date: 03/30/2017
ms.assetid: de17e7a2-257b-48b3-91a1-860e2e9bf6e6
ms.openlocfilehash: 70d5de587dda3cb61205a8d77f2173df9b93498b
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43480846"
---
# <a name="non-generic-parallelforeach"></a>Attività ParallelForEach non generica
[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] viene fornito nella casella degli strumenti un set di attività flusso di controllo, inclusa <xref:System.Activities.Statements.ParallelForEach%601>, che consente di scorrere <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` raccolte.  
  
 <xref:System.Activities.Statements.ParallelForEach%601> richiede la relativa <xref:System.Activities.Statements.ParallelForEach%601.Values%2A> proprietà sia di tipo <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable`. In questo modo gli utenti da scorrere le strutture di dati che implementano <!--zz <xref:System.Collections.IEnumerable%601> --> `System.Collections.IEnumerable` interfaccia (ad esempio, <xref:System.Collections.ArrayList>). La versione non generica dell'oggetto <xref:System.Activities.Statements.ParallelForEach%601> supera questo requisito, a discapito di una maggiore complessità della fase di esecuzione per assicurare la compatibilità dei tipi dei valori nella raccolta.  
  
 In questo esempio viene illustrato come implementare un'attività <xref:System.Activities.Statements.ParallelForEach%601> non generica e la relativa finestra di progettazione. Questa attività può essere usata per scorrere l'oggetto <xref:System.Collections.ArrayList>.  
  
## <a name="parallelforeach-activity"></a>Attività ParallelForEach  
 L'istruzione `foreach` di C#/VB enumera gli elementi di una raccolta eseguendo un'istruzione incorporata per ogni elemento della raccolta. Le attività equivalenti di [!INCLUDE[wf1](../../../../includes/wf1-md.md)] sono <xref:System.Activities.Statements.ForEach%601> e <xref:System.Activities.Statements.ParallelForEach%601>. L'attività <xref:System.Activities.Statements.ForEach%601> contiene un elenco di valori e un corpo. In fase di esecuzione, viene scorso l'elenco e il corpo viene eseguito per ogni valore dell'elenco.  
  
 L'oggetto <xref:System.Activities.Statements.ParallelForEach%601> dispone di una proprietà <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> in modo che l'attività <xref:System.Activities.Statements.ParallelForEach%601> possa essere completata in fretta se la valutazione della proprietà <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> restituisce `true`. La proprietà <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> viene valutata al termine di ogni iterazione.  
  
 Nella maggior parte dei casi, la versione generica dell'attività deve essere la soluzione preferita, poiché concerne la maggioranza degli scenari in cui viene usata e fornisce il controllo dei tipi in fase di compilazione. La versione non generica può essere usata per scorrere i tipi che implementano l'interfaccia <xref:System.Collections.IEnumerable> non generica.  
  
## <a name="class-definition"></a>Definizione della classe  
 Nell'esempio di codice seguente viene illustrata la definizione di un'attività `ParallelForEach` non generica.  
  
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
  
 Body (facoltativo)  
 Oggetto <xref:System.Activities.ActivityAction> di tipo <xref:System.Object> eseguito per ogni elemento della raccolta. Ogni singolo elemento viene passato al corpo tramite la proprietà Argument.  
  
 Values (facoltativo)  
 Raccolta di elementi che vengono scorsi. In fase di esecuzione si verifica che tutti gli elementi della raccolta siano di tipi compatibili.  
  
 CompletionCondition (facoltativo)  
 La proprietà <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> viene valutata al termine di qualsiasi iterazione. Se restituisce `true`, le iterazioni in sospeso pianificate vengono annullate. Se questa proprietà non è impostata, tutte le attività nella raccolta di rami vengono eseguite fino al completamento.  
  
## <a name="example-of-using-parallelforeach"></a>Esempio di utilizzo di ParallelForEach  
 Nel codice seguente viene illustrato come usare l'attività ParallelForEach in un'applicazione.  
  
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
  
## <a name="parallelforeach-designer"></a>Finestra di progettazione ParallelForEachT  
 L'aspetto dell'ActivityDesigner per l'esempio è simile a quello della finestra di progettazione fornita per l'attività <xref:System.Activities.Statements.ParallelForEach%601> incorporata. La finestra di progettazione viene visualizzata nella casella degli strumenti nel **Samples**, **attività Non generiche** categoria. La finestra di progettazione viene denominata **ParallelForEachWithBodyFactory** nella casella degli strumenti, poiché l'attività espone un <xref:System.Activities.Presentation.IActivityTemplateFactory> nella casella degli strumenti che crea l'attività con un correttamente configurato <xref:System.Activities.ActivityAction>.  
  
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
  
#### <a name="to-run-the-sample"></a>Per eseguire l'esempio  
  
1.  Impostare il progetto scelto come progetto di avvio della soluzione.  
  
    1.  **CodeTestClient** viene illustrato come usare l'attività usando il codice.  
  
    2.  **DesignerTestClient** viene illustrato come utilizzare l'attività all'interno della finestra di progettazione.  
  
2.  Compilare ed eseguire il progetto.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NonGenericParallelForEach`
