---
title: Espressioni C# - Panoramica del linguaggio C#
description: Le espressioni, gli operandi e gli operatori sono blocchi predefiniti del linguaggio C#
ms.date: 11/06/2016
ms.assetid: 20d5eb10-7381-47b9-ad90-f1cc895aa27e
ms.openlocfilehash: 4ffe947a4cb8c36a5925a4b3846486e44a9d8ec4
ms.sourcegitcommit: 859b2ba0c74a1a5a4ad0d59a3c3af23450995981
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/11/2019
ms.locfileid: "59480755"
---
# <a name="expressions"></a><span data-ttu-id="65f2e-103">Espressioni</span><span class="sxs-lookup"><span data-stu-id="65f2e-103">Expressions</span></span>

<span data-ttu-id="65f2e-104">Le *espressioni* sono costituite da *operandi* e *operatori*.</span><span class="sxs-lookup"><span data-stu-id="65f2e-104">*Expressions* are constructed from *operands* and *operators*.</span></span> <span data-ttu-id="65f2e-105">Gli operatori di un'espressione indicano le operazioni che devono essere eseguite sugli operandi.</span><span class="sxs-lookup"><span data-stu-id="65f2e-105">The operators of an expression indicate which operations to apply to the operands.</span></span> <span data-ttu-id="65f2e-106">Alcuni esempi di operatori sono `+`, `-`, `*`, `/` e `new`,</span><span class="sxs-lookup"><span data-stu-id="65f2e-106">Examples of operators include `+`, `-`, `*`, `/`, and `new`.</span></span> <span data-ttu-id="65f2e-107">mentre i valori effettivi, i campi, le variabili locali e le espressioni sono esempi di operandi.</span><span class="sxs-lookup"><span data-stu-id="65f2e-107">Examples of operands include literals, fields, local variables, and expressions.</span></span>

<span data-ttu-id="65f2e-108">Se un'espressione contiene più operatori, la *precedenza* degli operatori determina l'ordine in cui vengono valutati i singoli operatori.</span><span class="sxs-lookup"><span data-stu-id="65f2e-108">When an expression contains multiple operators, the *precedence* of the operators controls the order in which the individual operators are evaluated.</span></span> <span data-ttu-id="65f2e-109">L'espressione `x + y * z`, ad esempio, viene valutata come `x + (y * z)` poiché l'operatore `*` ha la precedenza sull'operatore `+`.</span><span class="sxs-lookup"><span data-stu-id="65f2e-109">For example, the expression `x + y * z` is evaluated as `x + (y * z)` because the `*` operator has higher precedence than the `+` operator.</span></span>

<span data-ttu-id="65f2e-110">Quando un operando si trova tra due operatori con la stessa precedenza, l'ordine di esecuzione delle operazioni viene determinato dall'*associatività* degli operatori:</span><span class="sxs-lookup"><span data-stu-id="65f2e-110">When an operand occurs between two operators with the same precedence, the *associativity* of the operators controls the order in which the operations are performed:</span></span>

* <span data-ttu-id="65f2e-111">Ad eccezione degli operatori di assegnazione, tutti gli operatori binari *prevedono l'associazione all'operando a sinistra*. In altri termini, le operazioni vengono eseguite da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="65f2e-111">Except for the assignment operators, all binary operators are *left-associative*, meaning that operations are performed from left to right.</span></span> <span data-ttu-id="65f2e-112">L'espressione `x + y + z` viene ad esempio valutata come `(x + y) + z`.</span><span class="sxs-lookup"><span data-stu-id="65f2e-112">For example, `x + y + z` is evaluated as `(x + y) + z`.</span></span>
* <span data-ttu-id="65f2e-113">Gli operatori di assegnazione e gli operatori condizionali (`?:`) *prevedono l'associazione all'operando a destra*. In altri termini, le operazioni vengono eseguite da destra a sinistra.</span><span class="sxs-lookup"><span data-stu-id="65f2e-113">The assignment operators and the conditional operator (`?:`) are *right-associative*, meaning that operations are performed from right to left.</span></span> <span data-ttu-id="65f2e-114">L'espressione `x = y = z` viene ad esempio valutata come `x = (y = z)`.</span><span class="sxs-lookup"><span data-stu-id="65f2e-114">For example, `x = y = z` is evaluated as `x = (y = z)`.</span></span>

