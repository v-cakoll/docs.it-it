---
title: Variabili e argomenti
description: Questo articolo descrive le variabili, che rappresentano l'archiviazione di dati e gli argomenti, che rappresentano il flusso di dati da e verso un'attività in Workflow Foundation.
ms.date: 03/30/2017
ms.assetid: d03dbe34-5b2e-4f21-8b57-693ee49611b8
ms.openlocfilehash: 5cce9931e9b0a37d5fafbfb84527ffd543a0a50f
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2020
ms.locfileid: "84201949"
---
# <a name="variables-and-arguments"></a>Variabili e argomenti
In Windows Workflow Foundation (WF) le variabili rappresentano l'archiviazione di dati e gli argomenti rappresentano il flusso di dati all'interno e all'esterno di un'attività. Un'attività dispone di un set di argomenti che costituiscono la firma dell'attività. Inoltre, un'attività può gestire un elenco di variabili a cui uno sviluppatore può aggiungere o rimuovere variabili durante la progettazione di un flusso di lavoro. Un argomento viene associato usando un'espressione che restituisce un valore.  
  
## <a name="variables"></a>Variabili  
 Le variabili sono percorsi di archiviazione per i dati e vengono dichiarate come parte della definizione di un flusso di lavoro. Le variabili accettano valori in fase di esecuzione che vengono poi archiviati come parte dello stato di un'istanza del flusso di lavoro. Una definizione di variabile specifica il tipo di variabile e, facoltativamente, il nome. Nel codice seguente viene mostrato come dichiarare una variabile, assegnarvi un valore usando un'attività <xref:System.Activities.Statements.Assign%601>, quindi come visualizzare il relativo valore nella console usando un'attività <xref:System.Activities.Statements.WriteLine>.  
  
```csharp  
// Define a variable named "str" of type string.  
Variable<string> var = new Variable<string>  
{  
    Name = "str"  
};  
  
// Declare the variable within a Sequence, assign  
// a value to it, and then display it.  
Activity wf = new Sequence()  
{  
    Variables = { var },  
    Activities =  
    {  
        new Assign<string>  
        {  
            To = var,  
            Value = "Hello World."  
        },  
        new WriteLine  
        {  
            Text = var  
        }  
    }  
};  
  
WorkflowInvoker.Invoke(wf);  
```  
  
 Un'espressione del valore predefinito può essere specificata facoltativamente come parte di una dichiarazione di variabile. Le variabili possono disporre anche di modificatori. Se ad esempio una variabile è di sola lettura, può essere applicato il modificatore <xref:System.Activities.VariableModifiers> di sola lettura. Nell'esempio seguente viene creata una variabile di sola lettura con un valore predefinito assegnato.  
  
```csharp  
// Define a read-only variable with a default value.  
Variable<string> var = new Variable<string>  
{  
    Default = "Hello World.",  
    Modifiers = VariableModifiers.ReadOnly  
};  
```  
  
## <a name="variable-scoping"></a>Ambito di variabili  
 La durata di una variabile in fase di esecuzione corrisponde alla durata dell'attività che la dichiara. Quando un'attività viene completata, le relative variabili vengono pulite e non possono essere più usate come riferimento.  
  
## <a name="arguments"></a>Argomenti  
 Gli autori di attività usano gli argomenti per definire la modalità in cui i dati fluiscono all'interno e all'esterno di un'attività. Ogni argomento ha una direzione specificata: <xref:System.Activities.ArgumentDirection.In>, <xref:System.Activities.ArgumentDirection.Out> o <xref:System.Activities.ArgumentDirection.InOut>.  
  
 L'esecuzione del flusso di lavoro assicura le seguenti garanzie relativamente agli intervalli di spostamento dei dati all'interno e all'esterno di attività:  
  
1. Quando si avvia l'esecuzione di un'attività, vengono calcolati i valori di tutti i relativi argomenti di input e di input/output. Ad esempio, indipendentemente da quando viene chiamato il metodo <xref:System.Activities.Argument.Get%2A>, il valore restituito sarà quello calcolato dal runtime antecedente alla chiamata di `Execute`.  
  
2. Quando viene chiamato il metodo <xref:System.Activities.InOutArgument%601.Set%2A>, il valore viene impostato immediatamente dal runtime.  
  
3. Facoltativamente gli argomenti possono avere il proprio <xref:System.Activities.Argument.EvaluationOrder%2A> specificato. <xref:System.Activities.Argument.EvaluationOrder%2A> è un valore in base zero che specifica l'ordine in cui viene valutato l'argomento. Per impostazione predefinita, l'ordine di valutazione dell'argomento non è specificato e corrisponde al valore <xref:System.Activities.Argument.UnspecifiedEvaluationOrder>. Impostare la proprietà <xref:System.Activities.Argument.EvaluationOrder%2A> su un valore maggiore o uguale a zero per specificare un ordine di valutazione per questo argomento. Windows Workflow Foundation valuta gli argomenti con un ordine di valutazione specificato in ordine crescente. Si noti che gli argomenti con un ordine di valutazione non specificato vengono valutati prima di quelli aventi un ordine di valutazione specificato.  
  
 Un autore di attività può usare un meccanismo fortemente tipizzato per esporre i relativi argomenti. A tale scopo, vengono dichiarate proprietà di tipo <xref:System.Activities.InArgument%601>, <xref:System.Activities.OutArgument%601> e <xref:System.Activities.InOutArgument%601>. In questo modo un autore di attività può stabilire un contratto specifico sui dati in ingresso o in uscita da un'attività.  
  
