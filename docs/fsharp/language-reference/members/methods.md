---
title: Metodi
description: Informazioni su come un F# metodo è una funzione associata a un tipo che vengono usate per esporre e implementare le funzionalità e il comportamento degli oggetti e tipi.
ms.date: 05/16/2016
ms.openlocfilehash: 03150cc67f79bfde58cf27e4a9d4dfa9e9ff3f55
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2018
ms.locfileid: "53614025"
---
# <a name="methods"></a><span data-ttu-id="572c1-103">Metodi</span><span class="sxs-lookup"><span data-stu-id="572c1-103">Methods</span></span>

<span data-ttu-id="572c1-104">Oggetto *metodo* è una funzione che è associata a un tipo.</span><span class="sxs-lookup"><span data-stu-id="572c1-104">A *method* is a function that is associated with a type.</span></span> <span data-ttu-id="572c1-105">Nella programmazione orientata agli oggetti, metodi vengono utilizzati per esporre e implementare le funzionalità e il comportamento degli oggetti e tipi.</span><span class="sxs-lookup"><span data-stu-id="572c1-105">In object-oriented programming, methods are used to expose and implement the functionality and behavior of objects and types.</span></span>

## <a name="syntax"></a><span data-ttu-id="572c1-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="572c1-106">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="572c1-107">Note</span><span class="sxs-lookup"><span data-stu-id="572c1-107">Remarks</span></span>

<span data-ttu-id="572c1-108">Nella sintassi precedente, è possibile visualizzare le varie forme di definizioni e dichiarazioni di metodo.</span><span class="sxs-lookup"><span data-stu-id="572c1-108">In the previous syntax, you can see the various forms of method declarations and definitions.</span></span> <span data-ttu-id="572c1-109">Nel corpo del metodo più lungo, un'interruzione di riga segue il segno di uguale (=) e l'intero corpo del metodo viene applicato un rientro.</span><span class="sxs-lookup"><span data-stu-id="572c1-109">In longer method bodies, a line break follows the equal sign (=), and the whole method body is indented.</span></span>

<span data-ttu-id="572c1-110">Gli attributi possono essere applicati a qualsiasi dichiarazione di metodo.</span><span class="sxs-lookup"><span data-stu-id="572c1-110">Attributes can be applied to any method declaration.</span></span> <span data-ttu-id="572c1-111">Essi precedere la sintassi per una definizione di metodo e sono elencati di solito su una riga separata.</span><span class="sxs-lookup"><span data-stu-id="572c1-111">They precede the syntax for a method definition and are usually listed on a separate line.</span></span> <span data-ttu-id="572c1-112">Per altre informazioni, vedere [Attributi](../attributes.md).</span><span class="sxs-lookup"><span data-stu-id="572c1-112">For more information, see [Attributes](../attributes.md).</span></span>

<span data-ttu-id="572c1-113">I metodi possono essere contrassegnati `inline`.</span><span class="sxs-lookup"><span data-stu-id="572c1-113">Methods can be marked `inline`.</span></span> <span data-ttu-id="572c1-114">Per informazioni su `inline`, vedere [Funzioni inline](../functions/inline-functions.md).</span><span class="sxs-lookup"><span data-stu-id="572c1-114">For information about `inline`, see [Inline Functions](../functions/inline-functions.md).</span></span>

<span data-ttu-id="572c1-115">I metodi non inline possono essere utilizzato in modo ricorsivo all'interno del tipo; non è necessario usare in modo esplicito il `rec` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="572c1-115">Non-inline methods can be used recursively within the type; there is no need to explicitly use the `rec` keyword.</span></span>

## <a name="instance-methods"></a><span data-ttu-id="572c1-116">Metodi di istanza</span><span class="sxs-lookup"><span data-stu-id="572c1-116">Instance Methods</span></span>

