---
title: Associazioni let
description: Informazioni su come usare un' F# associazione ' Let ', che associa un identificatore a un valore o una funzione.
ms.date: 05/16/2016
ms.openlocfilehash: 654631c7d1c48d8737e6098c98efee54cfdd91be
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630645"
---
# <a name="let-bindings"></a><span data-ttu-id="d61e5-103">Associazioni let</span><span class="sxs-lookup"><span data-stu-id="d61e5-103">let Bindings</span></span>

<span data-ttu-id="d61e5-104">Un' *associazione* associa un identificatore con un valore o una funzione.</span><span class="sxs-lookup"><span data-stu-id="d61e5-104">A *binding* associates an identifier with a value or function.</span></span> <span data-ttu-id="d61e5-105">Usare la `let` parola chiave per associare un nome a un valore o a una funzione.</span><span class="sxs-lookup"><span data-stu-id="d61e5-105">You use the `let` keyword to bind a name to a value or function.</span></span>

## <a name="syntax"></a><span data-ttu-id="d61e5-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d61e5-106">Syntax</span></span>

```fsharp
// Binding a value:
let identifier-or-pattern [: type] =expressionbody-expression
// Binding a function value:
let identifier parameter-list [: return-type ] =expressionbody-expression
```

## <a name="remarks"></a><span data-ttu-id="d61e5-107">Note</span><span class="sxs-lookup"><span data-stu-id="d61e5-107">Remarks</span></span>

<span data-ttu-id="d61e5-108">La `let` parola chiave viene utilizzata nelle espressioni di associazione per definire i valori o i valori di funzione per uno o più nomi.</span><span class="sxs-lookup"><span data-stu-id="d61e5-108">The `let` keyword is used in binding expressions to define values or function values for one or more names.</span></span> <span data-ttu-id="d61e5-109">La forma più semplice dell' `let` espressione associa un nome a un valore semplice, come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="d61e5-109">The simplest form of the `let` expression binds a name to a simple value, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1101.fs)]

<span data-ttu-id="d61e5-110">Se si separa l'espressione dall'identificatore utilizzando una nuova riga, è necessario rientrare ogni riga dell'espressione, come nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="d61e5-110">If you separate the expression from the identifier by using a new line, you must indent each line of the expression, as in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1102.fs)]

<span data-ttu-id="d61e5-111">Anziché solo un nome, è possibile specificare un modello che contiene nomi, ad esempio una tupla, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="d61e5-111">Instead of just a name, a pattern that contains names can be specified, for example, a tuple, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1103.fs)]

<span data-ttu-id="d61e5-112">*Body-Expression* è l'espressione in cui vengono usati i nomi.</span><span class="sxs-lookup"><span data-stu-id="d61e5-112">The *body-expression* is the expression in which the names are used.</span></span> <span data-ttu-id="d61e5-113">L'espressione Body viene visualizzata sulla propria riga, rientrata in linea esattamente con il primo carattere `let` della parola chiave:</span><span class="sxs-lookup"><span data-stu-id="d61e5-113">The body expression appears on its own line, indented to line up exactly with the first character in the `let` keyword:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1104.fs)]

<span data-ttu-id="d61e5-114">Un' `let` associazione può essere visualizzata a livello di modulo, nella definizione di un tipo di classe o negli ambiti locali, ad esempio in una definizione di funzione.</span><span class="sxs-lookup"><span data-stu-id="d61e5-114">A `let` binding can appear at the module level, in the definition of a class type, or in local scopes, such as in a function definition.</span></span> <span data-ttu-id="d61e5-115">Un' `let` associazione al primo livello in un modulo o in un tipo di classe non deve avere un'espressione Body, ma a livelli di ambito diversi, l'espressione corpo è obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="d61e5-115">A `let` binding at the top level in a module or in a class type does not need to have a body expression, but at other scope levels, the body expression is required.</span></span> <span data-ttu-id="d61e5-116">I nomi associati sono utilizzabili dopo il punto di definizione, ma non in nessun punto prima `let` che l'associazione appaia, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="d61e5-116">The bound names are usable after the point of definition, but not at any point before the `let` binding appears, as is illustrated in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1105.fs)]

