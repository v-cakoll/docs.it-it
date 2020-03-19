---
title: Metodi
description: Informazioni su come un metodo F è una funzione associata a un tipo utilizzato per esporre e implementare la funzionalità e il comportamento di oggetti e tipi.
ms.date: 11/04/2019
ms.openlocfilehash: 6f5ae76ea450b07763eb58d0c95b18b30f634551
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400211"
---
# <a name="methods"></a><span data-ttu-id="c59b8-103">Metodi</span><span class="sxs-lookup"><span data-stu-id="c59b8-103">Methods</span></span>

<span data-ttu-id="c59b8-104">Un *metodo* è una funzione associata a un tipo.</span><span class="sxs-lookup"><span data-stu-id="c59b8-104">A *method* is a function that is associated with a type.</span></span> <span data-ttu-id="c59b8-105">Nella programmazione orientata agli oggetti, i metodi vengono utilizzati per esporre e implementare la funzionalità e il comportamento di oggetti e tipi.</span><span class="sxs-lookup"><span data-stu-id="c59b8-105">In object-oriented programming, methods are used to expose and implement the functionality and behavior of objects and types.</span></span>

## <a name="syntax"></a><span data-ttu-id="c59b8-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c59b8-106">Syntax</span></span>

```fsharp
// Instance method definition.
[ attributes ]
member [inline] self-identifier.method-name parameter-list [ : return-type ] =
    method-body

// Static method definition.
[ attributes ]
static member [inline] method-name parameter-list [ : return-type ] =
    method-body

// Abstract method declaration or virtual dispatch slot.
[ attributes ]
abstract member method-name : type-signature

// Virtual method declaration and default implementation.
[ attributes ]
abstract member method-name : type-signature
[ attributes ]
default self-identifier.method-name parameter-list [ : return-type ] =
    method-body

// Override of inherited virtual method.
[ attributes ]
override self-identifier.method-name parameter-list [ : return-type ] =
    method-body

// Optional and DefaultParameterValue attributes on input parameters
[ attributes ]
[ modifier ] member [inline] self-identifier.method-name ([<Optional; DefaultParameterValue( default-value )>] input) [ : return-type ]
```

## <a name="remarks"></a><span data-ttu-id="c59b8-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c59b8-107">Remarks</span></span>

<span data-ttu-id="c59b8-108">Nella sintassi precedente, è possibile visualizzare le varie forme di dichiarazioni e definizioni di metodo.</span><span class="sxs-lookup"><span data-stu-id="c59b8-108">In the previous syntax, you can see the various forms of method declarations and definitions.</span></span> <span data-ttu-id="c59b8-109">Nei corpi di metodo più lunghi, un'interruzione di riga segue il segno di uguale (-) e l'intero corpo del metodo è rientrato.</span><span class="sxs-lookup"><span data-stu-id="c59b8-109">In longer method bodies, a line break follows the equal sign (=), and the whole method body is indented.</span></span>

<span data-ttu-id="c59b8-110">Gli attributi possono essere applicati a qualsiasi dichiarazione di metodo.</span><span class="sxs-lookup"><span data-stu-id="c59b8-110">Attributes can be applied to any method declaration.</span></span> <span data-ttu-id="c59b8-111">Precedono la sintassi per una definizione di metodo e sono in genere elencati in una riga separata.</span><span class="sxs-lookup"><span data-stu-id="c59b8-111">They precede the syntax for a method definition and are usually listed on a separate line.</span></span> <span data-ttu-id="c59b8-112">Per altre informazioni, vedere [Attributi](../attributes.md).</span><span class="sxs-lookup"><span data-stu-id="c59b8-112">For more information, see [Attributes](../attributes.md).</span></span>

<span data-ttu-id="c59b8-113">I metodi `inline`possono essere contrassegnati con .</span><span class="sxs-lookup"><span data-stu-id="c59b8-113">Methods can be marked `inline`.</span></span> <span data-ttu-id="c59b8-114">Per informazioni su `inline`, vedere [Funzioni inline](../functions/inline-functions.md).</span><span class="sxs-lookup"><span data-stu-id="c59b8-114">For information about `inline`, see [Inline Functions](../functions/inline-functions.md).</span></span>

