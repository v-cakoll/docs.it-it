---
title: Variabili e argomenti
description: Questo articolo descrive le variabili, che rappresentano l'archiviazione di dati e gli argomenti, che rappresentano il flusso di dati da e verso un'attività in Workflow Foundation.
ms.date: 03/30/2017
ms.assetid: d03dbe34-5b2e-4f21-8b57-693ee49611b8
ms.openlocfilehash: 47b8a7bddc8c3a9a8427bcb3e93760a63e5fa976
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421306"
---
# <a name="variables-and-arguments"></a><span data-ttu-id="0466f-103">Variabili e argomenti</span><span class="sxs-lookup"><span data-stu-id="0466f-103">Variables and Arguments</span></span>
<span data-ttu-id="0466f-104">In Windows Workflow Foundation (WF) le variabili rappresentano l'archiviazione di dati e gli argomenti rappresentano il flusso di dati all'interno e all'esterno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="0466f-104">In Windows Workflow Foundation (WF), variables represent the storage of data and arguments represent the flow of data into and out of an activity.</span></span> <span data-ttu-id="0466f-105">Un'attività dispone di un set di argomenti che costituiscono la firma dell'attività.</span><span class="sxs-lookup"><span data-stu-id="0466f-105">An activity has a set of arguments and they make up the signature of the activity.</span></span> <span data-ttu-id="0466f-106">Inoltre, un'attività può gestire un elenco di variabili a cui uno sviluppatore può aggiungere o rimuovere variabili durante la progettazione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0466f-106">Additionally, an activity can maintain a list of variables to which a developer can add or remove variables during the design of a workflow.</span></span> <span data-ttu-id="0466f-107">Un argomento viene associato usando un'espressione che restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="0466f-107">An argument is bound using an expression that returns a value.</span></span>  
  
## <a name="variables"></a><span data-ttu-id="0466f-108">Variabili</span><span class="sxs-lookup"><span data-stu-id="0466f-108">Variables</span></span>  
 <span data-ttu-id="0466f-109">Le variabili sono percorsi di archiviazione per i dati</span><span class="sxs-lookup"><span data-stu-id="0466f-109">Variables are storage locations for data.</span></span> <span data-ttu-id="0466f-110">e vengono dichiarate come parte della definizione di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0466f-110">Variables are declared as part of the definition of a workflow.</span></span> <span data-ttu-id="0466f-111">Le variabili accettano valori in fase di esecuzione che vengono poi archiviati come parte dello stato di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0466f-111">Variables take on values at runtime and these values are stored as part of the state of a workflow instance.</span></span> <span data-ttu-id="0466f-112">Una definizione di variabile specifica il tipo di variabile e, facoltativamente, il nome.</span><span class="sxs-lookup"><span data-stu-id="0466f-112">A variable definition specifies the type of the variable and optionally, the name.</span></span> <span data-ttu-id="0466f-113">Nel codice seguente viene mostrato come dichiarare una variabile, assegnarvi un valore usando un'attività <xref:System.Activities.Statements.Assign%601>, quindi come visualizzare il relativo valore nella console usando un'attività <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="0466f-113">The following code shows how to declare a variable, assign a value to it using an <xref:System.Activities.Statements.Assign%601> activity, and then display its value to the console using a <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
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
  
 <span data-ttu-id="0466f-114">Un'espressione del valore predefinito può essere specificata facoltativamente come parte di una dichiarazione di variabile.</span><span class="sxs-lookup"><span data-stu-id="0466f-114">A default value expression can optionally be specified as part of a variable declaration.</span></span> <span data-ttu-id="0466f-115">Le variabili possono disporre anche di modificatori.</span><span class="sxs-lookup"><span data-stu-id="0466f-115">Variables also can have modifiers.</span></span> <span data-ttu-id="0466f-116">Se ad esempio una variabile è di sola lettura, può essere applicato il modificatore <xref:System.Activities.VariableModifiers> di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="0466f-116">For example, if a variable is read-only then the read-only <xref:System.Activities.VariableModifiers> modifier can be applied.</span></span> <span data-ttu-id="0466f-117">Nell'esempio seguente viene creata una variabile di sola lettura con un valore predefinito assegnato.</span><span class="sxs-lookup"><span data-stu-id="0466f-117">In the following example, a read-only variable is created that has a default value assigned.</span></span>  
  