<span data-ttu-id="65f2e-115">È possibile controllare la precedenza e l'associatività usando le parentesi.</span><span class="sxs-lookup"><span data-stu-id="65f2e-115">Precedence and associativity can be controlled using parentheses.</span></span> <span data-ttu-id="65f2e-116">Ad esempio, `x + y * z` prima moltiplica `y` per `z` e quindi somma il risultato a `x`, ma `(x + y) * z` prima somma `x` e `y` e quindi moltiplica il risultato per `z`.</span><span class="sxs-lookup"><span data-stu-id="65f2e-116">For example, `x + y * z` first multiplies `y` by `z` and then adds the result to `x`, but `(x + y) * z` first adds `x` and `y` and then multiplies the result by `z`.</span></span>

<span data-ttu-id="65f2e-117">La maggior parte degli operatori può essere*in overload*.</span><span class="sxs-lookup"><span data-stu-id="65f2e-117">Most operators can be *overloaded*.</span></span> <span data-ttu-id="65f2e-118">L'overload degli operatori consente di specificare implementazioni di operatori definite dall'utente per le operazioni in cui uno o entrambi gli operandi appartengono a un tipo struct o a una classe definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="65f2e-118">Operator overloading permits user-defined operator implementations to be specified for operations where one or both of the operands are of a user-defined class or struct type.</span></span>

<span data-ttu-id="65f2e-119">Di seguito sono riepilogati gli operatori di C# e sono elencate le categorie di operatori in ordine di precedenza, a partire da quella più alta.</span><span class="sxs-lookup"><span data-stu-id="65f2e-119">The following summarizes C#’s operators, listing the operator categories in order of precedence from highest to lowest.</span></span> <span data-ttu-id="65f2e-120">Gli operatori della stessa categoria hanno uguale precedenza.</span><span class="sxs-lookup"><span data-stu-id="65f2e-120">Operators in the same category have equal precedence.</span></span> <span data-ttu-id="65f2e-121">Sotto ciascuna categoria è riportato il relativo elenco di espressioni e la descrizione di ogni tipo di espressione.</span><span class="sxs-lookup"><span data-stu-id="65f2e-121">Under each category is a list of expressions in that category along with the description of that expression type.</span></span>

