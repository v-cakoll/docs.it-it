---
title: Criteri di ricerca [F#]
description: 'Informazioni su come i modelli vengono usati in F # per confrontare i dati con strutture logiche, scomporre i dati in parti costituenti o estrarre informazioni dai dati.'
ms.date: 05/16/2016
ms.openlocfilehash: 5ad3d3e1a78246afdfa2948fd0fb84fa04686d30
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "45991424"
---
# <a name="pattern-matching"></a><span data-ttu-id="3d011-103">Criteri di ricerca</span><span class="sxs-lookup"><span data-stu-id="3d011-103">Pattern Matching</span></span>

<span data-ttu-id="3d011-104">I modelli sono regole per la trasformazione dei dati di input.</span><span class="sxs-lookup"><span data-stu-id="3d011-104">Patterns are rules for transforming input data.</span></span> <span data-ttu-id="3d011-105">Vengono utilizzati nel linguaggio F # per confrontare i dati con una o più strutture logiche, scomporre i dati in parti costituenti o estrarre informazioni dai dati in vari modi.</span><span class="sxs-lookup"><span data-stu-id="3d011-105">They are used throughout the F# language to compare data with a logical structure or structures, decompose data into constituent parts, or extract information from data in various ways.</span></span>

## <a name="remarks"></a><span data-ttu-id="3d011-106">Note</span><span class="sxs-lookup"><span data-stu-id="3d011-106">Remarks</span></span>

<span data-ttu-id="3d011-107">I modelli vengono utilizzati in numerosi costrutti di linguaggio, ad esempio il `match` espressione.</span><span class="sxs-lookup"><span data-stu-id="3d011-107">Patterns are used in many language constructs, such as the `match` expression.</span></span> <span data-ttu-id="3d011-108">Vengono usati quando si elaborano argomenti per le funzioni nel `let` associazioni, le espressioni lambda e nei gestori di eccezioni associati il `try...with` espressione.</span><span class="sxs-lookup"><span data-stu-id="3d011-108">They are used when you are processing arguments for functions in `let` bindings, lambda expressions, and in the exception handlers associated with the `try...with` expression.</span></span> <span data-ttu-id="3d011-109">Per altre informazioni, vedere [espressioni di ricerca](match-expressions.md), [associazioni let](functions/let-bindings.md), [espressioni Lambda: I `fun` parola chiave](functions/lambda-expressions-the-fun-keyword.md), e [eccezioni: il `try...with` Espressione](exception-handling/the-try-with-expression.md).</span><span class="sxs-lookup"><span data-stu-id="3d011-109">For more information, see [Match Expressions](match-expressions.md), [let Bindings](functions/let-bindings.md), [Lambda Expressions: The `fun` Keyword](functions/lambda-expressions-the-fun-keyword.md), and [Exceptions: The `try...with` Expression](exception-handling/the-try-with-expression.md).</span></span>

<span data-ttu-id="3d011-110">Ad esempio, nelle `match` espressione, il *pattern* è quello che segue il simbolo di barra verticale.</span><span class="sxs-lookup"><span data-stu-id="3d011-110">For example, in the `match` expression, the *pattern* is what follows the pipe symbol.</span></span>

```fsharp
match expression with
| pattern [ when condition ] -> result-expression
...
```

<span data-ttu-id="3d011-111">Ogni modello funge da una regola per trasformare l'input in qualche modo.</span><span class="sxs-lookup"><span data-stu-id="3d011-111">Each pattern acts as a rule for transforming input in some way.</span></span> <span data-ttu-id="3d011-112">Nel `match` espressione, ogni modello viene esaminato a turno per vedere se i dati di input sono compatibili con lo schema.</span><span class="sxs-lookup"><span data-stu-id="3d011-112">In the `match` expression, each pattern is examined in turn to see if the input data is compatible with the pattern.</span></span> <span data-ttu-id="3d011-113">Se viene trovata una corrispondenza, viene eseguito l'espressione di risultato.</span><span class="sxs-lookup"><span data-stu-id="3d011-113">If a match is found, the result expression is executed.</span></span> <span data-ttu-id="3d011-114">Se non viene trovata una corrispondenza, viene testata la regola del modello successiva.</span><span class="sxs-lookup"><span data-stu-id="3d011-114">If a match is not found, the next pattern rule is tested.</span></span> <span data-ttu-id="3d011-115">Facoltativo quando *condition* parte viene illustrata in [espressioni di ricerca](match-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="3d011-115">The optional when *condition* part is explained in [Match Expressions](match-expressions.md).</span></span>

<span data-ttu-id="3d011-116">Nella tabella seguente sono illustrati i modelli supportati.</span><span class="sxs-lookup"><span data-stu-id="3d011-116">Supported patterns are shown in the following table.</span></span> <span data-ttu-id="3d011-117">In fase di esecuzione, l'input viene verificato rispetto a ognuno dei modelli seguenti nell'ordine elencato nella tabella, e modelli applicate in modo ricorsivo, dalla prima all'ultimo così come appaiono nel codice e da sinistra a destra per i modelli per ogni riga.</span><span class="sxs-lookup"><span data-stu-id="3d011-117">At run time, the input is tested against each of the following patterns in the order listed in the table, and patterns are applied recursively, from first to last as they appear in your code, and from left to right for the patterns on each line.</span></span>

|<span data-ttu-id="3d011-118">nome</span><span class="sxs-lookup"><span data-stu-id="3d011-118">Name</span></span>|<span data-ttu-id="3d011-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3d011-119">Description</span></span>|<span data-ttu-id="3d011-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="3d011-120">Example</span></span>|
|----|-----------|-------|
|<span data-ttu-id="3d011-121">Criterio costante</span><span class="sxs-lookup"><span data-stu-id="3d011-121">Constant pattern</span></span>|<span data-ttu-id="3d011-122">Qualsiasi numerica, carattere, o valore letterale stringa, una costante di enumerazione o identificatore letterale definito</span><span class="sxs-lookup"><span data-stu-id="3d011-122">Any numeric, character, or string literal, an enumeration constant, or a defined literal identifier</span></span>|<span data-ttu-id="3d011-123">`1.0`, `"test"`, `30`, `Color.Red`</span><span class="sxs-lookup"><span data-stu-id="3d011-123">`1.0`, `"test"`, `30`, `Color.Red`</span></span>|
|<span data-ttu-id="3d011-124">Modello identificatore</span><span class="sxs-lookup"><span data-stu-id="3d011-124">Identifier pattern</span></span>|<span data-ttu-id="3d011-125">Valore case di unione discriminata, etichetta di eccezione o case di modello attivo</span><span class="sxs-lookup"><span data-stu-id="3d011-125">A case value of a discriminated union, an exception label, or an active pattern case</span></span>|`Some(x)`<br /><br />`Failure(msg)`|
|<span data-ttu-id="3d011-126">Modello variabile</span><span class="sxs-lookup"><span data-stu-id="3d011-126">Variable pattern</span></span>|<span data-ttu-id="3d011-127">*identifier*</span><span class="sxs-lookup"><span data-stu-id="3d011-127">*identifier*</span></span>|`a`|
|<span data-ttu-id="3d011-128">`as` Modello</span><span class="sxs-lookup"><span data-stu-id="3d011-128">`as` pattern</span></span>|<span data-ttu-id="3d011-129">*pattern* come *identificatore*</span><span class="sxs-lookup"><span data-stu-id="3d011-129">*pattern* as *identifier*</span></span>|`(a, b) as tuple1`|
|<span data-ttu-id="3d011-130">O un modello</span><span class="sxs-lookup"><span data-stu-id="3d011-130">OR pattern</span></span>|<span data-ttu-id="3d011-131">*pattern1* &#124; *pattern2*</span><span class="sxs-lookup"><span data-stu-id="3d011-131">*pattern1* &#124; *pattern2*</span></span>|<code>([h] &#124; [h; _])</code>|
|<span data-ttu-id="3d011-132">E criterio</span><span class="sxs-lookup"><span data-stu-id="3d011-132">AND pattern</span></span>|<span data-ttu-id="3d011-133">*pattern1* &amp; *pattern2*</span><span class="sxs-lookup"><span data-stu-id="3d011-133">*pattern1* &amp; *pattern2*</span></span>|`(a, b) & (_, "test")`|
|<span data-ttu-id="3d011-134">Modello costruttore</span><span class="sxs-lookup"><span data-stu-id="3d011-134">Cons pattern</span></span>|<span data-ttu-id="3d011-135">*Identificatore* :: *-identificatore dell'elenco*</span><span class="sxs-lookup"><span data-stu-id="3d011-135">*identifier* :: *list-identifier*</span></span>|`h :: t`|
|<span data-ttu-id="3d011-136">Modello elenco</span><span class="sxs-lookup"><span data-stu-id="3d011-136">List pattern</span></span>|<span data-ttu-id="3d011-137">[ *pattern_1*;.... *pattern_n* ]</span><span class="sxs-lookup"><span data-stu-id="3d011-137">[ *pattern_1*; ... ; *pattern_n* ]</span></span>|`[ a; b; c ]`|
|<span data-ttu-id="3d011-138">Modello matrice</span><span class="sxs-lookup"><span data-stu-id="3d011-138">Array pattern</span></span>|<span data-ttu-id="3d011-139">[&#124; *pattern_1*;..; *pattern_n* &#124;]</span><span class="sxs-lookup"><span data-stu-id="3d011-139">[&#124; *pattern_1*; ..; *pattern_n* &#124;]</span></span>|<code>[&#124; a; b; c &#124;]</code>|
|<span data-ttu-id="3d011-140">Modello con parentesi</span><span class="sxs-lookup"><span data-stu-id="3d011-140">Parenthesized pattern</span></span>|<span data-ttu-id="3d011-141">( *pattern* )</span><span class="sxs-lookup"><span data-stu-id="3d011-141">( *pattern* )</span></span>|`( a )`|
|<span data-ttu-id="3d011-142">Modello tupla</span><span class="sxs-lookup"><span data-stu-id="3d011-142">Tuple pattern</span></span>|<span data-ttu-id="3d011-143">( *pattern_1*,..., *pattern_n* )</span><span class="sxs-lookup"><span data-stu-id="3d011-143">( *pattern_1*, ... , *pattern_n* )</span></span>|`( a, b )`|
|<span data-ttu-id="3d011-144">Modello record</span><span class="sxs-lookup"><span data-stu-id="3d011-144">Record pattern</span></span>|<span data-ttu-id="3d011-145">{ *identifier1* = *pattern_1*;.... *identifier_n* = *pattern_n* }</span><span class="sxs-lookup"><span data-stu-id="3d011-145">{ *identifier1* = *pattern_1*; ... ; *identifier_n* = *pattern_n* }</span></span>|`{ Name = name; }`|
|<span data-ttu-id="3d011-146">Modello carattere jolly</span><span class="sxs-lookup"><span data-stu-id="3d011-146">Wildcard pattern</span></span>|<span data-ttu-id="3d011-147">_</span><span class="sxs-lookup"><span data-stu-id="3d011-147">_</span></span>|`_`|
|<span data-ttu-id="3d011-148">Modello con annotazione del tipo</span><span class="sxs-lookup"><span data-stu-id="3d011-148">Pattern together with type annotation</span></span>|<span data-ttu-id="3d011-149">*pattern* : *tipo*</span><span class="sxs-lookup"><span data-stu-id="3d011-149">*pattern* : *type*</span></span>|`a : int`|
|<span data-ttu-id="3d011-150">Modello di test del tipo</span><span class="sxs-lookup"><span data-stu-id="3d011-150">Type test pattern</span></span>|<span data-ttu-id="3d011-151">:?</span><span class="sxs-lookup"><span data-stu-id="3d011-151">:?</span></span> <span data-ttu-id="3d011-152">*tipo di* [come *identificatore* ]</span><span class="sxs-lookup"><span data-stu-id="3d011-152">*type* [ as *identifier* ]</span></span>|`:? System.DateTime as dt`|
|<span data-ttu-id="3d011-153">Modello null</span><span class="sxs-lookup"><span data-stu-id="3d011-153">Null pattern</span></span>|<span data-ttu-id="3d011-154">Null</span><span class="sxs-lookup"><span data-stu-id="3d011-154">null</span></span>|`null`|

## <a name="constant-patterns"></a><span data-ttu-id="3d011-155">Modelli costanti</span><span class="sxs-lookup"><span data-stu-id="3d011-155">Constant Patterns</span></span>

<span data-ttu-id="3d011-156">Modelli costanti sono numerici, di carattere e valori letterali stringa, le costanti di enumerazione (con il nome del tipo di enumerazione).</span><span class="sxs-lookup"><span data-stu-id="3d011-156">Constant patterns are numeric, character, and string literals, enumeration constants (with the enumeration type name included).</span></span> <span data-ttu-id="3d011-157">Oggetto `match` espressione che include solo modelli costanti può essere confrontato con un'istruzione case in altri linguaggi.</span><span class="sxs-lookup"><span data-stu-id="3d011-157">A `match` expression that has only constant patterns can be compared to a case statement in other languages.</span></span> <span data-ttu-id="3d011-158">L'input viene confrontato con il valore letterale e il modello corrispondente se i valori sono uguali.</span><span class="sxs-lookup"><span data-stu-id="3d011-158">The input is compared with the literal value and the pattern matches if the values are equal.</span></span> <span data-ttu-id="3d011-159">Il tipo del valore letterale deve essere compatibile con il tipo dell'input.</span><span class="sxs-lookup"><span data-stu-id="3d011-159">The type of the literal must be compatible with the type of the input.</span></span>

<span data-ttu-id="3d011-160">Nell'esempio seguente viene illustrato l'utilizzo di modelli letterali e Usa anche un modello variabile e un modello OR.</span><span class="sxs-lookup"><span data-stu-id="3d011-160">The following example demonstrates the use of literal patterns, and also uses a variable pattern and an OR pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4801.fs)]

<span data-ttu-id="3d011-161">Un altro esempio di modello letterale è un modello basato su costanti di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="3d011-161">Another example of a literal pattern is a pattern based on enumeration constants.</span></span> <span data-ttu-id="3d011-162">Quando si usano le costanti di enumerazione, è necessario specificare il nome del tipo di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="3d011-162">You must specify the enumeration type name when you use enumeration constants.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4802.fs)]

