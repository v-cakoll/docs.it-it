---
title: Criteri di ricerca
description: Informazioni sul modo in F# cui vengono usati i modelli per confrontare i dati con le strutture logiche, scomporre i dati in parti costituenti o estrarre informazioni dai dati.
ms.date: 05/16/2016
ms.openlocfilehash: 60e0d6cd550724bc8448fddd7b163c2c9f1637be
ms.sourcegitcommit: 8c6426a3d2adff5fbcbe1fed0f28eda718c15351
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2019
ms.locfileid: "68733475"
---
# <a name="pattern-matching"></a><span data-ttu-id="854c4-103">Criteri di ricerca</span><span class="sxs-lookup"><span data-stu-id="854c4-103">Pattern Matching</span></span>

<span data-ttu-id="854c4-104">I modelli sono regole per la trasformazione dei dati di input.</span><span class="sxs-lookup"><span data-stu-id="854c4-104">Patterns are rules for transforming input data.</span></span> <span data-ttu-id="854c4-105">Vengono usati in tutto il F# linguaggio per confrontare i dati con una struttura o strutture logiche, scomporre i dati in parti costituenti o estrarre informazioni dai dati in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="854c4-105">They are used throughout the F# language to compare data with a logical structure or structures, decompose data into constituent parts, or extract information from data in various ways.</span></span>

## <a name="remarks"></a><span data-ttu-id="854c4-106">Note</span><span class="sxs-lookup"><span data-stu-id="854c4-106">Remarks</span></span>

<span data-ttu-id="854c4-107">I modelli vengono utilizzati in molti costrutti di linguaggio, ad `match` esempio l'espressione.</span><span class="sxs-lookup"><span data-stu-id="854c4-107">Patterns are used in many language constructs, such as the `match` expression.</span></span> <span data-ttu-id="854c4-108">Vengono usati quando si elaborano gli argomenti per le funzioni `let` nelle associazioni, le espressioni lambda e nei gestori di eccezioni associati `try...with` all'espressione.</span><span class="sxs-lookup"><span data-stu-id="854c4-108">They are used when you are processing arguments for functions in `let` bindings, lambda expressions, and in the exception handlers associated with the `try...with` expression.</span></span> <span data-ttu-id="854c4-109">Per ulteriori informazioni, vedere [espressioni di corrispondenza](match-expressions.md), [associazioni let](./functions/let-bindings.md), [espressioni lambda: La `fun` parola](./functions/lambda-expressions-the-fun-keyword.md)chiave e[le eccezioni: `try...with` Espressione.](./exception-handling/the-try-with-expression.md)</span><span class="sxs-lookup"><span data-stu-id="854c4-109">For more information, see [Match Expressions](match-expressions.md), [let Bindings](./functions/let-bindings.md), [Lambda Expressions: The `fun` Keyword](./functions/lambda-expressions-the-fun-keyword.md), and [Exceptions: The `try...with` Expression](./exception-handling/the-try-with-expression.md).</span></span>

<span data-ttu-id="854c4-110">Nell' `match` espressione, ad esempio, il *modello* è quello che segue il simbolo della pipe.</span><span class="sxs-lookup"><span data-stu-id="854c4-110">For example, in the `match` expression, the *pattern* is what follows the pipe symbol.</span></span>

```fsharp
match expression with
| pattern [ when condition ] -> result-expression
...
```

<span data-ttu-id="854c4-111">Ogni modello funge da regola per trasformare in qualche modo l'input.</span><span class="sxs-lookup"><span data-stu-id="854c4-111">Each pattern acts as a rule for transforming input in some way.</span></span> <span data-ttu-id="854c4-112">`match` Nell'espressione ogni modello viene esaminato a sua volta per verificare se i dati di input sono compatibili con il modello.</span><span class="sxs-lookup"><span data-stu-id="854c4-112">In the `match` expression, each pattern is examined in turn to see if the input data is compatible with the pattern.</span></span> <span data-ttu-id="854c4-113">Se viene trovata una corrispondenza, viene eseguita l'espressione di risultato.</span><span class="sxs-lookup"><span data-stu-id="854c4-113">If a match is found, the result expression is executed.</span></span> <span data-ttu-id="854c4-114">Se non viene trovata alcuna corrispondenza, viene testata la regola del modello successiva.</span><span class="sxs-lookup"><span data-stu-id="854c4-114">If a match is not found, the next pattern rule is tested.</span></span> <span data-ttu-id="854c4-115">La parte della *condizione* when facoltativa è illustrata nelle [Espressioni match](match-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="854c4-115">The optional when *condition* part is explained in [Match Expressions](match-expressions.md).</span></span>