* <span data-ttu-id="65f2e-122">Primario</span><span class="sxs-lookup"><span data-stu-id="65f2e-122">Primary</span></span>
  - `x.m`<span data-ttu-id="65f2e-123">: Accesso ai membri</span><span class="sxs-lookup"><span data-stu-id="65f2e-123">: Member access</span></span>
  - `x(...)`<span data-ttu-id="65f2e-124">: Chiamata a metodi e delegati</span><span class="sxs-lookup"><span data-stu-id="65f2e-124">: Method and delegate invocation</span></span>
  - `x[...]`<span data-ttu-id="65f2e-125">: Accesso a matrici e indicizzatori</span><span class="sxs-lookup"><span data-stu-id="65f2e-125">: Array and indexer access</span></span>
  - `x++`<span data-ttu-id="65f2e-126">: Post-incremento</span><span class="sxs-lookup"><span data-stu-id="65f2e-126">: Post-increment</span></span>
  - `x--`<span data-ttu-id="65f2e-127">: Post-decremento</span><span class="sxs-lookup"><span data-stu-id="65f2e-127">: Post-decrement</span></span>
  - `new T(...)`<span data-ttu-id="65f2e-128">: Creazione di oggetti e delegati</span><span class="sxs-lookup"><span data-stu-id="65f2e-128">: Object and delegate creation</span></span>
  - `new T(...){...}`<span data-ttu-id="65f2e-129">: creazione di oggetti con inizializzatore</span><span class="sxs-lookup"><span data-stu-id="65f2e-129">: Object creation with initializer</span></span>
  - `new {...}`<span data-ttu-id="65f2e-130">:  inizializzatore di oggetti anonimo</span><span class="sxs-lookup"><span data-stu-id="65f2e-130">:  Anonymous object initializer</span></span>
  - `new T[...]`<span data-ttu-id="65f2e-131">: creazione di matrici</span><span class="sxs-lookup"><span data-stu-id="65f2e-131">: Array creation</span></span>
  - `typeof(T)`<span data-ttu-id="65f2e-132">: ottiene l'oggetto <xref:System.Type> per</span><span class="sxs-lookup"><span data-stu-id="65f2e-132">: Obtain <xref:System.Type> object for</span></span> `T`
  - `checked(x)`<span data-ttu-id="65f2e-133">: Valutare l'espressione in un contesto controllato (checked)</span><span class="sxs-lookup"><span data-stu-id="65f2e-133">: Evaluate expression in checked context</span></span>
  - `unchecked(x)`<span data-ttu-id="65f2e-134">: Valutare l'espressione in un contesto non controllato (unchecked)</span><span class="sxs-lookup"><span data-stu-id="65f2e-134">: Evaluate expression in unchecked context</span></span>
  - `default(T)`<span data-ttu-id="65f2e-135">: ottiene un valore predefinito di tipo</span><span class="sxs-lookup"><span data-stu-id="65f2e-135">: Obtain default value of type</span></span> `T`
  - `delegate {...}`<span data-ttu-id="65f2e-136">: Funzione anonima (metodo anonimo)</span><span class="sxs-lookup"><span data-stu-id="65f2e-136">: Anonymous function (anonymous method)</span></span>
* <span data-ttu-id="65f2e-137">Unario</span><span class="sxs-lookup"><span data-stu-id="65f2e-137">Unary</span></span>
  - `+x`<span data-ttu-id="65f2e-138">: identità</span><span class="sxs-lookup"><span data-stu-id="65f2e-138">: Identity</span></span>
  - `-x`<span data-ttu-id="65f2e-139">: Negazione</span><span class="sxs-lookup"><span data-stu-id="65f2e-139">: Negation</span></span>
  - `!x`<span data-ttu-id="65f2e-140">: Negazione logica</span><span class="sxs-lookup"><span data-stu-id="65f2e-140">: Logical negation</span></span>
  - `~x`<span data-ttu-id="65f2e-141">: Negazione bit per bit</span><span class="sxs-lookup"><span data-stu-id="65f2e-141">: Bitwise negation</span></span>
  - `++x`<span data-ttu-id="65f2e-142">: Pre-incremento</span><span class="sxs-lookup"><span data-stu-id="65f2e-142">: Pre-increment</span></span>
  - `--x`<span data-ttu-id="65f2e-143">: Pre-decremento</span><span class="sxs-lookup"><span data-stu-id="65f2e-143">: Pre-decrement</span></span>
  - `(T)x`<span data-ttu-id="65f2e-144">: converte in modo esplicito `x` al tipo</span><span class="sxs-lookup"><span data-stu-id="65f2e-144">: Explicitly convert `x` to type</span></span> `T`
  - `await x`<span data-ttu-id="65f2e-145">: attende in modo asincrono il completamento di `x`</span><span class="sxs-lookup"><span data-stu-id="65f2e-145">: Asynchronously wait for `x` to complete</span></span>