<span data-ttu-id="c59b8-115">I metodi non inline possono essere utilizzati in modo ricorsivo all'interno del tipo; non è necessario utilizzare `rec` in modo esplicito la parola chiave.</span><span class="sxs-lookup"><span data-stu-id="c59b8-115">Non-inline methods can be used recursively within the type; there is no need to explicitly use the `rec` keyword.</span></span>

## <a name="instance-methods"></a><span data-ttu-id="c59b8-116">Metodi di istanza</span><span class="sxs-lookup"><span data-stu-id="c59b8-116">Instance Methods</span></span>

<span data-ttu-id="c59b8-117">I metodi di `member` istanza vengono dichiarati con la parola chiave e un *autoidentificatore*, seguiti da un punto (.) e dal nome del metodo e dai parametri.</span><span class="sxs-lookup"><span data-stu-id="c59b8-117">Instance methods are declared with the `member` keyword and a *self-identifier*, followed by a period (.) and the method name and parameters.</span></span> <span data-ttu-id="c59b8-118">Come nel caso `let` delle associazioni, l'elenco *di parametri* può essere un modello.</span><span class="sxs-lookup"><span data-stu-id="c59b8-118">As is the case for `let` bindings, the *parameter-list* can be a pattern.</span></span> <span data-ttu-id="c59b8-119">In genere, i parametri del metodo vengono racchiusi tra parentesi in un formato di tupla, ovvero il modo in cui i metodi vengono visualizzati in F , quando vengono creati in altri linguaggi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c59b8-119">Typically, you enclose method parameters in parentheses in a tuple form, which is the way methods appear in F# when they are created in other .NET Framework languages.</span></span> <span data-ttu-id="c59b8-120">Tuttavia, anche la forma sottoposta a curryle (parametri separati da spazi) è comune e sono supportati anche altri modelli.</span><span class="sxs-lookup"><span data-stu-id="c59b8-120">However, the curried form (parameters separated by spaces) is also common, and other patterns are supported also.</span></span>

<span data-ttu-id="c59b8-121">Nell'esempio seguente vengono illustrati la definizione e l'utilizzo di un metodo di istanza non astratto.</span><span class="sxs-lookup"><span data-stu-id="c59b8-121">The following example illustrates the definition and use of a non-abstract instance method.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3401.fs)]

<span data-ttu-id="c59b8-122">All'interno dei metodi di istanza, non utilizzare l'autoidentificatore per accedere ai campi definiti utilizzando let associazioni.</span><span class="sxs-lookup"><span data-stu-id="c59b8-122">Within instance methods, do not use the self identifier to access fields defined by using let bindings.</span></span> <span data-ttu-id="c59b8-123">Utilizzare l'autoidentificatore quando si accede ad altri membri e proprietà.</span><span class="sxs-lookup"><span data-stu-id="c59b8-123">Use the self identifier when accessing other members and properties.</span></span>

## <a name="static-methods"></a><span data-ttu-id="c59b8-124">Metodi statici</span><span class="sxs-lookup"><span data-stu-id="c59b8-124">Static Methods</span></span>

<span data-ttu-id="c59b8-125">La `static` parola chiave viene utilizzata per specificare che un metodo può essere chiamato senza un'istanza e non è associato a un'istanza dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="c59b8-125">The keyword `static` is used to specify that a method can be called without an instance and is not associated with an object instance.</span></span> <span data-ttu-id="c59b8-126">In caso contrario, i metodi sono metodi di istanza.</span><span class="sxs-lookup"><span data-stu-id="c59b8-126">Otherwise, methods are instance methods.</span></span>

<span data-ttu-id="c59b8-127">L'esempio nella sezione successiva mostra `let` i campi dichiarati `member` con la parola chiave `static` , i membri di proprietà dichiarati con la parola chiave e un metodo statico dichiarato con la parola chiave .</span><span class="sxs-lookup"><span data-stu-id="c59b8-127">The example in the next section shows fields declared with the `let` keyword, property members declared with the `member` keyword, and a static method declared with the `static` keyword.</span></span>

<span data-ttu-id="c59b8-128">Nell'esempio seguente vengono illustrati la definizione e l'utilizzo di metodi statici.</span><span class="sxs-lookup"><span data-stu-id="c59b8-128">The following example illustrates the definition and use of static methods.</span></span> <span data-ttu-id="c59b8-129">Si supponga che queste `SomeType` definizioni di metodo sono nella classe nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="c59b8-129">Assume that these method definitions are in the `SomeType` class in the previous section.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3402.fs)]

