---
title: Richiamo della convalida di attività
ms.date: 03/30/2017
ms.assetid: 22bef766-c505-4fd4-ac0f-7b363b238969
ms.openlocfilehash: b45840081f5fc142cf3ec88853dea984b204c9d0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934971"
---
# <a name="invoking-activity-validation"></a><span data-ttu-id="9d5bb-102">Richiamo della convalida di attività</span><span class="sxs-lookup"><span data-stu-id="9d5bb-102">Invoking Activity Validation</span></span>
<span data-ttu-id="9d5bb-103">La convalida delle attività offre un metodo per identificare e segnalare errori nella configurazione di qualsiasi attività prima della relativa esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-103">Activity validation provides a method to identify and report errors in any activity’s configuration prior to its execution.</span></span> <span data-ttu-id="9d5bb-104">Viene eseguita quando un flusso di lavoro viene modificato nell'utilità di progettazione del flusso di lavoro e gli eventuali errori o avvisi di convalida vengono visualizzati in tale utilità.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-104">Validation occurs when a workflow is modified in the workflow designer and any validation errors or warnings are displayed in the workflow designer.</span></span> <span data-ttu-id="9d5bb-105">La convalida avviene anche in fase di esecuzione quando un flusso di lavoro viene richiamato e, se si verificano errori di convalida, viene generata un'eccezione <xref:System.Activities.InvalidWorkflowException> dalla logica di convalida predefinita.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-105">Validation also occurs at run time when a workflow is invoked and if any validation errors occur, an <xref:System.Activities.InvalidWorkflowException> is thrown by the default validation logic.</span></span> <span data-ttu-id="9d5bb-106">Windows Workflow Foundation (WF) fornisce la <xref:System.Activities.Validation.ActivityValidationServices> classe che può essere utilizzata dagli sviluppatori di applicazioni e strumenti del flusso di lavoro per convalidare in modo esplicito un'attività.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-106">Windows Workflow Foundation (WF) provides the <xref:System.Activities.Validation.ActivityValidationServices> class that can be used by workflow application and tooling developers to explicitly validate an activity.</span></span> <span data-ttu-id="9d5bb-107">In questo argomento viene descritto come usare l'oggetto <xref:System.Activities.Validation.ActivityValidationServices> per eseguire la convalida delle attività.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-107">This topic describes how to use <xref:System.Activities.Validation.ActivityValidationServices> to perform activity validation.</span></span>  
  
## <a name="using-activityvalidationservices"></a><span data-ttu-id="9d5bb-108">Uso di ActivityValidationServices</span><span class="sxs-lookup"><span data-stu-id="9d5bb-108">Using ActivityValidationServices</span></span>  
 <span data-ttu-id="9d5bb-109">L'oggetto <xref:System.Activities.Validation.ActivityValidationServices> dispone di due overload <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> usati per richiamare la logica di convalida di un'attività.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-109"><xref:System.Activities.Validation.ActivityValidationServices> has two <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> overloads that are used to invoke an activity’s validation logic.</span></span> <span data-ttu-id="9d5bb-110">Il primo overload accetta l'attività radice da convalidare e restituisce una raccolta di errori e di avvisi di convalida.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-110">The first overload takes the root activity to be validated and returns a collection of validation errors and warnings.</span></span> <span data-ttu-id="9d5bb-111">Nell'esempio seguente viene usata un'attività `Add` personalizzata con due argomenti obbligatori.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-111">In the following example, a custom `Add` activity is used that has two required arguments.</span></span>  
  
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
  
 <span data-ttu-id="9d5bb-112">L'attività `Add` viene usata all'interno di un oggetto <xref:System.Activities.Statements.Sequence>, ma i due relativi argomenti obbligatori non sono associati, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-112">The `Add` activity is used inside a <xref:System.Activities.Statements.Sequence>, but its two required arguments are not bound, as shown in the following example.</span></span>  
  
