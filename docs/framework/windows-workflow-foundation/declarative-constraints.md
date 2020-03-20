---
title: Vincoli dichiarativi
ms.date: 03/30/2017
ms.assetid: 67001ed1-7f4d-4ada-ae57-a31176901a53
ms.openlocfilehash: 321021e3d73daecae07268f33807c992414a7b4c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182955"
---
# <a name="declarative-constraints"></a><span data-ttu-id="ca784-102">Vincoli dichiarativi</span><span class="sxs-lookup"><span data-stu-id="ca784-102">Declarative Constraints</span></span>
<span data-ttu-id="ca784-103">I vincoli dichiarativi offrono un metodo potente di convalida per un'attività e le relative relazioni con altre attività.</span><span class="sxs-lookup"><span data-stu-id="ca784-103">Declarative constraints provide a powerful method of validation for an activity and its relationships with other activities.</span></span> <span data-ttu-id="ca784-104">I vincoli vengono configurati per un'attività durante il processo di creazione, ma vincoli aggiuntivi possono essere specificati anche dall'host del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ca784-104">Constraints are configured for an activity during the authoring process, but additional constraints can also be specified by the workflow host.</span></span> <span data-ttu-id="ca784-105">In questo argomento viene fornita una panoramica sull'utilizzo di vincoli dichiarativi per la convalida delle attività.</span><span class="sxs-lookup"><span data-stu-id="ca784-105">This topic provides an overview of using declarative constraints to provide activity validation.</span></span>  
  
## <a name="using-declarative-constraints"></a><span data-ttu-id="ca784-106">Uso di vincoli dichiarativi</span><span class="sxs-lookup"><span data-stu-id="ca784-106">Using Declarative Constraints</span></span>  
 <span data-ttu-id="ca784-107">Un vincolo è un'attività che contiene la logica di convalida.</span><span class="sxs-lookup"><span data-stu-id="ca784-107">A constraint is an activity that contains validation logic.</span></span> <span data-ttu-id="ca784-108">Questa attività del vincolo può essere creata nel codice o in XAML.</span><span class="sxs-lookup"><span data-stu-id="ca784-108">This constraint activity can be authored in code or in XAML.</span></span> <span data-ttu-id="ca784-109">Una volta creata un'attività del vincolo, gli autori di attività aggiungono questo vincolo alla proprietà <xref:System.Activities.Activity.Constraints%2A> dell'attività da convalidare o usano il vincolo per fornire convalida aggiuntiva tramite la proprietà <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> di un'istanza di <xref:System.Activities.Validation.ValidationSettings>.</span><span class="sxs-lookup"><span data-stu-id="ca784-109">After a constraint activity is created, activity authors add this constraint to the <xref:System.Activities.Activity.Constraints%2A> property of the activity to validate, or they use the constraint to provide additional validation by using the <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> property of a <xref:System.Activities.Validation.ValidationSettings> instance.</span></span> <span data-ttu-id="ca784-110">La logica di convalida può essere costituita da convalide semplici, ad esempio quella dei metadati di un'attività. Tuttavia una convalida può essere eseguita anche considerando la relazione dell'attività corrente con le relative attività padre, figlio e di pari livello.</span><span class="sxs-lookup"><span data-stu-id="ca784-110">The validation logic can consist of simple validations such as validating an activity’s metadata, but it can also perform validation that takes into account the relationship of the current activity to its parent, children, and sibling activities.</span></span> <span data-ttu-id="ca784-111">I vincoli vengono creati usando l'attività <xref:System.Activities.Validation.Constraint%601> e molte attività di convalida aggiuntive sono fornite per consentire la creazione di errori e di avvisi di convalida nonché per fornire informazioni sulle attività correlate nel flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ca784-111">Constraints are authored by using the <xref:System.Activities.Validation.Constraint%601> activity, and several additional validation activities are provided to assist with the creation of validation errors and warnings and to provide information about related activities in the workflow.</span></span>  
  