```csharp  
// Define a read-only variable with a default value.  
Variable<string> var = new Variable<string>  
{  
    Default = "Hello World.",  
    Modifiers = VariableModifiers.ReadOnly  
};  
```  
  
## <a name="variable-scoping"></a><span data-ttu-id="0466f-118">Ambito di variabili</span><span class="sxs-lookup"><span data-stu-id="0466f-118">Variable Scoping</span></span>  
 <span data-ttu-id="0466f-119">La durata di una variabile in fase di esecuzione corrisponde alla durata dell'attività che la dichiara.</span><span class="sxs-lookup"><span data-stu-id="0466f-119">The lifetime of a variable at runtime is equal to the lifetime of the activity that declares it.</span></span> <span data-ttu-id="0466f-120">Quando un'attività viene completata, le relative variabili vengono pulite e non possono essere più usate come riferimento.</span><span class="sxs-lookup"><span data-stu-id="0466f-120">When an activity completes, its variables are cleaned up and can no longer be referenced.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="0466f-121">Arguments</span><span class="sxs-lookup"><span data-stu-id="0466f-121">Arguments</span></span>  
 <span data-ttu-id="0466f-122">Gli autori di attività usano gli argomenti per definire la modalità in cui i dati fluiscono all'interno e all'esterno di un'attività.</span><span class="sxs-lookup"><span data-stu-id="0466f-122">Activity authors use arguments to define the way data flows into and out of an activity.</span></span> <span data-ttu-id="0466f-123">Ogni argomento ha una direzione specificata: <xref:System.Activities.ArgumentDirection.In>, <xref:System.Activities.ArgumentDirection.Out> o <xref:System.Activities.ArgumentDirection.InOut>.</span><span class="sxs-lookup"><span data-stu-id="0466f-123">Each argument has a specified direction: <xref:System.Activities.ArgumentDirection.In>, <xref:System.Activities.ArgumentDirection.Out>, or <xref:System.Activities.ArgumentDirection.InOut>.</span></span>  
  
 <span data-ttu-id="0466f-124">L'esecuzione del flusso di lavoro assicura le seguenti garanzie relativamente agli intervalli di spostamento dei dati all'interno e all'esterno di attività:</span><span class="sxs-lookup"><span data-stu-id="0466f-124">The workflow runtime makes the following guarantees about the timing of data movement into and out of activities:</span></span>  
  
1. <span data-ttu-id="0466f-125">Quando si avvia l'esecuzione di un'attività, vengono calcolati i valori di tutti i relativi argomenti di input e di input/output.</span><span class="sxs-lookup"><span data-stu-id="0466f-125">When an activity starts executing, the values of all of its input and input/output arguments are calculated.</span></span> <span data-ttu-id="0466f-126">Ad esempio, indipendentemente da quando viene chiamato il metodo <xref:System.Activities.Argument.Get%2A>, il valore restituito sarà quello calcolato dal runtime antecedente alla chiamata di `Execute`.</span><span class="sxs-lookup"><span data-stu-id="0466f-126">For example, regardless of when <xref:System.Activities.Argument.Get%2A> is called, the value returned is the one calculated by the runtime prior to its invocation of `Execute`.</span></span>  
  
2. <span data-ttu-id="0466f-127">Quando viene chiamato il metodo <xref:System.Activities.InOutArgument%601.Set%2A>, il valore viene impostato immediatamente dal runtime.</span><span class="sxs-lookup"><span data-stu-id="0466f-127">When <xref:System.Activities.InOutArgument%601.Set%2A> is called, the runtime sets the value immediately.</span></span>  
  