```csharp  
Variable<int> Operand1 = new Variable<int>{ Default = 10 };  
Variable<int> Operand2 = new Variable<int>{ Default = 15 };  
Variable<int> Result = new Variable<int>();  
  
Activity wf = new Sequence  
{  
    Variables = { Operand1, Operand2, Result },  
    Activities =   
    {  
        new Add(),  
        new WriteLine  
        {  
            Text = new InArgument<string>(env => "The result is " + Result.Get(env))  
        }  
    }  
};  
```  
  
 <span data-ttu-id="9d5bb-113">Questo flusso di lavoro può essere convalidato chiamando <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-113">This workflow can be validated by calling <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>.</span></span> <span data-ttu-id="9d5bb-114"><xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> restituisce una raccolta di tutti gli avvisi e gli errori di convalida contenuti nell'attività e negli elementi figlio, come mostrato nell'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-114"><xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> returns a collection of any validation errors or warnings contained by the activity and any children, as shown in the following example.</span></span>  
  
```csharp  
ValidationResults results = ActivityValidationServices.Validate(wf);  
  
if (results.Errors.Count == 0 && results.Warnings.Count == 0)  
{  
    Console.WriteLine("No warnings or errors");  
}  
else  
{  
    foreach (ValidationError error in results.Errors)  
    {  
        Console.WriteLine("Error: {0}", error.Message);  
    }  
    foreach (ValidationError warning in results.Warnings)  
    {  
        Console.WriteLine("Warning: {0}", warning.Message);  
    }  
}  
```  
  
 <span data-ttu-id="9d5bb-115">Quando il metodo <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> viene chiamato in questo flusso di lavoro di esempio, vengono restituiti due errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-115">When <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> is called on this sample workflow, two validation errors are returned.</span></span>  
  
 <span data-ttu-id="9d5bb-116">**Errore: Valore non specificato per un argomento di attività' operand2' obbligatorio.**</span><span class="sxs-lookup"><span data-stu-id="9d5bb-116">**Error: Value for a required activity argument 'Operand2' was not supplied.**</span></span>  
<span data-ttu-id="9d5bb-117">**Errore: Valore non specificato per un argomento di attività' Operand1' obbligatorio.**</span><span class="sxs-lookup"><span data-stu-id="9d5bb-117">**Error: Value for a required activity argument 'Operand1' was not supplied.**</span></span>  <span data-ttu-id="9d5bb-118">Se questo flusso di lavoro viene richiamato, viene generata un'eccezione <xref:System.Activities.InvalidWorkflowException>, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-118">If this workflow was invoked, an <xref:System.Activities.InvalidWorkflowException> would be thrown, as shown in the following example.</span></span>  
  
```csharp  
try  
{  
    WorkflowInvoker.Invoke(wf);  
}  
catch (Exception ex)  
{  
    Console.WriteLine(ex);  
}  
```  
  
 <span data-ttu-id="9d5bb-119">**System.Activities.InvalidWorkflowException:**</span><span class="sxs-lookup"><span data-stu-id="9d5bb-119">**System.Activities.InvalidWorkflowException:**</span></span>  
