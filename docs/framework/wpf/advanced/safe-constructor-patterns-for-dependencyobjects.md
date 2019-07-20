---
title: Modelli di costruttore sicuri per DependencyObject
ms.date: 03/30/2017
helpviewer_keywords:
- constructor patterns for dependency objects [WPF]
- dependency objects [WPF], constructor patterns
- FXCop tool [WPF]
ms.assetid: f704b81c-449a-47a4-ace1-9332e3cc6d60
ms.openlocfilehash: 9dffe06d340c7256ba8af687e30d90d51746ebe1
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2019
ms.locfileid: "68364240"
---
# <a name="safe-constructor-patterns-for-dependencyobjects"></a><span data-ttu-id="b4871-102">Modelli di costruttore sicuri per DependencyObject</span><span class="sxs-lookup"><span data-stu-id="b4871-102">Safe Constructor Patterns for DependencyObjects</span></span>
<span data-ttu-id="b4871-103">In genere, i costruttori di classe non devono chiamare callback come metodi virtuali o delegati, in quanto possono essere chiamati come inizializzazione di base di costruttori per una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="b4871-103">Generally, class constructors should not call callbacks such as virtual methods or delegates, because constructors can be called as base initialization of constructors for a derived class.</span></span> <span data-ttu-id="b4871-104">L'uso di elementi virtuali può avvenire in un stato incompleto dell'inizializzazione di qualsiasi dato oggetto.</span><span class="sxs-lookup"><span data-stu-id="b4871-104">Entering the virtual might be done at an incomplete initialization state of any given object.</span></span> <span data-ttu-id="b4871-105">Il sistema di proprietà stesso, tuttavia, chiama ed espone internamente i callback come parte del sistema di proprietà di dipendenza.</span><span class="sxs-lookup"><span data-stu-id="b4871-105">However, the property system itself calls and exposes callbacks internally, as part of the dependency property system.</span></span> <span data-ttu-id="b4871-106">Una semplice operazione come l'impostazione di un valore della proprietà <xref:System.Windows.DependencyObject.SetValue%2A> di dipendenza con Call potenzialmente include un callback in un punto qualsiasi della determinazione.</span><span class="sxs-lookup"><span data-stu-id="b4871-106">As simple an operation as setting a dependency property value with <xref:System.Windows.DependencyObject.SetValue%2A> call potentially includes a callback somewhere in the determination.</span></span> <span data-ttu-id="b4871-107">Per questa ragione, occorre prestare attenzione quando si impostano i valori delle proprietà di dipendenza all'interno del corpo di un costruttore, perché l'operazione può divenire problematica se il tipo viene usato come classe di base.</span><span class="sxs-lookup"><span data-stu-id="b4871-107">For this reason, you should be careful when setting dependency property values within the body of a constructor, which can become problematic if your type is used as a base class.</span></span> <span data-ttu-id="b4871-108">È disponibile un modello specifico per l' <xref:System.Windows.DependencyObject> implementazione di costruttori che consente di evitare problemi specifici con gli Stati delle proprietà di dipendenza e i callback inerenti, documentati qui.</span><span class="sxs-lookup"><span data-stu-id="b4871-108">There is a particular pattern for implementing <xref:System.Windows.DependencyObject> constructors that avoids specific problems with dependency property states and the inherent callbacks, which is documented here.</span></span>  

