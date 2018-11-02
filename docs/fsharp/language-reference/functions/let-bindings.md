---
title: Associazioni let (F#)
description: "Informazioni su come usare un'associazione, che associa un identificatore con un valore o funzione ' let' F #."
ms.date: 05/16/2016
ms.openlocfilehash: 1a35b5a39f2768a18665b5c7fe768af0e7714577
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "43777470"
---
# <a name="let-bindings"></a><span data-ttu-id="19c39-103">Associazioni let</span><span class="sxs-lookup"><span data-stu-id="19c39-103">let Bindings</span></span>

<span data-ttu-id="19c39-104">Oggetto *associazione* associa un identificatore con un valore o una funzione.</span><span class="sxs-lookup"><span data-stu-id="19c39-104">A *binding* associates an identifier with a value or function.</span></span> <span data-ttu-id="19c39-105">Si utilizza il `let` (parola chiave) per associare un nome a un valore o una funzione.</span><span class="sxs-lookup"><span data-stu-id="19c39-105">You use the `let` keyword to bind a name to a value or function.</span></span>

## <a name="syntax"></a><span data-ttu-id="19c39-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="19c39-106">Syntax</span></span>

```fsharp
// Binding a value:
let identifier-or-pattern [: type] =expressionbody-expression
// Binding a function value:
let identifier parameter-list [: return-type ] =expressionbody-expression
```

## <a name="remarks"></a><span data-ttu-id="19c39-107">Note</span><span class="sxs-lookup"><span data-stu-id="19c39-107">Remarks</span></span>

<span data-ttu-id="19c39-108">Il `let` parola chiave viene usata nelle espressioni per definire i valori o valori di funzione per uno o più nomi di associazione.</span><span class="sxs-lookup"><span data-stu-id="19c39-108">The `let` keyword is used in binding expressions to define values or function values for one or more names.</span></span> <span data-ttu-id="19c39-109">Il modo più semplice la `let` espressione associa un nome a un valore semplice, come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="19c39-109">The simplest form of the `let` expression binds a name to a simple value, as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1101.fs)]

<span data-ttu-id="19c39-110">Se l'espressione dall'identificatore sono separati, usando una nuova riga, è necessario impostare un rientro di ogni riga dell'espressione, come nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="19c39-110">If you separate the expression from the identifier by using a new line, you must indent each line of the expression, as in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1102.fs)]

<span data-ttu-id="19c39-111">Anziché un nome, è possibile specificare un modello che contiene i nomi, ad esempio, una tupla, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="19c39-111">Instead of just a name, a pattern that contains names can be specified, for example, a tuple, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1103.fs)]

<span data-ttu-id="19c39-112">Il *espressione corpo* è l'espressione in cui vengono utilizzati i nomi.</span><span class="sxs-lookup"><span data-stu-id="19c39-112">The *body-expression* is the expression in which the names are used.</span></span> <span data-ttu-id="19c39-113">L'espressione del corpo viene visualizzato nella riga a sé stante, rientrata alla riga backup esattamente con il primo carattere il `let` (parola chiave):</span><span class="sxs-lookup"><span data-stu-id="19c39-113">The body expression appears on its own line, indented to line up exactly with the first character in the `let` keyword:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1104.fs)]

<span data-ttu-id="19c39-114">Oggetto `let` associazione può essere visualizzati a livello di modulo, nella definizione di un tipo di classe o negli ambiti locali, ad esempio in una definizione di funzione.</span><span class="sxs-lookup"><span data-stu-id="19c39-114">A `let` binding can appear at the module level, in the definition of a class type, or in local scopes, such as in a function definition.</span></span> <span data-ttu-id="19c39-115">Oggetto `let` associazione al primo livello in un modulo o in un tipo di classe non è necessario disporre di un'espressione corpo, ma in altri livelli di ambito, è necessaria l'espressione del corpo.</span><span class="sxs-lookup"><span data-stu-id="19c39-115">A `let` binding at the top level in a module or in a class type does not need to have a body expression, but at other scope levels, the body expression is required.</span></span> <span data-ttu-id="19c39-116">I nomi associati possono essere utilizzati dopo il separatore della definizione, ma non in qualsiasi momento prima di `let` associazione viene visualizzata, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="19c39-116">The bound names are usable after the point of definition, but not at any point before the `let` binding appears, as is illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1105.fs)]