3. <span data-ttu-id="0466f-128">Facoltativamente gli argomenti possono avere il proprio <xref:System.Activities.Argument.EvaluationOrder%2A> specificato.</span><span class="sxs-lookup"><span data-stu-id="0466f-128">Arguments can optionally have their <xref:System.Activities.Argument.EvaluationOrder%2A> specified.</span></span> <span data-ttu-id="0466f-129"><xref:System.Activities.Argument.EvaluationOrder%2A> è un valore in base zero che specifica l'ordine in cui viene valutato l'argomento.</span><span class="sxs-lookup"><span data-stu-id="0466f-129"><xref:System.Activities.Argument.EvaluationOrder%2A> is a zero-based value that specifies the order in which the argument is evaluated.</span></span> <span data-ttu-id="0466f-130">Per impostazione predefinita, l'ordine di valutazione dell'argomento non è specificato e corrisponde al valore <xref:System.Activities.Argument.UnspecifiedEvaluationOrder>.</span><span class="sxs-lookup"><span data-stu-id="0466f-130">By default, the evaluation order of the argument is unspecified and is equal to the <xref:System.Activities.Argument.UnspecifiedEvaluationOrder> value.</span></span> <span data-ttu-id="0466f-131">Impostare la proprietà <xref:System.Activities.Argument.EvaluationOrder%2A> su un valore maggiore o uguale a zero per specificare un ordine di valutazione per questo argomento.</span><span class="sxs-lookup"><span data-stu-id="0466f-131">Set <xref:System.Activities.Argument.EvaluationOrder%2A> to a value greater or equal to zero to specify an evaluation order for this argument.</span></span> <span data-ttu-id="0466f-132">Windows Workflow Foundation valuta gli argomenti con un ordine di valutazione specificato in ordine crescente.</span><span class="sxs-lookup"><span data-stu-id="0466f-132">Windows Workflow Foundation evaluates arguments with a specified evaluation order in ascending order.</span></span> <span data-ttu-id="0466f-133">Si noti che gli argomenti con un ordine di valutazione non specificato vengono valutati prima di quelli aventi un ordine di valutazione specificato.</span><span class="sxs-lookup"><span data-stu-id="0466f-133">Note that arguments with an unspecified evaluation order are evaluated before those with a specified evaluation order.</span></span>  
  
 <span data-ttu-id="0466f-134">Un autore di attività può usare un meccanismo fortemente tipizzato per esporre gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="0466f-134">An activity author can use a strongly-typed mechanism for exposing its arguments.</span></span> <span data-ttu-id="0466f-135">A tale scopo, vengono dichiarate proprietà di tipo <xref:System.Activities.InArgument%601>, <xref:System.Activities.OutArgument%601> e <xref:System.Activities.InOutArgument%601>.</span><span class="sxs-lookup"><span data-stu-id="0466f-135">This is accomplished by declaring properties of type <xref:System.Activities.InArgument%601>, <xref:System.Activities.OutArgument%601>, and <xref:System.Activities.InOutArgument%601>.</span></span> <span data-ttu-id="0466f-136">In questo modo un autore di attività può stabilire un contratto specifico sui dati in ingresso o in uscita da un'attività.</span><span class="sxs-lookup"><span data-stu-id="0466f-136">This allows an activity author to establish a specific contract about the data going into and out of an activity.</span></span>  
  
### <a name="defining-the-arguments-on-an-activity"></a><span data-ttu-id="0466f-137">Definizione di argomenti in un'attività</span><span class="sxs-lookup"><span data-stu-id="0466f-137">Defining the Arguments on an Activity</span></span>  
 <span data-ttu-id="0466f-138">Gli argomenti possono essere definiti in un'attività specificando proprietà di tipo <xref:System.Activities.InArgument%601>, <xref:System.Activities.OutArgument%601> e <xref:System.Activities.InOutArgument%601>.</span><span class="sxs-lookup"><span data-stu-id="0466f-138">Arguments can be defined on an activity by specifying properties of type <xref:System.Activities.InArgument%601>, <xref:System.Activities.OutArgument%601>, and <xref:System.Activities.InOutArgument%601>.</span></span> <span data-ttu-id="0466f-139">Nel codice seguente viene mostrato come definire gli argomenti per un'attività `Prompt` che include una stringa da visualizzare all'utente e restituisce una stringa che contiene la risposta dell'utente.</span><span class="sxs-lookup"><span data-stu-id="0466f-139">The following code shows how to define the arguments for a `Prompt` activity that takes in a string to display to the user and returns a string that contains the user's response.</span></span>  
  
```csharp  
public class Prompt : Activity  
{  
    public InArgument<string> Text { get; set; }  
    public OutArgument<string> Response { get; set; }  
    // Rest of activity definition omitted.  
}  
```  
  
