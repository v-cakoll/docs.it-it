---
title: Istruzione switch in C#
ms.date: 04/09/2019
f1_keywords:
- switch_CSharpKeyword
- switch
- case
- case_CSharpKeyword
helpviewer_keywords:
- switch statement [C#]
- switch keyword [C#]
- case statement [C#]
- default keyword [C#]
ms.assetid: 44bae8b8-8841-4d85-826b-8a94277daecb
ms.openlocfilehash: e5580e81b9175cd95491fdba724bacbffa692a5e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345398"
---
# <a name="switch-c-reference"></a><span data-ttu-id="c8912-102">switch (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="c8912-102">switch (C# reference)</span></span>

<span data-ttu-id="c8912-103">`switch` è un'istruzione di selezione che sceglie una sola *sezione opzioni* da eseguire da un elenco di candidati in base a un criterio di ricerca con l'*espressione di ricerca*.</span><span class="sxs-lookup"><span data-stu-id="c8912-103">`switch` is a selection statement that chooses a single *switch section* to execute from a list of candidates based on a pattern match with the *match expression*.</span></span>

[!code-csharp[switch#1](~/samples/snippets/csharp/language-reference/keywords/switch/switch1.cs#1)]

<span data-ttu-id="c8912-104">L'istruzione `switch` viene spesso usata come alternativa a un costrutto [if-else](if-else.md) se una singola espressione viene testata in base a tre o più condizioni.</span><span class="sxs-lookup"><span data-stu-id="c8912-104">The `switch` statement is often used as an alternative to an [if-else](if-else.md) construct if a single expression is tested against three or more conditions.</span></span> <span data-ttu-id="c8912-105">Ad esempio, l'istruzione `switch` determina se una variabile di tipo `Color` ha uno dei tre valori:</span><span class="sxs-lookup"><span data-stu-id="c8912-105">For example, the following `switch` statement determines whether a variable of type `Color` has one of three values:</span></span>

[!code-csharp[switch#3](~/samples/snippets/csharp/language-reference/keywords/switch/switch3.cs#1)]

<span data-ttu-id="c8912-106">È equivalente all'esempio seguente che usa un costrutto `if`-`else`.</span><span class="sxs-lookup"><span data-stu-id="c8912-106">It's equivalent to the following example that uses an `if`-`else` construct.</span></span>

[!code-csharp[switch#3a](~/samples/snippets/csharp/language-reference/keywords/switch/switch3a.cs#1)]

## <a name="the-match-expression"></a><span data-ttu-id="c8912-107">Espressione di ricerca</span><span class="sxs-lookup"><span data-stu-id="c8912-107">The match expression</span></span>

<span data-ttu-id="c8912-108">L'espressione di ricerca fornisce il valore da confrontare con i modelli nelle etichette `case`.</span><span class="sxs-lookup"><span data-stu-id="c8912-108">The match expression provides the value to match against the patterns in `case` labels.</span></span> <span data-ttu-id="c8912-109">La sintassi è la seguente:</span><span class="sxs-lookup"><span data-stu-id="c8912-109">Its syntax is:</span></span>

```csharp
   switch (expr)
```

<span data-ttu-id="c8912-110">In C# 6 e versioni precedenti l'espressione di ricerca deve essere un'espressione che restituisce un valore dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8912-110">In C# 6 and earlier, the match expression must be an expression that returns a value of the following types:</span></span>

- <span data-ttu-id="c8912-111">un [char](../builtin-types/char.md).</span><span class="sxs-lookup"><span data-stu-id="c8912-111">a [char](../builtin-types/char.md).</span></span>
- <span data-ttu-id="c8912-112">una [string](../builtin-types/reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="c8912-112">a [string](../builtin-types/reference-types.md).</span></span>
- <span data-ttu-id="c8912-113">un [bool](../builtin-types/bool.md).</span><span class="sxs-lookup"><span data-stu-id="c8912-113">a [bool](../builtin-types/bool.md).</span></span>
- <span data-ttu-id="c8912-114">valore [integrale](../builtin-types/integral-numeric-types.md) , ad esempio un `int` o una `long`.</span><span class="sxs-lookup"><span data-stu-id="c8912-114">an [integral](../builtin-types/integral-numeric-types.md) value, such as an `int` or a `long`.</span></span>
- <span data-ttu-id="c8912-115">un valore [enum](../builtin-types/enum.md).</span><span class="sxs-lookup"><span data-stu-id="c8912-115">an [enum](../builtin-types/enum.md) value.</span></span>

<span data-ttu-id="c8912-116">A partire da C# 7.0, l'espressione di ricerca può essere qualsiasi espressione non null.</span><span class="sxs-lookup"><span data-stu-id="c8912-116">Starting with C# 7.0, the match expression can be any non-null expression.</span></span>

## <a name="the-switch-section"></a><span data-ttu-id="c8912-117">Sezione opzioni</span><span class="sxs-lookup"><span data-stu-id="c8912-117">The switch section</span></span>

<span data-ttu-id="c8912-118">Un'istruzione `switch` include una o più sezioni opzioni.</span><span class="sxs-lookup"><span data-stu-id="c8912-118">A `switch` statement includes one or more switch sections.</span></span> <span data-ttu-id="c8912-119">Ogni sezione switch contiene una o più *etichette case* (etichetta case o default) seguite da una o più istruzioni.</span><span class="sxs-lookup"><span data-stu-id="c8912-119">Each switch section contains one or more *case labels* (either a case or default label) followed by one or more statements.</span></span> <span data-ttu-id="c8912-120">L'istruzione `switch` può includere al massimo un'etichetta default posizionata in qualsiasi sezione switch.</span><span class="sxs-lookup"><span data-stu-id="c8912-120">The `switch` statement may include at most one default label placed in any switch section.</span></span> <span data-ttu-id="c8912-121">Nell'esempio seguente viene illustrata una semplice istruzione `switch` con tre sezioni switch, contenenti ognuna due istruzioni.</span><span class="sxs-lookup"><span data-stu-id="c8912-121">The following example shows a simple `switch` statement that has three switch sections, each containing two statements.</span></span> <span data-ttu-id="c8912-122">La seconda sezione switch contiene le etichette `case 2:` e `case 3:`.</span><span class="sxs-lookup"><span data-stu-id="c8912-122">The second switch section contains the `case 2:` and `case 3:` labels.</span></span>

<span data-ttu-id="c8912-123">Un'istruzione `switch` può contenere qualsiasi numero di sezioni opzioni e ogni sezione può avere una o più etichette case, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="c8912-123">A `switch` statement can include any number of switch sections, and each section can have one or more case labels, as shown in the following example.</span></span> <span data-ttu-id="c8912-124">Tuttavia, due etichette case non possono contenere la stessa espressione.</span><span class="sxs-lookup"><span data-stu-id="c8912-124">However, no two case labels may contain the same expression.</span></span>

[!code-csharp[switch#2](~/samples/snippets/csharp/language-reference/keywords/switch/switch2.cs#1)]

<span data-ttu-id="c8912-125">Viene eseguita una sola sezione opzioni in un'istruzione switch.</span><span class="sxs-lookup"><span data-stu-id="c8912-125">Only one switch section in a switch statement executes.</span></span> <span data-ttu-id="c8912-126">C# non consente di continuare l'esecuzione da una sezione opzioni a quella successiva.</span><span class="sxs-lookup"><span data-stu-id="c8912-126">C# doesn't allow execution to continue from one switch section to the next.</span></span> <span data-ttu-id="c8912-127">Per questo motivo, il codice seguente genera un errore del compilatore, CS0163: "il controllo non può passare da un'etichetta case (\<etichetta case >) a un'altra".</span><span class="sxs-lookup"><span data-stu-id="c8912-127">Because of this, the following code generates a compiler error, CS0163: "Control cannot fall through from one case label (\<case label>) to another."</span></span>

```csharp
switch (caseSwitch)
{
    // The following switch section causes an error.
    case 1:
        Console.WriteLine("Case 1...");
        // Add a break or other jump statement here.
    case 2:
        Console.WriteLine("... and/or Case 2");
        break;
}
```

<span data-ttu-id="c8912-128">Questo requisito viene generalmente soddisfatto chiudendo in modo esplicito la sezione opzioni tramite un'istruzione [break](break.md), [goto](goto.md) o [return](return.md).</span><span class="sxs-lookup"><span data-stu-id="c8912-128">This requirement is usually met by explicitly exiting the switch section by using a [break](break.md), [goto](goto.md), or [return](return.md) statement.</span></span> <span data-ttu-id="c8912-129">Tuttavia, anche il codice seguente è valido, perché assicura che il controllo del programma non possa passare alla sezione opzioni `default`.</span><span class="sxs-lookup"><span data-stu-id="c8912-129">However, the following code is also valid, because it ensures that program control can't fall through to the `default` switch section.</span></span>

[!code-csharp[switch#4](~/samples/snippets/csharp/language-reference/keywords/switch/switch4.cs#1)]

<span data-ttu-id="c8912-130">L'esecuzione dell'elenco di istruzioni nella sezione opzioni con un'etichetta case che corrisponde all'espressione di ricerca inizia con la prima istruzione e continua con l'elenco di istruzioni, in genere fino a raggiungere un'istruzione di salto, ad esempio `break`, `goto case`, `goto label`, `return` o `throw`.</span><span class="sxs-lookup"><span data-stu-id="c8912-130">Execution of the statement list in the switch section with a case label that matches the match expression begins with the first statement and proceeds through the statement list, typically until a jump statement, such as a `break`, `goto case`, `goto label`, `return`, or `throw`, is reached.</span></span> <span data-ttu-id="c8912-131">A quel punto, il controllo viene trasferito al di fuori dell'istruzione `switch` o in un'altra etichetta case.</span><span class="sxs-lookup"><span data-stu-id="c8912-131">At that point, control is transferred outside the `switch` statement or to another case label.</span></span> <span data-ttu-id="c8912-132">Un'istruzione `goto`, se usata, deve trasferire il controllo a un'etichetta costante.</span><span class="sxs-lookup"><span data-stu-id="c8912-132">A `goto` statement, if it's used, must transfer control to a constant label.</span></span> <span data-ttu-id="c8912-133">Questa restrizione è necessaria, perché il tentativo di trasferire il controllo a un'etichetta non costante può avere effetti collaterali indesiderati, come il trasferimento del controllo a una posizione non prevista nel codice o la creazione di un ciclo infinito.</span><span class="sxs-lookup"><span data-stu-id="c8912-133">This restriction is necessary, since attempting to transfer control to a non-constant label can have undesirable side-effects, such transferring control to an unintended location in code or creating an endless loop.</span></span>

## <a name="case-labels"></a><span data-ttu-id="c8912-134">Etichette case</span><span class="sxs-lookup"><span data-stu-id="c8912-134">Case labels</span></span>

<span data-ttu-id="c8912-135">Ogni etichetta case specifica un criterio da confrontare con l'espressione di ricerca (la variabile `caseSwitch` negli esempi precedenti).</span><span class="sxs-lookup"><span data-stu-id="c8912-135">Each case label specifies a pattern to compare to the match expression (the `caseSwitch` variable in the previous examples).</span></span> <span data-ttu-id="c8912-136">Se corrispondono, il controllo viene trasferito alla sezione opzioni che contiene la **prima** etichetta case corrispondente.</span><span class="sxs-lookup"><span data-stu-id="c8912-136">If they match, control is transferred to the switch section that contains the **first** matching case label.</span></span> <span data-ttu-id="c8912-137">Se nessun criterio di etichetta case corrisponde all'espressione di ricerca, il controllo viene trasferito alla sezione con etichetta case `default`, se presente.</span><span class="sxs-lookup"><span data-stu-id="c8912-137">If no case label pattern matches the match expression, control is transferred to the section with the `default` case label, if there's one.</span></span> <span data-ttu-id="c8912-138">Se non è presente alcun case `default`, non vengono eseguite istruzioni in nessuna sezione opzioni e il controllo viene trasferito al di fuori dell'istruzione `switch`.</span><span class="sxs-lookup"><span data-stu-id="c8912-138">If there's no `default` case, no statements in any switch section are executed, and control is transferred outside the `switch` statement.</span></span>

<span data-ttu-id="c8912-139">Per informazioni sull'istruzione `switch` e sui criteri di ricerca, vedere [Criteri di ricerca con la sezione `switch` istruzione](#pattern).</span><span class="sxs-lookup"><span data-stu-id="c8912-139">For information on the `switch` statement and pattern matching, see the [Pattern matching with the `switch` statement](#pattern) section.</span></span>

<span data-ttu-id="c8912-140">Poiché C# 6 supporta solo il criterio costante e non consente la ripetizione di valori costanti, le etichette case definiscono valori che si escludono a vicenda e solo un criterio può corrispondere all'espressione di ricerca.</span><span class="sxs-lookup"><span data-stu-id="c8912-140">Because C# 6 supports only the constant pattern and doesn't allow the repetition of constant values, case labels define mutually exclusive values, and only one pattern can match the match expression.</span></span> <span data-ttu-id="c8912-141">Di conseguenza, l'ordine in cui vengono visualizzate le istruzioni `case` non è rilevante.</span><span class="sxs-lookup"><span data-stu-id="c8912-141">As a result, the order in which `case` statements appear is unimportant.</span></span>

<span data-ttu-id="c8912-142">In C# 7.0, tuttavia, poiché sono supportati altri criteri, le etichette case non devono necessariamente definire valori che si escludono a vicenda e più criteri possono corrispondere all'espressione di ricerca.</span><span class="sxs-lookup"><span data-stu-id="c8912-142">In C# 7.0, however, because other patterns are supported, case labels need not define mutually exclusive values, and multiple patterns can match the match expression.</span></span> <span data-ttu-id="c8912-143">Dal momento che vengono eseguite solo le istruzioni nella prima sezione opzione che contiene il criterio di corrispondenza, l'ordine in cui ora vengono visualizzate le istruzioni `case` è importante.</span><span class="sxs-lookup"><span data-stu-id="c8912-143">Because only the statements in the first switch section that contains the matching pattern are executed, the order in which `case` statements appear is now important.</span></span> <span data-ttu-id="c8912-144">Se C# rileva una sezione opzioni la cui istruzione o istruzioni case sono equivalenti a o sono subset di istruzioni precedenti, viene generato l'errore del compilatore CS8120: "Lo switch case è già stato gestito da un case precedente."</span><span class="sxs-lookup"><span data-stu-id="c8912-144">If C# detects a switch section whose case statement or statements are equivalent to or are subsets of previous statements, it generates a compiler error, CS8120, "The switch case has already been handled by a previous case."</span></span>

<span data-ttu-id="c8912-145">Nell'esempio seguente viene illustrata un'istruzione `switch` che usa un'ampia gamma di criteri che non si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="c8912-145">The following example illustrates a `switch` statement that uses a variety of non-mutually exclusive patterns.</span></span> <span data-ttu-id="c8912-146">Se si sposta la sezione opzioni `case 0:` in modo che non sia più la prima sezione nell'istruzione `switch`, C# genera un errore del compilatore perché un numero intero il cui valore è uguale a zero è un sottoinsieme di tutti i numeri interi, che corrisponde al criterio definito dall'istruzione `case int val`.</span><span class="sxs-lookup"><span data-stu-id="c8912-146">If you move the `case 0:` switch section so that it's no longer the first section in the `switch` statement, C# generates a compiler error because an integer whose value is zero is a subset of all integers, which is the pattern defined by the `case int val` statement.</span></span>

[!code-csharp[switch#5](~/samples/snippets/csharp/language-reference/keywords/switch/switch5.cs#1)]

<span data-ttu-id="c8912-147">È possibile correggere il problema ed eliminare l'avviso del compilatore in uno dei due modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8912-147">You can correct this issue and eliminate the compiler warning in one of two ways:</span></span>

- <span data-ttu-id="c8912-148">Modificando l'ordine delle sezioni opzioni.</span><span class="sxs-lookup"><span data-stu-id="c8912-148">By changing the order of the switch sections.</span></span>

- <span data-ttu-id="c8912-149">Usando una [clausola when](#when) nell'etichetta `case`.</span><span class="sxs-lookup"><span data-stu-id="c8912-149">By using a [when clause](#when) in the `case` label.</span></span>

## <a name="the-default-case"></a><span data-ttu-id="c8912-150">Case `default`</span><span class="sxs-lookup"><span data-stu-id="c8912-150">The `default` case</span></span>

<span data-ttu-id="c8912-151">Il case `default` specifica la sezione opzioni da eseguire se l'espressione di ricerca non corrisponde a nessun'altra etichetta `case`.</span><span class="sxs-lookup"><span data-stu-id="c8912-151">The `default` case specifies the switch section to execute if the match expression doesn't match any other `case` label.</span></span> <span data-ttu-id="c8912-152">Se non è presente un case `default` e l'espressione di ricerca non corrisponde a nessun'altra etichetta `case`, il flusso del programma salta l'istruzione `switch`.</span><span class="sxs-lookup"><span data-stu-id="c8912-152">If a `default` case is not present and the match expression doesn't match any other `case` label, program flow falls through the `switch` statement.</span></span>

<span data-ttu-id="c8912-153">Il case `default` può essere visualizzato in qualsiasi ordine nell'istruzione `switch`.</span><span class="sxs-lookup"><span data-stu-id="c8912-153">The `default` case can appear in any order in the `switch` statement.</span></span> <span data-ttu-id="c8912-154">Indipendentemente dall'ordine nel codice sorgente, viene sempre valutato per ultimo, dopo la valutazione di tutte le etichette `case`.</span><span class="sxs-lookup"><span data-stu-id="c8912-154">Regardless of its order in the source code, it's always evaluated last, after all `case` labels have been evaluated.</span></span>

## <a name="a-namepattern--pattern-matching-with-the-switch-statement"></a><span data-ttu-id="c8912-155"><a name="pattern" /> Criteri di ricerca con istruzione `switch`</span><span class="sxs-lookup"><span data-stu-id="c8912-155"><a name="pattern" /> Pattern matching with the `switch` statement</span></span>

<span data-ttu-id="c8912-156">Ogni istruzione `case` definisce un criterio che, in caso di corrispondenza con l'espressione di ricerca, provoca l'esecuzione della sezione opzioni che la contiene.</span><span class="sxs-lookup"><span data-stu-id="c8912-156">Each `case` statement defines a pattern that, if it matches the match expression, causes its  containing switch section to be executed.</span></span> <span data-ttu-id="c8912-157">Tutte le versioni di C# supportano il criterio costante.</span><span class="sxs-lookup"><span data-stu-id="c8912-157">All versions of C# support the constant pattern.</span></span> <span data-ttu-id="c8912-158">I criteri rimanenti sono supportati a partire da C# 7.0.</span><span class="sxs-lookup"><span data-stu-id="c8912-158">The remaining patterns are supported beginning with C# 7.0.</span></span>

### <a name="constant-pattern"></a><span data-ttu-id="c8912-159">Criterio costante</span><span class="sxs-lookup"><span data-stu-id="c8912-159">Constant pattern</span></span>

<span data-ttu-id="c8912-160">Il criterio costante verifica se un'espressione di ricerca è uguale a una costante specificata.</span><span class="sxs-lookup"><span data-stu-id="c8912-160">The constant pattern tests whether the match expression equals a specified constant.</span></span> <span data-ttu-id="c8912-161">La sintassi è la seguente:</span><span class="sxs-lookup"><span data-stu-id="c8912-161">Its syntax is:</span></span>

```csharp
   case constant:
```

<span data-ttu-id="c8912-162">dove *costant* è il valore su cui eseguire il test.</span><span class="sxs-lookup"><span data-stu-id="c8912-162">where *constant* is the value to test for.</span></span> <span data-ttu-id="c8912-163">*constant* può essere una delle espressioni costanti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8912-163">*constant* can be any of the following constant expressions:</span></span>

- <span data-ttu-id="c8912-164">Valore letterale [bool](../builtin-types/bool.md) : `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="c8912-164">A [bool](../builtin-types/bool.md) literal: either `true` or `false`.</span></span>
- <span data-ttu-id="c8912-165">Qualsiasi costante [integrale](../builtin-types/integral-numeric-types.md) , ad esempio un `int`, un `long`o un `byte`.</span><span class="sxs-lookup"><span data-stu-id="c8912-165">Any [integral](../builtin-types/integral-numeric-types.md) constant, such as an `int`, a `long`, or a `byte`.</span></span>
- <span data-ttu-id="c8912-166">Il nome di una variabile `const` dichiarata.</span><span class="sxs-lookup"><span data-stu-id="c8912-166">The name of a declared `const` variable.</span></span>
- <span data-ttu-id="c8912-167">Una costante di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="c8912-167">An enumeration constant.</span></span>
- <span data-ttu-id="c8912-168">Un valore letterale [char](../builtin-types/char.md).</span><span class="sxs-lookup"><span data-stu-id="c8912-168">A [char](../builtin-types/char.md) literal.</span></span>
- <span data-ttu-id="c8912-169">Un valore letterale [string](../builtin-types/reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="c8912-169">A [string](../builtin-types/reference-types.md) literal.</span></span>

<span data-ttu-id="c8912-170">L'espressione costante viene valutata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="c8912-170">The constant expression is evaluated as follows:</span></span>

- <span data-ttu-id="c8912-171">Se *expr* e *constant* sono tipi integrali, l'operatore di uguaglianza C# determina se l'espressione restituisce `true` (ovvero, se `expr == constant`).</span><span class="sxs-lookup"><span data-stu-id="c8912-171">If *expr* and *constant* are integral types, the C# equality operator determines whether the expression returns `true` (that is, whether `expr == constant`).</span></span>

- <span data-ttu-id="c8912-172">In caso contrario, il valore dell'espressione è determinato da una chiamata al metodo [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) statico.</span><span class="sxs-lookup"><span data-stu-id="c8912-172">Otherwise, the value of the expression is determined by a call to the static [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) method.</span></span>

<span data-ttu-id="c8912-173">Nell'esempio seguente viene usato il modello costante per determinare se una determinata data è un fine settimana, il primo giorno della settimana lavorativa, l'ultimo giorno della settimana o nel mezzo della settimana lavorativa.</span><span class="sxs-lookup"><span data-stu-id="c8912-173">The following example uses the constant pattern to determine whether a particular date is a weekend, the first day of the work week, the last day of the work week, or the middle of the work week.</span></span> <span data-ttu-id="c8912-174">Viene valutata la proprietà <xref:System.DateTime.DayOfWeek?displayProperty=nameWithType> del giorno corrente con i membri dell'enumerazione <xref:System.DayOfWeek>.</span><span class="sxs-lookup"><span data-stu-id="c8912-174">It evaluates the <xref:System.DateTime.DayOfWeek?displayProperty=nameWithType> property of the current day against the members of the <xref:System.DayOfWeek> enumeration.</span></span>

[!code-csharp[switch#7](~/samples/snippets/csharp/language-reference/keywords/switch/const-pattern.cs#1)]

<span data-ttu-id="c8912-175">L'esempio seguente usa il modello costante per gestire l'input dell'utente in un'applicazione console che simula una macchina per il caffè automatica.</span><span class="sxs-lookup"><span data-stu-id="c8912-175">The following example uses the constant pattern to handle user input in a console application that simulates an automatic coffee machine.</span></span>

[!code-csharp[switch#6](~/samples/snippets/csharp/language-reference/keywords/switch/switch6.cs)]

### <a name="type-pattern"></a><span data-ttu-id="c8912-176">Criterio del tipo</span><span class="sxs-lookup"><span data-stu-id="c8912-176">Type pattern</span></span>

<span data-ttu-id="c8912-177">Il criterio del tipo consente la conversione e valutazione concise del tipo.</span><span class="sxs-lookup"><span data-stu-id="c8912-177">The type pattern enables concise type evaluation and conversion.</span></span> <span data-ttu-id="c8912-178">Quando si usa con l'espressione `switch` per eseguire i criteri di ricerca, verifica se un'espressione può essere convertita in un tipo specificato e, in tal caso, esegue il cast a una variabile di quel tipo.</span><span class="sxs-lookup"><span data-stu-id="c8912-178">When used with the `switch` statement to perform pattern matching, it tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span> <span data-ttu-id="c8912-179">La sintassi è la seguente:</span><span class="sxs-lookup"><span data-stu-id="c8912-179">Its syntax is:</span></span>

```csharp
   case type varname
```

<span data-ttu-id="c8912-180">dove *type* è il nome del tipo in cui il risultato di *expr* deve essere convertito e *varname* è l'oggetto in cui il risultato di *expr*deve essere convertito se la ricerca ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="c8912-180">where *type* is the name of the type to which the result of *expr* is to be converted, and *varname* is the object to which the result of *expr* is converted if the match succeeds.</span></span> <span data-ttu-id="c8912-181">Il tipo in fase di compilazione di *expr* può essere un parametro di tipo generico, a partire da C# 7.1.</span><span class="sxs-lookup"><span data-stu-id="c8912-181">The compile-time type of *expr* may be a generic type parameter, starting with C# 7.1.</span></span>

<span data-ttu-id="c8912-182">L'espressione `case` è `true` se una delle condizioni seguenti è true:</span><span class="sxs-lookup"><span data-stu-id="c8912-182">The `case` expression is `true` if any of the following is true:</span></span>

- <span data-ttu-id="c8912-183">*expr* è un'istanza dello stesso tipo di *type*.</span><span class="sxs-lookup"><span data-stu-id="c8912-183">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="c8912-184">*expr* è un'istanza di un tipo che deriva da *type*.</span><span class="sxs-lookup"><span data-stu-id="c8912-184">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="c8912-185">In altre parole, il risultato di *expr* può subire l'upcast a un'istanza di *type*.</span><span class="sxs-lookup"><span data-stu-id="c8912-185">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="c8912-186">*expr* ha un tipo in fase di compilazione che è una classe di base di *type* e *expr* ha un tipo di runtime che è *type* o è derivato da *type*.</span><span class="sxs-lookup"><span data-stu-id="c8912-186">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="c8912-187">Il *tipo in fase di compilazione* di una variabile è il tipo della variabile come definito nella relativa dichiarazione del tipo.</span><span class="sxs-lookup"><span data-stu-id="c8912-187">The *compile-time type* of a variable is the variable's type as defined in its type declaration.</span></span> <span data-ttu-id="c8912-188">Il *tipo di runtime* di una variabile è il tipo dell'istanza che viene assegnato alla variabile.</span><span class="sxs-lookup"><span data-stu-id="c8912-188">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="c8912-189">*expr* è un'istanza di un tipo che implementa l'interfaccia *type*.</span><span class="sxs-lookup"><span data-stu-id="c8912-189">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="c8912-190">Se l'espressione del case è true, *varname* viene assegnata in modo definitivo e ha l'ambito locale esclusivamente all'interno della sezione opzioni.</span><span class="sxs-lookup"><span data-stu-id="c8912-190">If the case expression is true, *varname* is definitely assigned and has local scope within the switch section only.</span></span>

<span data-ttu-id="c8912-191">Si noti che `null` non corrisponde a un tipo.</span><span class="sxs-lookup"><span data-stu-id="c8912-191">Note that `null` doesn't match a type.</span></span> <span data-ttu-id="c8912-192">Per associare un `null`, usare l'etichetta `case` seguente:</span><span class="sxs-lookup"><span data-stu-id="c8912-192">To match a `null`, you use the following `case` label:</span></span>

```csharp
case null:
```

<span data-ttu-id="c8912-193">Nell'esempio seguente viene usato il criterio del tipo per fornire informazioni sui vari generi di tipi di raccolta.</span><span class="sxs-lookup"><span data-stu-id="c8912-193">The following example uses the type pattern to provide information about various kinds of collection types.</span></span>

[!code-csharp[type-pattern#1](~/samples/snippets/csharp/language-reference/keywords/switch/type-pattern.cs#1)]

<span data-ttu-id="c8912-194">Invece di `object`, si potrebbe creare un metodo generico usando il tipo della raccolta come parametro di tipo, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="c8912-194">Instead of `object`, you could make a generic method, using the type of the collection as the type parameter, as shown in the following code:</span></span>

[!code-csharp[type-pattern#3](~/samples/snippets/csharp/language-reference/keywords/switch/type-pattern3.cs#1)]

<span data-ttu-id="c8912-195">La versione generica presenta due differenze rispetto al primo esempio.</span><span class="sxs-lookup"><span data-stu-id="c8912-195">The generic version is different than the first sample in two ways.</span></span> <span data-ttu-id="c8912-196">La prima è che non è possibile usare il case `null`.</span><span class="sxs-lookup"><span data-stu-id="c8912-196">First, you can't use the `null` case.</span></span> <span data-ttu-id="c8912-197">Non è possibile usare un case costante perché il compilatore non è in grado di convertire un tipo arbitrario `T` in alcun tipo diverso da `object`.</span><span class="sxs-lookup"><span data-stu-id="c8912-197">You can't use any constant case because the compiler can't convert any arbitrary type `T` to any type other than `object`.</span></span> <span data-ttu-id="c8912-198">Ciò che prima era il case `default` ora esegue il test per un `object` non Null.</span><span class="sxs-lookup"><span data-stu-id="c8912-198">What had been the `default` case now tests for a non-null `object`.</span></span> <span data-ttu-id="c8912-199">Questo significa che il case `default` esegue il test solo per `null`.</span><span class="sxs-lookup"><span data-stu-id="c8912-199">That means the `default` case tests only for `null`.</span></span>

<span data-ttu-id="c8912-200">Senza criteri di ricerca, questo codice potrebbe essere scritto come segue.</span><span class="sxs-lookup"><span data-stu-id="c8912-200">Without pattern matching, this code might be written as follows.</span></span> <span data-ttu-id="c8912-201">L'uso di criteri di ricerca del tipo produce codice più compatto e leggibile eliminando la necessità di verificare se il risultato di una conversione è un `null` o eseguire cast ripetuti.</span><span class="sxs-lookup"><span data-stu-id="c8912-201">The use of type pattern matching produces more compact, readable code by eliminating the need to test whether the result of a conversion is a `null` or to perform repeated casts.</span></span>

[!code-csharp[type-pattern2#1](~/samples/snippets/csharp/language-reference/keywords/switch/type-pattern2.cs#1)]

## <a name="a-namewhen--the-case-statement-and-the-when-clause"></a><span data-ttu-id="c8912-202"><a name="when" /> Istruzione `case` e clausola `when`</span><span class="sxs-lookup"><span data-stu-id="c8912-202"><a name="when" /> The `case` statement and the `when` clause</span></span>

<span data-ttu-id="c8912-203">A partire da C# 7.0, poiché le istruzioni case non devono escludersi a vicenda, è possibile aggiungere una clausola `when` per specificare una condizione aggiuntiva che deve essere soddisfatta perché l'istruzione case restituisca true.</span><span class="sxs-lookup"><span data-stu-id="c8912-203">Starting with C# 7.0, because case statements need not be mutually exclusive, you can add a `when` clause to specify an additional condition that must be satisfied for the case statement to evaluate to true.</span></span> <span data-ttu-id="c8912-204">La clausola `when` può essere qualsiasi espressione che restituisce un valore booleano.</span><span class="sxs-lookup"><span data-stu-id="c8912-204">The `when` clause can be any expression that returns a Boolean value.</span></span>

<span data-ttu-id="c8912-205">Nell'esempio seguente viene definita una classe `Shape` di base, una classe `Rectangle` che deriva da `Shape` e una classe `Square` che deriva da `Rectangle`.</span><span class="sxs-lookup"><span data-stu-id="c8912-205">The following example defines a base `Shape` class, a `Rectangle` class that derives from `Shape`, and a `Square` class that derives from `Rectangle`.</span></span> <span data-ttu-id="c8912-206">L'esempio usa la clausola `when` per assicurarsi che `ShowShapeInfo` consideri un oggetto `Rectangle` a cui è stata assegnata pari lunghezza e larghezza di un elemento `Square`, anche nel caso in cui non sia stata creata un'istanza come oggetto `Square`.</span><span class="sxs-lookup"><span data-stu-id="c8912-206">It uses the `when` clause to ensure that the `ShowShapeInfo` treats a `Rectangle` object that has been assigned equal lengths and widths as a `Square` even if it hasn't been instantiated as a `Square` object.</span></span> <span data-ttu-id="c8912-207">Il metodo non tenta di visualizzare informazioni su un oggetto `null` o su una forma la cui area è pari a zero.</span><span class="sxs-lookup"><span data-stu-id="c8912-207">The method doesn't attempt to display information either about an object that is `null` or a shape whose area is zero.</span></span>

[!code-csharp[when-clause#1](~/samples/snippets/csharp/language-reference/keywords/switch/when-clause.cs#1)]

<span data-ttu-id="c8912-208">Si noti che la clausola `when` dell'esempio che tenta di verificare se un oggetto `Shape` è `null` non viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="c8912-208">Note that the `when` clause in the example that attempts to test whether a `Shape` object is `null` doesn't execute.</span></span> <span data-ttu-id="c8912-209">Il criterio del tipo corretto da verificare per un `null` è `case null:`.</span><span class="sxs-lookup"><span data-stu-id="c8912-209">The correct type pattern to test for a `null` is `case null:`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c8912-210">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="c8912-210">C# language specification</span></span>

<span data-ttu-id="c8912-211">Per altre informazioni, vedere la sezione relativa all'[istruzione switch](~/_csharplang/spec/statements.md#the-switch-statement) nella [specifica del linguaggio C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="c8912-211">For more information, see [The switch statement](~/_csharplang/spec/statements.md#the-switch-statement) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="c8912-212">La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.</span><span class="sxs-lookup"><span data-stu-id="c8912-212">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="c8912-213">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8912-213">See also</span></span>

- [<span data-ttu-id="c8912-214">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="c8912-214">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c8912-215">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="c8912-215">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c8912-216">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="c8912-216">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="c8912-217">if-else</span><span class="sxs-lookup"><span data-stu-id="c8912-217">if-else</span></span>](if-else.md)
- [<span data-ttu-id="c8912-218">Criteri di ricerca</span><span class="sxs-lookup"><span data-stu-id="c8912-218">Pattern Matching</span></span>](../../pattern-matching.md)
