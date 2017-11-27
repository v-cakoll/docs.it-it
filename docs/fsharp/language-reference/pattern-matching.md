---
title: Criteri di ricerca [F#]
description: 'Informazioni su come i modelli vengono utilizzati in F # per confrontare i dati con strutture logiche, scomporre i dati in parti costituenti o estrarre informazioni dai dati.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 5562ee98-e2f1-4dcd-8e2f-16ae27baaade
ms.openlocfilehash: 7c7a3110a8f34c0c96c12d4584010a9ac4b485fa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="pattern-matching"></a><span data-ttu-id="1f241-104">Criteri di ricerca</span><span class="sxs-lookup"><span data-stu-id="1f241-104">Pattern Matching</span></span>

<span data-ttu-id="1f241-105">I modelli sono regole per la trasformazione dei dati di input.</span><span class="sxs-lookup"><span data-stu-id="1f241-105">Patterns are rules for transforming input data.</span></span> <span data-ttu-id="1f241-106">Vengono utilizzati nel linguaggio F # per confrontare i dati con una o più strutture logiche, scomporre i dati in parti costituenti o estrarre informazioni dai dati in vari modi.</span><span class="sxs-lookup"><span data-stu-id="1f241-106">They are used throughout the F# language to compare data with a logical structure or structures, decompose data into constituent parts, or extract information from data in various ways.</span></span>


## <a name="remarks"></a><span data-ttu-id="1f241-107">Note</span><span class="sxs-lookup"><span data-stu-id="1f241-107">Remarks</span></span>
<span data-ttu-id="1f241-108">Modelli vengono utilizzati in numerosi costrutti di linguaggio, ad esempio il `match` espressione.</span><span class="sxs-lookup"><span data-stu-id="1f241-108">Patterns are used in many language constructs, such as the `match` expression.</span></span> <span data-ttu-id="1f241-109">Vengono utilizzati quando si elaborano argomenti per le funzioni in `let` associazioni, le espressioni lambda e nei gestori di eccezioni associati il `try...with` espressione.</span><span class="sxs-lookup"><span data-stu-id="1f241-109">They are used when you are processing arguments for functions in `let` bindings, lambda expressions, and in the exception handlers associated with the `try...with` expression.</span></span> <span data-ttu-id="1f241-110">Per ulteriori informazioni, vedere [espressioni Match](match-expressions.md), [associazioni let](functions/let-bindings.md), [espressioni Lambda: I `fun` (parola chiave)](functions/lambda-expressions-the-fun-keyword.md), e [eccezioni: il `try...with` Espressione](exception-handling/the-try-with-expression.md).</span><span class="sxs-lookup"><span data-stu-id="1f241-110">For more information, see [Match Expressions](match-expressions.md), [let Bindings](functions/let-bindings.md), [Lambda Expressions: The `fun` Keyword](functions/lambda-expressions-the-fun-keyword.md), and [Exceptions: The `try...with` Expression](exception-handling/the-try-with-expression.md).</span></span>

<span data-ttu-id="1f241-111">Ad esempio, nel `match` espressione, il *modello* è quello che segue il simbolo di barra verticale.</span><span class="sxs-lookup"><span data-stu-id="1f241-111">For example, in the `match` expression, the *pattern* is what follows the pipe symbol.</span></span>

```fsharp
match expression with
| pattern [ when condition ] -> result-expression
...
```

<span data-ttu-id="1f241-112">Ogni modello funge da una regola per la trasformazione di input in qualche modo.</span><span class="sxs-lookup"><span data-stu-id="1f241-112">Each pattern acts as a rule for transforming input in some way.</span></span> <span data-ttu-id="1f241-113">Nel `match` espressione, ogni modello viene esaminato a sua volta per verificare se i dati di input sono compatibili con lo schema.</span><span class="sxs-lookup"><span data-stu-id="1f241-113">In the `match` expression, each pattern is examined in turn to see if the input data is compatible with the pattern.</span></span> <span data-ttu-id="1f241-114">Se viene trovata una corrispondenza, viene eseguita l'espressione di risultato.</span><span class="sxs-lookup"><span data-stu-id="1f241-114">If a match is found, the result expression is executed.</span></span> <span data-ttu-id="1f241-115">Se non viene trovata una corrispondenza, viene verificata la regola di modello successiva.</span><span class="sxs-lookup"><span data-stu-id="1f241-115">If a match is not found, the next pattern rule is tested.</span></span> <span data-ttu-id="1f241-116">Facoltativo quando *condizione* parte viene spiegata [espressioni Match](match-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="1f241-116">The optional when *condition* part is explained in [Match Expressions](match-expressions.md).</span></span>

<span data-ttu-id="1f241-117">Pattern supportati sono indicati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="1f241-117">Supported patterns are shown in the following table.</span></span> <span data-ttu-id="1f241-118">In fase di esecuzione, l'input viene verificato rispetto a ognuno dei modelli seguenti nell'ordine elencato nella tabella e modelli vengono applicate in modo ricorsivo, dalla prima all'ultimo come appaiono nel codice e da sinistra a destra per i modelli per ogni riga.</span><span class="sxs-lookup"><span data-stu-id="1f241-118">At run time, the input is tested against each of the following patterns in the order listed in the table, and patterns are applied recursively, from first to last as they appear in your code, and from left to right for the patterns on each line.</span></span>

|<span data-ttu-id="1f241-119">Nome</span><span class="sxs-lookup"><span data-stu-id="1f241-119">Name</span></span>|<span data-ttu-id="1f241-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1f241-120">Description</span></span>|<span data-ttu-id="1f241-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="1f241-121">Example</span></span>|
|----|-----------|-------|
|<span data-ttu-id="1f241-122">Criterio costante</span><span class="sxs-lookup"><span data-stu-id="1f241-122">Constant pattern</span></span>|<span data-ttu-id="1f241-123">Qualsiasi numerica, carattere, o valore letterale stringa, una costante di enumerazione o un identificatore di valore letterale definito</span><span class="sxs-lookup"><span data-stu-id="1f241-123">Any numeric, character, or string literal, an enumeration constant, or a defined literal identifier</span></span>|<span data-ttu-id="1f241-124">`1.0`, `"test"`, `30`, `Color.Red`</span><span class="sxs-lookup"><span data-stu-id="1f241-124">`1.0`, `"test"`, `30`, `Color.Red`</span></span>|
|<span data-ttu-id="1f241-125">Modello identificatore</span><span class="sxs-lookup"><span data-stu-id="1f241-125">Identifier pattern</span></span>|<span data-ttu-id="1f241-126">Valore case di unione discriminata, un'etichetta di eccezione o un case (modello attivo)</span><span class="sxs-lookup"><span data-stu-id="1f241-126">A case value of a discriminated union, an exception label, or an active pattern case</span></span>|`Some(x)`<br /><br />`Failure(msg)`|
|<span data-ttu-id="1f241-127">Modello variabile</span><span class="sxs-lookup"><span data-stu-id="1f241-127">Variable pattern</span></span>|<span data-ttu-id="1f241-128">*identifier*</span><span class="sxs-lookup"><span data-stu-id="1f241-128">*identifier*</span></span>|`a`|
|<span data-ttu-id="1f241-129">`as`modello</span><span class="sxs-lookup"><span data-stu-id="1f241-129">`as` pattern</span></span>|<span data-ttu-id="1f241-130">*modello* come *identificatore*</span><span class="sxs-lookup"><span data-stu-id="1f241-130">*pattern* as *identifier*</span></span>|`(a, b) as tuple1`|
|<span data-ttu-id="1f241-131">O un modello</span><span class="sxs-lookup"><span data-stu-id="1f241-131">OR pattern</span></span>|<span data-ttu-id="1f241-132">*pattern1* &#124; *pattern2*</span><span class="sxs-lookup"><span data-stu-id="1f241-132">*pattern1* &#124; *pattern2*</span></span>|<code>([h] &#124; [h; _])</code>|
|<span data-ttu-id="1f241-133">E modello</span><span class="sxs-lookup"><span data-stu-id="1f241-133">AND pattern</span></span>|<span data-ttu-id="1f241-134">*pattern1* &amp; *pattern2*</span><span class="sxs-lookup"><span data-stu-id="1f241-134">*pattern1* &amp; *pattern2*</span></span>|`(a, b) & (_, "test")`|
|<span data-ttu-id="1f241-135">Modello costruttore</span><span class="sxs-lookup"><span data-stu-id="1f241-135">Cons pattern</span></span>|<span data-ttu-id="1f241-136">*Identificatore* :: *-identificatore dell'elenco*</span><span class="sxs-lookup"><span data-stu-id="1f241-136">*identifier* :: *list-identifier*</span></span>|`h :: t`|
|<span data-ttu-id="1f241-137">Modello di elenco</span><span class="sxs-lookup"><span data-stu-id="1f241-137">List pattern</span></span>|<span data-ttu-id="1f241-138">[ *pattern_1*;.... *pattern_n* ]</span><span class="sxs-lookup"><span data-stu-id="1f241-138">[ *pattern_1*; ... ; *pattern_n* ]</span></span>|`[ a; b; c ]`|
|<span data-ttu-id="1f241-139">Modello di matrice</span><span class="sxs-lookup"><span data-stu-id="1f241-139">Array pattern</span></span>|<span data-ttu-id="1f241-140">[&#124; *pattern_1*;...; *pattern_n* &#124;]</span><span class="sxs-lookup"><span data-stu-id="1f241-140">[&#124; *pattern_1*; ..; *pattern_n* &#124;]</span></span>|<code>[&#124; a; b; c &#124;]</code>|
|<span data-ttu-id="1f241-141">Modello racchiuso tra parentesi</span><span class="sxs-lookup"><span data-stu-id="1f241-141">Parenthesized pattern</span></span>|<span data-ttu-id="1f241-142">( *modello* )</span><span class="sxs-lookup"><span data-stu-id="1f241-142">( *pattern* )</span></span>|`( a )`|
|<span data-ttu-id="1f241-143">Tupla (modello)</span><span class="sxs-lookup"><span data-stu-id="1f241-143">Tuple pattern</span></span>|<span data-ttu-id="1f241-144">( *pattern_1*,..., *pattern_n* )</span><span class="sxs-lookup"><span data-stu-id="1f241-144">( *pattern_1*, ... , *pattern_n* )</span></span>|`( a, b )`|
|<span data-ttu-id="1f241-145">Modello di record</span><span class="sxs-lookup"><span data-stu-id="1f241-145">Record pattern</span></span>|<span data-ttu-id="1f241-146">{ *identifier1* = *pattern_1*;.... *identifier_n* = *pattern_n* }</span><span class="sxs-lookup"><span data-stu-id="1f241-146">{ *identifier1* = *pattern_1*; ... ; *identifier_n* = *pattern_n* }</span></span>|`{ Name = name; }`|
|<span data-ttu-id="1f241-147">Caratteri jolly</span><span class="sxs-lookup"><span data-stu-id="1f241-147">Wildcard pattern</span></span>|<span data-ttu-id="1f241-148">_</span><span class="sxs-lookup"><span data-stu-id="1f241-148">_</span></span>|`_`|
|<span data-ttu-id="1f241-149">Modello con un'annotazione di tipo</span><span class="sxs-lookup"><span data-stu-id="1f241-149">Pattern together with type annotation</span></span>|<span data-ttu-id="1f241-150">*modello* : *tipo*</span><span class="sxs-lookup"><span data-stu-id="1f241-150">*pattern* : *type*</span></span>|`a : int`|
|<span data-ttu-id="1f241-151">Modello del test di tipo</span><span class="sxs-lookup"><span data-stu-id="1f241-151">Type test pattern</span></span>|<span data-ttu-id="1f241-152">:?</span><span class="sxs-lookup"><span data-stu-id="1f241-152">:?</span></span> <span data-ttu-id="1f241-153">*tipo* [come *identificatore* ]</span><span class="sxs-lookup"><span data-stu-id="1f241-153">*type* [ as *identifier* ]</span></span>|`:? System.DateTime as dt`|
|<span data-ttu-id="1f241-154">Modello null</span><span class="sxs-lookup"><span data-stu-id="1f241-154">Null pattern</span></span>|<span data-ttu-id="1f241-155">Null</span><span class="sxs-lookup"><span data-stu-id="1f241-155">null</span></span>|`null`|

## <a name="constant-patterns"></a><span data-ttu-id="1f241-156">Modelli costanti</span><span class="sxs-lookup"><span data-stu-id="1f241-156">Constant Patterns</span></span>
<span data-ttu-id="1f241-157">I modelli costanti sono numerici, caratteri e stringhe letterali, costanti di enumerazione (con il nome del tipo di enumerazione).</span><span class="sxs-lookup"><span data-stu-id="1f241-157">Constant patterns are numeric, character, and string literals, enumeration constants (with the enumeration type name included).</span></span> <span data-ttu-id="1f241-158">Oggetto `match` espressione che include solo modelli costanti può essere confrontato con un'istruzione case in altri linguaggi.</span><span class="sxs-lookup"><span data-stu-id="1f241-158">A `match` expression that has only constant patterns can be compared to a case statement in other languages.</span></span> <span data-ttu-id="1f241-159">L'input viene confrontato con il valore letterale e il modello corrispondente se i valori sono uguali.</span><span class="sxs-lookup"><span data-stu-id="1f241-159">The input is compared with the literal value and the pattern matches if the values are equal.</span></span> <span data-ttu-id="1f241-160">Il tipo del valore letterale deve essere compatibile con il tipo dell'input.</span><span class="sxs-lookup"><span data-stu-id="1f241-160">The type of the literal must be compatible with the type of the input.</span></span>

<span data-ttu-id="1f241-161">Nell'esempio seguente viene illustrato l'utilizzo di modelli di valore letterale e viene inoltre utilizzato un modello di variabile, un modello OR.</span><span class="sxs-lookup"><span data-stu-id="1f241-161">The following example demonstrates the use of literal patterns, and also uses a variable pattern and an OR pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4801.fs)]

