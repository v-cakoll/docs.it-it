---
title: Convalida basata su codice imperativo
ms.date: 03/30/2017
ms.assetid: ae12537c-455e-42b1-82f4-cea4c46c023e
ms.openlocfilehash: f3b07d0ab06b3753286c929b90e713a6941684ad
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143096"
---
# <a name="imperative-code-based-validation"></a><span data-ttu-id="60e9f-102">Convalida basata su codice imperativo</span><span class="sxs-lookup"><span data-stu-id="60e9f-102">Imperative Code-Based Validation</span></span>

<span data-ttu-id="60e9f-103">La convalida basata su codice imperativo fornisce un modo semplice per la convalida automatica di un'attività ed è disponibile per le attività che derivano dagli oggetti <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> e <xref:System.Activities.NativeActivity>.</span><span class="sxs-lookup"><span data-stu-id="60e9f-103">Imperative code-based validation provides a simple way for an activity to provide validation about itself, and is available for activities that derive from <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, and <xref:System.Activities.NativeActivity>.</span></span> <span data-ttu-id="60e9f-104">Il codice di convalida che determina qualsiasi errore o avviso di convalida viene aggiunto all'attività.</span><span class="sxs-lookup"><span data-stu-id="60e9f-104">Validation code that determines any validation errors or warnings is added to the activity.</span></span>  
  
## <a name="using-code-based-validation"></a><span data-ttu-id="60e9f-105">Utilizzo della convalida basata su codice</span><span class="sxs-lookup"><span data-stu-id="60e9f-105">Using Code-Based Validation</span></span>