<span data-ttu-id="854c4-116">Nella tabella seguente sono illustrati i modelli supportati.</span><span class="sxs-lookup"><span data-stu-id="854c4-116">Supported patterns are shown in the following table.</span></span> <span data-ttu-id="854c4-117">In fase di esecuzione, l'input viene testato rispetto a ognuno dei modelli seguenti nell'ordine elencato nella tabella e i modelli vengono applicati in modo ricorsivo, dal primo all'ultimo come appaiono nel codice e da sinistra a destra per i modelli in ogni riga.</span><span class="sxs-lookup"><span data-stu-id="854c4-117">At run time, the input is tested against each of the following patterns in the order listed in the table, and patterns are applied recursively, from first to last as they appear in your code, and from left to right for the patterns on each line.</span></span>

|<span data-ttu-id="854c4-118">NOME</span><span class="sxs-lookup"><span data-stu-id="854c4-118">Name</span></span>|<span data-ttu-id="854c4-119">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="854c4-119">Description</span></span>|<span data-ttu-id="854c4-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="854c4-120">Example</span></span>|
|----|-----------|-------|
|<span data-ttu-id="854c4-121">Criterio costante</span><span class="sxs-lookup"><span data-stu-id="854c4-121">Constant pattern</span></span>|<span data-ttu-id="854c4-122">Qualsiasi valore letterale stringa, numerico o carattere, una costante di enumerazione o un identificatore di valore letterale definito</span><span class="sxs-lookup"><span data-stu-id="854c4-122">Any numeric, character, or string literal, an enumeration constant, or a defined literal identifier</span></span>|<span data-ttu-id="854c4-123">`1.0`, `"test"`, `30`, `Color.Red`</span><span class="sxs-lookup"><span data-stu-id="854c4-123">`1.0`, `"test"`, `30`, `Color.Red`</span></span>|
|<span data-ttu-id="854c4-124">Modello di identificatore</span><span class="sxs-lookup"><span data-stu-id="854c4-124">Identifier pattern</span></span>|<span data-ttu-id="854c4-125">Valore del case di un'unione discriminata, un'etichetta di eccezione o un case del criterio attivo</span><span class="sxs-lookup"><span data-stu-id="854c4-125">A case value of a discriminated union, an exception label, or an active pattern case</span></span>|`Some(x)`<br /><br />`Failure(msg)`|
|<span data-ttu-id="854c4-126">Modello di variabile</span><span class="sxs-lookup"><span data-stu-id="854c4-126">Variable pattern</span></span>|<span data-ttu-id="854c4-127">*identifier*</span><span class="sxs-lookup"><span data-stu-id="854c4-127">*identifier*</span></span>|`a`|
|<span data-ttu-id="854c4-128">`as`modello</span><span class="sxs-lookup"><span data-stu-id="854c4-128">`as` pattern</span></span>|<span data-ttu-id="854c4-129">*modello* come *identificatore*</span><span class="sxs-lookup"><span data-stu-id="854c4-129">*pattern* as *identifier*</span></span>|`(a, b) as tuple1`|
|<span data-ttu-id="854c4-130">Modello OR</span><span class="sxs-lookup"><span data-stu-id="854c4-130">OR pattern</span></span>|<span data-ttu-id="854c4-131">*pattern1* &#124; *pattern2*</span><span class="sxs-lookup"><span data-stu-id="854c4-131">*pattern1* &#124; *pattern2*</span></span>|<code>([h] &#124; [h; _])</code>|
|<span data-ttu-id="854c4-132">Modello AND</span><span class="sxs-lookup"><span data-stu-id="854c4-132">AND pattern</span></span>|<span data-ttu-id="854c4-133">*Ripetizione piatta1* &amp; *pattern2*</span><span class="sxs-lookup"><span data-stu-id="854c4-133">*pattern1* &amp; *pattern2*</span></span>|`(a, b) & (_, "test")`|
|<span data-ttu-id="854c4-134">Modello cons</span><span class="sxs-lookup"><span data-stu-id="854c4-134">Cons pattern</span></span>|<span data-ttu-id="854c4-135">identificatore:: *List-Identifier*</span><span class="sxs-lookup"><span data-stu-id="854c4-135">*identifier* :: *list-identifier*</span></span>|`h :: t`|
|<span data-ttu-id="854c4-136">Modello di elenco</span><span class="sxs-lookup"><span data-stu-id="854c4-136">List pattern</span></span>|<span data-ttu-id="854c4-137">[ *pattern_1*;...; *pattern_n* ]</span><span class="sxs-lookup"><span data-stu-id="854c4-137">[ *pattern_1*; ... ; *pattern_n* ]</span></span>|`[ a; b; c ]`|
|<span data-ttu-id="854c4-138">Modello di matrice</span><span class="sxs-lookup"><span data-stu-id="854c4-138">Array pattern</span></span>|<span data-ttu-id="854c4-139">[&#124; *pattern_1*; ..; *pattern_n* &#124;]</span><span class="sxs-lookup"><span data-stu-id="854c4-139">[&#124; *pattern_1*; ..; *pattern_n* &#124;]</span></span>|<code>[&#124; a; b; c &#124;]</code>|
|<span data-ttu-id="854c4-140">Modello racchiuso tra parentesi</span><span class="sxs-lookup"><span data-stu-id="854c4-140">Parenthesized pattern</span></span>|<span data-ttu-id="854c4-141">( *modello* )</span><span class="sxs-lookup"><span data-stu-id="854c4-141">( *pattern* )</span></span>|`( a )`|
|<span data-ttu-id="854c4-142">Modello tupla</span><span class="sxs-lookup"><span data-stu-id="854c4-142">Tuple pattern</span></span>|<span data-ttu-id="854c4-143">( *pattern_1*,..., *pattern_n* )</span><span class="sxs-lookup"><span data-stu-id="854c4-143">( *pattern_1*, ... , *pattern_n* )</span></span>|`( a, b )`|
|<span data-ttu-id="854c4-144">Modello di record</span><span class="sxs-lookup"><span data-stu-id="854c4-144">Record pattern</span></span>|<span data-ttu-id="854c4-145">{ *identificatore1* = *pattern_1*;...; *identifier_n*  =  *pattern_n* }</span><span class="sxs-lookup"><span data-stu-id="854c4-145">{ *identifier1* = *pattern_1*; ... ; *identifier_n* = *pattern_n* }</span></span>|`{ Name = name; }`|
|<span data-ttu-id="854c4-146">Modello con caratteri jolly</span><span class="sxs-lookup"><span data-stu-id="854c4-146">Wildcard pattern</span></span>|<span data-ttu-id="854c4-147">_</span><span class="sxs-lookup"><span data-stu-id="854c4-147">_</span></span>|`_`|
|<span data-ttu-id="854c4-148">Modello insieme all'annotazione del tipo</span><span class="sxs-lookup"><span data-stu-id="854c4-148">Pattern together with type annotation</span></span>|<span data-ttu-id="854c4-149">*modello* : *tipo*</span><span class="sxs-lookup"><span data-stu-id="854c4-149">*pattern* : *type*</span></span>|`a : int`|
|<span data-ttu-id="854c4-150">Modello di test del tipo</span><span class="sxs-lookup"><span data-stu-id="854c4-150">Type test pattern</span></span>|<span data-ttu-id="854c4-151">:?</span><span class="sxs-lookup"><span data-stu-id="854c4-151">:?</span></span> <span data-ttu-id="854c4-152">*tipo* di [come *identificatore* ]</span><span class="sxs-lookup"><span data-stu-id="854c4-152">*type* [ as *identifier* ]</span></span>|`:? System.DateTime as dt`|
|<span data-ttu-id="854c4-153">Modello null</span><span class="sxs-lookup"><span data-stu-id="854c4-153">Null pattern</span></span>|<span data-ttu-id="854c4-154">Null</span><span class="sxs-lookup"><span data-stu-id="854c4-154">null</span></span>|`null`|

## <a name="constant-patterns"></a><span data-ttu-id="854c4-155">Modelli costanti</span><span class="sxs-lookup"><span data-stu-id="854c4-155">Constant Patterns</span></span>

<span data-ttu-id="854c4-156">I modelli costanti sono numerici, caratteri e valori letterali stringa, costanti di enumerazione (con il nome del tipo di enumerazione incluso).</span><span class="sxs-lookup"><span data-stu-id="854c4-156">Constant patterns are numeric, character, and string literals, enumeration constants (with the enumeration type name included).</span></span> <span data-ttu-id="854c4-157">Un' `match` espressione con solo criteri costanti può essere confrontata con un'istruzione case in altri linguaggi.</span><span class="sxs-lookup"><span data-stu-id="854c4-157">A `match` expression that has only constant patterns can be compared to a case statement in other languages.</span></span> <span data-ttu-id="854c4-158">L'input viene confrontato con il valore letterale e il criterio corrisponde se i valori sono uguali.</span><span class="sxs-lookup"><span data-stu-id="854c4-158">The input is compared with the literal value and the pattern matches if the values are equal.</span></span> <span data-ttu-id="854c4-159">Il tipo del valore letterale deve essere compatibile con il tipo di input.</span><span class="sxs-lookup"><span data-stu-id="854c4-159">The type of the literal must be compatible with the type of the input.</span></span>

<span data-ttu-id="854c4-160">Nell'esempio seguente viene illustrato l'utilizzo di modelli letterali e viene inoltre utilizzato un modello di variabile e un modello o.</span><span class="sxs-lookup"><span data-stu-id="854c4-160">The following example demonstrates the use of literal patterns, and also uses a variable pattern and an OR pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4801.fs)]