<span data-ttu-id="1f241-162">Un altro esempio di un modello di valore letterale è un modello in base alle costanti di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="1f241-162">Another example of a literal pattern is a pattern based on enumeration constants.</span></span> <span data-ttu-id="1f241-163">Quando si utilizzano costanti di enumerazione, è necessario specificare il nome del tipo di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="1f241-163">You must specify the enumeration type name when you use enumeration constants.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4802.fs)]

## <a name="identifier-patterns"></a><span data-ttu-id="1f241-164">Modelli identificatori</span><span class="sxs-lookup"><span data-stu-id="1f241-164">Identifier Patterns</span></span>
<span data-ttu-id="1f241-165">Se il modello è una stringa di caratteri che costituisce un identificatore valido, il formato dell'identificatore determina il modo in cui il modello è associato.</span><span class="sxs-lookup"><span data-stu-id="1f241-165">If the pattern is a string of characters that forms a valid identifier, the form of the identifier determines how the pattern is matched.</span></span> <span data-ttu-id="1f241-166">Se l'identificatore è più lungo di un singolo carattere e inizia con un carattere maiuscolo, il compilatore tenta di stabilire una corrispondenza per il modello identificatore.</span><span class="sxs-lookup"><span data-stu-id="1f241-166">If the identifier is longer than a single character and starts with an uppercase character, the compiler tries to make a match to the identifier pattern.</span></span> <span data-ttu-id="1f241-167">L'identificatore per questo modello può essere un valore contrassegnato con l'attributo letterale, un case di unione discriminato, un identificatore di eccezione o un case (modello attivo).</span><span class="sxs-lookup"><span data-stu-id="1f241-167">The identifier for this pattern could be a value marked with the Literal attribute, a discriminated union case, an exception identifier, or an active pattern case.</span></span> <span data-ttu-id="1f241-168">Se non viene trovato alcun identificatore corrispondente, la corrispondenza ha esito negativo e il modello di regole successivo, il modello di variabile, viene confrontato con l'input.</span><span class="sxs-lookup"><span data-stu-id="1f241-168">If no matching identifier is found, the match fails and the next pattern rule, the variable pattern, is compared to the input.</span></span>