<span data-ttu-id="572c1-117">Metodi di istanza vengono dichiarati con il `member` parola chiave e un *autoidentificatore*, seguita da un punto (.) e il nome del metodo e i parametri.</span><span class="sxs-lookup"><span data-stu-id="572c1-117">Instance methods are declared with the `member` keyword and a *self-identifier*, followed by a period (.) and the method name and parameters.</span></span> <span data-ttu-id="572c1-118">Come accade per `let` associazioni, il *elenco di parametri* può essere un modello.</span><span class="sxs-lookup"><span data-stu-id="572c1-118">As is the case for `let` bindings, the *parameter-list* can be a pattern.</span></span> <span data-ttu-id="572c1-119">In genere, si racchiudere i parametri tra parentesi nel formato di tupla, ovvero i metodi modo vengono visualizzati nel metodo F# quando vengono create in altri linguaggi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="572c1-119">Typically, you enclose method parameters in parentheses in a tuple form, which is the way methods appear in F# when they are created in other .NET Framework languages.</span></span> <span data-ttu-id="572c1-120">Tuttavia, il currying (parametri separati da spazi) è anche comune, e sono supportati anche altri criteri.</span><span class="sxs-lookup"><span data-stu-id="572c1-120">However, the curried form (parameters separated by spaces) is also common, and other patterns are supported also.</span></span>

<span data-ttu-id="572c1-121">L'esempio seguente illustra la definizione e utilizzo di un metodo di istanza non astratta.</span><span class="sxs-lookup"><span data-stu-id="572c1-121">The following example illustrates the definition and use of a non-abstract instance method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3401.fs)]

<span data-ttu-id="572c1-122">All'interno di metodi di istanza, non usare l'autoidentificatore per accedere ai campi definiti tramite associazioni let.</span><span class="sxs-lookup"><span data-stu-id="572c1-122">Within instance methods, do not use the self identifier to access fields defined by using let bindings.</span></span> <span data-ttu-id="572c1-123">Utilizzare l'autoidentificatore l'accesso ad altri membri e le proprietà.</span><span class="sxs-lookup"><span data-stu-id="572c1-123">Use the self identifier when accessing other members and properties.</span></span>

## <a name="static-methods"></a><span data-ttu-id="572c1-124">Metodi statici</span><span class="sxs-lookup"><span data-stu-id="572c1-124">Static Methods</span></span>

<span data-ttu-id="572c1-125">La parola chiave `static` viene usato per specificare che un metodo può essere chiamato senza un'istanza e non è associato a un'istanza dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="572c1-125">The keyword `static` is used to specify that a method can be called without an instance and is not associated with an object instance.</span></span> <span data-ttu-id="572c1-126">In caso contrario, i metodi sono metodi di istanza.</span><span class="sxs-lookup"><span data-stu-id="572c1-126">Otherwise, methods are instance methods.</span></span>

<span data-ttu-id="572c1-127">L'esempio nella sezione successiva illustra i campi dichiarati con il `let` parola chiave, i membri della proprietà dichiarata con il `member` parola chiave e un metodo statico dichiarata con il `static` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="572c1-127">The example in the next section shows fields declared with the `let` keyword, property members declared with the `member` keyword, and a static method declared with the `static` keyword.</span></span>

<span data-ttu-id="572c1-128">L'esempio seguente illustra la definizione e l'uso di metodi statici.</span><span class="sxs-lookup"><span data-stu-id="572c1-128">The following example illustrates the definition and use of static methods.</span></span> <span data-ttu-id="572c1-129">Si supponga che le definizioni di metodo siano nel `SomeType` classe nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="572c1-129">Assume that these method definitions are in the `SomeType` class in the previous section.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3402.fs)]

## <a name="abstract-and-virtual-methods"></a><span data-ttu-id="572c1-130">Metodi virtuali e astratti</span><span class="sxs-lookup"><span data-stu-id="572c1-130">Abstract and Virtual Methods</span></span>