<span data-ttu-id="854c4-161">Un altro esempio di modello letterale è un modello basato sulle costanti di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="854c4-161">Another example of a literal pattern is a pattern based on enumeration constants.</span></span> <span data-ttu-id="854c4-162">Quando si utilizzano le costanti di enumerazione, è necessario specificare il nome del tipo di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="854c4-162">You must specify the enumeration type name when you use enumeration constants.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4802.fs)]

## <a name="identifier-patterns"></a><span data-ttu-id="854c4-163">Modelli di identificatore</span><span class="sxs-lookup"><span data-stu-id="854c4-163">Identifier Patterns</span></span>

<span data-ttu-id="854c4-164">Se il modello è una stringa di caratteri che formano un identificatore valido, il formato dell'identificatore determina la modalità di corrispondenza del criterio.</span><span class="sxs-lookup"><span data-stu-id="854c4-164">If the pattern is a string of characters that forms a valid identifier, the form of the identifier determines how the pattern is matched.</span></span> <span data-ttu-id="854c4-165">Se l'identificatore è più lungo di un singolo carattere e inizia con un carattere maiuscolo, il compilatore tenta di trovare una corrispondenza con il modello di identificatore.</span><span class="sxs-lookup"><span data-stu-id="854c4-165">If the identifier is longer than a single character and starts with an uppercase character, the compiler tries to make a match to the identifier pattern.</span></span> <span data-ttu-id="854c4-166">L'identificatore per questo modello può essere un valore contrassegnato con l'attributo Literal, un case di unione discriminata, un identificatore di eccezione o un caso di criterio attivo.</span><span class="sxs-lookup"><span data-stu-id="854c4-166">The identifier for this pattern could be a value marked with the Literal attribute, a discriminated union case, an exception identifier, or an active pattern case.</span></span> <span data-ttu-id="854c4-167">Se non viene trovato alcun identificatore corrispondente, la corrispondenza ha esito negativo e la regola del criterio successiva, ovvero il modello di variabile, viene confrontata con l'input.</span><span class="sxs-lookup"><span data-stu-id="854c4-167">If no matching identifier is found, the match fails and the next pattern rule, the variable pattern, is compared to the input.</span></span>