## <a name="function-bindings"></a><span data-ttu-id="d61e5-117">Associazioni di funzioni</span><span class="sxs-lookup"><span data-stu-id="d61e5-117">Function Bindings</span></span>

<span data-ttu-id="d61e5-118">Le associazioni di funzioni seguono le regole per le associazioni di valori, ad eccezione del fatto che le associazioni di funzioni includono il nome della funzione e i parametri, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="d61e5-118">Function bindings follow the rules for value bindings, except that function bindings include the function name and the parameters, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1106.fs)]

<span data-ttu-id="d61e5-119">In generale, i parametri sono modelli, ad esempio un modello di tupla:</span><span class="sxs-lookup"><span data-stu-id="d61e5-119">In general, parameters are patterns, such as a tuple pattern:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1107.fs)]

<span data-ttu-id="d61e5-120">Un' `let` espressione di associazione restituisce il valore dell'ultima espressione.</span><span class="sxs-lookup"><span data-stu-id="d61e5-120">A `let` binding expression evaluates to the value of the last expression.</span></span> <span data-ttu-id="d61e5-121">Nell'esempio di codice seguente, pertanto, il valore di `result` viene calcolato da `100 * function3 (1, 2)` `300`, che restituisce.</span><span class="sxs-lookup"><span data-stu-id="d61e5-121">Therefore, in the following code example, the value of `result` is computed from `100 * function3 (1, 2)`, which evaluates to `300`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1109.fs)]

<span data-ttu-id="d61e5-122">Per altre informazioni, vedere [Funzioni](index.md).</span><span class="sxs-lookup"><span data-stu-id="d61e5-122">For more information, see [Functions](index.md).</span></span>

## <a name="type-annotations"></a><span data-ttu-id="d61e5-123">Annotazioni di tipo</span><span class="sxs-lookup"><span data-stu-id="d61e5-123">Type Annotations</span></span>

<span data-ttu-id="d61e5-124">È possibile specificare i tipi per i parametri includendo i due punti (:) seguito da un nome di tipo, racchiuso tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="d61e5-124">You can specify types for parameters by including a colon (:) followed by a type name, all enclosed in parentheses.</span></span> <span data-ttu-id="d61e5-125">È anche possibile specificare il tipo del valore restituito aggiungendo i due punti e il tipo dopo l'ultimo parametro.</span><span class="sxs-lookup"><span data-stu-id="d61e5-125">You can also specify the type of the return value by appending the colon and type after the last parameter.</span></span> <span data-ttu-id="d61e5-126">Di seguito sono riportate `function1`le annotazioni di tipo completo per, con Integer come tipi di parametro.</span><span class="sxs-lookup"><span data-stu-id="d61e5-126">The full type annotations for `function1`, with integers as the parameter types, would be as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1108.fs)]

<span data-ttu-id="d61e5-127">Quando non sono presenti parametri di tipo esplicito, viene usata l'inferenza del tipo per determinare i tipi di parametri delle funzioni.</span><span class="sxs-lookup"><span data-stu-id="d61e5-127">When there are no explicit type parameters, type inference is used to determine the types of parameters of functions.</span></span> <span data-ttu-id="d61e5-128">Questo può includere la generalizzazione automatica del tipo di un parametro in modo che sia generico.</span><span class="sxs-lookup"><span data-stu-id="d61e5-128">This can include automatically generalizing the type of a parameter to be generic.</span></span>

