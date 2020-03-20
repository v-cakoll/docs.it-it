---
title: ForEach non generica
ms.date: 03/30/2017
ms.assetid: 576cd07a-d58d-4536-b514-77bad60bff38
ms.openlocfilehash: 08dbac3974915f823a4f6e39f35927453a7c4b3a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142706"
---
# <a name="non-generic-foreach"></a>ForEach non generica
Nella casella degli strumenti di [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] è disponibile un set di attività del flusso di controllo, inclusa <xref:System.Activities.Statements.ForEach%601> che consente di scorrere le raccolte <xref:System.Collections.Generic.IEnumerable%601>.  
  
 L'oggetto <xref:System.Activities.Statements.ForEach%601> richiede che la relativa proprietà <xref:System.Activities.Statements.ForEach%601.Values%2A> sia di tipo <xref:System.Collections.Generic.IEnumerable%601>. In questo modo, gli utenti non possono scorrere le strutture di dati che implementano l'interfaccia <xref:System.Collections.Generic.IEnumerable%601> (ad esempio l'oggetto <xref:System.Collections.ArrayList>). La versione non generica dell'oggetto <xref:System.Activities.Statements.ForEach%601> supera questo requisito, a discapito di una maggiore complessità della fase di esecuzione per assicurare la compatibilità dei tipi dei valori nella raccolta.  
  
 In questo esempio viene illustrato come implementare un'attività <xref:System.Activities.Statements.ForEach%601> non generica e la relativa finestra di progettazione. Questa attività può essere usata per scorrere l'oggetto <xref:System.Collections.ArrayList>.  
  
## <a name="foreach-activity"></a>Attività ForEach  
 L'istruzione di `foreach` Visual Basic di C, enumera gli elementi di una raccolta, eseguendo un'istruzione incorporata per ogni elemento dell'insieme. Le attività [!INCLUDE[wf1](../../../../includes/wf1-md.md)] equivalenti di `foreach` sono <xref:System.Activities.Statements.ForEach%601> e <xref:System.Activities.Statements.ParallelForEach%601>. L'attività <xref:System.Activities.Statements.ForEach%601> contiene un elenco di valori e un corpo. In fase di esecuzione, viene scorso l'elenco e il corpo viene eseguito per ogni valore dell'elenco.  
  
 Nella maggior parte dei casi, la versione generica dell'attività deve essere la soluzione preferita, poiché concerne la maggioranza degli scenari in cui verrà usata e fornisce il controllo dei tipi in fase di compilazione. La versione non generica può essere usata per scorrere i tipi che implementano l'interfaccia <xref:System.Collections.IEnumerable> non generica.  
  
## <a name="class-definition"></a>Definizione della classe  
 Nell'esempio di codice seguente viene illustrata la definizione di un'attività `ForEach` non generica.  
  
```csharp  
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
  
```csharp  
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
  
|Condizione|Message|Gravità|Tipo di eccezione|  
|---------------|-------------|--------------|--------------------|  
|I valori sono `null`|Valore non specificato per un argomento di attività 'Values' obbligatorio.|Errore|<xref:System.InvalidOperationException>|  
  
## <a name="foreach-designer"></a>Finestra di progettazione ForEach  
 L'aspetto dell'ActivityDesigner per l'esempio è simile a quello della finestra di progettazione fornita per l'attività <xref:System.Activities.Statements.ForEach%601> incorporata. La finestra di progettazione viene visualizzata nella casella degli strumenti nella categoria **Esempi**, **Attività non generiche** . La finestra di progettazione è denominata **ForEachWithBodyFactory** nella casella degli strumenti, perché l'attività espone un <xref:System.Activities.Presentation.IActivityTemplateFactory> oggetto nella casella degli strumenti, che crea l'attività con un oggetto configurato <xref:System.Activities.ActivityAction>correttamente.  
  
```csharp  
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
  
#### <a name="to-run-this-sample"></a>Per eseguire questo esempio  
  
1. Impostare il progetto scelto come progetto di avvio della soluzione:  
  
    1. **CodeTestClient** viene illustrato come utilizzare l'attività utilizzando il codice.  
  
    2. **DesignerTestClient** viene illustrato come utilizzare l'attività all'interno della finestra di progettazione.  
  
2. Compilare ed eseguire il progetto.  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NonGenericForEach`
