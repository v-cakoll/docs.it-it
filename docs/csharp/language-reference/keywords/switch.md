---
title: Parola chiave switch (Riferimenti per C#)
ms.date: 03/07/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
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
caps.latest.revision: "47"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1c345d0c6c935271600a386752e18c19a25cc389
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="switch-c-reference"></a><span data-ttu-id="d4bbe-102">switch (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="d4bbe-102">switch (C# Reference)</span></span>
<span data-ttu-id="d4bbe-103">`switch` è un'istruzione di selezione che sceglie una sola *sezione opzioni* da eseguire da un elenco di candidati in base a un criterio di ricerca con l'*espressione di ricerca*.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-103">`switch` is a selection statement that chooses a single *switch section* to execute from a list of candidates based on a pattern match with the *match expression*.</span></span> 
  
 [!code-csharp[switch#1](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch1.cs#1)]  

<span data-ttu-id="d4bbe-104">L'istruzione `switch` viene spesso usata come alternativa a un costrutto [if-else](if-else.md) se una singola espressione viene testata in base a tre o più condizioni.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-104">The `switch` statement is often used as an alternative to an [if-else](if-else.md) construct if a single expression is tested against three or more conditions.</span></span> <span data-ttu-id="d4bbe-105">Ad esempio, l'istruzione `switch` determina se una variabile di tipo `Color` ha uno dei tre valori:</span><span class="sxs-lookup"><span data-stu-id="d4bbe-105">For example, the following `switch` statement determines whether a variable of type `Color` has one of three values:</span></span> 

[!code-csharp[switch#3](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch3.cs#1)] 

<span data-ttu-id="d4bbe-106">È equivalente all'esempio seguente che usa un costrutto `if`-`else`.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-106">It is equivalent to the following example that uses an `if`-`else` construct.</span></span> 

[!code-csharp[switch#3a](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch3a.cs#1)] 

## <a name="the-match-expression"></a><span data-ttu-id="d4bbe-107">Espressione di ricerca</span><span class="sxs-lookup"><span data-stu-id="d4bbe-107">The match expression</span></span>

<span data-ttu-id="d4bbe-108">L'espressione di ricerca fornisce il valore da confrontare con i modelli nelle etichette `case`.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-108">The match expression provides the value to match against the patterns in `case` labels.</span></span> <span data-ttu-id="d4bbe-109">La sintassi è la seguente:</span><span class="sxs-lookup"><span data-stu-id="d4bbe-109">Its syntax is:</span></span>

```csharp
   switch (expr)
```

<span data-ttu-id="d4bbe-110">In C# 6, l'espressione di ricerca deve essere un'espressione che restituisce un valore dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4bbe-110">In C# 6, the match expression must be an expression that returns a value of the following types:</span></span>

- <span data-ttu-id="d4bbe-111">un [char](char.md).</span><span class="sxs-lookup"><span data-stu-id="d4bbe-111">a [char](char.md).</span></span>
- <span data-ttu-id="d4bbe-112">una [string](string.md).</span><span class="sxs-lookup"><span data-stu-id="d4bbe-112">a [string](string.md).</span></span>
- <span data-ttu-id="d4bbe-113">un [bool](bool.md).</span><span class="sxs-lookup"><span data-stu-id="d4bbe-113">a [bool](bool.md).</span></span> 
- <span data-ttu-id="d4bbe-114">un valore integrale, ad esempio un [int](int.md) o un [long](long.md).</span><span class="sxs-lookup"><span data-stu-id="d4bbe-114">an integral value, such as an [int](int.md) or a [long](long.md).</span></span>
- <span data-ttu-id="d4bbe-115">un valore [enum](enum.md).</span><span class="sxs-lookup"><span data-stu-id="d4bbe-115">an [enum](enum.md) value.</span></span>

<span data-ttu-id="d4bbe-116">A partire da C# 7, l'espressione di ricerca può essere qualsiasi espressione non null.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-116">Starting with C# 7, the match expression can be any non-null expression.</span></span>
 
## <a name="the-switch-section"></a><span data-ttu-id="d4bbe-117">Sezione opzioni</span><span class="sxs-lookup"><span data-stu-id="d4bbe-117">The switch section</span></span>
 
 <span data-ttu-id="d4bbe-118">Un'istruzione `switch` include una o più sezioni opzioni.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-118">A `switch` statement includes one or more switch sections.</span></span> <span data-ttu-id="d4bbe-119">Ogni sezione opzioni contiene una o più *etichette case* seguite da una o più istruzioni.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-119">Each switch section contains one or more *case labels* followed by one or more statements.</span></span> <span data-ttu-id="d4bbe-120">Nell'esempio seguente viene illustrata una semplice istruzione `switch` con tre sezioni opzioni.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-120">The following example shows a simple `switch` statement that has three switch sections.</span></span> <span data-ttu-id="d4bbe-121">Ogni sezione opzione ha un'etichetta case, ad esempio `case 1:`, e due istruzioni.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-121">Each switch section has one case label, such as `case 1:`, and two statements.</span></span>
 
  <span data-ttu-id="d4bbe-122">Un'istruzione `switch` può contenere qualsiasi numero di sezioni opzioni e ogni sezione può avere una o più etichette case, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-122">A `switch` statement can include any number of switch sections, and each section can have one or more case labels, as shown in the following example.</span></span> <span data-ttu-id="d4bbe-123">Tuttavia, due etichette case non possono contenere la stessa espressione.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-123">However, no two case labels may contain the same expression.</span></span>  

 [!code-csharp[switch#2](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch2.cs#1)]  

 <span data-ttu-id="d4bbe-124">Viene eseguita una sola sezione opzioni in un'istruzione switch.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-124">Only one switch section in a switch statement executes.</span></span> <span data-ttu-id="d4bbe-125">C# non consente di continuare l'esecuzione da una sezione opzioni a quella successiva.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-125">C# does not allow execution to continue from one switch section to the next.</span></span> <span data-ttu-id="d4bbe-126">Per questo motivo, il codice seguente genera un errore di compilazione CS0163: "Il controllo non può passare da un'etichetta case ("<case label>") a un'altra".</span><span class="sxs-lookup"><span data-stu-id="d4bbe-126">Because of this, the following code generates a compiler error, CS0163: "Control cannot fall through from one case label (<case label>) to another."</span></span>  

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
<span data-ttu-id="d4bbe-127">Questo requisito viene generalmente soddisfatto chiudendo in modo esplicito la sezione opzioni tramite un'istruzione [break](break.md), [goto](goto.md) o [return](return.md).</span><span class="sxs-lookup"><span data-stu-id="d4bbe-127">This requirement is usually met by explicitly exiting the switch section by using a [break](break.md), [goto](goto.md), or [return](return.md) statement.</span></span> <span data-ttu-id="d4bbe-128">Tuttavia, anche il codice seguente è valido, perché assicura che il controllo del programma non può passare alla sezione opzioni `default`.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-128">However, the following code is also valid, because it ensures that program control cannot fall through to the `default` switch section.</span></span>
  
 [!code-csharp[switch#4](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch4.cs#1)]    
  
 <span data-ttu-id="d4bbe-129">L'esecuzione dell'elenco di istruzioni nella sezione opzioni con un'etichetta case che corrisponde all'espressione di ricerca inizia con la prima istruzione e continua con l'elenco di istruzioni, in genere fino a raggiungere un'istruzione di salto, ad esempio `break`, `goto case`, `goto label`, `return` o `throw`.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-129">Execution of the statement list in the switch section with a case label that matches the match expression begins with the first statement and proceeds through the statement list, typically until a jump statement, such as a `break`, `goto case`, `goto label`, `return`, or `throw`, is reached.</span></span> <span data-ttu-id="d4bbe-130">A quel punto, il controllo viene trasferito al di fuori dell'istruzione `switch` o in un'altra etichetta case.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-130">At that point, control is transferred outside the `switch` statement or to another case label.</span></span> <span data-ttu-id="d4bbe-131">Un'istruzione `goto`, se usata, deve trasferire il controllo a un'etichetta costante.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-131">A `goto` statement, if it is used, must transfer control to a constant label.</span></span> <span data-ttu-id="d4bbe-132">Questa restrizione è necessaria, perché il tentativo di trasferire il controllo a un'etichetta non costante può avere effetti collaterali indesiderati, come il trasferimento del controllo a una posizione non prevista nel codice o la creazione di un ciclo infinito.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-132">This restriction is necessary, since attempting to transfer control to a non-constant label can have undesirable side-effects, such transferring control to an unintended location in code or creating an endless loop.</span></span>

## <a name="case-labels"></a><span data-ttu-id="d4bbe-133">Etichette case</span><span class="sxs-lookup"><span data-stu-id="d4bbe-133">Case labels</span></span>

 <span data-ttu-id="d4bbe-134">Ogni etichetta case specifica un criterio da confrontare con l'espressione di ricerca (la variabile `caseSwitch` negli esempi precedenti).</span><span class="sxs-lookup"><span data-stu-id="d4bbe-134">Each case label specifies a pattern to compare to the match expression (the `caseSwitch` variable in the previous examples).</span></span> <span data-ttu-id="d4bbe-135">Se corrispondono, il controllo viene trasferito alla sezione opzioni che contiene la **prima** etichetta case corrispondente.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-135">If they match, control is transferred to the switch section that contains the **first** matching case label.</span></span> <span data-ttu-id="d4bbe-136">Se nessun criterio di etichetta case corrisponde all'espressione di ricerca, il controllo viene trasferito alla sezione con etichetta case `default`, se presente.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-136">If no case label pattern matches the match expression, control is transferred to the section with the `default` case label, if there is one.</span></span> <span data-ttu-id="d4bbe-137">Se non è presente alcun case `default`, non vengono eseguite istruzioni in nessuna sezione opzioni e il controllo viene trasferito al di fuori dell'istruzione `switch`.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-137">If there is no `default` case, no statements in any switch section are executed, and control is transferred outside the `switch` statement.</span></span>

 <span data-ttu-id="d4bbe-138">Per informazioni sull'istruzione `switch` e sui criteri di ricerca, vedere [Criteri di ricerca con la sezione `switch` istruzione](#pattern).</span><span class="sxs-lookup"><span data-stu-id="d4bbe-138">For information on the `switch` statement and pattern matching, see the [Pattern matching with the `switch` statement](#pattern) section.</span></span>

 <span data-ttu-id="d4bbe-139">Poiché C# 6 supporta solo il criterio costante e non consente la ripetizione di valori costanti, le etichette case definiscono valori che si escludono a vicenda e solo un criterio può corrispondere all'espressione di ricerca.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-139">Because C# 6 supports only the constant pattern and does not allow the repetition of constant values, case labels define mutually exclusive values, and only one pattern can match the match expression.</span></span> <span data-ttu-id="d4bbe-140">Di conseguenza, l'ordine in cui vengono visualizzate le istruzioni `case` non è rilevante.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-140">As a result, the order in which `case` statements appear is unimportant.</span></span>

 <span data-ttu-id="d4bbe-141">In C# 7, tuttavia, poiché sono supportati altri criteri, le etichette case non devono necessariamente definire valori che si escludono a vicenda e più criteri possono corrispondere all'espressione di ricerca.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-141">In C# 7, however, because other patterns are supported, case labels need not define mutually exclusive values, and multiple patterns can match the match expression.</span></span> <span data-ttu-id="d4bbe-142">Dal momento che vengono eseguite solo le istruzioni nella sezione opzione che contiene il criterio di prima corrispondenza, l'ordine in cui ora vengono visualizzate le istruzioni `case` è importante.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-142">Because only the statements in the switch section that contains the first matching pattern are executed, the order in which `case` statements appear is now important.</span></span> <span data-ttu-id="d4bbe-143">Se C# rileva una sezione opzioni la cui istruzione o istruzioni case sono equivalenti a o sono subset di istruzioni precedenti, viene generato l'errore del compilatore CS8120: "Lo switch case è già stato gestito da un case precedente."</span><span class="sxs-lookup"><span data-stu-id="d4bbe-143">If C# detects a switch section whose case statement or statements are equivalent to or are subsets of previous statements, it generates a compiler error, CS8120, "The switch case has already been handled by a previous case."</span></span> 

 <span data-ttu-id="d4bbe-144">Nell'esempio seguente viene illustrata un'istruzione `switch` che usa un'ampia gamma di criteri che non si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-144">The following example illustrates a `switch` statement that uses a variety of non-mutually exclusive patterns.</span></span> <span data-ttu-id="d4bbe-145">Se si sposta la sezione opzioni `case 0:` in modo che non sia più la prima sezione nell'istruzione `switch`, C# genera un errore del compilatore perché un numero intero il cui valore è uguale a zero è un sottoinsieme di tutti i numeri interi, che corrisponde al criterio definito dall'istruzione `case int val`.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-145">If you move the `case 0:` switch section so that it is no longer the first section in the `switch` statement, C# generates a compiler error because an integer whose value is zero is a subset of all integers, which is the pattern defined by the `case int val` statement.</span></span>

 [!code-csharp[switch#5](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch5.cs#1)]    

<span data-ttu-id="d4bbe-146">È possibile correggere il problema ed eliminare l'avviso del compilatore in uno dei due modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4bbe-146">You can correct this issue and eliminate the compiler warning in one of two ways:</span></span>

- <span data-ttu-id="d4bbe-147">Modificando l'ordine delle sezioni opzioni.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-147">By changing the order of the switch sections.</span></span> 
 
- <span data-ttu-id="d4bbe-148">Usando un oggetto </a name="when"> quando la clausola </a> si trova nell'etichetta `case`.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-148">By using a </a name="when">when clause</a> in the `case` label.</span></span>
 
## <a name="the-default-case"></a><span data-ttu-id="d4bbe-149">Case `default`</span><span class="sxs-lookup"><span data-stu-id="d4bbe-149">The `default` case</span></span>

<span data-ttu-id="d4bbe-150">Il case `default` specifica la sezione opzioni da eseguire se l'espressione di ricerca non corrisponde nessun'altra etichetta `case`.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-150">The `default` case specifies the switch section to execute if the match expression does not match any other `case` label.</span></span> <span data-ttu-id="d4bbe-151">Se non è presente un case `default` e l'espressione di ricerca non corrisponde a nessun'altra etichetta `case`, il flusso del programma salta l'istruzione `switch`.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-151">If a `default` case is not present and the match expression does not match any other `case` label, program flow falls through the `switch` statement.</span></span>

<span data-ttu-id="d4bbe-152">Il case `default` può essere visualizzato in qualsiasi ordine nell'istruzione `switch`.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-152">The `default` case can appear in any order in the `switch` statement.</span></span> <span data-ttu-id="d4bbe-153">Indipendentemente dall'ordine nel codice sorgente, viene sempre valutato per ultimo, dopo la valutazione di tutte le etichette `case`.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-153">Regardless of its order in the source code, it is always evaluated last, after all `case` labels have been evaluated.</span></span>

## <a name="a-namepattern--pattern-matching-with-the-switch-statement"></a><span data-ttu-id="d4bbe-154"><a name="pattern" /> Criteri di ricerca con istruzione `switch`</span><span class="sxs-lookup"><span data-stu-id="d4bbe-154"><a name="pattern" /> Pattern matching with the `switch` statement</span></span>
  
<span data-ttu-id="d4bbe-155">Ogni istruzione `case` definisce un criterio che, in caso di corrispondenza con l'espressione di ricerca, provoca l'esecuzione della sezione opzioni che la contiene.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-155">Each `case` statement defines a pattern that, if it matches the match expression, causes its  containing switch section to be executed.</span></span> <span data-ttu-id="d4bbe-156">Tutte le versioni di C# supportano il criterio costante.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-156">All versions of C# support the constant pattern.</span></span> <span data-ttu-id="d4bbe-157">I criteri rimanenti sono supportati a partire da C# 7.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-157">The remaining patterns are supported beginning with C# 7.</span></span> 
  
### <a name="constant-pattern"></a><span data-ttu-id="d4bbe-158">Criterio costante</span><span class="sxs-lookup"><span data-stu-id="d4bbe-158">Constant pattern</span></span> 

<span data-ttu-id="d4bbe-159">Il criterio costante verifica se un'espressione di ricerca è uguale a una costante specificata.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-159">The constant pattern tests whether the match expression equals a specified constant.</span></span> <span data-ttu-id="d4bbe-160">La sintassi è la seguente:</span><span class="sxs-lookup"><span data-stu-id="d4bbe-160">Its syntax is:</span></span>

```csharp
   case constant:
```

<span data-ttu-id="d4bbe-161">dove *costant* è il valore su cui eseguire il test.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-161">where *constant* is the value to test for.</span></span> <span data-ttu-id="d4bbe-162">*constant* può essere una delle espressioni costanti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4bbe-162">*constant* can be any of the following constant expressions:</span></span> 

- <span data-ttu-id="d4bbe-163">Un valore letterale [bool](bool.md), ad esempio `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-163">A [bool](bool.md) literal, either `true` or `false`.</span></span>
- <span data-ttu-id="d4bbe-164">Qualsiasi costante integrale, ad esempio un [int](int.md), un [long](long.md) o un [byte](byte.md).</span><span class="sxs-lookup"><span data-stu-id="d4bbe-164">Any integral constant, such as an [int](int.md), a [long](long.md), or a [byte](byte.md).</span></span> 
- <span data-ttu-id="d4bbe-165">Il nome di una variabile `const` dichiarata.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-165">The name of a declared `const` variable.</span></span>
- <span data-ttu-id="d4bbe-166">Una costante di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-166">An enumeration constant.</span></span>
- <span data-ttu-id="d4bbe-167">Un valore letterale [char](char.md).</span><span class="sxs-lookup"><span data-stu-id="d4bbe-167">A [char](char.md) literal.</span></span>
- <span data-ttu-id="d4bbe-168">Un valore letterale [string](string.md).</span><span class="sxs-lookup"><span data-stu-id="d4bbe-168">A [string](string.md) literal.</span></span>

<span data-ttu-id="d4bbe-169">L'espressione costante viene valutata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="d4bbe-169">The constant expression is evaluated as follows:</span></span>

- <span data-ttu-id="d4bbe-170">Se *expr* e *constant* sono tipi integrali, l'operatore di uguaglianza C# determina se l'espressione restituisce `true` (ovvero, se `expr == constant`).</span><span class="sxs-lookup"><span data-stu-id="d4bbe-170">If *expr* and *constant* are integral types, the C# equality operator determines whether the expression returns `true` (that is, whether `expr == constant`).</span></span>

- <span data-ttu-id="d4bbe-171">In caso contrario, il valore dell'espressione è determinato da una chiamata al metodo [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) statico.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-171">Otherwise, the value of the expression is determined by a call to the static [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) method.</span></span>  

<span data-ttu-id="d4bbe-172">Nell'esempio seguente viene usato il modello costante per determinare se una determinata data è un fine settimana, il primo giorno della settimana lavorativa, l'ultimo giorno della settimana o nel mezzo della settimana lavorativa.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-172">The following example uses the constant pattern to determine whether a particular date is a weekend, the first day of the work week, the last day of the work week, or the middle of the work week.</span></span> <span data-ttu-id="d4bbe-173">Viene valutata la proprietà <xref:System.DateTime.DayOfWeek?displayProperty=nameWithType> del giorno corrente con i membri dell'enumerazione <xref:System.DayOfWeek>.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-173">It evaluates the <xref:System.DateTime.DayOfWeek?displayProperty=nameWithType> property of the current day against the members of the <xref:System.DayOfWeek> enumeration.</span></span> 

[!code-csharp[switch#7](../../../../samples/snippets/csharp/language-reference/keywords/switch/const-pattern.cs#1)]

<span data-ttu-id="d4bbe-174">L'esempio seguente usa il modello costante per gestire l'input dell'utente in un'applicazione console che simula una macchina per il caffè automatica.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-174">The following example uses the constant pattern to handle user input in a console application that simulates an automatic coffee machine.</span></span>
  
 [!code-csharp[switch#6](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch6.cs)]  

### <a name="type-pattern"></a><span data-ttu-id="d4bbe-175">Criterio del tipo</span><span class="sxs-lookup"><span data-stu-id="d4bbe-175">Type pattern</span></span>

<span data-ttu-id="d4bbe-176">Il criterio del tipo consente la conversione e valutazione concise del tipo.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-176">The type pattern enables concise type evaluation and conversion.</span></span> <span data-ttu-id="d4bbe-177">Quando si usa con l'espressione `switch` per eseguire i criteri di ricerca, verifica se un'espressione può essere convertita in un tipo specificato e, in tal caso, esegue il cast a una variabile di quel tipo.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-177">When used with the `switch` statement to perform pattern matching, it tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span> <span data-ttu-id="d4bbe-178">La sintassi è la seguente:</span><span class="sxs-lookup"><span data-stu-id="d4bbe-178">Its syntax is:</span></span>

```csharp
   case type varname 
```
<span data-ttu-id="d4bbe-179">dove *type* è il nome del tipo in cui il risultato di *expr* deve essere convertito e *varname* è l'oggetto in cui il risultato di *expr*deve essere convertito se la ricerca ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-179">where *type* is the name of the type to which the result of *expr* is to be converted, and *varname* is the object to which the result of *expr* is converted if the match succeeds.</span></span> 

<span data-ttu-id="d4bbe-180">L'espressione `case` è `true` se una delle condizioni seguenti è true:</span><span class="sxs-lookup"><span data-stu-id="d4bbe-180">The `case` expression is `true` if any of the following is true:</span></span>

- <span data-ttu-id="d4bbe-181">*expr* è un'istanza dello stesso tipo di *type*.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-181">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="d4bbe-182">*expr* è un'istanza di un tipo che deriva da *type*.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-182">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="d4bbe-183">In altre parole, il risultato di *expr* può subire l'upcast a un'istanza di *type*.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-183">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="d4bbe-184">*expr* ha un tipo in fase di compilazione che è una classe di base di *type* e *expr* ha un tipo di runtime che è *type* o è derivato da *type*.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-184">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="d4bbe-185">Il *tipo in fase di compilazione* di una variabile è il tipo della variabile come definito nella relativa dichiarazione del tipo.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-185">The *compile-time type* of a variable is the variable's type as defined in its type declaration.</span></span> <span data-ttu-id="d4bbe-186">Il *tipo di runtime* di una variabile è il tipo dell'istanza che viene assegnato alla variabile.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-186">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="d4bbe-187">*expr* è un'istanza di un tipo che implementa l'interfaccia *type*.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-187">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="d4bbe-188">Se l'espressione del case è true, *varname* viene assegnata in modo definitivo e ha l'ambito locale esclusivamente all'interno della sezione opzioni.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-188">If the case expression is true, *varname* is definitely assigned and has local scope within the switch section only.</span></span>

<span data-ttu-id="d4bbe-189">Si noti che `null` non corrisponde a un tipo.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-189">Note that `null` does not match a type.</span></span> <span data-ttu-id="d4bbe-190">Per associare un `null`, usare l'etichetta `case` seguente:</span><span class="sxs-lookup"><span data-stu-id="d4bbe-190">To match a `null`, you use the following `case` label:</span></span>

```csharp
case null:
```
 
<span data-ttu-id="d4bbe-191">Nell'esempio seguente viene usato il criterio del tipo per fornire informazioni sui vari generi di tipi di raccolta.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-191">The following example uses the type pattern to provide information about various kinds of collection types.</span></span>

[!code-csharp[switch#5](../../../../samples/snippets/csharp/language-reference/keywords/switch/type-pattern.cs#1)]

<span data-ttu-id="d4bbe-192">Senza criteri di ricerca, questo codice potrebbe essere scritto come segue.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-192">Without pattern matching, this code might be written as follows.</span></span> <span data-ttu-id="d4bbe-193">L'uso di criteri di ricerca del tipo produce codice più compatto e leggibile eliminando la necessità di verificare se il risultato di una conversione è un `null` o eseguire cast ripetuti.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-193">The use of type pattern matching produces more compact, readable code by eliminating the need to test whether the result of a conversion is a `null` or to perform repeated casts.</span></span>  

[!code-csharp[switch#6](../../../../samples/snippets/csharp/language-reference/keywords/switch/type-pattern2.cs#1)]

## <a name="the-case-statement-and-the-when-clause"></a><span data-ttu-id="d4bbe-194">L'istruzione `case` e la clausola `when`</span><span class="sxs-lookup"><span data-stu-id="d4bbe-194">The `case` statement and the `when` clause</span></span>

<span data-ttu-id="d4bbe-195">A partire da C# 7, poiché le istruzioni case devono escludersi a vicenda, è possibile aggiungere una clausola `when` per specificare una condizione aggiuntiva che deve essere soddisfatta perché l'istruzione case restituisca true.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-195">Starting with C# 7, because case statements need not be mutually exclusive, you can use add a `when` clause to specify an additional condition that must be satisfied for the case statement to evaluate to true.</span></span> <span data-ttu-id="d4bbe-196">La clausola `when` può essere qualsiasi espressione che restituisce un valore booleano.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-196">The `when` clause can be any expression that returns a Boolean value.</span></span> <span data-ttu-id="d4bbe-197">Comunemente, la clausola `when` viene usata per impedire l'esecuzione di una sezione opzioni quando il valore di un'espressione di ricerca è `null`.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-197">One of the more common uses for the `when` clause is used to prevent a switch section from executing when the value of a match expression is `null`.</span></span> 

 <span data-ttu-id="d4bbe-198">Nell'esempio seguente viene definita una classe `Shape` di base, una classe `Rectangle` che deriva da `Shape` e una classe `Square` che deriva da `Rectangle`.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-198">The following example defines a base `Shape` class, a `Rectangle` class that derives from `Shape`, and a `Square` class that derives from `Rectangle`.</span></span> <span data-ttu-id="d4bbe-199">L'esempio usa una clausola `when` per assicurarsi che `ShowShapeInfo` consideri un oggetto `Rectangle` a cui è stata assegnata pari lunghezza e larghezza di un `Square`, anche nel caso in cui non sia stata creata un'istanza come oggetto `Square`.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-199">It uses the `when` clause to ensure that the `ShowShapeInfo` treats a `Rectangle` object that has been assigned equal lengths and widths as a `Square` even if is has not been instantiated as a `Square` object.</span></span> <span data-ttu-id="d4bbe-200">Il metodo non tenta di visualizzare informazioni su un oggetto `null` o su una forma la cui l'area è pari a zero.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-200">The method does not attempt to display information either about an object that is `null` or a shape whose area is zero.</span></span> 

[!code-csharp[switch#8](../../../../samples/snippets/csharp/language-reference/keywords/switch/when-clause.cs#1)]
  
<span data-ttu-id="d4bbe-201">Si noti che non viene eseguita la clausola `when` nell'esempio che tenta di verificare se un oggetto `Shape` è `null`.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-201">Note that the `when` clause in the example that attempts to test whether a `Shape` object is `null` does not execute.</span></span> <span data-ttu-id="d4bbe-202">Il criterio del tipo corretto da verificare per un `null` è `case null:`.</span><span class="sxs-lookup"><span data-stu-id="d4bbe-202">The correct type pattern to test for a `null` is `case null:`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="d4bbe-203">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="d4bbe-203">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](../../../../includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d4bbe-204">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4bbe-204">See Also</span></span>  

 [<span data-ttu-id="d4bbe-205">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="d4bbe-205">C# Reference</span></span>](../index.md)  
 [<span data-ttu-id="d4bbe-206">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="d4bbe-206">C# Programming Guide</span></span>](../../programming-guide/index.md)  
 [<span data-ttu-id="d4bbe-207">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="d4bbe-207">C# Keywords</span></span>](index.md)  
 [<span data-ttu-id="d4bbe-208">if-else</span><span class="sxs-lookup"><span data-stu-id="d4bbe-208">if-else</span></span>](if-else.md)  
 [<span data-ttu-id="d4bbe-209">Criteri di ricerca</span><span class="sxs-lookup"><span data-stu-id="d4bbe-209">Pattern Matching</span></span>](../../pattern-matching.md)  
 

 