## <a name="abstract-and-virtual-methods"></a><span data-ttu-id="c59b8-130">Metodi virtuali e astratti</span><span class="sxs-lookup"><span data-stu-id="c59b8-130">Abstract and Virtual Methods</span></span>

<span data-ttu-id="c59b8-131">La `abstract` parola chiave indica che un metodo dispone di uno slot di invio virtuale e potrebbe non avere una definizione nella classe.</span><span class="sxs-lookup"><span data-stu-id="c59b8-131">The keyword `abstract` indicates that a method has a virtual dispatch slot and might not have a definition in the class.</span></span> <span data-ttu-id="c59b8-132">Uno slot di *invio virtuale* è una voce in una tabella di funzioni gestita internamente utilizzata in fase di esecuzione per cercare chiamate di funzione virtuale in un tipo orientato agli oggetti.</span><span class="sxs-lookup"><span data-stu-id="c59b8-132">A *virtual dispatch slot* is an entry in an internally maintained table of functions that is used at run time to look up virtual function calls in an object-oriented type.</span></span> <span data-ttu-id="c59b8-133">Il meccanismo di invio virtuale è il meccanismo che implementa il *polimorfismo,* una caratteristica importante della programmazione orientata agli oggetti.</span><span class="sxs-lookup"><span data-stu-id="c59b8-133">The virtual dispatch mechanism is the mechanism that implements *polymorphism*, an important feature of object-oriented programming.</span></span> <span data-ttu-id="c59b8-134">Una classe che dispone di almeno un metodo astratto senza una definizione è una *classe astratta*, il che significa che non è possibile creare alcuna istanza di tale classe.</span><span class="sxs-lookup"><span data-stu-id="c59b8-134">A class that has at least one abstract method without a definition is an *abstract class*, which means that no instances can be created of that class.</span></span> <span data-ttu-id="c59b8-135">Per ulteriori informazioni sulle classi astratte, vedere [Classi astratte](../abstract-classes.md).</span><span class="sxs-lookup"><span data-stu-id="c59b8-135">For more information about abstract classes, see [Abstract Classes](../abstract-classes.md).</span></span>

<span data-ttu-id="c59b8-136">Le dichiarazioni di metodi astratti non includono un corpo del metodo.</span><span class="sxs-lookup"><span data-stu-id="c59b8-136">Abstract method declarations do not include a method body.</span></span> <span data-ttu-id="c59b8-137">Al contrario, il nome del metodo è seguito da due punti (:) e una firma del tipo per il metodo.</span><span class="sxs-lookup"><span data-stu-id="c59b8-137">Instead, the name of the method is followed by a colon (:) and a type signature for the method.</span></span> <span data-ttu-id="c59b8-138">La firma del tipo di un metodo è uguale a quella visualizzata da IntelliSense quando si posiziona il puntatore del mouse sul nome di un metodo nell'editor di codice di Visual Studio, ad eccezione dei nomi di parametro.</span><span class="sxs-lookup"><span data-stu-id="c59b8-138">The type signature of a method is the same as that shown by IntelliSense when you pause the mouse pointer over a method name in the Visual Studio Code Editor, except without parameter names.</span></span> <span data-ttu-id="c59b8-139">Le firme di tipo vengono visualizzate anche dall'interprete, fsi.exe, quando si lavora in modo interattivo.</span><span class="sxs-lookup"><span data-stu-id="c59b8-139">Type signatures are also displayed by the interpreter, fsi.exe, when you are working interactively.</span></span> <span data-ttu-id="c59b8-140">La firma del tipo di un metodo viene formata elencando i tipi dei parametri, seguiti dal tipo restituito, con i simboli di separatore appropriati.</span><span class="sxs-lookup"><span data-stu-id="c59b8-140">The type signature of a method is formed by listing out the types of the parameters, followed by the return type, with appropriate separator symbols.</span></span> <span data-ttu-id="c59b8-141">I parametri sottoposti a `->` curryè sono separati `*`da e i parametri della tupla sono separati da .</span><span class="sxs-lookup"><span data-stu-id="c59b8-141">Curried parameters are separated by `->` and tuple parameters are separated by `*`.</span></span> <span data-ttu-id="c59b8-142">Il valore restituito è sempre separato `->` dagli argomenti da un simbolo.</span><span class="sxs-lookup"><span data-stu-id="c59b8-142">The return value is always separated from the arguments by a `->` symbol.</span></span> <span data-ttu-id="c59b8-143">Le parentesi possono essere usate per raggruppare parametri complessi, ad esempio quando un tipo di funzione è un parametro, o per indicare quando una tupla viene considerata come un singolo parametro anziché come due parametri.</span><span class="sxs-lookup"><span data-stu-id="c59b8-143">Parentheses can be used to group complex parameters, such as when a function type is a parameter, or to indicate when a tuple is treated as a single parameter rather than as two parameters.</span></span>