<span data-ttu-id="1f241-169">Modelli di unione discriminata possono essere semplici denominato casi o hanno un valore o una tupla contenente più valori.</span><span class="sxs-lookup"><span data-stu-id="1f241-169">Discriminated union patterns can be simple named cases or they can have a value, or a tuple containing multiple values.</span></span> <span data-ttu-id="1f241-170">Se è presente un valore, è necessario specificare un identificatore per il valore.</span><span class="sxs-lookup"><span data-stu-id="1f241-170">If there is a value, you must specify an identifier for the value.</span></span> <span data-ttu-id="1f241-171">Nel caso di una tupla, è necessario fornire un modello di tupla con un identificatore per ogni elemento della tupla o un identificatore con un nome di campo per uno o più denominate campi unioni.</span><span class="sxs-lookup"><span data-stu-id="1f241-171">In the case of a tuple, you must supply a tuple pattern with an identifier for each element of the tuple or an identifier with a field name for one or more named union fields.</span></span> <span data-ttu-id="1f241-172">Vedere gli esempi di codice in questa sezione per gli esempi.</span><span class="sxs-lookup"><span data-stu-id="1f241-172">See the code examples in this section for examples.</span></span>

<span data-ttu-id="1f241-173">Il `option` tipo è un'unione discriminata che dispone di due casi, `Some` e `None`.</span><span class="sxs-lookup"><span data-stu-id="1f241-173">The `option` type is a discriminated union that has two cases, `Some` and `None`.</span></span> <span data-ttu-id="1f241-174">Un caso (`Some`) è un valore, mentre l'altro (`None`) è semplicemente un case denominato.</span><span class="sxs-lookup"><span data-stu-id="1f241-174">One case (`Some`) has a value, but the other (`None`) is just a named case.</span></span> <span data-ttu-id="1f241-175">Pertanto, `Some` deve disporre di una variabile per il valore associato di `Some` , ma `None` deve essere visualizzata da sola.</span><span class="sxs-lookup"><span data-stu-id="1f241-175">Therefore, `Some` needs to have a variable for the value associated with the `Some` case, but `None` must appear by itself.</span></span> <span data-ttu-id="1f241-176">Nel codice seguente, la variabile `var1` è assegnato il valore ottenuto dalla corrispondenza con il `Some` case.</span><span class="sxs-lookup"><span data-stu-id="1f241-176">In the following code, the variable `var1` is given the value that is obtained by matching to the `Some` case.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4803.fs)]