## <a name="identifier-patterns"></a><span data-ttu-id="3d011-163">Modelli identificatori</span><span class="sxs-lookup"><span data-stu-id="3d011-163">Identifier Patterns</span></span>

<span data-ttu-id="3d011-164">Se il modello è una stringa di caratteri che costituisce un identificatore valido, il formato dell'identificatore determina il modo in cui il modello è associato.</span><span class="sxs-lookup"><span data-stu-id="3d011-164">If the pattern is a string of characters that forms a valid identifier, the form of the identifier determines how the pattern is matched.</span></span> <span data-ttu-id="3d011-165">Se l'identificatore è più lungo di un singolo carattere e inizia con un carattere maiuscolo, il compilatore prova a trovare una corrispondenza per il modello identificatore.</span><span class="sxs-lookup"><span data-stu-id="3d011-165">If the identifier is longer than a single character and starts with an uppercase character, the compiler tries to make a match to the identifier pattern.</span></span> <span data-ttu-id="3d011-166">L'identificatore per questo modello può essere un valore contrassegnato con l'attributo letterale, un case di unione discriminato, un identificatore di eccezione o case di modello attivo.</span><span class="sxs-lookup"><span data-stu-id="3d011-166">The identifier for this pattern could be a value marked with the Literal attribute, a discriminated union case, an exception identifier, or an active pattern case.</span></span> <span data-ttu-id="3d011-167">Se non viene trovato alcun identificatore corrispondente, la corrispondenza ha esito negativo e l'input viene confrontato con la regola del modello successiva, il modello variabile.</span><span class="sxs-lookup"><span data-stu-id="3d011-167">If no matching identifier is found, the match fails and the next pattern rule, the variable pattern, is compared to the input.</span></span>