<span data-ttu-id="d61e5-129">Per altre informazioni, vedere [generalizzazione automatica](../generics/automatic-generalization.md) e [inferenza del tipo](../type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="d61e5-129">For more information, see [Automatic Generalization](../generics/automatic-generalization.md) and [Type Inference](../type-inference.md).</span></span>

## <a name="let-bindings-in-classes"></a><span data-ttu-id="d61e5-130">Associazioni let nelle classi</span><span class="sxs-lookup"><span data-stu-id="d61e5-130">let Bindings in Classes</span></span>

<span data-ttu-id="d61e5-131">Un' `let` associazione può essere visualizzata in un tipo di classe ma non in una struttura o un tipo di record.</span><span class="sxs-lookup"><span data-stu-id="d61e5-131">A `let` binding can appear in a class type but not in a structure or record type.</span></span> <span data-ttu-id="d61e5-132">Per usare un'associazione let in un tipo di classe, la classe deve avere un costruttore primario.</span><span class="sxs-lookup"><span data-stu-id="d61e5-132">To use a let binding in a class type, the class must have a primary constructor.</span></span> <span data-ttu-id="d61e5-133">I parametri del costruttore devono comparire dopo il nome del tipo nella definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="d61e5-133">Constructor parameters must appear after the type name in the class definition.</span></span> <span data-ttu-id="d61e5-134">Un' `let` associazione in un tipo di classe definisce i campi e i membri privati per quel tipo di classe `do` e, insieme alle associazioni nel tipo, costituisce il codice per il costruttore primario per il tipo.</span><span class="sxs-lookup"><span data-stu-id="d61e5-134">A `let` binding in a class type defines private fields and members for that class type and, together with `do` bindings in the type, forms the code for the primary constructor for the type.</span></span> <span data-ttu-id="d61e5-135">Negli esempi di codice seguenti viene illustrata una classe `MyClass` con `field2`campi `field1` privati e.</span><span class="sxs-lookup"><span data-stu-id="d61e5-135">The following code examples show a class `MyClass` with private fields `field1` and `field2`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1110.fs)]

<span data-ttu-id="d61e5-136">Gli ambiti di `field1` e `field2` sono limitati al tipo in cui vengono dichiarati.</span><span class="sxs-lookup"><span data-stu-id="d61e5-136">The scopes of `field1` and `field2` are limited to the type in which they are declared.</span></span> <span data-ttu-id="d61e5-137">Per ulteriori informazioni, vedere [ `let` binding in classi](../members/let-bindings-in-classes.md) e [classi](../classes.md).</span><span class="sxs-lookup"><span data-stu-id="d61e5-137">For more information, see [`let` Bindings in Classes](../members/let-bindings-in-classes.md) and [Classes](../classes.md).</span></span>

## <a name="type-parameters-in-let-bindings"></a><span data-ttu-id="d61e5-138">Parametri di tipo nelle associazioni let</span><span class="sxs-lookup"><span data-stu-id="d61e5-138">Type Parameters in let Bindings</span></span>

<span data-ttu-id="d61e5-139">Un' `let` associazione a livello di modulo, in un tipo o in un'espressione di calcolo può avere parametri di tipo espliciti.</span><span class="sxs-lookup"><span data-stu-id="d61e5-139">A `let` binding at the module level, in a type, or in a computation expression can have explicit type parameters.</span></span> <span data-ttu-id="d61e5-140">Un'associazione let in un'espressione, ad esempio all'interno di una definizione di funzione, non può avere parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="d61e5-140">A let binding in an expression, such as within a function definition, cannot have type parameters.</span></span> <span data-ttu-id="d61e5-141">Per altre informazioni, vedere [Generics](../generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="d61e5-141">For more information, see [Generics](../generics/index.md).</span></span>

## <a name="attributes-on-let-bindings"></a><span data-ttu-id="d61e5-142">Attributi sulle associazioni let</span><span class="sxs-lookup"><span data-stu-id="d61e5-142">Attributes on let Bindings</span></span>

<span data-ttu-id="d61e5-143">Gli attributi possono essere applicati alle associazioni di `let` primo livello in un modulo, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="d61e5-143">Attributes can be applied to top-level `let` bindings in a module, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1111.fs)]

## <a name="scope-and-accessibility-of-let-bindings"></a><span data-ttu-id="d61e5-144">Ambito e accessibilità delle associazioni let</span><span class="sxs-lookup"><span data-stu-id="d61e5-144">Scope and Accessibility of Let Bindings</span></span>