<span data-ttu-id="1f241-177">Nell'esempio seguente, il `PersonName` unione discriminata contiene una combinazione di stringhe e caratteri che rappresentano i formati possibili dei nomi.</span><span class="sxs-lookup"><span data-stu-id="1f241-177">In the following example, the `PersonName` discriminated union contains a mixture of strings and characters that represent possible forms of names.</span></span> <span data-ttu-id="1f241-178">I case di unione discriminata sono `FirstOnly`, `LastOnly`, e `FirstLast`.</span><span class="sxs-lookup"><span data-stu-id="1f241-178">The cases of the discriminated union are `FirstOnly`, `LastOnly`, and `FirstLast`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4804.fs)]

<span data-ttu-id="1f241-179">Per le unioni discriminate denominato campi, utilizzare il segno di uguale (=) per estrarre il valore di un campo denominato.</span><span class="sxs-lookup"><span data-stu-id="1f241-179">For discriminated unions that have named fields, you use the equals sign (=) to extract the value of a named field.</span></span> <span data-ttu-id="1f241-180">Si consideri, ad esempio, un'unione discriminata con una dichiarazione simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="1f241-180">For example, consider a discriminated union with a declaration like the following.</span></span>

```fsharp
type Shape =
    | Rectangle of height : float * width : float
    | Circle of radius : float
```