<span data-ttu-id="3d011-168">Modelli di unione discriminata possono essere case denominati a semplici oppure possono avere un valore o una tupla contenente più valori.</span><span class="sxs-lookup"><span data-stu-id="3d011-168">Discriminated union patterns can be simple named cases or they can have a value, or a tuple containing multiple values.</span></span> <span data-ttu-id="3d011-169">Se è presente un valore, è necessario specificare un identificatore per il valore.</span><span class="sxs-lookup"><span data-stu-id="3d011-169">If there is a value, you must specify an identifier for the value.</span></span> <span data-ttu-id="3d011-170">Nel caso di una tupla, è necessario fornire un modello tupla con un identificatore per ogni elemento della tupla o un identificatore con un nome di campo per uno o più campi unione denominati.</span><span class="sxs-lookup"><span data-stu-id="3d011-170">In the case of a tuple, you must supply a tuple pattern with an identifier for each element of the tuple or an identifier with a field name for one or more named union fields.</span></span> <span data-ttu-id="3d011-171">Vedere gli esempi di codice in questa sezione per gli esempi.</span><span class="sxs-lookup"><span data-stu-id="3d011-171">See the code examples in this section for examples.</span></span>

<span data-ttu-id="3d011-172">Il `option` il tipo è un'unione discriminata con due casi `Some` e `None`.</span><span class="sxs-lookup"><span data-stu-id="3d011-172">The `option` type is a discriminated union that has two cases, `Some` and `None`.</span></span> <span data-ttu-id="3d011-173">Un caso (`Some`) ha un valore, mentre l'altro (`None`) è semplicemente un case denominato.</span><span class="sxs-lookup"><span data-stu-id="3d011-173">One case (`Some`) has a value, but the other (`None`) is just a named case.</span></span> <span data-ttu-id="3d011-174">Pertanto `Some` deve avere una variabile per il valore associato il `Some` , ma `None` deve comparire da solo.</span><span class="sxs-lookup"><span data-stu-id="3d011-174">Therefore, `Some` needs to have a variable for the value associated with the `Some` case, but `None` must appear by itself.</span></span> <span data-ttu-id="3d011-175">Nel codice seguente, la variabile `var1` viene assegnato il valore ottenuto dalla corrispondenza il `Some` case.</span><span class="sxs-lookup"><span data-stu-id="3d011-175">In the following code, the variable `var1` is given the value that is obtained by matching to the `Some` case.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4803.fs)]