<span data-ttu-id="854c4-168">I modelli di Unione discriminati possono essere semplici casi denominati o possono avere un valore oppure una tupla contenente più valori.</span><span class="sxs-lookup"><span data-stu-id="854c4-168">Discriminated union patterns can be simple named cases or they can have a value, or a tuple containing multiple values.</span></span> <span data-ttu-id="854c4-169">Se è presente un valore, è necessario specificare un identificatore per il valore.</span><span class="sxs-lookup"><span data-stu-id="854c4-169">If there is a value, you must specify an identifier for the value.</span></span> <span data-ttu-id="854c4-170">Nel caso di una tupla, è necessario fornire un modello di tupla con un identificatore per ogni elemento della tupla o un identificatore con un nome di campo per uno o più campi di unione denominati.</span><span class="sxs-lookup"><span data-stu-id="854c4-170">In the case of a tuple, you must supply a tuple pattern with an identifier for each element of the tuple or an identifier with a field name for one or more named union fields.</span></span> <span data-ttu-id="854c4-171">Per esempi, vedere gli esempi di codice in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="854c4-171">See the code examples in this section for examples.</span></span>

<span data-ttu-id="854c4-172">Il `option` tipo è un'unione discriminata con due case, `Some` e `None`.</span><span class="sxs-lookup"><span data-stu-id="854c4-172">The `option` type is a discriminated union that has two cases, `Some` and `None`.</span></span> <span data-ttu-id="854c4-173">Un case (`Some`) ha un valore, ma l'altro (`None`) è solo un case denominato.</span><span class="sxs-lookup"><span data-stu-id="854c4-173">One case (`Some`) has a value, but the other (`None`) is just a named case.</span></span> <span data-ttu-id="854c4-174">Pertanto, `Some` deve disporre di una variabile per il valore associato `Some` al case, ma `None` deve essere visualizzata da sola.</span><span class="sxs-lookup"><span data-stu-id="854c4-174">Therefore, `Some` needs to have a variable for the value associated with the `Some` case, but `None` must appear by itself.</span></span> <span data-ttu-id="854c4-175">Nel codice seguente alla variabile `var1` viene assegnato il valore ottenuto mediante la corrispondenza `Some` al case.</span><span class="sxs-lookup"><span data-stu-id="854c4-175">In the following code, the variable `var1` is given the value that is obtained by matching to the `Some` case.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4803.fs)]