<span data-ttu-id="d61e5-145">L'ambito di un'entità dichiarata con un'associazione let è limitato alla parte dell'ambito contenitore, ad esempio una funzione, un modulo, un file o una classe, dopo che l'associazione viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="d61e5-145">The scope of an entity declared with a let binding is limited to the portion of the containing scope (such as a function, module, file or class) after the binding appears.</span></span> <span data-ttu-id="d61e5-146">È pertanto possibile affermare che un'associazione let introduce un nome in un ambito.</span><span class="sxs-lookup"><span data-stu-id="d61e5-146">Therefore, it can be said that a let binding introduces a name into a scope.</span></span> <span data-ttu-id="d61e5-147">In un modulo, una funzione o un valore associato a Let è accessibile ai client di un modulo, purché il modulo sia accessibile, perché le associazioni let in un modulo vengono compilate in funzioni pubbliche del modulo.</span><span class="sxs-lookup"><span data-stu-id="d61e5-147">In a module, a let-bound value or function is accessible to clients of a module as long as the module is accessible, since the let bindings in a module are compiled into public functions of the module.</span></span> <span data-ttu-id="d61e5-148">Al contrario, le associazioni let in una classe sono private per la classe.</span><span class="sxs-lookup"><span data-stu-id="d61e5-148">By contrast, let bindings in a class are private to the class.</span></span>

<span data-ttu-id="d61e5-149">In genere, le funzioni nei moduli devono essere qualificate dal nome del modulo quando vengono usate dal codice client.</span><span class="sxs-lookup"><span data-stu-id="d61e5-149">Normally, functions in modules must be qualified by the name of the module when used by client code.</span></span> <span data-ttu-id="d61e5-150">Se ad esempio un modulo `Module1` dispone di una funzione `function1`, gli utenti specificano `Module1.function1` di fare riferimento alla funzione.</span><span class="sxs-lookup"><span data-stu-id="d61e5-150">For example, if a module `Module1` has a function `function1`, users would specify `Module1.function1` to refer to the function.</span></span>

<span data-ttu-id="d61e5-151">Gli utenti di un modulo possono usare una dichiarazione di importazione per rendere le funzioni all'interno di tale modulo disponibili per l'uso senza essere qualificate dal nome del modulo.</span><span class="sxs-lookup"><span data-stu-id="d61e5-151">Users of a module may use an import declaration to make the functions within that module available for use without being qualified by the module name.</span></span> <span data-ttu-id="d61e5-152">Nell'esempio appena illustrato, gli utenti del modulo possono in tal caso aprire il modulo usando la dichiarazione di importazione aperta `Module1` e successivamente fare riferimento direttamente a. `function1`</span><span class="sxs-lookup"><span data-stu-id="d61e5-152">In the example just mentioned, users of the module can in that case open the module by using the import declaration open `Module1` and thereafter refer to `function1` directly.</span></span>

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

<span data-ttu-id="d61e5-153">Alcuni moduli hanno l'attributo [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15), il che significa che le funzioni che espongono devono essere qualificate con il nome del modulo.</span><span class="sxs-lookup"><span data-stu-id="d61e5-153">Some modules have the attribute [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15), which means that the functions that they expose must be qualified with the name of the module.</span></span> <span data-ttu-id="d61e5-154">Ad esempio, il F# modulo List presenta questo attributo.</span><span class="sxs-lookup"><span data-stu-id="d61e5-154">For example, the F# List module has this attribute.</span></span>

<span data-ttu-id="d61e5-155">Per ulteriori informazioni sui moduli e sul controllo di accesso, vedere [moduli](../modules.md) e [controllo di accesso](../access-control.md).</span><span class="sxs-lookup"><span data-stu-id="d61e5-155">For more information on modules and access control, see [Modules](../modules.md) and [Access Control](../access-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d61e5-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d61e5-156">See also</span></span>

- [<span data-ttu-id="d61e5-157">Funzioni</span><span class="sxs-lookup"><span data-stu-id="d61e5-157">Functions</span></span>](index.md)
- [<span data-ttu-id="d61e5-158">Associazioni `let` nelle classi</span><span class="sxs-lookup"><span data-stu-id="d61e5-158">`let` Bindings in Classes</span></span>](../members/let-bindings-in-classes.md)