<span data-ttu-id="572c1-131">La parola chiave `abstract` indica che un metodo dispone di uno slot di distribuzione virtuale e potrebbe non disporre di una definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="572c1-131">The keyword `abstract` indicates that a method has a virtual dispatch slot and might not have a definition in the class.</span></span> <span data-ttu-id="572c1-132">Oggetto *slot di distribuzione virtuale* è una voce in una tabella gestita internamente delle funzioni che è utilizzata in fase di esecuzione per cercare di funzione virtuale chiama in un tipo orientate a oggetti.</span><span class="sxs-lookup"><span data-stu-id="572c1-132">A *virtual dispatch slot* is an entry in an internally maintained table of functions that is used at run time to look up virtual function calls in an object-oriented type.</span></span> <span data-ttu-id="572c1-133">Il meccanismo di distribuzione virtuale è il meccanismo che implementa *polimorfismo*, una caratteristica importante della programmazione orientata agli oggetti.</span><span class="sxs-lookup"><span data-stu-id="572c1-133">The virtual dispatch mechanism is the mechanism that implements *polymorphism*, an important feature of object-oriented programming.</span></span> <span data-ttu-id="572c1-134">È una classe che ha almeno un metodo astratto senza una definizione di un *classe astratta*, il che significa che è possibile creare nessuna istanza di tale classe.</span><span class="sxs-lookup"><span data-stu-id="572c1-134">A class that has at least one abstract method without a definition is an *abstract class*, which means that no instances can be created of that class.</span></span> <span data-ttu-id="572c1-135">Per altre informazioni sulle classi astratte, vedere [classi astratte](../abstract-classes.md).</span><span class="sxs-lookup"><span data-stu-id="572c1-135">For more information about abstract classes, see [Abstract Classes](../abstract-classes.md).</span></span>

<span data-ttu-id="572c1-136">Le dichiarazioni di metodo astratto non includono un corpo del metodo.</span><span class="sxs-lookup"><span data-stu-id="572c1-136">Abstract method declarations do not include a method body.</span></span> <span data-ttu-id="572c1-137">Al contrario, il nome del metodo è seguito da due punti (:) e una firma di tipo per il metodo.</span><span class="sxs-lookup"><span data-stu-id="572c1-137">Instead, the name of the method is followed by a colon (:) and a type signature for the method.</span></span> <span data-ttu-id="572c1-138">La firma del tipo di un metodo è uguale a quello mostrata da IntelliSense quando si posiziona il puntatore del mouse su un nome di metodo nell'Editor di codice di Visual Studio, ad eccezione senza i nomi dei parametri.</span><span class="sxs-lookup"><span data-stu-id="572c1-138">The type signature of a method is the same as that shown by IntelliSense when you pause the mouse pointer over a method name in the Visual Studio Code Editor, except without parameter names.</span></span> <span data-ttu-id="572c1-139">Le firme di tipo vengono visualizzate dall'interprete, fsi.exe, anche quando si lavora in modo interattivo.</span><span class="sxs-lookup"><span data-stu-id="572c1-139">Type signatures are also displayed by the interpreter, fsi.exe, when you are working interactively.</span></span> <span data-ttu-id="572c1-140">La firma del tipo di un metodo è formata elencando i tipi dei parametri, seguiti dal tipo restituito, con i simboli separatori appropriati.</span><span class="sxs-lookup"><span data-stu-id="572c1-140">The type signature of a method is formed by listing out the types of the parameters, followed by the return type, with appropriate separator symbols.</span></span> <span data-ttu-id="572c1-141">Parametri sottoposti a currying sono separati da `->` e i parametri di tupla sono separati da `*`.</span><span class="sxs-lookup"><span data-stu-id="572c1-141">Curried parameters are separated by `->` and tuple parameters are separated by `*`.</span></span> <span data-ttu-id="572c1-142">Il valore restituito è sempre separato dagli argomenti per un `->` simbolo.</span><span class="sxs-lookup"><span data-stu-id="572c1-142">The return value is always separated from the arguments by a `->` symbol.</span></span> <span data-ttu-id="572c1-143">Possono utilizzare le parentesi per raggruppare i parametri complessi, ad esempio quando un tipo di funzione è un parametro, o per indicare quando una tupla viene considerata come un singolo parametro anziché come due parametri.</span><span class="sxs-lookup"><span data-stu-id="572c1-143">Parentheses can be used to group complex parameters, such as when a function type is a parameter, or to indicate when a tuple is treated as a single parameter rather than as two parameters.</span></span>