<span data-ttu-id="3d011-176">Nell'esempio seguente, il `PersonName` unione discriminata contiene una combinazione di stringhe e caratteri che rappresentano i possibili formati dei nomi.</span><span class="sxs-lookup"><span data-stu-id="3d011-176">In the following example, the `PersonName` discriminated union contains a mixture of strings and characters that represent possible forms of names.</span></span> <span data-ttu-id="3d011-177">I case di unione discriminata sono `FirstOnly`, `LastOnly`, e `FirstLast`.</span><span class="sxs-lookup"><span data-stu-id="3d011-177">The cases of the discriminated union are `FirstOnly`, `LastOnly`, and `FirstLast`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4804.fs)]

<span data-ttu-id="3d011-178">Per le unioni discriminate con campi denominati, utilizzare il segno di uguale (=) per estrarre il valore di un campo denominato.</span><span class="sxs-lookup"><span data-stu-id="3d011-178">For discriminated unions that have named fields, you use the equals sign (=) to extract the value of a named field.</span></span> <span data-ttu-id="3d011-179">Ad esempio, si consideri un'unione discriminata con una dichiarazione simile alla seguente.</span><span class="sxs-lookup"><span data-stu-id="3d011-179">For example, consider a discriminated union with a declaration like the following.</span></span>