### <a name="defining-the-arguments-on-an-activity"></a>Definizione di argomenti in un'attività  
 Gli argomenti possono essere definiti in un'attività specificando proprietà di tipo <xref:System.Activities.InArgument%601>, <xref:System.Activities.OutArgument%601> e <xref:System.Activities.InOutArgument%601>. Nel codice seguente viene mostrato come definire gli argomenti per un'attività `Prompt` che include una stringa da visualizzare all'utente e restituisce una stringa che contiene la risposta dell'utente.  
  
```csharp  
public class Prompt : Activity  
{  
    public InArgument<string> Text { get; set; }  
    public OutArgument<string> Response { get; set; }  
    // Rest of activity definition omitted.  
}  
```  
  
> [!NOTE]
> Le attività che restituiscono un singolo valore possono derivare dagli oggetti  <xref:System.Activities.Activity%601>, <xref:System.Activities.NativeActivity%601> o <xref:System.Activities.CodeActivity%601>. Queste attività dispongono di un oggetto <xref:System.Activities.OutArgument%601> ben definito denominato <xref:System.Activities.Activity%601.Result%2A> che contiene il valore restituito dell'attività.  
  
### <a name="using-variables-and-arguments-in-workflows"></a>Uso di variabili e argomenti nei flussi di lavoro  
 Nell'esempio seguente viene mostrato come vengono usati variabili e argomenti in un flusso di lavoro. Il flusso di lavoro è una sequenza che dichiara tre variabili: `var1`, `var2` e `var3`. La prima attività nel flusso di lavoro è un'attività `Assign` che assegna il valore di variabile `var1` alla variabile `var2`. Questa attività è seguita da un'attività `WriteLine` che stampa il valore della variabile `var2`. La successiva è un'altra attività `Assign` che assegna il valore di variabile `var2` alla variabile `var3`. Infine è disponibile un'altra attività `WriteLine` che stampa il valore della variabile `var3`. La prima attività `Assign` usa gli oggetti `InArgument<string>` e `OutArgument<string>` che rappresentano in modo esplicito le associazioni per gli argomenti dell'attività. L'oggetto `InArgument<string>` viene usato per <xref:System.Activities.Statements.Assign.Value%2A> in quanto il valore passa nell'attività <xref:System.Activities.Statements.Assign%601> attraverso il relativo argomento <xref:System.Activities.Statements.Assign.Value%2A>; l'oggetto `OutArgument<string>` viene usato per <xref:System.Activities.Statements.Assign.To%2A> in quanto il valore passa dall'argomento <xref:System.Activities.Statements.Assign.To%2A> alla variabile. La seconda attività `Assign` esegue la stessa operazione più compatta, ma con sintassi equivalente che usa cast impliciti. Anche le attività `WriteLine` usano la sintassi compatta.  
  
```csharp  
// Declare three variables; the first one is given an initial value.  
Variable<string> var1 = new Variable<string>()  
{  
    Default = "one"  
};  
Variable<string> var2 = new Variable<string>();  
Variable<string> var3 = new Variable<string>();  
  
// Define the workflow  
Activity wf = new Sequence  
{  
    Variables = { var1, var2, var3 },  
    Activities =
    {  
        new Assign<string>()  
        {  
            Value = new InArgument<string>(var1),  
            To = new OutArgument<string>(var2)  
        },  
        new WriteLine() { Text = var2 },  
        new Assign<string>()  
        {  
            Value = var2,  
            To = var3  
        },  
        new WriteLine() { Text = var3 }  
    }  
};  
  
WorkflowInvoker.Invoke(wf);  
```  
  
### <a name="using-variables-and-arguments-in-code-based-activities"></a>Uso di variabili e argomenti in attività basate su codice  
 Negli esempi precedenti viene mostrato come usare argomenti e variabili in flussi di lavoro e attività dichiarative. Gli argomenti e le variabili vengono usati anche in attività basate su codice. Dal punto di vista concettuale l'uso è molto simile. Le variabili rappresentano l'archivio dati all'interno dell'attività, mentre gli argomenti rappresentano il flusso di dati all'interno o all'esterno dell'attività e vengono associati dall'autore del flusso di lavoro alle altre variabili o argomenti nel flusso di lavoro che rappresentano il punto dal quale o verso il quale fluiscono i dati. Per ottenere o impostare il valore di una variabile o di un argomento in un'attività, deve essere usato un contesto di attività che rappresenta l'ambiente di esecuzione corrente dell'attività. Questo viene passato nel metodo <xref:System.Activities.CodeActivity%601.Execute%2A> dell'attività dall'esecuzione del flusso di lavoro. In questo esempio viene definita un'attività `Add` personalizzata che dispone di due argomenti <xref:System.Activities.ArgumentDirection.In>. Per accedere al valore degli argomenti, vengono usati il metodo <xref:System.Activities.Argument.Get%2A> e il contesto passato dall'esecuzione del flusso di lavoro.  
  
```csharp  
public sealed class Add : CodeActivity<int>  
{  
    [RequiredArgument]  
    public InArgument<int> Operand1 { get; set; }  
  
    [RequiredArgument]  
    public InArgument<int> Operand2 { get; set; }  
  
    protected override int Execute(CodeActivityContext context)  
    {  
        return Operand1.Get(context) + Operand2.Get(context);  
    }  
}  
```  
  
 Per ulteriori informazioni sull'utilizzo di argomenti, variabili ed espressioni nel codice, vedere [creazione di flussi di lavoro, attività ed espressioni tramite codice imperativo](authoring-workflows-activities-and-expressions-using-imperative-code.md) e [argomenti obbligatori e gruppi di overload](required-arguments-and-overload-groups.md).