<span data-ttu-id="854c4-176">Nell'esempio seguente, l' `PersonName` unione discriminata contiene una combinazione di stringhe e caratteri che rappresentano le possibili forme di nomi.</span><span class="sxs-lookup"><span data-stu-id="854c4-176">In the following example, the `PersonName` discriminated union contains a mixture of strings and characters that represent possible forms of names.</span></span> <span data-ttu-id="854c4-177">I case dell'unione discriminata sono `FirstOnly`, `LastOnly`e `FirstLast`.</span><span class="sxs-lookup"><span data-stu-id="854c4-177">The cases of the discriminated union are `FirstOnly`, `LastOnly`, and `FirstLast`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4804.fs)]

<span data-ttu-id="854c4-178">Per le unioni discriminate con campi denominati, è possibile usare il segno di uguale (=) per estrarre il valore di un campo denominato.</span><span class="sxs-lookup"><span data-stu-id="854c4-178">For discriminated unions that have named fields, you use the equals sign (=) to extract the value of a named field.</span></span> <span data-ttu-id="854c4-179">Si consideri, ad esempio, un'unione discriminata con una dichiarazione simile alla seguente.</span><span class="sxs-lookup"><span data-stu-id="854c4-179">For example, consider a discriminated union with a declaration like the following.</span></span>

```fsharp
type Shape =
    | Rectangle of height : float * width : float
    | Circle of radius : float
```

<span data-ttu-id="854c4-180">È possibile utilizzare i campi denominati in un'espressione di criteri di ricerca come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="854c4-180">You can use the named fields in a pattern matching expression as follows.</span></span>

```fsharp
let matchShape shape =
    match shape with
    | Rectangle(height = h) -> printfn "Rectangle with length %f" h
    | Circle(r) -> printfn "Circle with radius %f" r
```

<span data-ttu-id="854c4-181">L'uso del campo denominato è facoltativo, quindi nell'esempio precedente, sia `Circle(r)` che `Circle(radius = r)` hanno lo stesso effetto.</span><span class="sxs-lookup"><span data-stu-id="854c4-181">The use of the named field is optional, so in the previous example, both `Circle(r)` and `Circle(radius = r)` have the same effect.</span></span>

<span data-ttu-id="854c4-182">Quando si specificano più campi, usare il punto e virgola (;) come separatore.</span><span class="sxs-lookup"><span data-stu-id="854c4-182">When you specify multiple fields, use the semicolon (;) as a separator.</span></span>

```
match shape with
| Rectangle(height = h; width = w) -> printfn "Rectangle with height %f and width %f" h w
| _ -> ()
```

<span data-ttu-id="854c4-183">I criteri attivi consentono di definire criteri di ricerca personalizzati più complessi.</span><span class="sxs-lookup"><span data-stu-id="854c4-183">Active patterns enable you to define more complex custom pattern matching.</span></span> <span data-ttu-id="854c4-184">Per ulteriori informazioni sui modelli attivi, vedere [modelli attivi](active-patterns.md).</span><span class="sxs-lookup"><span data-stu-id="854c4-184">For more information about active patterns, see [Active Patterns](active-patterns.md).</span></span>

<span data-ttu-id="854c4-185">Il caso in cui l'identificatore è un'eccezione viene usato nei criteri di ricerca nel contesto dei gestori di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="854c4-185">The case in which the identifier is an exception is used in pattern matching in the context of exception handlers.</span></span> <span data-ttu-id="854c4-186">Per informazioni sui criteri di ricerca nella gestione delle eccezioni [, vedere eccezioni: `try...with` Espressione.](./exception-handling/the-try-with-expression.md)</span><span class="sxs-lookup"><span data-stu-id="854c4-186">For information about pattern matching in exception handling, see [Exceptions: The `try...with` Expression](./exception-handling/the-try-with-expression.md).</span></span>

## <a name="variable-patterns"></a><span data-ttu-id="854c4-187">Modelli variabili</span><span class="sxs-lookup"><span data-stu-id="854c4-187">Variable Patterns</span></span>

<span data-ttu-id="854c4-188">Il modello di variabile assegna il valore corrispondente a un nome di variabile, che è quindi disponibile per l'uso nell'espressione di esecuzione a destra del `->` simbolo.</span><span class="sxs-lookup"><span data-stu-id="854c4-188">The variable pattern assigns the value being matched to a variable name, which is then available for use in the execution expression to the right of the `->` symbol.</span></span> <span data-ttu-id="854c4-189">Un modello variabile da solo corrisponde a qualsiasi input, ma i modelli variabili vengono spesso visualizzati all'interno di altri modelli, consentendo quindi di rendere le strutture più complesse, ad esempio le tuple e le matrici, da scomporre in variabili.</span><span class="sxs-lookup"><span data-stu-id="854c4-189">A variable pattern alone matches any input, but variable patterns often appear within other patterns, therefore enabling more complex structures such as tuples and arrays to be decomposed into variables.</span></span>

<span data-ttu-id="854c4-190">Nell'esempio seguente viene illustrato un modello di variabile all'interno di un modello di tupla.</span><span class="sxs-lookup"><span data-stu-id="854c4-190">The following example demonstrates a variable pattern within a tuple pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4805.fs)]