```fsharp
type Shape =
    | Rectangle of height : float * width : float
    | Circle of radius : float
```

<span data-ttu-id="3d011-180">È possibile usare i campi denominati in un'espressione corrispondente come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="3d011-180">You can use the named fields in a pattern matching expression as follows.</span></span>

```fsharp
let matchShape shape =
    match shape with
    | Rectangle(height = h) -> printfn "Rectangle with length %f" h
    | Circle(r) -> printfn "Circle with radius %f" r
```

<span data-ttu-id="3d011-181">L'utilizzo del campo denominato è facoltativo, pertanto nell'esempio precedente, entrambi `Circle(r)` e `Circle(radius = r)` hanno lo stesso effetto.</span><span class="sxs-lookup"><span data-stu-id="3d011-181">The use of the named field is optional, so in the previous example, both `Circle(r)` and `Circle(radius = r)` have the same effect.</span></span>

<span data-ttu-id="3d011-182">Quando si specificano più campi, usare il punto e virgola (;) come separatore.</span><span class="sxs-lookup"><span data-stu-id="3d011-182">When you specify multiple fields, use the semicolon (;) as a separator.</span></span>

```
match shape with
| Rectangle(height = h; width = w) -> printfn "Rectangle with height %f and width %f" h w
| _ -> ()
```

<span data-ttu-id="3d011-183">Modelli attivi consentono di definire la corrispondenza di modelli personalizzata più complessa.</span><span class="sxs-lookup"><span data-stu-id="3d011-183">Active patterns enable you to define more complex custom pattern matching.</span></span> <span data-ttu-id="3d011-184">Per altre informazioni sui modelli attivi, vedere [modelli attivi](active-patterns.md).</span><span class="sxs-lookup"><span data-stu-id="3d011-184">For more information about active patterns, see [Active Patterns](active-patterns.md).</span></span>

<span data-ttu-id="3d011-185">Il caso in cui l'identificatore è un'eccezione viene usato nel criterio di corrispondenza nel contesto dei gestori di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="3d011-185">The case in which the identifier is an exception is used in pattern matching in the context of exception handlers.</span></span> <span data-ttu-id="3d011-186">Per informazioni sui criteri di ricerca nella gestione delle eccezioni, vedere [eccezioni: il `try...with` espressione](exception-handling/the-try-with-expression.md).</span><span class="sxs-lookup"><span data-stu-id="3d011-186">For information about pattern matching in exception handling, see [Exceptions: The `try...with` Expression](exception-handling/the-try-with-expression.md).</span></span>

## <a name="variable-patterns"></a><span data-ttu-id="3d011-187">Modelli variabili</span><span class="sxs-lookup"><span data-stu-id="3d011-187">Variable Patterns</span></span>

<span data-ttu-id="3d011-188">Il modello variabile assegna la corrispondenza con un nome di variabile, che è quindi disponibile per l'utilizzo nell'espressione di esecuzione a destra del valore di `->` simbolo.</span><span class="sxs-lookup"><span data-stu-id="3d011-188">The variable pattern assigns the value being matched to a variable name, which is then available for use in the execution expression to the right of the `->` symbol.</span></span> <span data-ttu-id="3d011-189">Un modello variabile da solo corrisponde a qualsiasi input, ma modelli variabili sono spesso inclusi in altri modelli, consentendo pertanto di creare strutture più complesse come tuple e matrici da scomporre in variabili.</span><span class="sxs-lookup"><span data-stu-id="3d011-189">A variable pattern alone matches any input, but variable patterns often appear within other patterns, therefore enabling more complex structures such as tuples and arrays to be decomposed into variables.</span></span>

<span data-ttu-id="3d011-190">L'esempio seguente illustra un modello variabile all'interno di un modello tupla.</span><span class="sxs-lookup"><span data-stu-id="3d011-190">The following example demonstrates a variable pattern within a tuple pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4805.fs)]