<span data-ttu-id="1f241-181">È possibile utilizzare i campi denominati in un'espressione corrispondente come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="1f241-181">You can use the named fields in a pattern matching expression as follows.</span></span>

```fsharp
let matchShape shape =
    match shape with
    | Rectangle(height = h) -> printfn "Rectangle with length %f" h
    | Circle(r) -> printfn "Circle with radius %f" r
```

<span data-ttu-id="1f241-182">L'utilizzo del campo denominato è facoltativo, pertanto nell'esempio precedente, entrambi `Circle(r)` e `Circle(radius = r)` hanno lo stesso effetto.</span><span class="sxs-lookup"><span data-stu-id="1f241-182">The use of the named field is optional, so in the previous example, both `Circle(r)` and `Circle(radius = r)` have the same effect.</span></span>

<span data-ttu-id="1f241-183">Quando si specificano più campi, utilizzare il punto e virgola (;) come separatore.</span><span class="sxs-lookup"><span data-stu-id="1f241-183">When you specify multiple fields, use the semicolon (;) as a separator.</span></span>

```
match shape with
| Rectangle(height = h; width = w) -> printfn "Rectangle with height %f and width %f" h w
| _ -> ()
```

<span data-ttu-id="1f241-184">Criteri attivi consentono di definire i criteri di ricerca personalizzato più complessi.</span><span class="sxs-lookup"><span data-stu-id="1f241-184">Active patterns enable you to define more complex custom pattern matching.</span></span> <span data-ttu-id="1f241-185">Per ulteriori informazioni sui modelli attivi, vedere [criteri attivi](active-patterns.md).</span><span class="sxs-lookup"><span data-stu-id="1f241-185">For more information about active patterns, see [Active Patterns](active-patterns.md).</span></span>

<span data-ttu-id="1f241-186">Il caso in cui l'identificatore è un'eccezione viene utilizzato in corrispondenza dei modelli nel contesto dei gestori di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="1f241-186">The case in which the identifier is an exception is used in pattern matching in the context of exception handlers.</span></span> <span data-ttu-id="1f241-187">Per informazioni sui criteri di ricerca nella gestione delle eccezioni, vedere [eccezioni: il `try...with` espressione](exception-handling/the-try-with-expression.md).</span><span class="sxs-lookup"><span data-stu-id="1f241-187">For information about pattern matching in exception handling, see [Exceptions: The `try...with` Expression](exception-handling/the-try-with-expression.md).</span></span>


## <a name="variable-patterns"></a><span data-ttu-id="1f241-188">Pattern variabili</span><span class="sxs-lookup"><span data-stu-id="1f241-188">Variable Patterns</span></span>
<span data-ttu-id="1f241-189">Il modello variabile assegna il valore da associare a un nome di variabile, quale diventa quindi disponibile per l'utilizzo nell'espressione a destra dell'esecuzione di `->` simbolo.</span><span class="sxs-lookup"><span data-stu-id="1f241-189">The variable pattern assigns the value being matched to a variable name, which is then available for use in the execution expression to the right of the `->` symbol.</span></span> <span data-ttu-id="1f241-190">Qualsiasi input corrisponde a un modello di variabile da solo, ma pattern variabili spesso vengono visualizzati all'interno di altri modelli, consentendo pertanto strutture più complesse, ad esempio matrici di scomporre in variabili e Tuple.</span><span class="sxs-lookup"><span data-stu-id="1f241-190">A variable pattern alone matches any input, but variable patterns often appear within other patterns, therefore enabling more complex structures such as tuples and arrays to be decomposed into variables.</span></span>

<span data-ttu-id="1f241-191">Nell'esempio seguente viene illustrato un modello di variabile all'interno di un tupla (modello).</span><span class="sxs-lookup"><span data-stu-id="1f241-191">The following example demonstrates a variable pattern within a tuple pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4805.fs)]