<span data-ttu-id="9d5bb-120">**Durante l'elaborazione dell'albero del flusso di lavoro sono stati rilevati gli errori seguenti:**  </span><span class="sxs-lookup"><span data-stu-id="9d5bb-120">**The following errors were encountered while processing the workflow tree:** </span></span>  
<span data-ttu-id="9d5bb-121">**' Aggiungi ': Valore non specificato per un argomento di attività' operand2' obbligatorio.**  </span><span class="sxs-lookup"><span data-stu-id="9d5bb-121">**'Add': Value for a required activity argument 'Operand2' was not supplied.** </span></span>  
<span data-ttu-id="9d5bb-122">**' Aggiungi ': Valore non specificato per un argomento di attività' Operand1' obbligatorio.**</span><span class="sxs-lookup"><span data-stu-id="9d5bb-122">**'Add': Value for a required activity argument 'Operand1' was not supplied.**</span></span>  <span data-ttu-id="9d5bb-123">Affinché questo flusso di lavoro di esempio sia valido, è necessario associare i due argomenti obbligatori dell'attività `Add`.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-123">For this example workflow to be valid, the two required arguments of the `Add` activity must be bound.</span></span> <span data-ttu-id="9d5bb-124">Nell'esempio seguente i due argomenti obbligatori vengono associati alle variabili del flusso di lavoro insieme al valore di risultato.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-124">In the following example, the two required arguments are bound to workflow variables along with the result value.</span></span> <span data-ttu-id="9d5bb-125">In questo esempio l'argomento <xref:System.Activities.Activity%601.Result%2A> viene associato insieme ai due argomenti obbligatori.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-125">In this example the <xref:System.Activities.Activity%601.Result%2A> argument is bound along with the two required arguments.</span></span> <span data-ttu-id="9d5bb-126">L'argomento <xref:System.Activities.Activity%601.Result%2A> non deve essere associato e tale condizione non genera un errore di convalida.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-126">The <xref:System.Activities.Activity%601.Result%2A> argument is not required to be bound and does not cause a validation error if it is not.</span></span> <span data-ttu-id="9d5bb-127">È compito dell'autore del flusso di lavoro associare la proprietà <xref:System.Activities.Activity%601.Result%2A> qualora il relativo valore venisse usato in altri punti all'interno del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-127">It is the responsibility of the workflow author to bind <xref:System.Activities.Activity%601.Result%2A> if its value is used elsewhere in the workflow.</span></span>  
  
```csharp  
new Add  
{  
    Operand1 = Operand1,  
    Operand2 = Operand2,  
    Result = Result  
}  
```  
  
### <a name="validating-required-arguments-on-the-root-activity"></a><span data-ttu-id="9d5bb-128">Convalida di argomenti obbligatori nell'attività radice</span><span class="sxs-lookup"><span data-stu-id="9d5bb-128">Validating Required Arguments on the Root Activity</span></span>  
 <span data-ttu-id="9d5bb-129">Se l'attività radice di un flusso di lavoro dispone di argomenti, questi vengono associati solo quando il flusso di lavoro viene richiamato e i parametri vengono passati al flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-129">If the root activity of a workflow has arguments, these are not bound until the workflow is invoked and parameters are passed to the workflow.</span></span> <span data-ttu-id="9d5bb-130">Il seguente flusso di lavoro supera la convalida, ma viene generata un'eccezione se il flusso di lavoro viene richiamato senza passare gli argomenti obbligatori, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-130">The following workflow passes validation, but an exception is thrown if the workflow is invoked without passing in the required arguments, as shown in the following example.</span></span>  
  
```csharp  
Activity wf = new Add();  
  
ValidationResults results = ActivityValidationServices.Validate(wf);  
// results has no errors or warnings, but when the workflow  
// is invoked, an InvalidWorkflowException is thrown.  
try  
{  
    WorkflowInvoker.Invoke(wf);  
}  
catch (Exception ex)  
{  
    Console.WriteLine(ex);  
}  
```  
  
 <span data-ttu-id="9d5bb-131">**System.ArgumentException: Le impostazioni degli argomenti dell'attività radice non sono corrette.**</span><span class="sxs-lookup"><span data-stu-id="9d5bb-131">**System.ArgumentException: The root activity's argument settings are incorrect.**</span></span>  
<span data-ttu-id="9d5bb-132">**Correggere la definizione del flusso di lavoro o fornire i valori di input per correggere gli errori:**  </span><span class="sxs-lookup"><span data-stu-id="9d5bb-132">**Either fix the workflow definition or supply input values to fix these errors:** </span></span>  
<span data-ttu-id="9d5bb-133">**' Aggiungi ': Valore non specificato per un argomento di attività' operand2' obbligatorio.**  </span><span class="sxs-lookup"><span data-stu-id="9d5bb-133">**'Add': Value for a required activity argument 'Operand2' was not supplied.** </span></span>  
<span data-ttu-id="9d5bb-134">**' Aggiungi ': Valore non specificato per un argomento di attività' Operand1' obbligatorio.**</span><span class="sxs-lookup"><span data-stu-id="9d5bb-134">**'Add': Value for a required activity argument 'Operand1' was not supplied.**</span></span>  <span data-ttu-id="9d5bb-135">Una volta passati gli argomenti appropriati, il flusso di lavoro viene completato correttamente, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-135">After the correct arguments are passed, the workflow completes successfully, as shown in the following example.</span></span>  
  