## <a name="as-pattern"></a><span data-ttu-id="854c4-191">Modello As</span><span class="sxs-lookup"><span data-stu-id="854c4-191">as Pattern</span></span>

<span data-ttu-id="854c4-192">Il `as` modello è un modello a cui è `as` stata aggiunta una clausola.</span><span class="sxs-lookup"><span data-stu-id="854c4-192">The `as` pattern is a pattern that has an `as` clause appended to it.</span></span> <span data-ttu-id="854c4-193">La clausola associa il valore corrispondente a un nome che può essere utilizzato nell'espressione di esecuzione di un' `match` espressione o, nel caso in cui questo modello venga utilizzato in un' `let` associazione, il nome viene aggiunto come binding all'ambito locale. `as`</span><span class="sxs-lookup"><span data-stu-id="854c4-193">The `as` clause binds the matched value to a name that can be used in the execution expression of a `match` expression, or, in the case where this pattern is used in a `let` binding, the name is added as a binding to the local scope.</span></span>

<span data-ttu-id="854c4-194">Nell'esempio seguente viene usato `as` un modello.</span><span class="sxs-lookup"><span data-stu-id="854c4-194">The following example uses an `as` pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4806.fs)]

## <a name="or-pattern"></a><span data-ttu-id="854c4-195">Modello OR</span><span class="sxs-lookup"><span data-stu-id="854c4-195">OR Pattern</span></span>

<span data-ttu-id="854c4-196">Il modello o viene usato quando i dati di input possono corrispondere a più modelli e si vuole eseguire lo stesso codice di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="854c4-196">The OR pattern is used when input data can match multiple patterns, and you want to execute the same code as a result.</span></span> <span data-ttu-id="854c4-197">I tipi di entrambi i lati del modello o devono essere compatibili.</span><span class="sxs-lookup"><span data-stu-id="854c4-197">The types of both sides of the OR pattern must be compatible.</span></span>

<span data-ttu-id="854c4-198">Nell'esempio seguente viene illustrato il modello o.</span><span class="sxs-lookup"><span data-stu-id="854c4-198">The following example demonstrates the OR pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4807.fs)]

## <a name="and-pattern"></a><span data-ttu-id="854c4-199">Modello AND</span><span class="sxs-lookup"><span data-stu-id="854c4-199">AND Pattern</span></span>

<span data-ttu-id="854c4-200">Per il modello AND è necessario che l'input corrisponda a due modelli.</span><span class="sxs-lookup"><span data-stu-id="854c4-200">The AND pattern requires that the input match two patterns.</span></span> <span data-ttu-id="854c4-201">I tipi di entrambi i lati del modello e devono essere compatibili.</span><span class="sxs-lookup"><span data-stu-id="854c4-201">The types of both sides of the AND pattern must be compatible.</span></span>

<span data-ttu-id="854c4-202">L'esempio seguente è simile `detectZeroTuple` a quello illustrato nella sezione relativa al [modello](https://msdn.microsoft.com/library/#tuple) di tupla più avanti in `var1` questo `var2` argomento, ma in questo caso e vengono ottenuti come valori utilizzando il modello e.</span><span class="sxs-lookup"><span data-stu-id="854c4-202">The following example is like `detectZeroTuple` shown in the [Tuple Pattern](https://msdn.microsoft.com/library/#tuple) section later in this topic, but here both `var1` and `var2` are obtained as values by using the AND pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4808.fs)]

## <a name="cons-pattern"></a><span data-ttu-id="854c4-203">Modello cons</span><span class="sxs-lookup"><span data-stu-id="854c4-203">Cons Pattern</span></span>

<span data-ttu-id="854c4-204">Il modello cons viene usato per scomporre un elenco nel primo elemento, la *testa*e un elenco che contiene gli elementi rimanenti, ovvero la *coda*.</span><span class="sxs-lookup"><span data-stu-id="854c4-204">The cons pattern is used to decompose a list into the first element, the *head*, and a list that contains the remaining elements, the *tail*.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4809.fs)]

## <a name="list-pattern"></a><span data-ttu-id="854c4-205">Modello di elenco</span><span class="sxs-lookup"><span data-stu-id="854c4-205">List Pattern</span></span>

<span data-ttu-id="854c4-206">Il modello elenco consente di scomporre gli elenchi in un numero di elementi.</span><span class="sxs-lookup"><span data-stu-id="854c4-206">The list pattern enables lists to be decomposed into a number of elements.</span></span> <span data-ttu-id="854c4-207">Il pattern list stesso può corrispondere solo a elenchi di un numero specifico di elementi.</span><span class="sxs-lookup"><span data-stu-id="854c4-207">The list pattern itself can match only lists of a specific number of elements.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4810.fs)]