## <a name="as-pattern"></a><span data-ttu-id="3d011-191">come modello</span><span class="sxs-lookup"><span data-stu-id="3d011-191">as Pattern</span></span>

<span data-ttu-id="3d011-192">Il `as` pattern è un modello che ha un `as` aggiunta la clausola.</span><span class="sxs-lookup"><span data-stu-id="3d011-192">The `as` pattern is a pattern that has an `as` clause appended to it.</span></span> <span data-ttu-id="3d011-193">Il `as` clausola associa il valore corrispondente a un nome che può essere utilizzato nell'espressione di esecuzione di un `match` espressione, o, nel caso in cui questo modello viene usato in un `let` associazione, il nome viene aggiunto come associazione all'ambito locale.</span><span class="sxs-lookup"><span data-stu-id="3d011-193">The `as` clause binds the matched value to a name that can be used in the execution expression of a `match` expression, or, in the case where this pattern is used in a `let` binding, the name is added as a binding to the local scope.</span></span>

<span data-ttu-id="3d011-194">L'esempio seguente usa un `as` pattern.</span><span class="sxs-lookup"><span data-stu-id="3d011-194">The following example uses an `as` pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4806.fs)]

## <a name="or-pattern"></a><span data-ttu-id="3d011-195">O un modello</span><span class="sxs-lookup"><span data-stu-id="3d011-195">OR Pattern</span></span>

<span data-ttu-id="3d011-196">Il modello OR viene utilizzato quando i dati di input possono corrispondere a più modelli e si desidera eseguire lo stesso codice di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="3d011-196">The OR pattern is used when input data can match multiple patterns, and you want to execute the same code as a result.</span></span> <span data-ttu-id="3d011-197">I tipi di entrambi i lati del modello OR devono essere compatibili.</span><span class="sxs-lookup"><span data-stu-id="3d011-197">The types of both sides of the OR pattern must be compatible.</span></span>

<span data-ttu-id="3d011-198">Nell'esempio seguente viene illustrato il modello OR.</span><span class="sxs-lookup"><span data-stu-id="3d011-198">The following example demonstrates the OR pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4807.fs)]

## <a name="and-pattern"></a><span data-ttu-id="3d011-199">E criterio</span><span class="sxs-lookup"><span data-stu-id="3d011-199">AND Pattern</span></span>

<span data-ttu-id="3d011-200">Il modello AND richiede che l'input corrisponda a due modelli.</span><span class="sxs-lookup"><span data-stu-id="3d011-200">The AND pattern requires that the input match two patterns.</span></span> <span data-ttu-id="3d011-201">I tipi di entrambi i lati del modello AND devono essere compatibili.</span><span class="sxs-lookup"><span data-stu-id="3d011-201">The types of both sides of the AND pattern must be compatible.</span></span>

<span data-ttu-id="3d011-202">Nell'esempio seguente è simile a `detectZeroTuple` mostrato nel [modello tupla](https://msdn.microsoft.com/library/#tuple) sezione più avanti in questo argomento, ma in questo caso entrambe `var1` e `var2` ottenuti come valori utilizzando il modello AND.</span><span class="sxs-lookup"><span data-stu-id="3d011-202">The following example is like `detectZeroTuple` shown in the [Tuple Pattern](https://msdn.microsoft.com/library/#tuple) section later in this topic, but here both `var1` and `var2` are obtained as values by using the AND pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4808.fs)]

## <a name="cons-pattern"></a><span data-ttu-id="3d011-203">Modello costruttore</span><span class="sxs-lookup"><span data-stu-id="3d011-203">Cons Pattern</span></span>

<span data-ttu-id="3d011-204">Il modello costruttore viene utilizzato per scomporre un elenco nel primo elemento, il *head*e un elenco che contiene gli elementi rimanenti, il *tail*.</span><span class="sxs-lookup"><span data-stu-id="3d011-204">The cons pattern is used to decompose a list into the first element, the *head*, and a list that contains the remaining elements, the *tail*.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4809.fs)]

## <a name="list-pattern"></a><span data-ttu-id="3d011-205">Modello elenco</span><span class="sxs-lookup"><span data-stu-id="3d011-205">List Pattern</span></span>

<span data-ttu-id="3d011-206">Il modello elenco consente gli elenchi da scomporre in un numero di elementi.</span><span class="sxs-lookup"><span data-stu-id="3d011-206">The list pattern enables lists to be decomposed into a number of elements.</span></span> <span data-ttu-id="3d011-207">Il modello elenco può corrispondere solo elenchi di un numero specifico di elementi.</span><span class="sxs-lookup"><span data-stu-id="3d011-207">The list pattern itself can match only lists of a specific number of elements.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4810.fs)]