```csharp  
Add wf = new Add();  
  
ValidationResults results = ActivityValidationServices.Validate(wf);  
// results has no errors or warnings, and the workflow completes  
// successfully because the required arguments were passed.  
try  
{  
    Dictionary<string, object> wfparams = new Dictionary<string, object>  
    {  
        { "Operand1", 10 },  
        { "Operand2", 15 }  
    };  
  
    int result = WorkflowInvoker.Invoke(wf, wfparams);  
    Console.WriteLine("Result: {0}", result);  
}  
catch (Exception ex)  
{  
    Console.WriteLine(ex);  
}  
```  
  
> [!NOTE]
> <span data-ttu-id="9d5bb-136">In questo esempio l'attività radice è stata dichiarata come `Add` anziché `Activity` come nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-136">In this example, the root activity was declared as `Add` instead of `Activity` as in the previous example.</span></span> <span data-ttu-id="9d5bb-137">In questo modo il metodo `WorkflowInvoker.Invoke` può restituire un solo Integer che rappresenta i risultati dell'attività `Add` anziché un dizionario di argomenti `out`.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-137">This allows the `WorkflowInvoker.Invoke` method to return a single integer that represents the results of the `Add` activity instead of a dictionary of `out` arguments.</span></span> <span data-ttu-id="9d5bb-138">Anche la variabile `wf` può essere stata dichiarata come `Activity<int>`.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-138">The variable `wf` could also have been declared as `Activity<int>`.</span></span>  
  
 <span data-ttu-id="9d5bb-139">In caso di convalida di argomenti radice, è compito dell'applicazione host assicurare che vengano passati tutti gli argomenti obbligatori quando viene richiamato il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-139">When validating root arguments, it is the responsibility of the host application to ensure that all required arguments are passed when the workflow is invoked.</span></span>  
  
### <a name="invoking-imperative-code-based-validation"></a><span data-ttu-id="9d5bb-140">Chiamata della convalida basata su codice imperativo</span><span class="sxs-lookup"><span data-stu-id="9d5bb-140">Invoking Imperative Code-Based Validation</span></span>

<span data-ttu-id="9d5bb-141">La convalida basata su codice imperativo fornisce un modo semplice per la convalida automatica di un'attività ed è disponibile per le attività che derivano dagli oggetti <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> e <xref:System.Activities.NativeActivity>.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-141">Imperative code-based validation provides a simple way for an activity to provide validation about itself, and is available for activities that derive from <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, and <xref:System.Activities.NativeActivity>.</span></span> <span data-ttu-id="9d5bb-142">Il codice di convalida che determina qualsiasi errore o avviso di convalida viene aggiunto all'attività.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-142">Validation code that determines any validation errors or warnings is added to the activity.</span></span> <span data-ttu-id="9d5bb-143">Quando la convalida viene richiamata sull'attività, questi avvisi o errori sono contenuti nella raccolta restituita dalla chiamata a <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-143">When validation is invoked on the activity, these warnings or errors are contained in the collection returned by the call to <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>.</span></span> <span data-ttu-id="9d5bb-144">Nell'esempio seguente viene definita un'attività `CreateProduct` .</span><span class="sxs-lookup"><span data-stu-id="9d5bb-144">In the following example, a `CreateProduct` activity is defined.</span></span> <span data-ttu-id="9d5bb-145">Se `Cost` è maggiore di `Price`, viene aggiunto un errore di convalida ai metadati nell'override di <xref:System.Activities.CodeActivity.CacheMetadata%2A>.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-145">If the `Cost` is greater than the `Price`, a validation error is added to the metadata in the <xref:System.Activities.CodeActivity.CacheMetadata%2A> override.</span></span>  
  