## <a name="as-pattern"></a><span data-ttu-id="1f241-192">come modello</span><span class="sxs-lookup"><span data-stu-id="1f241-192">as Pattern</span></span>
<span data-ttu-id="1f241-193">Il `as` modello è un modello con un `as` aggiunta la clausola.</span><span class="sxs-lookup"><span data-stu-id="1f241-193">The `as` pattern is a pattern that has an `as` clause appended to it.</span></span> <span data-ttu-id="1f241-194">Il `as` clausola associa il valore corrispondente a un nome che può essere utilizzato nell'espressione di esecuzione di un `match` espressione, o, nel caso in cui questo modello viene usato in un `let` associazione, il nome viene aggiunto come un'associazione all'ambito locale.</span><span class="sxs-lookup"><span data-stu-id="1f241-194">The `as` clause binds the matched value to a name that can be used in the execution expression of a `match` expression, or, in the case where this pattern is used in a `let` binding, the name is added as a binding to the local scope.</span></span>

<span data-ttu-id="1f241-195">Nell'esempio seguente viene utilizzato un `as` modello.</span><span class="sxs-lookup"><span data-stu-id="1f241-195">The following example uses an `as` pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4806.fs)]

## <a name="or-pattern"></a><span data-ttu-id="1f241-196">O un modello</span><span class="sxs-lookup"><span data-stu-id="1f241-196">OR Pattern</span></span>
<span data-ttu-id="1f241-197">Quando i dati di input possono corrispondere a più modelli e si desidera eseguire lo stesso codice di conseguenza, viene utilizzato il modello OR.</span><span class="sxs-lookup"><span data-stu-id="1f241-197">The OR pattern is used when input data can match multiple patterns, and you want to execute the same code as a result.</span></span> <span data-ttu-id="1f241-198">I tipi di entrambi i lati del modello OR devono essere compatibili.</span><span class="sxs-lookup"><span data-stu-id="1f241-198">The types of both sides of the OR pattern must be compatible.</span></span>

<span data-ttu-id="1f241-199">Nell'esempio seguente viene illustrato il modello OR.</span><span class="sxs-lookup"><span data-stu-id="1f241-199">The following example demonstrates the OR pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4807.fs)]

## <a name="and-pattern"></a><span data-ttu-id="1f241-200">E modello</span><span class="sxs-lookup"><span data-stu-id="1f241-200">AND Pattern</span></span>
<span data-ttu-id="1f241-201">Il modello e richiede che l'input corrisponda a due modelli.</span><span class="sxs-lookup"><span data-stu-id="1f241-201">The AND pattern requires that the input match two patterns.</span></span> <span data-ttu-id="1f241-202">I tipi di entrambi i lati del modello e devono essere compatibili.</span><span class="sxs-lookup"><span data-stu-id="1f241-202">The types of both sides of the AND pattern must be compatible.</span></span>

<span data-ttu-id="1f241-203">Nell'esempio seguente viene ad esempio `detectZeroTuple` illustrato nella [tupla (modello)](https://msdn.microsoft.com/library/#tuple) sezione più avanti in questo argomento, ma in questo caso entrambi `var1` e `var2` vengono ottenuti utilizzando il modello e come valori.</span><span class="sxs-lookup"><span data-stu-id="1f241-203">The following example is like `detectZeroTuple` shown in the [Tuple Pattern](https://msdn.microsoft.com/library/#tuple) section later in this topic, but here both `var1` and `var2` are obtained as values by using the AND pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4808.fs)]

## <a name="cons-pattern"></a><span data-ttu-id="1f241-204">Modello costruttore</span><span class="sxs-lookup"><span data-stu-id="1f241-204">Cons Pattern</span></span>
<span data-ttu-id="1f241-205">Il modello costruttore viene utilizzato per scomporre un elenco nel primo elemento, il *head*e un elenco che contiene gli elementi rimanenti, il *della parte finale del*.</span><span class="sxs-lookup"><span data-stu-id="1f241-205">The cons pattern is used to decompose a list into the first element, the *head*, and a list that contains the remaining elements, the *tail*.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4809.fs)]

## <a name="list-pattern"></a><span data-ttu-id="1f241-206">Modello di elenco</span><span class="sxs-lookup"><span data-stu-id="1f241-206">List Pattern</span></span>
<span data-ttu-id="1f241-207">Il modello di elenco consente gli elenchi per essere scomposta in un numero di elementi.</span><span class="sxs-lookup"><span data-stu-id="1f241-207">The list pattern enables lists to be decomposed into a number of elements.</span></span> <span data-ttu-id="1f241-208">Il modello elenco può corrispondere solo elenchi di un numero specifico di elementi.</span><span class="sxs-lookup"><span data-stu-id="1f241-208">The list pattern itself can match only lists of a specific number of elements.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4810.fs)]