### <a name="assertvalidation-and-addvalidationerror"></a><span data-ttu-id="ca784-112">Oggetti AssertValidation e AddValidationError</span><span class="sxs-lookup"><span data-stu-id="ca784-112">AssertValidation and AddValidationError</span></span>  
 <span data-ttu-id="ca784-113">L'attività <xref:System.Activities.Validation.AssertValidation> valuta l'espressione a cui fa riferimento la relativa proprietà <xref:System.Activities.Validation.AssertValidation.Assertion%2A> e se l'espressione restituisce `false`, un errore o avviso di convalida viene aggiunto all'oggetto <xref:System.Activities.Validation.ValidationResults>.</span><span class="sxs-lookup"><span data-stu-id="ca784-113">The <xref:System.Activities.Validation.AssertValidation> activity evaluates the expression referenced by its <xref:System.Activities.Validation.AssertValidation.Assertion%2A> property, and if the expression evaluates to `false`, a validation error or warning is added to the <xref:System.Activities.Validation.ValidationResults>.</span></span> <span data-ttu-id="ca784-114">La proprietà <xref:System.Activities.Validation.AssertValidation.Message%2A> descrive l'errore di convalida mentre la proprietà <xref:System.Activities.Validation.AssertValidation.IsWarning%2A> indica se l'errore di convalida è un errore effettivo o un avviso.</span><span class="sxs-lookup"><span data-stu-id="ca784-114">The <xref:System.Activities.Validation.AssertValidation.Message%2A> property describes the validation error and the <xref:System.Activities.Validation.AssertValidation.IsWarning%2A> property indicates whether the validation failure is an error or a warning.</span></span> <span data-ttu-id="ca784-115">Il valore predefinito per la proprietà <xref:System.Activities.Validation.AssertValidation.IsWarning%2A> è `false`.</span><span class="sxs-lookup"><span data-stu-id="ca784-115">The default value for <xref:System.Activities.Validation.AssertValidation.IsWarning%2A> is `false`.</span></span>  
  
 <span data-ttu-id="ca784-116">Nell'esempio seguente viene dichiarato un vincolo che restituisce un avviso di convalida se la proprietà <xref:System.Activities.Activity.DisplayName%2A> dell'attività convalidata ha una lunghezza che non supera i due caratteri.</span><span class="sxs-lookup"><span data-stu-id="ca784-116">In the following example, a constraint is declared that returns a validation warning if the <xref:System.Activities.Activity.DisplayName%2A> of the activity being validated is two characters or less in length.</span></span> <span data-ttu-id="ca784-117">Il parametro di tipo generico usato per <xref:System.Activities.Validation.Constraint%601> specifica il tipo di attività convalidata dal vincolo.</span><span class="sxs-lookup"><span data-stu-id="ca784-117">The generic type parameter used for <xref:System.Activities.Validation.Constraint%601> specifies the type of activity that is validated by the constraint.</span></span> <span data-ttu-id="ca784-118">Questo vincolo usa l'oggetto <xref:System.Activities.Activity> come tipo generico e può essere usato per la convalida di tutti i tipi di attività.</span><span class="sxs-lookup"><span data-stu-id="ca784-118">This constraint uses <xref:System.Activities.Activity> as the generic type and can be used to validate all types of activities.</span></span>  
  
```csharp  
public static Constraint ActivityDisplayNameIsNotSetWarning()  
{  
    DelegateInArgument<Activity> element = new DelegateInArgument<Activity>();  
  
    return new Constraint<Activity>  
    {  
        Body = new ActivityAction<Activity, ValidationContext>  
        {  
            Argument1 = element,  
            Handler = new AssertValidation  
            {  
                IsWarning = true,  
                Assertion = new InArgument<bool>(env => (element.Get(env).DisplayName.Length > 2)),  
                Message = new InArgument<string>("It is a best practice to have a DisplayName of more than 2 characters."),  
            }  
        }  
    };  
}  
```  
  
 <span data-ttu-id="ca784-119">Per specificare questo vincolo per un'attività, viene aggiunto alla proprietà <xref:System.Activities.Activity.Constraints%2A> dell'attività, come mostrato nel codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ca784-119">To specify this constraint for an activity, it is added to the <xref:System.Activities.Activity.Constraints%2A> of the activity, as shown in the following example code.</span></span>  
  
```csharp  
public sealed class SampleActivity : CodeActivity  
{  
    public SampleActivity()  
    {  
        base.Constraints.Add(ActivityDisplayNameIsNotSetWarning());  
    }  
  
    // Activity implementation omitted.  
}  
```  
  
 <span data-ttu-id="ca784-120">Questo vincolo potrebbe essere specificato dall'host anche per le attività in un flusso di lavoro usando la proprietà <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A>, illustrata nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="ca784-120">The host could also specify this constraint for activities in a workflow by using <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A>, which is covered in the next section.</span></span>  
  
 <span data-ttu-id="ca784-121">L'attività <xref:System.Activities.Validation.AddValidationError> viene usata per generare un errore o avviso di convalida senza richiedere la valutazione di un'espressione.</span><span class="sxs-lookup"><span data-stu-id="ca784-121">The <xref:System.Activities.Validation.AddValidationError> activity is used to generate a validation error or warning without requiring the evaluation of an expression.</span></span> <span data-ttu-id="ca784-122">Le relative proprietà sono simili all'oggetto <xref:System.Activities.Validation.AssertValidation> che può essere usato insieme alle attività di controllo del flusso di un vincolo quale l'attività <xref:System.Activities.Statements.If>.</span><span class="sxs-lookup"><span data-stu-id="ca784-122">Its properties are similar to <xref:System.Activities.Validation.AssertValidation> and it can be used in conjunction with flow control activities of a constraint such as the <xref:System.Activities.Statements.If> activity.</span></span>
  