## <a name="array-pattern"></a><span data-ttu-id="854c4-208">Modello di matrice</span><span class="sxs-lookup"><span data-stu-id="854c4-208">Array Pattern</span></span>

<span data-ttu-id="854c4-209">Il modello di matrice è simile al modello di elenco e può essere usato per scomporre le matrici di una lunghezza specifica.</span><span class="sxs-lookup"><span data-stu-id="854c4-209">The array pattern resembles the list pattern and can be used to decompose arrays of a specific length.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4811.fs)]

## <a name="parenthesized-pattern"></a><span data-ttu-id="854c4-210">Modello racchiuso tra parentesi</span><span class="sxs-lookup"><span data-stu-id="854c4-210">Parenthesized Pattern</span></span>

<span data-ttu-id="854c4-211">Le parentesi possono essere raggruppate intorno ai modelli per ottenere l'associatività desiderata.</span><span class="sxs-lookup"><span data-stu-id="854c4-211">Parentheses can be grouped around patterns to achieve the desired associativity.</span></span> <span data-ttu-id="854c4-212">Nell'esempio seguente, le parentesi vengono utilizzate per controllare l'associatività tra un pattern AND e un modello cons.</span><span class="sxs-lookup"><span data-stu-id="854c4-212">In the following example, parentheses are used to control associativity between an AND pattern and a cons pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4812.fs)]

## <a name="tuple-pattern"></a><span data-ttu-id="854c4-213">Modello tupla</span><span class="sxs-lookup"><span data-stu-id="854c4-213">Tuple Pattern</span></span>

<span data-ttu-id="854c4-214">Il modello di tupla corrisponde all'input nel modulo di tupla e consente di scomporre la tupla nei relativi elementi costitutivi usando variabili di criteri di ricerca per ogni posizione nella tupla.</span><span class="sxs-lookup"><span data-stu-id="854c4-214">The tuple pattern matches input in tuple form and enables the tuple to be decomposed into its constituent elements by using pattern matching variables for each position in the tuple.</span></span>

<span data-ttu-id="854c4-215">Nell'esempio seguente viene illustrato il modello di tupla e vengono utilizzati anche modelli letterali, modelli variabili e il modello con caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="854c4-215">The following example demonstrates the tuple pattern and also uses literal patterns, variable patterns, and the wildcard pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4813.fs)]

## <a name="record-pattern"></a><span data-ttu-id="854c4-216">Modello di record</span><span class="sxs-lookup"><span data-stu-id="854c4-216">Record Pattern</span></span>

<span data-ttu-id="854c4-217">Il pattern di record viene usato per scomporre i record per estrarre i valori dei campi.</span><span class="sxs-lookup"><span data-stu-id="854c4-217">The record pattern is used to decompose records to extract the values of fields.</span></span> <span data-ttu-id="854c4-218">Il modello non deve fare riferimento a tutti i campi del record; tutti i campi omessi non partecipano alla corrispondenza e non vengono estratti.</span><span class="sxs-lookup"><span data-stu-id="854c4-218">The pattern does not have to reference all fields of the record; any omitted fields just do not participate in matching and are not extracted.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4814.fs)]

## <a name="wildcard-pattern"></a><span data-ttu-id="854c4-219">Modello con caratteri jolly</span><span class="sxs-lookup"><span data-stu-id="854c4-219">Wildcard Pattern</span></span>

<span data-ttu-id="854c4-220">Il carattere jolly è rappresentato dal carattere di sottolineatura (`_`) e corrisponde a qualsiasi input, proprio come il modello di variabile, ad eccezione del fatto che l'input viene eliminato anziché assegnato a una variabile.</span><span class="sxs-lookup"><span data-stu-id="854c4-220">The wildcard pattern is represented by the underscore (`_`) character and matches any input, just like the variable pattern, except that the input is discarded instead of assigned to a variable.</span></span> <span data-ttu-id="854c4-221">Il modello con caratteri jolly viene spesso usato all'interno di altri modelli come segnaposto per i valori che non sono necessari nell'espressione a `->` destra del simbolo.</span><span class="sxs-lookup"><span data-stu-id="854c4-221">The wildcard pattern is often used within other patterns as a placeholder for values that are not needed in the expression to the right of the `->` symbol.</span></span> <span data-ttu-id="854c4-222">Il modello con caratteri jolly viene usato spesso anche alla fine di un elenco di modelli per trovare la corrispondenza con qualsiasi input senza corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="854c4-222">The wildcard pattern is also frequently used at the end of a list of patterns to match any unmatched input.</span></span> <span data-ttu-id="854c4-223">Il modello con caratteri jolly è illustrato in molti esempi di codice in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="854c4-223">The wildcard pattern is demonstrated in many code examples in this topic.</span></span> <span data-ttu-id="854c4-224">Per un esempio, vedere il codice precedente.</span><span class="sxs-lookup"><span data-stu-id="854c4-224">See the preceding code for one example.</span></span>