* <span data-ttu-id="65f2e-146">Moltiplicazione</span><span class="sxs-lookup"><span data-stu-id="65f2e-146">Multiplicative</span></span>
  - `x * y`<span data-ttu-id="65f2e-147">: Moltiplicazione</span><span class="sxs-lookup"><span data-stu-id="65f2e-147">: Multiplication</span></span>
  - `x / y`<span data-ttu-id="65f2e-148">: Divisione</span><span class="sxs-lookup"><span data-stu-id="65f2e-148">: Division</span></span>
  - `x % y`<span data-ttu-id="65f2e-149">: Resto</span><span class="sxs-lookup"><span data-stu-id="65f2e-149">: Remainder</span></span>
* <span data-ttu-id="65f2e-150">Addizione</span><span class="sxs-lookup"><span data-stu-id="65f2e-150">Additive</span></span>
  - `x + y`<span data-ttu-id="65f2e-151">: Addizione, concatenazione di stringhe, combinazione di delegati</span><span class="sxs-lookup"><span data-stu-id="65f2e-151">: Addition, string concatenation, delegate combination</span></span>
  - `x – y`<span data-ttu-id="65f2e-152">: Sottrazione, rimozione di delegati</span><span class="sxs-lookup"><span data-stu-id="65f2e-152">: Subtraction, delegate removal</span></span>
* <span data-ttu-id="65f2e-153">Shift</span><span class="sxs-lookup"><span data-stu-id="65f2e-153">Shift</span></span>
  - `x << y`<span data-ttu-id="65f2e-154">: Spostamento a sinistra</span><span class="sxs-lookup"><span data-stu-id="65f2e-154">: Shift left</span></span>
  - `x >> y`<span data-ttu-id="65f2e-155">: Spostamento a destra</span><span class="sxs-lookup"><span data-stu-id="65f2e-155">: Shift right</span></span>
* <span data-ttu-id="65f2e-156">Operatori relazionali e operatori di test del tipo</span><span class="sxs-lookup"><span data-stu-id="65f2e-156">Relational and type testing</span></span>
  - `x < y`<span data-ttu-id="65f2e-157">: Minore di</span><span class="sxs-lookup"><span data-stu-id="65f2e-157">: Less than</span></span>
  - `x > y`<span data-ttu-id="65f2e-158">: Maggiore di</span><span class="sxs-lookup"><span data-stu-id="65f2e-158">: Greater than</span></span>
  - `x <= y`<span data-ttu-id="65f2e-159">: Minore o uguale</span><span class="sxs-lookup"><span data-stu-id="65f2e-159">: Less than or equal</span></span>
  - `x >= y`<span data-ttu-id="65f2e-160">: Maggiore o uguale a</span><span class="sxs-lookup"><span data-stu-id="65f2e-160">: Greater than or equal</span></span>
  - `x is T`<span data-ttu-id="65f2e-161">: restituisce `true` se `x` è un oggetto `T`, altrimenti `false`</span><span class="sxs-lookup"><span data-stu-id="65f2e-161">: Return `true` if `x` is a `T`, `false` otherwise</span></span>
  - `x as T`<span data-ttu-id="65f2e-162">: restituisce `x` tipizzato come `T` oppure `null` se `x` non è un oggetto</span><span class="sxs-lookup"><span data-stu-id="65f2e-162">: Return `x` typed as `T`, or `null` if `x` is not a</span></span> `T`
* <span data-ttu-id="65f2e-163">Uguaglianza</span><span class="sxs-lookup"><span data-stu-id="65f2e-163">Equality</span></span>
  - `x == y`<span data-ttu-id="65f2e-164">: Uguale</span><span class="sxs-lookup"><span data-stu-id="65f2e-164">: Equal</span></span>
  - `x != y`<span data-ttu-id="65f2e-165">: Diverso</span><span class="sxs-lookup"><span data-stu-id="65f2e-165">: Not equal</span></span>
* <span data-ttu-id="65f2e-166">AND logico</span><span class="sxs-lookup"><span data-stu-id="65f2e-166">Logical AND</span></span>
  - `x & y`<span data-ttu-id="65f2e-167">: AND Integer bit per bit, AND logico booleano</span><span class="sxs-lookup"><span data-stu-id="65f2e-167">: Integer bitwise AND, boolean logical AND</span></span>