<span data-ttu-id="c59b8-144">È inoltre possibile assegnare definizioni predefinite ai metodi `default` astratti aggiungendo la definizione alla classe e usando la parola chiave , come illustrato nel blocco di sintassi in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="c59b8-144">You can also give abstract methods default definitions by adding the definition to the class and using the `default` keyword, as shown in the syntax block in this topic.</span></span> <span data-ttu-id="c59b8-145">Un metodo astratto con una definizione nella stessa classe è equivalente a un metodo virtuale in altri linguaggi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c59b8-145">An abstract method that has a definition in the same class is equivalent to a virtual method in other .NET Framework languages.</span></span> <span data-ttu-id="c59b8-146">Indipendentemente dal fatto che `abstract` esista o meno una definizione, la parola chiave crea un nuovo slot di invio nella tabella delle funzioni virtuali per la classe.</span><span class="sxs-lookup"><span data-stu-id="c59b8-146">Whether or not a definition exists, the `abstract` keyword creates a new dispatch slot in the virtual function table for the class.</span></span>

<span data-ttu-id="c59b8-147">Indipendentemente dal fatto che una classe base implementa i relativi metodi astratti, le classi derivate possono fornire implementazioni di metodi astratti.</span><span class="sxs-lookup"><span data-stu-id="c59b8-147">Regardless of whether a base class implements its abstract methods, derived classes can provide implementations of abstract methods.</span></span> <span data-ttu-id="c59b8-148">Per implementare un metodo astratto in una classe derivata, definire un metodo `override` con `default` lo stesso nome e la stessa firma nella classe derivata, ad eccezione di utilizzare la parola chiave o e fornire il corpo del metodo.</span><span class="sxs-lookup"><span data-stu-id="c59b8-148">To implement an abstract method in a derived class, define a method that has the same name and signature in the derived class, except use the `override` or `default` keyword, and provide the method body.</span></span> <span data-ttu-id="c59b8-149">Le `override` parole `default` chiave e significano esattamente la stessa cosa.</span><span class="sxs-lookup"><span data-stu-id="c59b8-149">The keywords `override` and `default` mean exactly the same thing.</span></span> <span data-ttu-id="c59b8-150">Utilizzare `override` se il nuovo metodo esegue l'override di un'implementazione della classe base; utilizzare `default` quando si crea un'implementazione nella stessa classe della dichiarazione astratta originale.</span><span class="sxs-lookup"><span data-stu-id="c59b8-150">Use `override` if the new method overrides a base class implementation; use `default` when you create an implementation in the same class as the original abstract declaration.</span></span> <span data-ttu-id="c59b8-151">Non utilizzare `abstract` la parola chiave sul metodo che implementa il metodo dichiarato abstract nella classe base.</span><span class="sxs-lookup"><span data-stu-id="c59b8-151">Do not use the `abstract` keyword on the method that implements the method that was declared abstract in the base class.</span></span>

<span data-ttu-id="c59b8-152">Nell'esempio seguente viene `Rotate` illustrato un metodo astratto con un'implementazione predefinita, l'equivalente di un metodo virtuale di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c59b8-152">The following example illustrates an abstract method `Rotate` that has a default implementation, the equivalent of a .NET Framework virtual method.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3403.fs)]