### <a name="workflow-relationship-activities"></a><span data-ttu-id="ca784-123">Attività di relazioni di flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="ca784-123">Workflow Relationship Activities</span></span>

<span data-ttu-id="ca784-124">Sono disponibili numerose attività di convalida che forniscono informazioni sulle altre attività del flusso di lavoro in relazione all'attività da convalidare.</span><span class="sxs-lookup"><span data-stu-id="ca784-124">Several validation activities are available that provide information about the other activities in the workflow in relation to the activity being validated.</span></span> <span data-ttu-id="ca784-125"><xref:System.Activities.Validation.GetParentChain> restituisce una raccolta di attività contenente tutte le attività tra l'attività in corso e l'attività radice.</span><span class="sxs-lookup"><span data-stu-id="ca784-125"><xref:System.Activities.Validation.GetParentChain> returns a collection of activities that contains all of the activities between the current activity and the root activity.</span></span> <span data-ttu-id="ca784-126"><xref:System.Activities.Validation.GetChildSubtree> fornisce una raccolta di attività contenente le attività figlio nel modello ricorsivo e <xref:System.Activities.Validation.GetWorkflowTree> ottiene tutte le attività nel flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ca784-126"><xref:System.Activities.Validation.GetChildSubtree> provides a collection of activities that contains the child activities in a recursive pattern, and <xref:System.Activities.Validation.GetWorkflowTree> gets all the activities in the workflow.</span></span>  
  
<span data-ttu-id="ca784-127">Nell'esempio seguente viene definita un'attività `CreateState` .</span><span class="sxs-lookup"><span data-stu-id="ca784-127">In the following example, a `CreateState` activity is defined.</span></span> <span data-ttu-id="ca784-128">L'attività `CreateState` deve essere contenuta all'interno di un'attività `CreateCountry` e il metodo `GetParent` restituisce un vincolo che applica questo requisito.</span><span class="sxs-lookup"><span data-stu-id="ca784-128">The `CreateState` activity must be contained within a `CreateCountry` activity, and the `GetParent` method returns a constraint that enforces this requirement.</span></span> <span data-ttu-id="ca784-129">`GetParent` usa l'attività <xref:System.Activities.Validation.GetParentChain> insieme a un'attività <xref:System.Activities.Statements.ForEach%601> per controllare le attività padre dell'attività `CreateState` per determinare se il requisito è stato rispettato.</span><span class="sxs-lookup"><span data-stu-id="ca784-129">`GetParent` uses the <xref:System.Activities.Validation.GetParentChain> activity in conjunction with a <xref:System.Activities.Statements.ForEach%601> activity to inspect the parent activities of the `CreateState` activity to determine if the requirement is met.</span></span>  
  
```csharp  
public sealed class CreateState : CodeActivity  
{  
    public CreateState()  
    {  
        base.Constraints.Add(CheckParent());  
        this.Cities = new List<Activity>();
    }  
  
    public List<Activity> Cities { get; set; }  
  
    public string Name { get; set; }
  
    static Constraint CheckParent()  
    {  
        DelegateInArgument<CreateState> element = new DelegateInArgument<CreateState>();  
        DelegateInArgument<ValidationContext> context = new DelegateInArgument<ValidationContext>();
        Variable<bool> result = new Variable<bool>();  
        DelegateInArgument<Activity> parent = new DelegateInArgument<Activity>();  
  
        return new Constraint<CreateState>  
        {
            Body = new ActivityAction<CreateState,ValidationContext>  
            {
                Argument1 = element,  
                Argument2 = context,  
                Handler = new Sequence  
                {  
                    Variables =  
                    {  
                        result
                    },  
                    Activities =  
                    {  
                        new ForEach<Activity>  
                        {
                            Values = new GetParentChain  
                            {  
                                ValidationContext = context
                            },  
                            Body = new ActivityAction<Activity>  
                            {
                                Argument = parent,
                                Handler = new If()  
                                {
                                    Condition = new InArgument<bool>((env) => object.Equals(parent.Get(env).GetType(),typeof(CreateCountry))),
                                    Then = new Assign<bool>  
                                    {  
                                        Value = true,  
                                        To = result  
                                    }  
                                }  
                            }
                        },  
                        new AssertValidation  
                        {  
                            Assertion = new InArgument<bool>(result),  
                            Message = new InArgument<string> ("CreateState has to be inside a CreateCountry activity"),
                        }  
                    }  
                }  
            }  
        };  
    }  
  
    protected override void Execute(CodeActivityContext context)  
    {  
        // not needed for the sample  
    }  
}  
```
  