<a name="Property_System_Virtual_Methods"></a>   
## <a name="property-system-virtual-methods"></a><span data-ttu-id="b4871-109">Metodi virtuali del sistema di proprietà</span><span class="sxs-lookup"><span data-stu-id="b4871-109">Property System Virtual Methods</span></span>  
 <span data-ttu-id="b4871-110">I metodi virtuali o i callback seguenti vengono potenzialmente chiamati durante i calcoli della <xref:System.Windows.DependencyObject.SetValue%2A> chiamata che imposta un valore della proprietà di dipendenza: <xref:System.Windows.ValidateValueCallback>, <xref:System.Windows.PropertyChangedCallback>, <xref:System.Windows.CoerceValueCallback>,. <xref:System.Windows.DependencyObject.OnPropertyChanged%2A></span><span class="sxs-lookup"><span data-stu-id="b4871-110">The following virtual methods or callbacks are potentially called during the computations of the <xref:System.Windows.DependencyObject.SetValue%2A> call that sets a dependency property value: <xref:System.Windows.ValidateValueCallback>, <xref:System.Windows.PropertyChangedCallback>, <xref:System.Windows.CoerceValueCallback>, <xref:System.Windows.DependencyObject.OnPropertyChanged%2A>.</span></span> <span data-ttu-id="b4871-111">Ognuno di questi metodi virtuali o callback serve a uno scopo particolare nell'espansione della versatilità del sistema di proprietà [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] e delle proprietà di dipendenza.</span><span class="sxs-lookup"><span data-stu-id="b4871-111">Each of these virtual methods or callbacks serves a particular purpose in expanding the versatility of the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] property system and dependency properties.</span></span> <span data-ttu-id="b4871-112">Per altre informazioni su come usare questi elementi virtuali per personalizzare la determinazione del valore della proprietà, vedere [Callback e convalida delle proprietà di dipendenza](dependency-property-callbacks-and-validation.md).</span><span class="sxs-lookup"><span data-stu-id="b4871-112">For more information on how to use these virtuals to customize property value determination, see [Dependency Property Callbacks and Validation](dependency-property-callbacks-and-validation.md).</span></span>  
  
### <a name="fxcop-rule-enforcement-vs-property-system-virtuals"></a><span data-ttu-id="b4871-113">Confronto tra l'imposizione della regola FXCop e metodi virtuali del sistema di proprietà</span><span class="sxs-lookup"><span data-stu-id="b4871-113">FXCop Rule Enforcement vs. Property System Virtuals</span></span>  
 <span data-ttu-id="b4871-114">Se si usa lo strumento Microsoft FXCop come parte del processo di compilazione e si esegue la derivazione da determinate classi del framework [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] che chiamano il costruttore di base oppure si implementano proprietà di dipendenza personalizzate sulle classi derivate, può verificarsi la violazione di una particolare regola FXCop.</span><span class="sxs-lookup"><span data-stu-id="b4871-114">If you use the Microsoft tool FXCop as part of your build process, and you either derive from certain [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] framework classes calling the base constructor, or implement your own dependency properties on derived classes, you might encounter a particular FXCop rule violation.</span></span> <span data-ttu-id="b4871-115">La stringa del nome di questa violazione è:</span><span class="sxs-lookup"><span data-stu-id="b4871-115">The name string for this violation is:</span></span>  
  
 `DoNotCallOverridableMethodsInConstructors`  
  
 <span data-ttu-id="b4871-116">Si tratta di una regola che fa parte del set di regole pubblico predefinito per FXCop.</span><span class="sxs-lookup"><span data-stu-id="b4871-116">This is a rule that is part of the default public rule set for FXCop.</span></span> <span data-ttu-id="b4871-117">È possibile che questa regola segnali una traccia tramite il sistema di proprietà di dipendenza che infine chiama il metodo virtuale di un sistema di proprietà di dipendenza.</span><span class="sxs-lookup"><span data-stu-id="b4871-117">What this rule might be reporting is a trace through the dependency property system that eventually calls a dependency property system virtual method.</span></span> <span data-ttu-id="b4871-118">La violazione di questa regola potrebbe continuare ad apparire anche dopo avere seguito i modelli del costruttore consigliati illustrati in questo argomento, pertanto potrebbe essere necessario disabilitare o eliminare la regola nella configurazione del set di regole FXCop.</span><span class="sxs-lookup"><span data-stu-id="b4871-118">This rule violation might continue to appear even after following the recommended constructor patterns documented in this topic, so you might need to disable or suppress that rule in your FXCop rule set configuration.</span></span>  
  