```csharp  
public sealed class CreateProduct : CodeActivity  
{  
    public double Price { get; set; }  
    public double Cost { get; set; }  
  
    // [RequiredArgument] attribute will generate a validation error   
    // if the Description argument is not set.  
    [RequiredArgument]  
    public InArgument<string> Description { get; set; }  
  
    protected override void CacheMetadata(CodeActivityMetadata metadata)  
    {  
        base.CacheMetadata(metadata);  
        // Determine when the activity has been configured in an invalid way.  
        if (this.Cost > this.Price)  
        {  
            // Add a validation error with a custom message.  
            metadata.AddValidationError("The Cost must be less than or equal to the Price.");  
        }  
    }  
  
    protected override void Execute(CodeActivityContext context)  
    {  
        // Not needed for the sample.  
    }  
}  
```  
  
 <span data-ttu-id="9d5bb-146">In questo esempio, un flusso di lavoro viene configurato usando l'attività `CreateProduct`.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-146">In this example, a workflow is configured using the `CreateProduct` activity.</span></span> <span data-ttu-id="9d5bb-147">In questo flusso di lavoro, `Cost` è maggiore di `Price` e l'argomento obbligatorio `Description` non è impostato.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-147">In this workflow, the `Cost` is greater than the `Price`, and the required `Description` argument is not set.</span></span> <span data-ttu-id="9d5bb-148">Quando viene richiamata la convalida, vengono restituiti gli errori seguenti.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-148">When validation is invoked, the following errors are returned.</span></span>  
  
```csharp  
Activity wf = new Sequence  
{  
    Activities =   
    {  
        new CreateProduct  
        {  
            Cost = 75.00,  
            Price = 55.00  
            // Cost > Price and required Description argument not set.  
        },  
        new WriteLine  
        {  
            Text = "Product added."  
        }  
    }  
};  
  
ValidationResults results = ActivityValidationServices.Validate(wf);  
  
if (results.Errors.Count == 0 && results.Warnings.Count == 0)  
{  
    Console.WriteLine("No warnings or errors");  
}  
else  
{  
    foreach (ValidationError error in results.Errors)  
    {  
        Console.WriteLine("Error: {0}", error.Message);  
    }  
    foreach (ValidationError warning in results.Warnings)  
    {  
        Console.WriteLine("Warning: {0}", warning.Message);  
    }  
}  
```  
  
 <span data-ttu-id="9d5bb-149">**Errore: Il costo deve essere minore o uguale al prezzo.**</span><span class="sxs-lookup"><span data-stu-id="9d5bb-149">**Error: The Cost must be less than or equal to the Price.**</span></span>  
<span data-ttu-id="9d5bb-150">**Errore: Il valore per un argomento di attività' Description ' obbligatorio non è stato specificato.**</span><span class="sxs-lookup"><span data-stu-id="9d5bb-150">**Error: Value for a required activity argument 'Description' was not supplied.**</span></span>    
> [!NOTE]
> <span data-ttu-id="9d5bb-151">Gli autori di attività personalizzate possono fornire la logica di convalida nell'override di un'attività <xref:System.Activities.CodeActivity.CacheMetadata%2A>.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-151">Custom activity authors can provide validation logic in an activity's <xref:System.Activities.CodeActivity.CacheMetadata%2A> override.</span></span> <span data-ttu-id="9d5bb-152">Qualsiasi eccezione generata dal metodo <xref:System.Activities.CodeActivity.CacheMetadata%2A> non viene considerata come errore di convalida.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-152">Any exceptions that are thrown from <xref:System.Activities.CodeActivity.CacheMetadata%2A> are not treated as validation errors.</span></span> <span data-ttu-id="9d5bb-153">Queste eccezioni saranno escluse dalla chiamata all'oggetto <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> e devono essere gestite dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-153">These exceptions will escape from the call to <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> and must be handled by the caller.</span></span>  
  