> [!NOTE]
> <span data-ttu-id="0466f-140">Le attività che restituiscono un singolo valore possono derivare dagli oggetti  <xref:System.Activities.Activity%601>, <xref:System.Activities.NativeActivity%601> o <xref:System.Activities.CodeActivity%601>.</span><span class="sxs-lookup"><span data-stu-id="0466f-140">Activities that return a single value can derive from <xref:System.Activities.Activity%601>, <xref:System.Activities.NativeActivity%601>, or <xref:System.Activities.CodeActivity%601>.</span></span> <span data-ttu-id="0466f-141">Queste attività dispongono di un oggetto <xref:System.Activities.OutArgument%601> ben definito denominato <xref:System.Activities.Activity%601.Result%2A> che contiene il valore restituito dell'attività.</span><span class="sxs-lookup"><span data-stu-id="0466f-141">These activities have a well-defined <xref:System.Activities.OutArgument%601> named <xref:System.Activities.Activity%601.Result%2A> that contains the return value of the activity.</span></span>  
  
### <a name="using-variables-and-arguments-in-workflows"></a><span data-ttu-id="0466f-142">Uso di variabili e argomenti nei flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="0466f-142">Using Variables and Arguments in Workflows</span></span>  
 <span data-ttu-id="0466f-143">Nell'esempio seguente viene mostrato come vengono usati variabili e argomenti in un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0466f-143">The following example shows how variables and arguments are used in a workflow.</span></span> <span data-ttu-id="0466f-144">Il flusso di lavoro è una sequenza che dichiara tre variabili: `var1`, `var2` e `var3`.</span><span class="sxs-lookup"><span data-stu-id="0466f-144">The workflow is a sequence that declares three variables: `var1`, `var2`, and `var3`.</span></span> <span data-ttu-id="0466f-145">La prima attività nel flusso di lavoro è un'attività `Assign` che assegna il valore di variabile `var1` alla variabile `var2`.</span><span class="sxs-lookup"><span data-stu-id="0466f-145">The first activity in the workflow is an `Assign` activity that assigns the value of variable `var1` to the variable `var2`.</span></span> <span data-ttu-id="0466f-146">Questa attività è seguita da un'attività `WriteLine` che stampa il valore della variabile `var2`.</span><span class="sxs-lookup"><span data-stu-id="0466f-146">This is followed by a `WriteLine` activity that prints the value of the `var2` variable.</span></span> <span data-ttu-id="0466f-147">La successiva è un'altra attività `Assign` che assegna il valore di variabile `var2` alla variabile `var3`.</span><span class="sxs-lookup"><span data-stu-id="0466f-147">Next is another `Assign` activity that assigns the value of variable `var2` to the variable `var3`.</span></span> <span data-ttu-id="0466f-148">Infine è disponibile un'altra attività `WriteLine` che stampa il valore della variabile `var3`.</span><span class="sxs-lookup"><span data-stu-id="0466f-148">Finally there is another `WriteLine` activity that prints the value of the `var3` variable.</span></span> <span data-ttu-id="0466f-149">La prima attività `Assign` usa gli oggetti `InArgument<string>` e `OutArgument<string>` che rappresentano in modo esplicito le associazioni per gli argomenti dell'attività.</span><span class="sxs-lookup"><span data-stu-id="0466f-149">The first `Assign` activity uses `InArgument<string>` and `OutArgument<string>` objects that explicitly represent the bindings for the activity's arguments.</span></span> <span data-ttu-id="0466f-150">L'oggetto `InArgument<string>` viene usato per <xref:System.Activities.Statements.Assign.Value%2A> in quanto il valore passa nell'attività <xref:System.Activities.Statements.Assign%601> attraverso il relativo argomento <xref:System.Activities.Statements.Assign.Value%2A>; l'oggetto `OutArgument<string>` viene usato per <xref:System.Activities.Statements.Assign.To%2A> in quanto il valore passa dall'argomento <xref:System.Activities.Statements.Assign.To%2A> alla variabile.</span><span class="sxs-lookup"><span data-stu-id="0466f-150">`InArgument<string>` is used for <xref:System.Activities.Statements.Assign.Value%2A> because the value is flowing into the <xref:System.Activities.Statements.Assign%601> activity through its <xref:System.Activities.Statements.Assign.Value%2A> argument, and `OutArgument<string>` is used for <xref:System.Activities.Statements.Assign.To%2A> because the value is flowing out of the <xref:System.Activities.Statements.Assign.To%2A> argument into the variable.</span></span> <span data-ttu-id="0466f-151">La seconda attività `Assign` esegue la stessa operazione più compatta, ma con sintassi equivalente che usa cast impliciti.</span><span class="sxs-lookup"><span data-stu-id="0466f-151">The second `Assign` activity accomplishes the same thing with more compact but equivalent syntax that uses implicit casts.</span></span> <span data-ttu-id="0466f-152">Anche le attività `WriteLine` usano la sintassi compatta.</span><span class="sxs-lookup"><span data-stu-id="0466f-152">The `WriteLine` activities also use the compact syntax.</span></span>  
  
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
  