### <a name="most-issues-come-from-deriving-classes-not-using-existing-classes"></a><span data-ttu-id="b4871-119">La maggior parte dei problemi è causata dalla derivazione delle classi e dal mancato uso delle classi esistenti</span><span class="sxs-lookup"><span data-stu-id="b4871-119">Most Issues Come From Deriving Classes, Not Using Existing Classes</span></span>  
 <span data-ttu-id="b4871-120">I problemi segnalati da questa regola si verificano quando una classe implementata con metodi virtuali nella relativa sequenza di costruzione viene successivamente derivata.</span><span class="sxs-lookup"><span data-stu-id="b4871-120">The issues reported by this rule occur when a class that you implement with virtual methods in its construction sequence is then derived from.</span></span> <span data-ttu-id="b4871-121">Se la classe viene contrassegnata come sealed oppure si sa o si decide che la classe non sarà derivata, le considerazioni qui illustrate e i problemi che hanno motivato la regola FXCop non si applicano a questa situazione.</span><span class="sxs-lookup"><span data-stu-id="b4871-121">If you seal your class, or otherwise know or enforce that your class will not be derived from, the considerations explained here and the issues that motivated the FXCop rule do not apply to you.</span></span> <span data-ttu-id="b4871-122">Se tuttavia se si stanno creando classi in modo che vengano usate come classi di base, ad esempio se si stanno creando modelli o un set di librerie di controlli espandibile, è consigliabile seguire i modelli raccomandati in questo argomento per i costruttori.</span><span class="sxs-lookup"><span data-stu-id="b4871-122">However, if you are authoring classes in such a way that they are intended to be used as base classes, for instance if you are creating templates, or an expandable control library set, you should follow the patterns recommended here for constructors.</span></span>  
  
### <a name="default-constructors-must-initialize-all-values-requested-by-callbacks"></a><span data-ttu-id="b4871-123">I costruttori predefiniti devono inizializzare tutti i valori richiesti dai callback</span><span class="sxs-lookup"><span data-stu-id="b4871-123">Default Constructors Must Initialize All Values Requested By Callbacks</span></span>  
 <span data-ttu-id="b4871-124">Tutti i membri di istanza usati dalla classe esegue l'override o i callback (i callback dall'elenco nella sezione relativa alle virtuali del sistema di proprietà) devono essere inizializzati nel costruttore senza parametri della classe, anche se alcuni di questi valori sono riempiti da valori "reali" tramite parametri dei costruttori senza parametri.</span><span class="sxs-lookup"><span data-stu-id="b4871-124">Any instance members that are used by your class overrides or callbacks (the callbacks from the list in the Property System Virtuals section) must be initialized in your class parameterless constructor, even if some of those values are filled by "real" values through parameters of the nonparameterless constructors.</span></span>  
  
 <span data-ttu-id="b4871-125">L'esempio di codice seguente e i successivi sono esempi di pseudo codice C# in cui questa regola viene violata e in cui viene illustrato il problema:</span><span class="sxs-lookup"><span data-stu-id="b4871-125">The following example code (and subsequent examples) is a pseudo-C# example that violates this rule and explains the problem:</span></span>  
  
```  
public class MyClass : DependencyObject  
{  
    public MyClass() {}  
    public MyClass(object toSetWobble)  
        : this()  
    {  
        Wobble = toSetWobble; //this is backed by a DependencyProperty  
        _myList = new ArrayList();    // this line should be in the default ctor  
    }  
    public static readonly DependencyProperty WobbleProperty =   
        DependencyProperty.Register("Wobble", typeof(object), typeof(MyClass));  
    public object Wobble  
    {  
        get { return GetValue(WobbleProperty); }  
        set { SetValue(WobbleProperty, value); }  
    }  
    protected override void OnPropertyChanged(DependencyPropertyChangedEventArgs e)  
    {  
        int count = _myList.Count;    // null-reference exception  
    }  
    private ArrayList _myList;  
}  
```  
  
 <span data-ttu-id="b4871-126">Quando il codice dell' `new MyClass(objectvalue)`applicazione chiama, chiama il costruttore senza parametri e i costruttori della classe base.</span><span class="sxs-lookup"><span data-stu-id="b4871-126">When application code calls `new MyClass(objectvalue)`, this calls the parameterless constructor and base class constructors.</span></span> <span data-ttu-id="b4871-127">Quindi imposta `Property1 = object1`, che chiama il metodo `OnPropertyChanged` virtuale nell'oggetto proprietario `MyClass`. <xref:System.Windows.DependencyObject></span><span class="sxs-lookup"><span data-stu-id="b4871-127">Then it sets `Property1 = object1`, which calls the virtual method `OnPropertyChanged` on the owning `MyClass` <xref:System.Windows.DependencyObject>.</span></span>  <span data-ttu-id="b4871-128">L'override fa riferimento a `_myList`, che non è stato ancora inizializzato.</span><span class="sxs-lookup"><span data-stu-id="b4871-128">The override refers to `_myList`, which has not been initialized yet.</span></span>  
  
 <span data-ttu-id="b4871-129">Un modo per evitare questi problemi consiste nel verificare che i callback usino solo altre proprietà di dipendenza e che ognuna di esse abbia un valore predefinito stabilito come parte dei relativi metadati registrati.</span><span class="sxs-lookup"><span data-stu-id="b4871-129">One way to avoid these issues is to make sure that callbacks use only other dependency properties, and that each such dependency property has an established default value as part of its registered metadata.</span></span>  
  