<span data-ttu-id="572c1-144">È anche possibile assegnare i metodi astratti definizioni predefinite aggiungendo la definizione per la classe e usato la `default` (parola chiave), come mostrato nel blocco di sintassi in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="572c1-144">You can also give abstract methods default definitions by adding the definition to the class and using the `default` keyword, as shown in the syntax block in this topic.</span></span> <span data-ttu-id="572c1-145">Un metodo astratto con una definizione della stessa classe è equivalente a un metodo virtuale in altri linguaggi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="572c1-145">An abstract method that has a definition in the same class is equivalent to a virtual method in other .NET Framework languages.</span></span> <span data-ttu-id="572c1-146">Se esiste una definizione, il `abstract` (parola chiave) crea un nuovo slot di distribuzione nella tabella di funzioni virtuali per la classe.</span><span class="sxs-lookup"><span data-stu-id="572c1-146">Whether or not a definition exists, the `abstract` keyword creates a new dispatch slot in the virtual function table for the class.</span></span>

<span data-ttu-id="572c1-147">Indipendentemente dal fatto che una classe base implementa metodi astratti, le classi derivate possono fornire implementazioni dei metodi astratti.</span><span class="sxs-lookup"><span data-stu-id="572c1-147">Regardless of whether a base class implements its abstract methods, derived classes can provide implementations of abstract methods.</span></span> <span data-ttu-id="572c1-148">Per implementare un metodo astratto in una classe derivata, definire un metodo che ha lo stesso nome e firma nella classe derivata, ad eccezione di usare la `override` o `default` (parola chiave) e specificare il corpo del metodo.</span><span class="sxs-lookup"><span data-stu-id="572c1-148">To implement an abstract method in a derived class, define a method that has the same name and signature in the derived class, except use the `override` or `default` keyword, and provide the method body.</span></span> <span data-ttu-id="572c1-149">Le parole chiave `override` e `default` esattamente lo stesso significato.</span><span class="sxs-lookup"><span data-stu-id="572c1-149">The keywords `override` and `default` mean exactly the same thing.</span></span> <span data-ttu-id="572c1-150">Usare `override` se il nuovo metodo che esegue l'override di un'implementazione della classe base; usare `default` quando si crea un'implementazione della stessa classe come astratta dichiarazione originale.</span><span class="sxs-lookup"><span data-stu-id="572c1-150">Use `override` if the new method overrides a base class implementation; use `default` when you create an implementation in the same class as the original abstract declaration.</span></span> <span data-ttu-id="572c1-151">Non usare il `abstract` (parola chiave) sul metodo che implementa il metodo che è stato dichiarato astratto nella classe di base.</span><span class="sxs-lookup"><span data-stu-id="572c1-151">Do not use the `abstract` keyword on the method that implements the method that was declared abstract in the base class.</span></span>

<span data-ttu-id="572c1-152">L'esempio seguente illustra un metodo astratto `Rotate` che ha un'implementazione predefinita, l'equivalente di un metodo virtuale di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="572c1-152">The following example illustrates an abstract method `Rotate` that has a default implementation, the equivalent of a .NET Framework virtual method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3403.fs)]

<span data-ttu-id="572c1-153">Nell'esempio seguente viene illustrata una classe derivata che esegue l'override di un metodo della classe base.</span><span class="sxs-lookup"><span data-stu-id="572c1-153">The following example illustrates a derived class that overrides a base class method.</span></span> <span data-ttu-id="572c1-154">In questo caso, la sostituzione viene modificato il comportamento in modo che il metodo non esegue alcuna operazione.</span><span class="sxs-lookup"><span data-stu-id="572c1-154">In this case, the override changes the behavior so that the method does nothing.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3404.fs)]