## <a name="using-validationsettings"></a><span data-ttu-id="9d5bb-154">Utilizzo dell'oggetto ValidationSettings</span><span class="sxs-lookup"><span data-stu-id="9d5bb-154">Using ValidationSettings</span></span>  
 <span data-ttu-id="9d5bb-155">Per impostazione predefinita, tutte le attività nell'albero delle attività vengono valutate quando la convalida viene richiamata da <xref:System.Activities.Validation.ActivityValidationServices>.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-155">By default, all activities in the activity tree are evaluated when validation is invoked by <xref:System.Activities.Validation.ActivityValidationServices>.</span></span> <span data-ttu-id="9d5bb-156"><xref:System.Activities.Validation.ValidationSettings> consente di personalizzare la convalida in vari modi attraverso la configurazione delle relative tre proprietà.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-156"><xref:System.Activities.Validation.ValidationSettings> allows the validation to be customized in several different ways by configuring its three properties.</span></span> <span data-ttu-id="9d5bb-157"><xref:System.Activities.Validation.ValidationSettings.SingleLevel%2A> specifica se il validator deve analizzare l'intero albero delle attività o applicare semplicemente la logica di convalida all'attività fornita.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-157"><xref:System.Activities.Validation.ValidationSettings.SingleLevel%2A> specifies whether the validator should walk the entire activity tree or only apply validation logic to the supplied activity.</span></span> <span data-ttu-id="9d5bb-158">L'impostazione predefinita per questo valore è `false`.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-158">The default for this value is `false`.</span></span> <span data-ttu-id="9d5bb-159"><xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> specifica il mapping di vincoli aggiuntivi da un tipo a un elenco di vincoli.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-159"><xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> specifies additional constraint mapping from a type to a list of constraints.</span></span> <span data-ttu-id="9d5bb-160">Per il tipo base di ogni attività nell'albero delle attività convalidata è disponibile una ricerca nella proprietà <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A>.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-160">For the base type of each activity in the activity tree being validated there is a lookup into <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A>.</span></span> <span data-ttu-id="9d5bb-161">Se viene individuato un elenco di vincoli corrispondente, tutti i vincoli nell'elenco vengono valutati per l'attività.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-161">If a matching constraint list is found, all constraints in the list are evaluated for the activity.</span></span> <span data-ttu-id="9d5bb-162"><xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A> specifica se tutti i vincoli o solo quelli specificati in <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> devono essere valutati dal validator.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-162"><xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A> specifies whether the validator should evaluate all constraints or only those specified in <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A>.</span></span> <span data-ttu-id="9d5bb-163">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-163">The default value is `false`.</span></span> <span data-ttu-id="9d5bb-164">Gli autori di host del flusso di lavoro usano <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> e <xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A> per aggiungere un'ulteriore convalida ai flussi di lavoro, quali i vincoli di criteri per strumenti come FxCop.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-164"><xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> and <xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A> are useful for workflow host authors to add additional validation for workflows, such as policy constraints for tools such as FxCop.</span></span> <span data-ttu-id="9d5bb-165">Per ulteriori informazioni sui vincoli, vedere [vincoli](declarative-constraints.md)dichiarativi.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-165">For more information about constraints, see [Declarative Constraints](declarative-constraints.md).</span></span>  
  
 <span data-ttu-id="9d5bb-166">Per usare l'oggetto <xref:System.Activities.Validation.ValidationSettings>, configurare le proprietà desiderate, quindi passarlo nella chiamata al metodo <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-166">To use <xref:System.Activities.Validation.ValidationSettings>, configure the desired properties, and then pass it in the call to <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>.</span></span> <span data-ttu-id="9d5bb-167">In questo esempio viene convalidato un flusso di lavoro che è costituito da un oggetto <xref:System.Activities.Statements.Sequence> con un'attività `Add` personalizzata.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-167">In this example, a workflow that consists of a <xref:System.Activities.Statements.Sequence> with a custom `Add` activity is validated.</span></span> <span data-ttu-id="9d5bb-168">L'attività `Add` dispone di due argomenti obbligatori.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-168">The `Add` activity has two required arguments.</span></span>  
  
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
  
 <span data-ttu-id="9d5bb-169">L'attività `Add` seguente viene usata in un oggetto <xref:System.Activities.Statements.Sequence>, ma i due argomenti obbligatori non sono associati.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-169">The following `Add` activity is used in a <xref:System.Activities.Statements.Sequence>, but its two required arguments are not bound.</span></span>  
  