<a name="Safe_Constructor_Patterns"></a>   
## <a name="safe-constructor-patterns"></a><span data-ttu-id="b4871-130">Modelli di costruttore sicuri</span><span class="sxs-lookup"><span data-stu-id="b4871-130">Safe Constructor Patterns</span></span>  
 <span data-ttu-id="b4871-131">Per evitare i rischi di un'inizializzazione incompleta nel caso in cui la classe sia usata come classe di base, seguire questi modelli:</span><span class="sxs-lookup"><span data-stu-id="b4871-131">To avoid the risks of incomplete initialization if your class is used as a base class, follow these patterns:</span></span>  
  
#### <a name="parameterless-constructors-calling-base-initialization"></a><span data-ttu-id="b4871-132">Costruttori senza parametri che chiamano l'inizializzazione di base</span><span class="sxs-lookup"><span data-stu-id="b4871-132">Parameterless constructors calling base initialization</span></span>  
 <span data-ttu-id="b4871-133">Implementare questi costruttori che chiamano l'impostazione predefinita di base:</span><span class="sxs-lookup"><span data-stu-id="b4871-133">Implement these constructors calling the base default:</span></span>  
  
```  
public MyClass : SomeBaseClass {  
    public MyClass() : base() {  
        // ALL class initialization, including initial defaults for   
        // possible values that other ctors specify or that callbacks need.  
    }  
}  
```  
  
#### <a name="non-default-convenience-constructors-not-matching-any-base-signatures"></a><span data-ttu-id="b4871-134">Costruttori non predefiniti (di comodo), che non corrispondono ad alcuna firma di base</span><span class="sxs-lookup"><span data-stu-id="b4871-134">Non-default (convenience) constructors, not matching any base signatures</span></span>  
 <span data-ttu-id="b4871-135">Se questi costruttori usano i parametri per impostare le proprietà di dipendenza nell'inizializzazione, chiamare prima il costruttore senza parametri della classe per l'inizializzazione e quindi usare i parametri per impostare le proprietà di dipendenza.</span><span class="sxs-lookup"><span data-stu-id="b4871-135">If these constructors use the parameters to set dependency properties in the initialization, first call your own class parameterless constructor for initialization, and then use the parameters to set dependency properties.</span></span> <span data-ttu-id="b4871-136">Queste ultime potrebbero essere proprietà di dipendenza definite dalla classe o proprietà di dipendenza ereditate dalle classi di base. In entrambi i casi, tuttavia, usare il modello seguente:</span><span class="sxs-lookup"><span data-stu-id="b4871-136">These could either be dependency properties defined by your class, or dependency properties inherited from base classes, but in either case use the following pattern:</span></span>  
  
```  
public MyClass : SomeBaseClass {  
    public MyClass(object toSetProperty1) : this() {  
        // Class initialization NOT done by default.  
        // Then, set properties to values as passed in ctor parameters.  
        Property1 = toSetProperty1;  
    }  
}  
```  
  