## <a name="overloaded-methods"></a><span data-ttu-id="572c1-155">Metodi di overload</span><span class="sxs-lookup"><span data-stu-id="572c1-155">Overloaded Methods</span></span>

<span data-ttu-id="572c1-156">Metodi di overload sono metodi che dispongono di nomi identici in un determinato tipo, ma che dispongono di argomenti diversi.</span><span class="sxs-lookup"><span data-stu-id="572c1-156">Overloaded methods are methods that have identical names in a given type but that have different arguments.</span></span> <span data-ttu-id="572c1-157">In F#, gli argomenti facoltativi vengono in genere usati invece i metodi di overload.</span><span class="sxs-lookup"><span data-stu-id="572c1-157">In F#, optional arguments are usually used instead of overloaded methods.</span></span> <span data-ttu-id="572c1-158">Tuttavia, i metodi di overload sono consentiti nella lingua, condizione che gli argomenti sono in formato di tupla, non sottoposto a currying.</span><span class="sxs-lookup"><span data-stu-id="572c1-158">However, overloaded methods are permitted in the language, provided that the arguments are in tuple form, not curried form.</span></span>

## <a name="optional-arguments"></a><span data-ttu-id="572c1-159">Argomenti facoltativi</span><span class="sxs-lookup"><span data-stu-id="572c1-159">Optional Arguments</span></span>

<span data-ttu-id="572c1-160">A partire da F# 4.1, è anche possibile avere argomenti facoltativi con un valore di parametro predefinito nei metodi.</span><span class="sxs-lookup"><span data-stu-id="572c1-160">Starting with F# 4.1, you can also have optional arguments with a default parameter value in methods.</span></span>  <span data-ttu-id="572c1-161">In modo da facilitare l'interoperabilità con codice c#.</span><span class="sxs-lookup"><span data-stu-id="572c1-161">This is to help facilitate interoperation with C# code.</span></span>  <span data-ttu-id="572c1-162">Nell'esempio seguente viene illustrata la sintassi:</span><span class="sxs-lookup"><span data-stu-id="572c1-162">The following example demonstrates the syntax:</span></span>

```fsharp
// A class with a method M, which takes in an optional integer argument.
type C() =
    __.M([<Optional; DefaultParameterValue(12)>] i) = i + 1
```

<span data-ttu-id="572c1-163">Si noti che il valore passato per `DefaultParameterValue` deve corrispondere al tipo di input.</span><span class="sxs-lookup"><span data-stu-id="572c1-163">Note that the value passed in for `DefaultParameterValue` must match the input type.</span></span>  <span data-ttu-id="572c1-164">Nell'esempio precedente, è un `int`.</span><span class="sxs-lookup"><span data-stu-id="572c1-164">In the above sample, it is an `int`.</span></span>  <span data-ttu-id="572c1-165">Tentativo di passare un valore diverso da integer in `DefaultParameterValue` comporterebbe un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="572c1-165">Attempting to pass a non-integer value into `DefaultParameterValue` would result in a compile error.</span></span>

## <a name="example-properties-and-methods"></a><span data-ttu-id="572c1-166">Esempio: Proprietà e metodi</span><span class="sxs-lookup"><span data-stu-id="572c1-166">Example: Properties and Methods</span></span>

<span data-ttu-id="572c1-167">L'esempio seguente contiene un tipo che contiene esempi di campi, funzioni private, le proprietà e un metodo statico.</span><span class="sxs-lookup"><span data-stu-id="572c1-167">The following example contains a type that has examples of fields, private functions, properties, and a static method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3406.fs)]

## <a name="see-also"></a><span data-ttu-id="572c1-168">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="572c1-168">See also</span></span>

- [<span data-ttu-id="572c1-169">Membri</span><span class="sxs-lookup"><span data-stu-id="572c1-169">Members</span></span>](index.md)