* <span data-ttu-id="65f2e-168">XOR logico</span><span class="sxs-lookup"><span data-stu-id="65f2e-168">Logical XOR</span></span>
  - `x ^ y`<span data-ttu-id="65f2e-169">: XOR Integer bit per bit, XOR logico booleano</span><span class="sxs-lookup"><span data-stu-id="65f2e-169">: Integer bitwise XOR, boolean logical XOR</span></span>
* <span data-ttu-id="65f2e-170">OR logico</span><span class="sxs-lookup"><span data-stu-id="65f2e-170">Logical OR</span></span>
  - `x | y`<span data-ttu-id="65f2e-171">: OR Integer bit per bit, OR logico booleano</span><span class="sxs-lookup"><span data-stu-id="65f2e-171">: Integer bitwise OR, boolean logical OR</span></span>
* <span data-ttu-id="65f2e-172">AND condizionale</span><span class="sxs-lookup"><span data-stu-id="65f2e-172">Conditional AND</span></span>
  - `x && y`<span data-ttu-id="65f2e-173">: restituisce `y` solo se `x` non è</span><span class="sxs-lookup"><span data-stu-id="65f2e-173">: Evaluates `y` only if `x` is not</span></span> `false`
* <span data-ttu-id="65f2e-174">OR condizionale</span><span class="sxs-lookup"><span data-stu-id="65f2e-174">Conditional OR</span></span>
  - `x || y`<span data-ttu-id="65f2e-175">: restituisce `y` solo se `x` non è</span><span class="sxs-lookup"><span data-stu-id="65f2e-175">: Evaluates `y` only if `x` is not</span></span> `true`
* <span data-ttu-id="65f2e-176">Null-coalescing</span><span class="sxs-lookup"><span data-stu-id="65f2e-176">Null coalescing</span></span>
  - `x ?? y`<span data-ttu-id="65f2e-177">: Restituisce `y` se `x` è null, altrimenti `x`</span><span class="sxs-lookup"><span data-stu-id="65f2e-177">: Evaluates to `y` if `x` is null, to `x` otherwise</span></span>
* <span data-ttu-id="65f2e-178">Condizionale</span><span class="sxs-lookup"><span data-stu-id="65f2e-178">Conditional</span></span>
  - `x ? y : z`<span data-ttu-id="65f2e-179">: restituisce `y` se `x` è `true`, `z` se `x` è</span><span class="sxs-lookup"><span data-stu-id="65f2e-179">: Evaluates `y` if `x` is `true`, `z` if `x` is</span></span> `false`
* <span data-ttu-id="65f2e-180">Assegnazione o funzione anonima</span><span class="sxs-lookup"><span data-stu-id="65f2e-180">Assignment or anonymous function</span></span>
  - `x = y`<span data-ttu-id="65f2e-181">: Assegnazione</span><span class="sxs-lookup"><span data-stu-id="65f2e-181">: Assignment</span></span>
  - `x op= y`<span data-ttu-id="65f2e-182">: assegnazione composta. Gli operatori supportati sono</span><span class="sxs-lookup"><span data-stu-id="65f2e-182">: Compound assignment; supported operators are</span></span>
    - `*=`   `/=`   `%=`   `+=`   `-=`   `<<=`   `>>=`   `&=`  `^=`  `|=`
  - `(T x) => y`<span data-ttu-id="65f2e-183">: Funzione anonima (espressione lambda)</span><span class="sxs-lookup"><span data-stu-id="65f2e-183">: Anonymous function (lambda expression)</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="65f2e-184">[Precedente](types-and-variables.md)
> [Successivo](statements.md)</span><span class="sxs-lookup"><span data-stu-id="65f2e-184">[Previous](types-and-variables.md)
[Next](statements.md)</span></span>