## <a name="patterns-that-have-type-annotations"></a><span data-ttu-id="854c4-225">Modelli con annotazioni di tipo</span><span class="sxs-lookup"><span data-stu-id="854c4-225">Patterns That Have Type Annotations</span></span>

<span data-ttu-id="854c4-226">I modelli possono avere annotazioni di tipo.</span><span class="sxs-lookup"><span data-stu-id="854c4-226">Patterns can have type annotations.</span></span> <span data-ttu-id="854c4-227">Si comportano come altre annotazioni di tipo e inferenza guida come altre annotazioni di tipo.</span><span class="sxs-lookup"><span data-stu-id="854c4-227">These behave like other type annotations and guide inference like other type annotations.</span></span> <span data-ttu-id="854c4-228">Le parentesi sono obbligatorie intorno alle annotazioni di tipo nei modelli.</span><span class="sxs-lookup"><span data-stu-id="854c4-228">Parentheses are required around type annotations in patterns.</span></span> <span data-ttu-id="854c4-229">Il codice seguente illustra un modello con un'annotazione di tipo.</span><span class="sxs-lookup"><span data-stu-id="854c4-229">The following code shows a pattern that has a type annotation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4815.fs)]

## <a name="type-test-pattern"></a><span data-ttu-id="854c4-230">Modello di test del tipo</span><span class="sxs-lookup"><span data-stu-id="854c4-230">Type Test Pattern</span></span>

<span data-ttu-id="854c4-231">Il modello di test del tipo viene usato per trovare la corrispondenza con l'input rispetto a un tipo.</span><span class="sxs-lookup"><span data-stu-id="854c4-231">The type test pattern is used to match the input against a type.</span></span> <span data-ttu-id="854c4-232">Se il tipo di input corrisponde a (o a un tipo derivato di) il tipo specificato nel criterio, la corrispondenza ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="854c4-232">If the input type is a match to (or a derived type of) the type specified in the pattern, the match succeeds.</span></span>

<span data-ttu-id="854c4-233">Nell'esempio seguente viene illustrato il modello di test del tipo.</span><span class="sxs-lookup"><span data-stu-id="854c4-233">The following example demonstrates the type test pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4816.fs)]

## <a name="null-pattern"></a><span data-ttu-id="854c4-234">Modello null</span><span class="sxs-lookup"><span data-stu-id="854c4-234">Null Pattern</span></span>

<span data-ttu-id="854c4-235">Il criterio null corrisponde al valore null che può essere visualizzato quando si utilizzano tipi che consentono un valore null.</span><span class="sxs-lookup"><span data-stu-id="854c4-235">The null pattern matches the null value that can appear when you are working with types that allow a null value.</span></span> <span data-ttu-id="854c4-236">I modelli null vengono spesso usati quando si interopera con .NET Framework codice.</span><span class="sxs-lookup"><span data-stu-id="854c4-236">Null patterns are frequently used when interoperating with .NET Framework code.</span></span> <span data-ttu-id="854c4-237">Ad esempio, il valore restituito di un'API .NET potrebbe essere l'input di un' `match` espressione.</span><span class="sxs-lookup"><span data-stu-id="854c4-237">For example, the return value of a .NET API might be the input to a `match` expression.</span></span> <span data-ttu-id="854c4-238">È possibile controllare il flusso del programma in base al fatto che il valore restituito sia null e anche ad altre caratteristiche del valore restituito.</span><span class="sxs-lookup"><span data-stu-id="854c4-238">You can control program flow based on whether the return value is null, and also on other characteristics of the returned value.</span></span> <span data-ttu-id="854c4-239">È possibile usare il modello null per impedire che i valori null vengano propagati al resto del programma.</span><span class="sxs-lookup"><span data-stu-id="854c4-239">You can use the null pattern to prevent null values from propagating to the rest of your program.</span></span>

<span data-ttu-id="854c4-240">Nell'esempio seguente vengono utilizzati il modello null e il modello di variabile.</span><span class="sxs-lookup"><span data-stu-id="854c4-240">The following example uses the null pattern and the variable pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4817.fs)]

## <a name="see-also"></a><span data-ttu-id="854c4-241">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="854c4-241">See also</span></span>

- [<span data-ttu-id="854c4-242">Espressioni match</span><span class="sxs-lookup"><span data-stu-id="854c4-242">Match Expressions</span></span>](match-expressions.md)
- [<span data-ttu-id="854c4-243">Criteri attivi</span><span class="sxs-lookup"><span data-stu-id="854c4-243">Active Patterns</span></span>](active-patterns.md)
- [<span data-ttu-id="854c4-244">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="854c4-244">F# Language Reference</span></span>](index.md)