<span data-ttu-id="60e9f-106">La convalida basata su codice è supportata dalle attività che derivano dagli oggetti <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> e <xref:System.Activities.NativeActivity>.</span><span class="sxs-lookup"><span data-stu-id="60e9f-106">Code-based validation is supported by activities that derive from <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, and <xref:System.Activities.NativeActivity>.</span></span> <span data-ttu-id="60e9f-107">Il codice di convalida può essere inserito nell'override <xref:System.Activities.CodeActivity.CacheMetadata%2A> e gli errori o gli avvisi di convalida possono essere aggiunti all'argomento dei metadati.</span><span class="sxs-lookup"><span data-stu-id="60e9f-107">Validation code can be placed in the <xref:System.Activities.CodeActivity.CacheMetadata%2A> override, and validation errors or warnings can be added to the metadata argument.</span></span> <span data-ttu-id="60e9f-108">Nell'esempio seguente se `Cost` è maggiore di `Price`, ai metadati viene aggiunto un errore di convalida.</span><span class="sxs-lookup"><span data-stu-id="60e9f-108">In the following example, if the `Cost` is greater than the `Price`, a validation error is added to the metadata.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="60e9f-109">Si noti che `Cost` e `Price` non sono argomenti dell'attività, ma proprietà impostate in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="60e9f-109">Note that `Cost` and `Price` are not arguments to the activity, but are properties that are set at design time.</span></span> <span data-ttu-id="60e9f-110">Per questo motivo i valori possono essere convalidati nell'override <xref:System.Activities.CodeActivity.CacheMetadata%2A>.</span><span class="sxs-lookup"><span data-stu-id="60e9f-110">That is why their values can be validated in the <xref:System.Activities.CodeActivity.CacheMetadata%2A> override.</span></span> <span data-ttu-id="60e9f-111">Il valore dei dati passati mediante un argomento non può essere convalidato in fase di progettazione perché i dati non si propagano fino alla fase di esecuzione, ma gli argomenti dell'attività possono essere convalidati per assicurarsi che siano associati usano i gruppi di overload e di attributo `RequiredArgument`.</span><span class="sxs-lookup"><span data-stu-id="60e9f-111">The value of the data flowing through an argument cannot be validated at design time because the data does not flow until run time, but activity arguments can be validated to ensure that they are bound by using the `RequiredArgument` attribute and overload groups.</span></span> <span data-ttu-id="60e9f-112">Questo codice di esempio rileva l'attributo `RequiredArgument` per l'argomento `Description` e, se non è associato, viene generato un errore di convalida.</span><span class="sxs-lookup"><span data-stu-id="60e9f-112">This example code sees the `RequiredArgument` attribute for the `Description` argument, and if it is not bound then a validation error is generated.</span></span> <span data-ttu-id="60e9f-113">Gli argomenti obbligatori sono descritti in [Argomenti obbligatori e Gruppi di overload](required-arguments-and-overload-groups.md).</span><span class="sxs-lookup"><span data-stu-id="60e9f-113">Required arguments are covered in [Required Arguments and Overload Groups](required-arguments-and-overload-groups.md).</span></span>  
  
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
  
 <span data-ttu-id="60e9f-114">Per impostazione predefinita, un errore di convalida viene aggiunto ai metadati quando viene chiamato il metodo <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A>.</span><span class="sxs-lookup"><span data-stu-id="60e9f-114">By default, a validation error is added to the metadata when <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A> is called.</span></span> <span data-ttu-id="60e9f-115">Per aggiungere un avviso di convalida, usare l'overload <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A> che accetta un oggetto <xref:System.Activities.Validation.ValidationError> e specificare che l'oggetto <xref:System.Activities.Validation.ValidationError> rappresenta un avviso impostando la proprietà <xref:System.Activities.Validation.ValidationError.IsWarning%2A>.</span><span class="sxs-lookup"><span data-stu-id="60e9f-115">To add a validation warning, use the <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A> overload that takes a <xref:System.Activities.Validation.ValidationError>, and specify that the <xref:System.Activities.Validation.ValidationError> represents a warning by setting the <xref:System.Activities.Validation.ValidationError.IsWarning%2A> property.</span></span>  
  
 <span data-ttu-id="60e9f-116">Viene eseguita quando un flusso di lavoro viene modificato nell'utilità di progettazione del flusso di lavoro e gli eventuali errori o avvisi di convalida vengono visualizzati in tale utilità.</span><span class="sxs-lookup"><span data-stu-id="60e9f-116">Validation occurs when a workflow is modified in the workflow designer and any validation errors or warnings are displayed in the workflow designer.</span></span> <span data-ttu-id="60e9f-117">La convalida avviene anche in fase di esecuzione quando un flusso di lavoro viene richiamato e, se si verificano errori di convalida, viene generata un'eccezione <xref:System.Activities.InvalidWorkflowException> dalla logica di convalida predefinita.</span><span class="sxs-lookup"><span data-stu-id="60e9f-117">Validation also occurs at run time when a workflow is invoked and if any validation errors occur, an <xref:System.Activities.InvalidWorkflowException> is thrown by the default validation logic.</span></span> <span data-ttu-id="60e9f-118">Per ulteriori informazioni sulla chiamata della convalida e sull'accesso a eventuali avvisi o errori di convalida, vedere [Richiamare](invoking-activity-validation.md)la convalida dell'attività .</span><span class="sxs-lookup"><span data-stu-id="60e9f-118">For more information about invoking validation and accessing any validation warnings or errors, see [Invoking Activity Validation](invoking-activity-validation.md).</span></span>  
  
 <span data-ttu-id="60e9f-119">Qualsiasi eccezione generata dal metodo <xref:System.Activities.CodeActivity.CacheMetadata%2A> non viene considerata come errore di convalida.</span><span class="sxs-lookup"><span data-stu-id="60e9f-119">Any exceptions that are thrown from <xref:System.Activities.CodeActivity.CacheMetadata%2A> are not treated as validation errors.</span></span> <span data-ttu-id="60e9f-120">Queste eccezioni saranno escluse dalla chiamata all'oggetto <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> e devono essere gestite dal chiamante.</span><span class="sxs-lookup"><span data-stu-id="60e9f-120">These exceptions will escape from the call to <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> and must be handled by the caller.</span></span>  
  
 <span data-ttu-id="60e9f-121">La convalida basata su codice è utile per convalidare l'attività che contiene il codice, tuttavia non è visibile nelle altre attività del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="60e9f-121">Code-based validation is useful for validating the activity that contains the code, but it does not have visibility into the other activities in the workflow.</span></span> <span data-ttu-id="60e9f-122">La convalida dei vincoli dichiarativi consente di convalidare le relazioni tra un'attività e altre attività nel flusso di lavoro ed è descritta nell'argomento [Vincoli dichiarativi.](declarative-constraints.md)</span><span class="sxs-lookup"><span data-stu-id="60e9f-122">Declarative constraints validation provides the ability to validate the relationships between an activity and other activities in the workflow, and is covered in the [Declarative Constraints](declarative-constraints.md) topic.</span></span>