```csharp  
Variable<int> Operand1 = new Variable<int> { Default = 10 };  
Variable<int> Operand2 = new Variable<int> { Default = 15 };  
Variable<int> Result = new Variable<int>();  
  
Activity wf = new Sequence  
{  
    Variables = { Operand1, Operand2, Result },  
    Activities =   
    {  
        new Add(),  
        new WriteLine  
        {  
            Text = new InArgument<string>(env => "The result is " + Result.Get(env))  
        }  
    }  
};  
```  
  
 <span data-ttu-id="9d5bb-170">Per l'esempio seguente, la convalida viene eseguita con la proprietà <xref:System.Activities.Validation.ValidationSettings.SingleLevel%2A> impostata su `true`, pertanto solo l'attività <xref:System.Activities.Statements.Sequence> radice viene convalidata.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-170">For the following example, validation is performed with <xref:System.Activities.Validation.ValidationSettings.SingleLevel%2A> set to `true`, so only the root <xref:System.Activities.Statements.Sequence> activity is validated.</span></span>  
  
```csharp  
ValidationSettings settings = new ValidationSettings  
{  
    SingleLevel = true  
};  
  
ValidationResults results = ActivityValidationServices.Validate(wf, settings);  
  
if (results.Errors.Count == 0 && results.Warnings.Count == 0)  
{  
    Console.WriteLine("No warnings or errors");  
}  
else  
{  
    foreach (ValidationError error in results.Errors)  
    {  
        Console.WriteLine("Error: {0}", error.Message);  
    }  
    foreach (ValidationError warning in results.Warnings)  
    {  
        Console.WriteLine("Warning: {0}", warning.Message);  
    }  
}  
```  
  
 <span data-ttu-id="9d5bb-171">Di seguito viene visualizzato l'output del codice:</span><span class="sxs-lookup"><span data-stu-id="9d5bb-171">This code displays the following output:</span></span>  
  
 <span data-ttu-id="9d5bb-172">**Nessun avviso o errore** Anche se l' `Add` attività dispone di argomenti obbligatori che non sono associati, la convalida ha esito positivo perché viene valutata solo l'attività radice.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-172">**No warnings or errors** Even though the `Add` activity has required arguments that are not bound, validation is successful because only the root activity is evaluated.</span></span> <span data-ttu-id="9d5bb-173">Questo tipo di convalida è utile per convalidare solo elementi specifici in un albero delle attività, ad esempio la convalida di una modifica a una proprietà di una singola attività in una finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-173">This type of validation is useful for validating only specific elements in an activity tree, such as validation of a property change of a single activity in a designer.</span></span> <span data-ttu-id="9d5bb-174">Si noti che se questo flusso di lavoro viene richiamato, viene valutata l'intera convalida configurata nel flusso di lavoro ed eventualmente viene generata un'eccezione <xref:System.Activities.InvalidWorkflowException>.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-174">Note that if this workflow is invoked, the full validation configured in the workflow is evaluated and an <xref:System.Activities.InvalidWorkflowException> would be thrown.</span></span> <span data-ttu-id="9d5bb-175"><xref:System.Activities.Validation.ActivityValidationServices> e <xref:System.Activities.Validation.ValidationSettings> configurano solo la convalida richiamata in modo esplicito dall'host e non la convalida che viene eseguita quando un flusso di lavoro viene richiamato.</span><span class="sxs-lookup"><span data-stu-id="9d5bb-175"><xref:System.Activities.Validation.ActivityValidationServices> and <xref:System.Activities.Validation.ValidationSettings> configure only validation explicitly invoked by the host, and not the validation that occurs when a workflow is invoked.</span></span>