## <a name="function-bindings"></a><span data-ttu-id="19c39-117">Associazioni di funzione</span><span class="sxs-lookup"><span data-stu-id="19c39-117">Function Bindings</span></span>

<span data-ttu-id="19c39-118">Le associazioni di funzioni seguono le regole per le associazioni di valore, ad eccezione del fatto che le associazioni di funzioni includono il nome della funzione e i parametri, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="19c39-118">Function bindings follow the rules for value bindings, except that function bindings include the function name and the parameters, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1106.fs)]

<span data-ttu-id="19c39-119">In generale, i parametri sono modelli, ad esempio un modello tupla:</span><span class="sxs-lookup"><span data-stu-id="19c39-119">In general, parameters are patterns, such as a tuple pattern:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1107.fs)]

<span data-ttu-id="19c39-120">Oggetto `let` espressione di associazione restituisce il valore dell'ultima espressione.</span><span class="sxs-lookup"><span data-stu-id="19c39-120">A `let` binding expression evaluates to the value of the last expression.</span></span> <span data-ttu-id="19c39-121">Pertanto, nell'esempio di codice seguente, il valore di `result` calcolato dal `100 * function3 (1, 2)`, che viene valutata `300`.</span><span class="sxs-lookup"><span data-stu-id="19c39-121">Therefore, in the following code example, the value of `result` is computed from `100 * function3 (1, 2)`, which evaluates to `300`.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1109.fs)]

<span data-ttu-id="19c39-122">Per altre informazioni, vedere [Funzioni](index.md).</span><span class="sxs-lookup"><span data-stu-id="19c39-122">For more information, see [Functions](index.md).</span></span>

## <a name="type-annotations"></a><span data-ttu-id="19c39-123">Annotazioni di tipo</span><span class="sxs-lookup"><span data-stu-id="19c39-123">Type Annotations</span></span>

<span data-ttu-id="19c39-124">È possibile specificare tipi ai parametri, includendo i due punti (:) seguito da un nome di tipo, tutto racchiuso tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="19c39-124">You can specify types for parameters by including a colon (:) followed by a type name, all enclosed in parentheses.</span></span> <span data-ttu-id="19c39-125">È anche possibile specificare il tipo del valore restituito mediante l'aggiunta di due punti e il tipo dopo l'ultimo parametro.</span><span class="sxs-lookup"><span data-stu-id="19c39-125">You can also specify the type of the return value by appending the colon and type after the last parameter.</span></span> <span data-ttu-id="19c39-126">Le annotazioni di tipo completo per `function1`, con numeri interi come tipi di parametri, sarebbe come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="19c39-126">The full type annotations for `function1`, with integers as the parameter types, would be as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1108.fs)]

<span data-ttu-id="19c39-127">Quando non sono presenti parametri di tipo esplicito, l'inferenza del tipo viene utilizzato per determinare i tipi di parametri delle funzioni.</span><span class="sxs-lookup"><span data-stu-id="19c39-127">When there are no explicit type parameters, type inference is used to determine the types of parameters of functions.</span></span> <span data-ttu-id="19c39-128">Può trattarsi di generalizzazione automaticamente il tipo di un parametro come generici.</span><span class="sxs-lookup"><span data-stu-id="19c39-128">This can include automatically generalizing the type of a parameter to be generic.</span></span>