#### <a name="non-default-convenience-constructors-which-do-match-base-signatures"></a><span data-ttu-id="b4871-137">Costruttori non predefiniti (di comodo), che corrispondono alle firme di base</span><span class="sxs-lookup"><span data-stu-id="b4871-137">Non-default (convenience) constructors, which do match base signatures</span></span>  
 <span data-ttu-id="b4871-138">Anziché chiamare il costruttore di base con la stessa parametrizzazione, chiamare di nuovo il costruttore senza parametri della propria classe.</span><span class="sxs-lookup"><span data-stu-id="b4871-138">Instead of calling the base constructor with the same parameterization, again call your own class' parameterless constructor.</span></span> <span data-ttu-id="b4871-139">Non chiamare l'inizializzatore di base, bensì chiamare `this()`.</span><span class="sxs-lookup"><span data-stu-id="b4871-139">Do not call the base initializer; instead you should call `this()`.</span></span> <span data-ttu-id="b4871-140">A questo punto, riprodurre il comportamento del costruttore originale usando i parametri passati come valori per l'impostazione delle proprietà pertinenti.</span><span class="sxs-lookup"><span data-stu-id="b4871-140">Then reproduce the original constructor behavior by using the passed parameters as values for setting the relevant properties.</span></span> <span data-ttu-id="b4871-141">Per informazioni sulla determinazione delle proprietà da impostare tramite determinati parametri, usare la documentazione originale del costruttore di base:</span><span class="sxs-lookup"><span data-stu-id="b4871-141">Use the original base constructor documentation for guidance in determining the properties that the particular parameters are intended to set:</span></span>  
  
```  
public MyClass : SomeBaseClass {  
    public MyClass(object toSetProperty1) : this() {  
        // Class initialization NOT done by default.  
        // Then, set properties to values as passed in ctor parameters.  
        Property1 = toSetProperty1;  
    }  
}  
```  
  
#### <a name="must-match-all-signatures"></a><span data-ttu-id="b4871-142">Deve corrispondere a tutte le firme</span><span class="sxs-lookup"><span data-stu-id="b4871-142">Must match all signatures</span></span>  
 <span data-ttu-id="b4871-143">Per i casi in cui il tipo di base ha più firme, è necessario associare intenzionalmente tutte le firme possibili con un'implementazione del costruttore personalizzata che usa il modello consigliato per chiamare il costruttore senza parametri della classe prima di impostare ulteriormente Proprietà.</span><span class="sxs-lookup"><span data-stu-id="b4871-143">For cases where the base type has multiple signatures, you must deliberately match all possible signatures with a constructor implementation of your own that uses the recommended pattern of calling the class parameterless constructor before setting further properties.</span></span>  
  
#### <a name="setting-dependency-properties-with-setvalue"></a><span data-ttu-id="b4871-144">Impostazione delle proprietà di dipendenza con SetValue</span><span class="sxs-lookup"><span data-stu-id="b4871-144">Setting dependency properties with SetValue</span></span>  
 <span data-ttu-id="b4871-145">Questi stessi modelli si applicano se si imposta una proprietà che non dispone di un wrapper per l'impostazione della proprietà convenienza e si <xref:System.Windows.DependencyObject.SetValue%2A>impostano i valori con.</span><span class="sxs-lookup"><span data-stu-id="b4871-145">These same patterns apply if you are setting a property that does not have a wrapper for property setting convenience, and set values with <xref:System.Windows.DependencyObject.SetValue%2A>.</span></span> <span data-ttu-id="b4871-146">Le chiamate a <xref:System.Windows.DependencyObject.SetValue%2A> che passano attraverso i parametri del costruttore devono chiamare anche il costruttore senza parametri della classe per l'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="b4871-146">Your calls to <xref:System.Windows.DependencyObject.SetValue%2A> that pass through constructor parameters should also call the class' parameterless constructor for initialization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4871-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4871-147">See also</span></span>

- [<span data-ttu-id="b4871-148">Proprietà di dipendenza personalizzate</span><span class="sxs-lookup"><span data-stu-id="b4871-148">Custom Dependency Properties</span></span>](custom-dependency-properties.md)
- [<span data-ttu-id="b4871-149">Panoramica sulle proprietà di dipendenza</span><span class="sxs-lookup"><span data-stu-id="b4871-149">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="b4871-150">Sicurezza delle proprietà di dipendenza</span><span class="sxs-lookup"><span data-stu-id="b4871-150">Dependency Property Security</span></span>](dependency-property-security.md)