## <a name="array-pattern"></a><span data-ttu-id="1f241-209">Modello di matrice</span><span class="sxs-lookup"><span data-stu-id="1f241-209">Array Pattern</span></span>
<span data-ttu-id="1f241-210">Il modello di matrice è analogo allo schema di elenco e può essere usato per scomporre le matrici di un determinato periodo.</span><span class="sxs-lookup"><span data-stu-id="1f241-210">The array pattern resembles the list pattern and can be used to decompose arrays of a specific length.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4811.fs)]

## <a name="parenthesized-pattern"></a><span data-ttu-id="1f241-211">Modello racchiuso tra parentesi</span><span class="sxs-lookup"><span data-stu-id="1f241-211">Parenthesized Pattern</span></span>
<span data-ttu-id="1f241-212">È possibile raggruppare le parentesi attorno ai modelli per ottenere l'associazione desiderata.</span><span class="sxs-lookup"><span data-stu-id="1f241-212">Parentheses can be grouped around patterns to achieve the desired associativity.</span></span> <span data-ttu-id="1f241-213">Nell'esempio seguente, vengono usate parentesi per controllare l'associazione tra un modello AND e un modello di costruttore.</span><span class="sxs-lookup"><span data-stu-id="1f241-213">In the following example, parentheses are used to control associativity between an AND pattern and a cons pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4812.fs)]

## <a name="tuple-pattern"></a><span data-ttu-id="1f241-214">Tupla (modello)</span><span class="sxs-lookup"><span data-stu-id="1f241-214">Tuple Pattern</span></span>
<span data-ttu-id="1f241-215">Il modello tupla corrisponde input in formato di tupla e consente la tupla di scomporre nei relativi elementi costituenti utilizzando criteri di ricerca di variabili per ogni posizione nella tupla.</span><span class="sxs-lookup"><span data-stu-id="1f241-215">The tuple pattern matches input in tuple form and enables the tuple to be decomposed into its constituent elements by using pattern matching variables for each position in the tuple.</span></span>

<span data-ttu-id="1f241-216">Nell'esempio seguente viene illustrato il modello di tupla e utilizza anche modelli letterali pattern variabili e il carattere jolly.</span><span class="sxs-lookup"><span data-stu-id="1f241-216">The following example demonstrates the tuple pattern and also uses literal patterns, variable patterns, and the wildcard pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4813.fs)]

## <a name="record-pattern"></a><span data-ttu-id="1f241-217">Modello di record</span><span class="sxs-lookup"><span data-stu-id="1f241-217">Record Pattern</span></span>
<span data-ttu-id="1f241-218">Il modello di record viene usato per scomporre record per estrarre i valori dei campi.</span><span class="sxs-lookup"><span data-stu-id="1f241-218">The record pattern is used to decompose records to extract the values of fields.</span></span> <span data-ttu-id="1f241-219">Il modello non è necessario fare riferimento a tutti i campi del record. eventuali campi omessi sufficiente non partecipi alla corrispondenza e non vengono estratti.</span><span class="sxs-lookup"><span data-stu-id="1f241-219">The pattern does not have to reference all fields of the record; any omitted fields just do not participate in matching and are not extracted.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4814.fs)]

## <a name="wildcard-pattern"></a><span data-ttu-id="1f241-220">Caratteri jolly</span><span class="sxs-lookup"><span data-stu-id="1f241-220">Wildcard Pattern</span></span>
<span data-ttu-id="1f241-221">Il carattere jolly è rappresentato dal carattere di sottolineatura (`_`) di caratteri e corrisponde a qualsiasi input, come il modello di variabile, ad eccezione del fatto che l'input viene rimosso anziché assegnato a una variabile.</span><span class="sxs-lookup"><span data-stu-id="1f241-221">The wildcard pattern is represented by the underscore (`_`) character and matches any input, just like the variable pattern, except that the input is discarded instead of assigned to a variable.</span></span> <span data-ttu-id="1f241-222">Il carattere jolly viene spesso utilizzato all'interno di altri modelli come segnaposto per i valori che non sono necessari nell'espressione a destra del `->` simbolo.</span><span class="sxs-lookup"><span data-stu-id="1f241-222">The wildcard pattern is often used within other patterns as a placeholder for values that are not needed in the expression to the right of the `->` symbol.</span></span> <span data-ttu-id="1f241-223">Il carattere jolly viene utilizzato spesso anche alla fine di un elenco di modelli per la corrispondenza di qualsiasi input senza corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="1f241-223">The wildcard pattern is also frequently used at the end of a list of patterns to match any unmatched input.</span></span> <span data-ttu-id="1f241-224">Il carattere jolly è illustrato in molti esempi di codice in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="1f241-224">The wildcard pattern is demonstrated in many code examples in this topic.</span></span> <span data-ttu-id="1f241-225">Vedere il codice per un esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="1f241-225">See the preceding code for one example.</span></span>