## <a name="array-pattern"></a><span data-ttu-id="3d011-208">Modello matrice</span><span class="sxs-lookup"><span data-stu-id="3d011-208">Array Pattern</span></span>

<span data-ttu-id="3d011-209">Il modello matrice assomiglia al modello elenco e può essere utilizzato per scomporre matrici di un determinato periodo.</span><span class="sxs-lookup"><span data-stu-id="3d011-209">The array pattern resembles the list pattern and can be used to decompose arrays of a specific length.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4811.fs)]

## <a name="parenthesized-pattern"></a><span data-ttu-id="3d011-210">Modello con parentesi</span><span class="sxs-lookup"><span data-stu-id="3d011-210">Parenthesized Pattern</span></span>

<span data-ttu-id="3d011-211">È possibile raggruppare le parentesi attorno ai modelli per ottenere l'associazione desiderata.</span><span class="sxs-lookup"><span data-stu-id="3d011-211">Parentheses can be grouped around patterns to achieve the desired associativity.</span></span> <span data-ttu-id="3d011-212">Nell'esempio seguente vengono usate parentesi per controllare l'associazione tra un modello AND e un modello di costruttore.</span><span class="sxs-lookup"><span data-stu-id="3d011-212">In the following example, parentheses are used to control associativity between an AND pattern and a cons pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4812.fs)]

## <a name="tuple-pattern"></a><span data-ttu-id="3d011-213">Modello tupla</span><span class="sxs-lookup"><span data-stu-id="3d011-213">Tuple Pattern</span></span>

<span data-ttu-id="3d011-214">Il modello tupla corrisponde all'input in formato di tupla e consente la tupla scomporre nei relativi elementi costituenti utilizzando criteri di ricerca di variabili per ogni posizione nella tupla.</span><span class="sxs-lookup"><span data-stu-id="3d011-214">The tuple pattern matches input in tuple form and enables the tuple to be decomposed into its constituent elements by using pattern matching variables for each position in the tuple.</span></span>

<span data-ttu-id="3d011-215">Nell'esempio seguente viene illustrato il modello tupla e anche utilizzati modelli letterali, modelli variabili e il modello carattere jolly.</span><span class="sxs-lookup"><span data-stu-id="3d011-215">The following example demonstrates the tuple pattern and also uses literal patterns, variable patterns, and the wildcard pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4813.fs)]

## <a name="record-pattern"></a><span data-ttu-id="3d011-216">Modello record</span><span class="sxs-lookup"><span data-stu-id="3d011-216">Record Pattern</span></span>

<span data-ttu-id="3d011-217">Il modello di record è utilizzato per scomporre record per estrarre i valori dei campi.</span><span class="sxs-lookup"><span data-stu-id="3d011-217">The record pattern is used to decompose records to extract the values of fields.</span></span> <span data-ttu-id="3d011-218">Il modello non dovrà fare riferimento a tutti i campi del record. eventuali campi omessi non partecipano alla corrispondenza sufficiente e non vengono estratti.</span><span class="sxs-lookup"><span data-stu-id="3d011-218">The pattern does not have to reference all fields of the record; any omitted fields just do not participate in matching and are not extracted.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4814.fs)]

## <a name="wildcard-pattern"></a><span data-ttu-id="3d011-219">Modello carattere jolly</span><span class="sxs-lookup"><span data-stu-id="3d011-219">Wildcard Pattern</span></span>

<span data-ttu-id="3d011-220">Il modello carattere jolly è rappresentato dal carattere di sottolineatura (`_`) di caratteri e corrisponde a qualsiasi input, come il modello variabile, ad eccezione del fatto che l'input viene rimosso anziché essere assegnato a una variabile.</span><span class="sxs-lookup"><span data-stu-id="3d011-220">The wildcard pattern is represented by the underscore (`_`) character and matches any input, just like the variable pattern, except that the input is discarded instead of assigned to a variable.</span></span> <span data-ttu-id="3d011-221">Il modello carattere jolly viene spesso usato in altri modelli come segnaposto per i valori che non sono necessari nell'espressione a destra del `->` simbolo.</span><span class="sxs-lookup"><span data-stu-id="3d011-221">The wildcard pattern is often used within other patterns as a placeholder for values that are not needed in the expression to the right of the `->` symbol.</span></span> <span data-ttu-id="3d011-222">Il modello con caratteri jolly viene usato spesso anche alla fine di un elenco di modelli per la corrispondenza di qualsiasi input senza corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="3d011-222">The wildcard pattern is also frequently used at the end of a list of patterns to match any unmatched input.</span></span> <span data-ttu-id="3d011-223">In molti esempi di codice in questo argomento viene illustrato il modello carattere jolly.</span><span class="sxs-lookup"><span data-stu-id="3d011-223">The wildcard pattern is demonstrated in many code examples in this topic.</span></span> <span data-ttu-id="3d011-224">Vedere il codice precedente per un esempio.</span><span class="sxs-lookup"><span data-stu-id="3d011-224">See the preceding code for one example.</span></span>