<span data-ttu-id="19c39-129">Per altre informazioni, vedere [generalizzazione automatica](../generics/automatic-generalization.md) e [l'inferenza del tipo](../type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="19c39-129">For more information, see [Automatic Generalization](../generics/automatic-generalization.md) and [Type Inference](../type-inference.md).</span></span>

## <a name="let-bindings-in-classes"></a><span data-ttu-id="19c39-130">Associazioni let nelle classi</span><span class="sxs-lookup"><span data-stu-id="19c39-130">let Bindings in Classes</span></span>

<span data-ttu-id="19c39-131">Oggetto `let` associazione può essere visualizzati in un tipo di classe ma non in una struttura o un tipo di record.</span><span class="sxs-lookup"><span data-stu-id="19c39-131">A `let` binding can appear in a class type but not in a structure or record type.</span></span> <span data-ttu-id="19c39-132">Per usare un'associazione let in un tipo di classe, la classe deve avere un costruttore primario.</span><span class="sxs-lookup"><span data-stu-id="19c39-132">To use a let binding in a class type, the class must have a primary constructor.</span></span> <span data-ttu-id="19c39-133">I parametri del costruttore devono essere visualizzata dopo il nome del tipo nella definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="19c39-133">Constructor parameters must appear after the type name in the class definition.</span></span> <span data-ttu-id="19c39-134">Oggetto `let` associazione in un tipo di classe definisce i campi privati e i membri per tipo di classe e, insieme a `do` associazioni del tipo, il codice per il costruttore principale per il tipo di form.</span><span class="sxs-lookup"><span data-stu-id="19c39-134">A `let` binding in a class type defines private fields and members for that class type and, together with `do` bindings in the type, forms the code for the primary constructor for the type.</span></span> <span data-ttu-id="19c39-135">Gli esempi di codice seguente mostrano una classe `MyClass` con i campi privati `field1` e `field2`.</span><span class="sxs-lookup"><span data-stu-id="19c39-135">The following code examples show a class `MyClass` with private fields `field1` and `field2`.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1110.fs)]

<span data-ttu-id="19c39-136">Gli ambiti delle `field1` e `field2` sono limitati al tipo in cui sono dichiarate.</span><span class="sxs-lookup"><span data-stu-id="19c39-136">The scopes of `field1` and `field2` are limited to the type in which they are declared.</span></span> <span data-ttu-id="19c39-137">Per altre informazioni, vedere [ `let` associazioni nelle classi](../members/let-bindings-in-classes.md) e [classi](../classes.md).</span><span class="sxs-lookup"><span data-stu-id="19c39-137">For more information, see [`let` Bindings in Classes](../members/let-bindings-in-classes.md) and [Classes](../classes.md).</span></span>

## <a name="type-parameters-in-let-bindings"></a><span data-ttu-id="19c39-138">Parametri di tipo nelle associazioni let</span><span class="sxs-lookup"><span data-stu-id="19c39-138">Type Parameters in let Bindings</span></span>

<span data-ttu-id="19c39-139">Oggetto `let` associazione a livello di modulo, in un tipo o in un'espressione di calcolo può avere parametri di tipo esplicito.</span><span class="sxs-lookup"><span data-stu-id="19c39-139">A `let` binding at the module level, in a type, or in a computation expression can have explicit type parameters.</span></span> <span data-ttu-id="19c39-140">Un'associazione in un'espressione, ad esempio all'interno di una definizione di funzione, let non può avere parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="19c39-140">A let binding in an expression, such as within a function definition, cannot have type parameters.</span></span> <span data-ttu-id="19c39-141">Per altre informazioni, vedere [Generics](../generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="19c39-141">For more information, see [Generics](../generics/index.md).</span></span>

## <a name="attributes-on-let-bindings"></a><span data-ttu-id="19c39-142">Attributi nelle associazioni let</span><span class="sxs-lookup"><span data-stu-id="19c39-142">Attributes on let Bindings</span></span>

<span data-ttu-id="19c39-143">Gli attributi possono essere applicati a livello superiore `let` associazioni in un modulo, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="19c39-143">Attributes can be applied to top-level `let` bindings in a module, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1111.fs)]

## <a name="scope-and-accessibility-of-let-bindings"></a><span data-ttu-id="19c39-144">Ambito e l'accessibilità delle associazioni Let</span><span class="sxs-lookup"><span data-stu-id="19c39-144">Scope and Accessibility of Let Bindings</span></span>