<span data-ttu-id="c59b8-153">Nell'esempio seguente viene illustrata una classe derivata che esegue l'override di un metodo della classe base.</span><span class="sxs-lookup"><span data-stu-id="c59b8-153">The following example illustrates a derived class that overrides a base class method.</span></span> <span data-ttu-id="c59b8-154">In questo caso, l'override modifica il comportamento in modo che il metodo non eseda alcuna operazione.</span><span class="sxs-lookup"><span data-stu-id="c59b8-154">In this case, the override changes the behavior so that the method does nothing.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3404.fs)]

## <a name="overloaded-methods"></a><span data-ttu-id="c59b8-155">Metodi di overload</span><span class="sxs-lookup"><span data-stu-id="c59b8-155">Overloaded Methods</span></span>

<span data-ttu-id="c59b8-156">I metodi di overload sono metodi con nomi identici in un determinato tipo ma con argomenti diversi.</span><span class="sxs-lookup"><span data-stu-id="c59b8-156">Overloaded methods are methods that have identical names in a given type but that have different arguments.</span></span> <span data-ttu-id="c59b8-157">In F , gli argomenti facoltativi vengono in genere utilizzati al posto dei metodi di overload.</span><span class="sxs-lookup"><span data-stu-id="c59b8-157">In F#, optional arguments are usually used instead of overloaded methods.</span></span> <span data-ttu-id="c59b8-158">Tuttavia, i metodi di overload sono consentiti nel linguaggio, a condizione che gli argomenti siano in formato tupla, non sottoposti a curryazione.</span><span class="sxs-lookup"><span data-stu-id="c59b8-158">However, overloaded methods are permitted in the language, provided that the arguments are in tuple form, not curried form.</span></span>

## <a name="optional-arguments"></a><span data-ttu-id="c59b8-159">Argomenti facoltativi</span><span class="sxs-lookup"><span data-stu-id="c59b8-159">Optional Arguments</span></span>

<span data-ttu-id="c59b8-160">A partire dalla versione 4.1, è anche possibile avere argomenti facoltativi con un valore di parametro predefinito nei metodi.</span><span class="sxs-lookup"><span data-stu-id="c59b8-160">Starting with F# 4.1, you can also have optional arguments with a default parameter value in methods.</span></span>  <span data-ttu-id="c59b8-161">In questo modo è possibile facilitare l'interoperabilità con il codice di C.</span><span class="sxs-lookup"><span data-stu-id="c59b8-161">This is to help facilitate interoperation with C# code.</span></span>  <span data-ttu-id="c59b8-162">Nell'esempio seguente viene illustrata la sintassi:</span><span class="sxs-lookup"><span data-stu-id="c59b8-162">The following example demonstrates the syntax:</span></span>

```fsharp
// A class with a method M, which takes in an optional integer argument.
type C() =
    _.M([<Optional; DefaultParameterValue(12)>] i) = i + 1
```

<span data-ttu-id="c59b8-163">Si noti che `DefaultParameterValue` il valore passato per deve corrispondere al tipo di input.</span><span class="sxs-lookup"><span data-stu-id="c59b8-163">Note that the value passed in for `DefaultParameterValue` must match the input type.</span></span>  <span data-ttu-id="c59b8-164">Nell'esempio precedente, è `int`un file .</span><span class="sxs-lookup"><span data-stu-id="c59b8-164">In the above sample, it is an `int`.</span></span>  <span data-ttu-id="c59b8-165">Il tentativo di passare un `DefaultParameterValue` valore non intero in genererebbe un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="c59b8-165">Attempting to pass a non-integer value into `DefaultParameterValue` would result in a compile error.</span></span>

## <a name="example-properties-and-methods"></a><span data-ttu-id="c59b8-166">Esempio: Proprietà e metodi</span><span class="sxs-lookup"><span data-stu-id="c59b8-166">Example: Properties and Methods</span></span>

<span data-ttu-id="c59b8-167">L'esempio seguente contiene un tipo che contiene esempi di campi, funzioni private, proprietà e un metodo statico.</span><span class="sxs-lookup"><span data-stu-id="c59b8-167">The following example contains a type that has examples of fields, private functions, properties, and a static method.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3406.fs)]

## <a name="see-also"></a><span data-ttu-id="c59b8-168">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c59b8-168">See also</span></span>

- [<span data-ttu-id="c59b8-169">Membri</span><span class="sxs-lookup"><span data-stu-id="c59b8-169">Members</span></span>](index.md)