## <a name="additional-constraints"></a><span data-ttu-id="ca784-130">Vincoli aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="ca784-130">Additional Constraints</span></span>  
 <span data-ttu-id="ca784-131">Gli autori di host del flusso di lavoro possono specificare vincoli di convalida aggiuntivi per le attività in un flusso di lavoro creando vincoli e aggiungendoli al dizionario <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> di un'istanza di <xref:System.Activities.Validation.ValidationSettings>.</span><span class="sxs-lookup"><span data-stu-id="ca784-131">Workflow host authors can specify additional validation constraints for activities in a workflow by creating constraints and adding them to the <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> dictionary of a <xref:System.Activities.Validation.ValidationSettings> instance.</span></span> <span data-ttu-id="ca784-132">Ogni elemento nella proprietà <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> contiene il tipo di attività per il quale vengono applicati i vincoli e un elenco dei vincoli aggiuntivi per quel tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="ca784-132">Each item in <xref:System.Activities.Validation.ValidationSettings.AdditionalConstraints%2A> contains the type of activity for which the constraints apply and a list of the additional constraints for that type of activity.</span></span> <span data-ttu-id="ca784-133">Quando la convalida viene richiamata per il flusso di lavoro, ogni attività del tipo specificato, incluse le classi derivate, valuta i vincoli.</span><span class="sxs-lookup"><span data-stu-id="ca784-133">When validation is invoked for the workflow, each activity of the specified type, including derived classes, evaluates the constraints.</span></span> <span data-ttu-id="ca784-134">In questo esempio il vincolo `ActivityDisplayNameIsNotSetWarning` della sezione precedente viene applicato a tutte le attività in un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ca784-134">In this example, the `ActivityDisplayNameIsNotSetWarning` constraint from the previous section is applied to all activities in a workflow.</span></span>  
  
```csharp  
Activity wf = new Sequence  
{  
    // Workflow Details Omitted.  
};  
  
ValidationSettings settings = new ValidationSettings()  
{  
  
    AdditionalConstraints =  
    {  
        {typeof(Activity), new List<Constraint> {ActivityDisplayNameIsNotSetWarning()}},
    }  
};  
  
// Validate the workflow.  
ValidationResults results = ActivityValidationServices.Validate(wf, settings);  
  
// Evaluate the results.  
if (results.Errors.Count == 0 && results.Warnings.Count == 0)  
{  
    Console.WriteLine("No warnings or errors");  
}  
else  
{  
    foreach (ValidationError error in results.Errors)  
    {  
        Console.WriteLine("Error in " + error.Source.DisplayName + ": " + error.Message);  
    }  
    foreach (ValidationError warning in results.Warnings)  
    {  
        Console.WriteLine("Warning in " + warning.Source.DisplayName + ": " + warning.Message);  
    }  
}  
```  
  
 <span data-ttu-id="ca784-135">Se la proprietà <xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A> dell'oggetto <xref:System.Activities.Validation.ValidationSettings> è `true`, solo i vincoli aggiuntivi specificati vengono valutati quando la convalida viene richiamata mediante la chiamata al metodo <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="ca784-135">If the <xref:System.Activities.Validation.ValidationSettings.OnlyUseAdditionalConstraints%2A> property of <xref:System.Activities.Validation.ValidationSettings> is `true`, then only the specified additional constraints are evaluated when validation is invoked by calling <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>.</span></span> <span data-ttu-id="ca784-136">Ciò può essere utile per esaminare i flussi di lavoro per configurazioni di convalida specifiche.</span><span class="sxs-lookup"><span data-stu-id="ca784-136">This can be useful for inspecting workflows for specific validation configurations.</span></span> <span data-ttu-id="ca784-137">Si noti tuttavia che quando viene richiamato il flusso di lavoro, la logica di convalida configurata nel flusso di lavoro viene valutata e deve passare per il flusso di lavoro per iniziare correttamente.</span><span class="sxs-lookup"><span data-stu-id="ca784-137">Note however that when the workflow is invoked, the validation logic configured in the workflow is evaluated and must pass for the workflow to successfully begin.</span></span> <span data-ttu-id="ca784-138">Per ulteriori informazioni sulla chiamata della convalida, vedere Richiamare la [convalida dell'attività](invoking-activity-validation.md).</span><span class="sxs-lookup"><span data-stu-id="ca784-138">For more information about invoking validation, see [Invoking Activity Validation](invoking-activity-validation.md).</span></span>