<span data-ttu-id="19c39-145">L'ambito di un'entità dichiarata con un'associazione "Let" è limitato alla porzione dell'oggetto contenitore di ambito (ad esempio, una funzione, modulo, file o classe) quando viene visualizzato l'associazione.</span><span class="sxs-lookup"><span data-stu-id="19c39-145">The scope of an entity declared with a let binding is limited to the portion of the containing scope (such as a function, module, file or class) after the binding appears.</span></span> <span data-ttu-id="19c39-146">Pertanto, si può dire che un'associazione "Let" introduce un nome in un ambito.</span><span class="sxs-lookup"><span data-stu-id="19c39-146">Therefore, it can be said that a let binding introduces a name into a scope.</span></span> <span data-ttu-id="19c39-147">In un modulo, un valore con associazione a let o una funzione è accessibile ai client di un modulo, purché il modulo è accessibile, poiché i binding "Let" in un modulo vengono compilati in funzioni pubbliche del modulo.</span><span class="sxs-lookup"><span data-stu-id="19c39-147">In a module, a let-bound value or function is accessible to clients of a module as long as the module is accessible, since the let bindings in a module are compiled into public functions of the module.</span></span> <span data-ttu-id="19c39-148">Al contrario, le associazioni let in una classe sono private alla classe.</span><span class="sxs-lookup"><span data-stu-id="19c39-148">By contrast, let bindings in a class are private to the class.</span></span>

<span data-ttu-id="19c39-149">In genere, le funzioni in moduli devono essere qualificate dal nome del modulo quando vengono usati dal codice client.</span><span class="sxs-lookup"><span data-stu-id="19c39-149">Normally, functions in modules must be qualified by the name of the module when used by client code.</span></span> <span data-ttu-id="19c39-150">Ad esempio, se un modulo `Module1` dispone di una funzione `function1`, specificano gli utenti `Module1.function1` per fare riferimento alla funzione.</span><span class="sxs-lookup"><span data-stu-id="19c39-150">For example, if a module `Module1` has a function `function1`, users would specify `Module1.function1` to refer to the function.</span></span>

<span data-ttu-id="19c39-151">Gli utenti di un modulo possono usare una dichiarazione di importazione per rendere disponibili per l'uso di funzioni all'interno del modulo senza siano qualificate dal nome del modulo.</span><span class="sxs-lookup"><span data-stu-id="19c39-151">Users of a module may use an import declaration to make the functions within that module available for use without being qualified by the module name.</span></span> <span data-ttu-id="19c39-152">Nell'esempio descritti in precedenza, gli utenti del modulo possono aprire in questo caso il modulo tramite l'apertura di dichiarazione di importazione `Module1` e quindi fare riferimento a `function1` direttamente.</span><span class="sxs-lookup"><span data-stu-id="19c39-152">In the example just mentioned, users of the module can in that case open the module by using the import declaration open `Module1` and thereafter refer to `function1` directly.</span></span>

```fsharp
module Module1 =
    let function1 x = x + 1.0

module Module2 =
    let function2 x =
        Module1.function1 x

open Module1

let function3 x =
    function1 x
```

<span data-ttu-id="19c39-153">Alcuni moduli presentano l'attributo [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15), il che significa che le funzioni che espongono devono essere qualificate con il nome del modulo.</span><span class="sxs-lookup"><span data-stu-id="19c39-153">Some modules have the attribute [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15), which means that the functions that they expose must be qualified with the name of the module.</span></span> <span data-ttu-id="19c39-154">Ad esempio, il modulo elenco di F # ha questo attributo.</span><span class="sxs-lookup"><span data-stu-id="19c39-154">For example, the F# List module has this attribute.</span></span>

<span data-ttu-id="19c39-155">Per altre informazioni sul controllo di accesso e i moduli, vedere [moduli](../modules.md) e [Access Control](../access-control.md).</span><span class="sxs-lookup"><span data-stu-id="19c39-155">For more information on modules and access control, see [Modules](../modules.md) and [Access Control](../access-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="19c39-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19c39-156">See also</span></span>

- [<span data-ttu-id="19c39-157">Funzioni</span><span class="sxs-lookup"><span data-stu-id="19c39-157">Functions</span></span>](index.md)
- [<span data-ttu-id="19c39-158">Associazioni `let` nelle classi</span><span class="sxs-lookup"><span data-stu-id="19c39-158">`let` Bindings in Classes</span></span>](../members/let-bindings-in-classes.md)