### <a name="using-variables-and-arguments-in-code-based-activities"></a><span data-ttu-id="0466f-153">Uso di variabili e argomenti in attività basate su codice</span><span class="sxs-lookup"><span data-stu-id="0466f-153">Using Variables and Arguments in Code-Based Activities</span></span>  
 <span data-ttu-id="0466f-154">Negli esempi precedenti viene mostrato come usare argomenti e variabili in flussi di lavoro e attività dichiarative.</span><span class="sxs-lookup"><span data-stu-id="0466f-154">The previous examples show how to use arguments and variables in workflows and declarative activities.</span></span> <span data-ttu-id="0466f-155">Gli argomenti e le variabili vengono usati anche in attività basate su codice.</span><span class="sxs-lookup"><span data-stu-id="0466f-155">Arguments and variables are also used in code-based activities.</span></span> <span data-ttu-id="0466f-156">Dal punto di vista concettuale l'uso è molto simile.</span><span class="sxs-lookup"><span data-stu-id="0466f-156">Conceptually the usage is very similar.</span></span> <span data-ttu-id="0466f-157">Le variabili rappresentano l'archivio dati all'interno dell'attività, mentre gli argomenti rappresentano il flusso di dati all'interno o all'esterno dell'attività e vengono associati dall'autore del flusso di lavoro alle altre variabili o argomenti nel flusso di lavoro che rappresentano il punto dal quale o verso il quale fluiscono i dati.</span><span class="sxs-lookup"><span data-stu-id="0466f-157">Variables represent data storage within the activity, and arguments represent the flow of data into or out of the activity, and are bound by the workflow author to other variables or arguments in the workflow that represent where the data flows to or from.</span></span> <span data-ttu-id="0466f-158">Per ottenere o impostare il valore di una variabile o di un argomento in un'attività, deve essere usato un contesto di attività che rappresenta l'ambiente di esecuzione corrente dell'attività.</span><span class="sxs-lookup"><span data-stu-id="0466f-158">To get or set the value of a variable or argument in an activity, an activity context must be used that represents the current execution environment of the activity.</span></span> <span data-ttu-id="0466f-159">Questo viene passato nel metodo <xref:System.Activities.CodeActivity%601.Execute%2A> dell'attività dall'esecuzione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0466f-159">This is passed into the <xref:System.Activities.CodeActivity%601.Execute%2A> method of the activity by the workflow runtime.</span></span> <span data-ttu-id="0466f-160">In questo esempio viene definita un'attività `Add` personalizzata che dispone di due argomenti <xref:System.Activities.ArgumentDirection.In>.</span><span class="sxs-lookup"><span data-stu-id="0466f-160">In this example, a custom `Add` activity is defined that has two <xref:System.Activities.ArgumentDirection.In> arguments.</span></span> <span data-ttu-id="0466f-161">Per accedere al valore degli argomenti, vengono usati il metodo <xref:System.Activities.Argument.Get%2A> e il contesto passato dall'esecuzione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0466f-161">To access the value of the arguments, the <xref:System.Activities.Argument.Get%2A> method is used and the context that was passed in by the workflow runtime is used.</span></span>  
  
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
  
 <span data-ttu-id="0466f-162">Per ulteriori informazioni sull'utilizzo di argomenti, variabili ed espressioni nel codice, vedere [creazione di flussi di lavoro, attività ed espressioni tramite codice imperativo](authoring-workflows-activities-and-expressions-using-imperative-code.md) e [argomenti obbligatori e gruppi di overload](required-arguments-and-overload-groups.md).</span><span class="sxs-lookup"><span data-stu-id="0466f-162">For more information about working with arguments, variables, and expressions in code, see [Authoring Workflows, Activities, and Expressions Using Imperative Code](authoring-workflows-activities-and-expressions-using-imperative-code.md) and [Required Arguments and Overload Groups](required-arguments-and-overload-groups.md).</span></span>