## <a name="patterns-that-have-type-annotations"></a><span data-ttu-id="1f241-226">Schemi con annotazioni di tipo</span><span class="sxs-lookup"><span data-stu-id="1f241-226">Patterns That Have Type Annotations</span></span>
<span data-ttu-id="1f241-227">Modelli possono avere annotazioni di tipo.</span><span class="sxs-lookup"><span data-stu-id="1f241-227">Patterns can have type annotations.</span></span> <span data-ttu-id="1f241-228">Questi si comportano come altre annotazioni di tipo e determinano l'inferenza come altre annotazioni di tipo.</span><span class="sxs-lookup"><span data-stu-id="1f241-228">These behave like other type annotations and guide inference like other type annotations.</span></span> <span data-ttu-id="1f241-229">Le parentesi sono necessarie annotazioni del tipo nei modelli.</span><span class="sxs-lookup"><span data-stu-id="1f241-229">Parentheses are required around type annotations in patterns.</span></span> <span data-ttu-id="1f241-230">Il codice seguente viene illustrato un modello con un'annotazione di tipo.</span><span class="sxs-lookup"><span data-stu-id="1f241-230">The following code shows a pattern that has a type annotation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4815.fs)]

## <a name="type-test-pattern"></a><span data-ttu-id="1f241-231">Modello del Test di tipo</span><span class="sxs-lookup"><span data-stu-id="1f241-231">Type Test Pattern</span></span>
<span data-ttu-id="1f241-232">Il modello del test di tipo viene utilizzato in base all'input rispetto a un tipo.</span><span class="sxs-lookup"><span data-stu-id="1f241-232">The type test pattern is used to match the input against a type.</span></span> <span data-ttu-id="1f241-233">Se il tipo di input è una corrispondenza (o un tipo derivato di) il tipo specificato nel modello, la corrispondenza ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="1f241-233">If the input type is a match to (or a derived type of) the type specified in the pattern, the match succeeds.</span></span>

<span data-ttu-id="1f241-234">Nell'esempio seguente viene illustrato il modello di prova di tipo.</span><span class="sxs-lookup"><span data-stu-id="1f241-234">The following example demonstrates the type test pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4816.fs)]

## <a name="null-pattern"></a><span data-ttu-id="1f241-235">Modello null</span><span class="sxs-lookup"><span data-stu-id="1f241-235">Null Pattern</span></span>
<span data-ttu-id="1f241-236">Il modello null corrisponde al valore null che può essere visualizzati quando si lavora con i tipi che consentono a un valore null.</span><span class="sxs-lookup"><span data-stu-id="1f241-236">The null pattern matches the null value that can appear when you are working with types that allow a null value.</span></span> <span data-ttu-id="1f241-237">Modelli null vengono spesso utilizzati per l'interazione con codice di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1f241-237">Null patterns are frequently used when interoperating with .NET Framework code.</span></span> <span data-ttu-id="1f241-238">Ad esempio, il valore restituito di un'API .NET può essere l'input per un `match` espressione.</span><span class="sxs-lookup"><span data-stu-id="1f241-238">For example, the return value of a .NET API might be the input to a `match` expression.</span></span> <span data-ttu-id="1f241-239">È possibile controllare il flusso di programma dipende se il valore restituito è null e anche su altre caratteristiche del valore restituito.</span><span class="sxs-lookup"><span data-stu-id="1f241-239">You can control program flow based on whether the return value is null, and also on other characteristics of the returned value.</span></span> <span data-ttu-id="1f241-240">È possibile utilizzare il modello null per escludere i valori null vengano propagate al resto del programma.</span><span class="sxs-lookup"><span data-stu-id="1f241-240">You can use the null pattern to prevent null values from propagating to the rest of your program.</span></span>

<span data-ttu-id="1f241-241">L'esempio seguente usa il modello null e il modello di variabile.</span><span class="sxs-lookup"><span data-stu-id="1f241-241">The following example uses the null pattern and the variable pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4817.fs)]

## <a name="see-also"></a><span data-ttu-id="1f241-242">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1f241-242">See Also</span></span>
[<span data-ttu-id="1f241-243">Espressioni match</span><span class="sxs-lookup"><span data-stu-id="1f241-243">Match Expressions</span></span>](match-expressions.md)

[<span data-ttu-id="1f241-244">Criteri attivi</span><span class="sxs-lookup"><span data-stu-id="1f241-244">Active Patterns</span></span>](active-patterns.md)

[<span data-ttu-id="1f241-245">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="1f241-245">F# Language Reference</span></span>](index.md)