## <a name="patterns-that-have-type-annotations"></a><span data-ttu-id="3d011-225">Modelli con annotazioni del tipo</span><span class="sxs-lookup"><span data-stu-id="3d011-225">Patterns That Have Type Annotations</span></span>

<span data-ttu-id="3d011-226">I modelli possono includere annotazioni del tipo.</span><span class="sxs-lookup"><span data-stu-id="3d011-226">Patterns can have type annotations.</span></span> <span data-ttu-id="3d011-227">Queste si comportano come altre annotazioni del tipo e determinano l'inferenza, come altre annotazioni del tipo.</span><span class="sxs-lookup"><span data-stu-id="3d011-227">These behave like other type annotations and guide inference like other type annotations.</span></span> <span data-ttu-id="3d011-228">Le parentesi sono necessari annotazioni del tipo nei modelli.</span><span class="sxs-lookup"><span data-stu-id="3d011-228">Parentheses are required around type annotations in patterns.</span></span> <span data-ttu-id="3d011-229">Il codice seguente illustra un modello che ha un'annotazione di tipo.</span><span class="sxs-lookup"><span data-stu-id="3d011-229">The following code shows a pattern that has a type annotation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4815.fs)]

## <a name="type-test-pattern"></a><span data-ttu-id="3d011-230">Modello di Test del tipo</span><span class="sxs-lookup"><span data-stu-id="3d011-230">Type Test Pattern</span></span>

<span data-ttu-id="3d011-231">In base all'input rispetto a un tipo viene utilizzato il modello di test del tipo.</span><span class="sxs-lookup"><span data-stu-id="3d011-231">The type test pattern is used to match the input against a type.</span></span> <span data-ttu-id="3d011-232">Se il tipo di input affinché una corrispondenza (o un tipo derivato del) il tipo specificato nel modello, la corrispondenza ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="3d011-232">If the input type is a match to (or a derived type of) the type specified in the pattern, the match succeeds.</span></span>

<span data-ttu-id="3d011-233">Nell'esempio seguente viene illustrato il modello di test del tipo.</span><span class="sxs-lookup"><span data-stu-id="3d011-233">The following example demonstrates the type test pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4816.fs)]

## <a name="null-pattern"></a><span data-ttu-id="3d011-234">Modello null</span><span class="sxs-lookup"><span data-stu-id="3d011-234">Null Pattern</span></span>

<span data-ttu-id="3d011-235">Il modello null corrisponde al valore null che può essere visualizzato quando si lavora con tipi che consentono un valore null.</span><span class="sxs-lookup"><span data-stu-id="3d011-235">The null pattern matches the null value that can appear when you are working with types that allow a null value.</span></span> <span data-ttu-id="3d011-236">Modelli null vengono spesso utilizzati per l'interazione con codice di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3d011-236">Null patterns are frequently used when interoperating with .NET Framework code.</span></span> <span data-ttu-id="3d011-237">Ad esempio, il valore restituito di un'API .NET può essere l'input per un `match` espressione.</span><span class="sxs-lookup"><span data-stu-id="3d011-237">For example, the return value of a .NET API might be the input to a `match` expression.</span></span> <span data-ttu-id="3d011-238">È possibile controllare il flusso di programma basato se il valore restituito è null, nonché su altre caratteristiche del valore restituito.</span><span class="sxs-lookup"><span data-stu-id="3d011-238">You can control program flow based on whether the return value is null, and also on other characteristics of the returned value.</span></span> <span data-ttu-id="3d011-239">È possibile usare il modello null per impedire la propagazione al resto del programma di valori null.</span><span class="sxs-lookup"><span data-stu-id="3d011-239">You can use the null pattern to prevent null values from propagating to the rest of your program.</span></span>

<span data-ttu-id="3d011-240">L'esempio seguente usa il modello null e il modello variabile.</span><span class="sxs-lookup"><span data-stu-id="3d011-240">The following example uses the null pattern and the variable pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4817.fs)]

## <a name="see-also"></a><span data-ttu-id="3d011-241">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d011-241">See also</span></span>

- [<span data-ttu-id="3d011-242">Espressioni match</span><span class="sxs-lookup"><span data-stu-id="3d011-242">Match Expressions</span></span>](match-expressions.md)
- [<span data-ttu-id="3d011-243">Criteri attivi</span><span class="sxs-lookup"><span data-stu-id="3d011-243">Active Patterns</span></span>](active-patterns.md)
- [<span data-ttu-id="3d011-244">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="3d011-244">F# Language Reference</span></span>](index.md)
