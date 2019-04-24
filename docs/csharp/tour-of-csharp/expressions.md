---
title: Espressioni C# - Panoramica del linguaggio C#
description: Le espressioni, gli operandi e gli operatori sono blocchi predefiniti del linguaggio C#
ms.date: 11/06/2016
ms.assetid: 20d5eb10-7381-47b9-ad90-f1cc895aa27e
ms.openlocfilehash: 4ffe947a4cb8c36a5925a4b3846486e44a9d8ec4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59480755"
---
# <a name="expressions"></a><span data-ttu-id="cfe77-103">Espressioni</span><span class="sxs-lookup"><span data-stu-id="cfe77-103">Expressions</span></span>

<span data-ttu-id="cfe77-104">Le *espressioni* sono costituite da *operandi* e *operatori*.</span><span class="sxs-lookup"><span data-stu-id="cfe77-104">*Expressions* are constructed from *operands* and *operators*.</span></span> <span data-ttu-id="cfe77-105">Gli operatori di un'espressione indicano le operazioni che devono essere eseguite sugli operandi.</span><span class="sxs-lookup"><span data-stu-id="cfe77-105">The operators of an expression indicate which operations to apply to the operands.</span></span> <span data-ttu-id="cfe77-106">Alcuni esempi di operatori sono `+`, `-`, `*`, `/` e `new`,</span><span class="sxs-lookup"><span data-stu-id="cfe77-106">Examples of operators include `+`, `-`, `*`, `/`, and `new`.</span></span> <span data-ttu-id="cfe77-107">mentre i valori effettivi, i campi, le variabili locali e le espressioni sono esempi di operandi.</span><span class="sxs-lookup"><span data-stu-id="cfe77-107">Examples of operands include literals, fields, local variables, and expressions.</span></span>

<span data-ttu-id="cfe77-108">Se un'espressione contiene più operatori, la *precedenza* degli operatori determina l'ordine in cui vengono valutati i singoli operatori.</span><span class="sxs-lookup"><span data-stu-id="cfe77-108">When an expression contains multiple operators, the *precedence* of the operators controls the order in which the individual operators are evaluated.</span></span> <span data-ttu-id="cfe77-109">L'espressione `x + y * z`, ad esempio, viene valutata come `x + (y * z)` poiché l'operatore `*` ha la precedenza sull'operatore `+`.</span><span class="sxs-lookup"><span data-stu-id="cfe77-109">For example, the expression `x + y * z` is evaluated as `x + (y * z)` because the `*` operator has higher precedence than the `+` operator.</span></span>

<span data-ttu-id="cfe77-110">Quando un operando si trova tra due operatori con la stessa precedenza, l'ordine di esecuzione delle operazioni viene determinato dall'*associatività* degli operatori:</span><span class="sxs-lookup"><span data-stu-id="cfe77-110">When an operand occurs between two operators with the same precedence, the *associativity* of the operators controls the order in which the operations are performed:</span></span>

* <span data-ttu-id="cfe77-111">Ad eccezione degli operatori di assegnazione, tutti gli operatori binari *prevedono l'associazione all'operando a sinistra*. In altri termini, le operazioni vengono eseguite da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="cfe77-111">Except for the assignment operators, all binary operators are *left-associative*, meaning that operations are performed from left to right.</span></span> <span data-ttu-id="cfe77-112">L'espressione `x + y + z` viene ad esempio valutata come `(x + y) + z`.</span><span class="sxs-lookup"><span data-stu-id="cfe77-112">For example, `x + y + z` is evaluated as `(x + y) + z`.</span></span>
* <span data-ttu-id="cfe77-113">Gli operatori di assegnazione e gli operatori condizionali (`?:`) *prevedono l'associazione all'operando a destra*. In altri termini, le operazioni vengono eseguite da destra a sinistra.</span><span class="sxs-lookup"><span data-stu-id="cfe77-113">The assignment operators and the conditional operator (`?:`) are *right-associative*, meaning that operations are performed from right to left.</span></span> <span data-ttu-id="cfe77-114">L'espressione `x = y = z` viene ad esempio valutata come `x = (y = z)`.</span><span class="sxs-lookup"><span data-stu-id="cfe77-114">For example, `x = y = z` is evaluated as `x = (y = z)`.</span></span>

<span data-ttu-id="cfe77-115">È possibile controllare la precedenza e l'associatività usando le parentesi.</span><span class="sxs-lookup"><span data-stu-id="cfe77-115">Precedence and associativity can be controlled using parentheses.</span></span> <span data-ttu-id="cfe77-116">Ad esempio, `x + y * z` prima moltiplica `y` per `z` e quindi somma il risultato a `x`, ma `(x + y) * z` prima somma `x` e `y` e quindi moltiplica il risultato per `z`.</span><span class="sxs-lookup"><span data-stu-id="cfe77-116">For example, `x + y * z` first multiplies `y` by `z` and then adds the result to `x`, but `(x + y) * z` first adds `x` and `y` and then multiplies the result by `z`.</span></span>

<span data-ttu-id="cfe77-117">La maggior parte degli operatori può essere*in overload*.</span><span class="sxs-lookup"><span data-stu-id="cfe77-117">Most operators can be *overloaded*.</span></span> <span data-ttu-id="cfe77-118">L'overload degli operatori consente di specificare implementazioni di operatori definite dall'utente per le operazioni in cui uno o entrambi gli operandi appartengono a un tipo struct o a una classe definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="cfe77-118">Operator overloading permits user-defined operator implementations to be specified for operations where one or both of the operands are of a user-defined class or struct type.</span></span>

<span data-ttu-id="cfe77-119">Di seguito sono riepilogati gli operatori di C# e sono elencate le categorie di operatori in ordine di precedenza, a partire da quella più alta.</span><span class="sxs-lookup"><span data-stu-id="cfe77-119">The following summarizes C#’s operators, listing the operator categories in order of precedence from highest to lowest.</span></span> <span data-ttu-id="cfe77-120">Gli operatori della stessa categoria hanno uguale precedenza.</span><span class="sxs-lookup"><span data-stu-id="cfe77-120">Operators in the same category have equal precedence.</span></span> <span data-ttu-id="cfe77-121">Sotto ciascuna categoria è riportato il relativo elenco di espressioni e la descrizione di ogni tipo di espressione.</span><span class="sxs-lookup"><span data-stu-id="cfe77-121">Under each category is a list of expressions in that category along with the description of that expression type.</span></span>

* <span data-ttu-id="cfe77-122">Primario</span><span class="sxs-lookup"><span data-stu-id="cfe77-122">Primary</span></span>
  - <span data-ttu-id="cfe77-123">`x.m`: Accesso ai membri</span><span class="sxs-lookup"><span data-stu-id="cfe77-123">`x.m`: Member access</span></span>
  - <span data-ttu-id="cfe77-124">`x(...)`: Chiamata a metodi e delegati</span><span class="sxs-lookup"><span data-stu-id="cfe77-124">`x(...)`: Method and delegate invocation</span></span>
  - <span data-ttu-id="cfe77-125">`x[...]`: Accesso a matrici e indicizzatori</span><span class="sxs-lookup"><span data-stu-id="cfe77-125">`x[...]`: Array and indexer access</span></span>
  - <span data-ttu-id="cfe77-126">`x++`: Post-incremento</span><span class="sxs-lookup"><span data-stu-id="cfe77-126">`x++`: Post-increment</span></span>
  - <span data-ttu-id="cfe77-127">`x--`: Post-decremento</span><span class="sxs-lookup"><span data-stu-id="cfe77-127">`x--`: Post-decrement</span></span>
  - <span data-ttu-id="cfe77-128">`new T(...)`: Creazione di oggetti e delegati</span><span class="sxs-lookup"><span data-stu-id="cfe77-128">`new T(...)`: Object and delegate creation</span></span>
  - <span data-ttu-id="cfe77-129">`new T(...){...}`: creazione di oggetti con inizializzatore</span><span class="sxs-lookup"><span data-stu-id="cfe77-129">`new T(...){...}`: Object creation with initializer</span></span>
  - <span data-ttu-id="cfe77-130">`new {...}`:  inizializzatore di oggetti anonimo</span><span class="sxs-lookup"><span data-stu-id="cfe77-130">`new {...}`:  Anonymous object initializer</span></span>
  - <span data-ttu-id="cfe77-131">`new T[...]`: creazione di matrici</span><span class="sxs-lookup"><span data-stu-id="cfe77-131">`new T[...]`: Array creation</span></span>
  - <span data-ttu-id="cfe77-132">`typeof(T)`: ottiene l'oggetto <xref:System.Type> per `T`</span><span class="sxs-lookup"><span data-stu-id="cfe77-132">`typeof(T)`: Obtain <xref:System.Type> object for `T`</span></span>
  - <span data-ttu-id="cfe77-133">`checked(x)`: Valutare l'espressione in un contesto controllato (checked)</span><span class="sxs-lookup"><span data-stu-id="cfe77-133">`checked(x)`: Evaluate expression in checked context</span></span>
  - <span data-ttu-id="cfe77-134">`unchecked(x)`: Valutare l'espressione in un contesto non controllato (unchecked)</span><span class="sxs-lookup"><span data-stu-id="cfe77-134">`unchecked(x)`: Evaluate expression in unchecked context</span></span>
  - <span data-ttu-id="cfe77-135">`default(T)`: ottiene un valore predefinito di tipo `T`</span><span class="sxs-lookup"><span data-stu-id="cfe77-135">`default(T)`: Obtain default value of type `T`</span></span>
  - <span data-ttu-id="cfe77-136">`delegate {...}`: Funzione anonima (metodo anonimo)</span><span class="sxs-lookup"><span data-stu-id="cfe77-136">`delegate {...}`: Anonymous function (anonymous method)</span></span>
* <span data-ttu-id="cfe77-137">Unario</span><span class="sxs-lookup"><span data-stu-id="cfe77-137">Unary</span></span>
  - <span data-ttu-id="cfe77-138">`+x`: identità</span><span class="sxs-lookup"><span data-stu-id="cfe77-138">`+x`: Identity</span></span>
  - <span data-ttu-id="cfe77-139">`-x`: Negazione</span><span class="sxs-lookup"><span data-stu-id="cfe77-139">`-x`: Negation</span></span>
  - <span data-ttu-id="cfe77-140">`!x`: Negazione logica</span><span class="sxs-lookup"><span data-stu-id="cfe77-140">`!x`: Logical negation</span></span>
  - <span data-ttu-id="cfe77-141">`~x`: Negazione bit per bit</span><span class="sxs-lookup"><span data-stu-id="cfe77-141">`~x`: Bitwise negation</span></span>
  - <span data-ttu-id="cfe77-142">`++x`: Pre-incremento</span><span class="sxs-lookup"><span data-stu-id="cfe77-142">`++x`: Pre-increment</span></span>
  - <span data-ttu-id="cfe77-143">`--x`: Pre-decremento</span><span class="sxs-lookup"><span data-stu-id="cfe77-143">`--x`: Pre-decrement</span></span>
  - <span data-ttu-id="cfe77-144">`(T)x`: converte in modo esplicito `x` al tipo `T`</span><span class="sxs-lookup"><span data-stu-id="cfe77-144">`(T)x`: Explicitly convert `x` to type `T`</span></span>
  - <span data-ttu-id="cfe77-145">`await x`: attende in modo asincrono il completamento di `x`</span><span class="sxs-lookup"><span data-stu-id="cfe77-145">`await x`: Asynchronously wait for `x` to complete</span></span>
* <span data-ttu-id="cfe77-146">Moltiplicazione</span><span class="sxs-lookup"><span data-stu-id="cfe77-146">Multiplicative</span></span>
  - <span data-ttu-id="cfe77-147">`x * y`: Moltiplicazione</span><span class="sxs-lookup"><span data-stu-id="cfe77-147">`x * y`: Multiplication</span></span>
  - <span data-ttu-id="cfe77-148">`x / y`: Divisione</span><span class="sxs-lookup"><span data-stu-id="cfe77-148">`x / y`: Division</span></span>
  - <span data-ttu-id="cfe77-149">`x % y`: Resto</span><span class="sxs-lookup"><span data-stu-id="cfe77-149">`x % y`: Remainder</span></span>
* <span data-ttu-id="cfe77-150">Addizione</span><span class="sxs-lookup"><span data-stu-id="cfe77-150">Additive</span></span>
  - <span data-ttu-id="cfe77-151">`x + y`: Addizione, concatenazione di stringhe, combinazione di delegati</span><span class="sxs-lookup"><span data-stu-id="cfe77-151">`x + y`: Addition, string concatenation, delegate combination</span></span>
  - <span data-ttu-id="cfe77-152">`x – y`: Sottrazione, rimozione di delegati</span><span class="sxs-lookup"><span data-stu-id="cfe77-152">`x – y`: Subtraction, delegate removal</span></span>
* <span data-ttu-id="cfe77-153">Shift</span><span class="sxs-lookup"><span data-stu-id="cfe77-153">Shift</span></span>
  - <span data-ttu-id="cfe77-154">`x << y`: Spostamento a sinistra</span><span class="sxs-lookup"><span data-stu-id="cfe77-154">`x << y`: Shift left</span></span>
  - <span data-ttu-id="cfe77-155">`x >> y`: Spostamento a destra</span><span class="sxs-lookup"><span data-stu-id="cfe77-155">`x >> y`: Shift right</span></span>
* <span data-ttu-id="cfe77-156">Operatori relazionali e operatori di test del tipo</span><span class="sxs-lookup"><span data-stu-id="cfe77-156">Relational and type testing</span></span>
  - <span data-ttu-id="cfe77-157">`x < y`: Minore di</span><span class="sxs-lookup"><span data-stu-id="cfe77-157">`x < y`: Less than</span></span>
  - <span data-ttu-id="cfe77-158">`x > y`: Maggiore di</span><span class="sxs-lookup"><span data-stu-id="cfe77-158">`x > y`: Greater than</span></span>
  - <span data-ttu-id="cfe77-159">`x <= y`: Minore o uguale</span><span class="sxs-lookup"><span data-stu-id="cfe77-159">`x <= y`: Less than or equal</span></span>
  - <span data-ttu-id="cfe77-160">`x >= y`: Maggiore o uguale a</span><span class="sxs-lookup"><span data-stu-id="cfe77-160">`x >= y`: Greater than or equal</span></span>
  - <span data-ttu-id="cfe77-161">`x is T`: restituisce `true` se `x` è un oggetto `T`, altrimenti `false`</span><span class="sxs-lookup"><span data-stu-id="cfe77-161">`x is T`: Return `true` if `x` is a `T`, `false` otherwise</span></span>
  - <span data-ttu-id="cfe77-162">`x as T`: restituisce `x` tipizzato come `T` oppure `null` se `x` non è un oggetto `T`</span><span class="sxs-lookup"><span data-stu-id="cfe77-162">`x as T`: Return `x` typed as `T`, or `null` if `x` is not a `T`</span></span>
* <span data-ttu-id="cfe77-163">Uguaglianza</span><span class="sxs-lookup"><span data-stu-id="cfe77-163">Equality</span></span>
  - <span data-ttu-id="cfe77-164">`x == y`: Uguale</span><span class="sxs-lookup"><span data-stu-id="cfe77-164">`x == y`: Equal</span></span>
  - <span data-ttu-id="cfe77-165">`x != y`: Diverso</span><span class="sxs-lookup"><span data-stu-id="cfe77-165">`x != y`: Not equal</span></span>
* <span data-ttu-id="cfe77-166">AND logico</span><span class="sxs-lookup"><span data-stu-id="cfe77-166">Logical AND</span></span>
  - <span data-ttu-id="cfe77-167">`x & y`: AND Integer bit per bit, AND logico booleano</span><span class="sxs-lookup"><span data-stu-id="cfe77-167">`x & y`: Integer bitwise AND, boolean logical AND</span></span>
* <span data-ttu-id="cfe77-168">XOR logico</span><span class="sxs-lookup"><span data-stu-id="cfe77-168">Logical XOR</span></span>
  - <span data-ttu-id="cfe77-169">`x ^ y`: XOR Integer bit per bit, XOR logico booleano</span><span class="sxs-lookup"><span data-stu-id="cfe77-169">`x ^ y`: Integer bitwise XOR, boolean logical XOR</span></span>
* <span data-ttu-id="cfe77-170">OR logico</span><span class="sxs-lookup"><span data-stu-id="cfe77-170">Logical OR</span></span>
  - <span data-ttu-id="cfe77-171">`x | y`: OR Integer bit per bit, OR logico booleano</span><span class="sxs-lookup"><span data-stu-id="cfe77-171">`x | y`: Integer bitwise OR, boolean logical OR</span></span>
* <span data-ttu-id="cfe77-172">AND condizionale</span><span class="sxs-lookup"><span data-stu-id="cfe77-172">Conditional AND</span></span>
  - <span data-ttu-id="cfe77-173">`x && y`: restituisce `y` solo se `x` non è `false`</span><span class="sxs-lookup"><span data-stu-id="cfe77-173">`x && y`: Evaluates `y` only if `x` is not `false`</span></span>
* <span data-ttu-id="cfe77-174">OR condizionale</span><span class="sxs-lookup"><span data-stu-id="cfe77-174">Conditional OR</span></span>
  - <span data-ttu-id="cfe77-175">`x || y`: restituisce `y` solo se `x` non è `true`</span><span class="sxs-lookup"><span data-stu-id="cfe77-175">`x || y`: Evaluates `y` only if `x` is not `true`</span></span>
* <span data-ttu-id="cfe77-176">Null-coalescing</span><span class="sxs-lookup"><span data-stu-id="cfe77-176">Null coalescing</span></span>
  - <span data-ttu-id="cfe77-177">`x ?? y`: Restituisce `y` se `x` è null, altrimenti `x`</span><span class="sxs-lookup"><span data-stu-id="cfe77-177">`x ?? y`: Evaluates to `y` if `x` is null, to `x` otherwise</span></span>
* <span data-ttu-id="cfe77-178">Condizionale</span><span class="sxs-lookup"><span data-stu-id="cfe77-178">Conditional</span></span>
  - <span data-ttu-id="cfe77-179">`x ? y : z`: restituisce `y` se `x` è `true`, `z` se `x` è `false`</span><span class="sxs-lookup"><span data-stu-id="cfe77-179">`x ? y : z`: Evaluates `y` if `x` is `true`, `z` if `x` is `false`</span></span>
* <span data-ttu-id="cfe77-180">Assegnazione o funzione anonima</span><span class="sxs-lookup"><span data-stu-id="cfe77-180">Assignment or anonymous function</span></span>
  - <span data-ttu-id="cfe77-181">`x = y`: Assegnazione</span><span class="sxs-lookup"><span data-stu-id="cfe77-181">`x = y`: Assignment</span></span>
  - <span data-ttu-id="cfe77-182">`x op= y`: assegnazione composta. Gli operatori supportati sono</span><span class="sxs-lookup"><span data-stu-id="cfe77-182">`x op= y`: Compound assignment; supported operators are</span></span>
    - <span data-ttu-id="cfe77-183">`*=`   `/=`   `%=`   `+=`   `-=`   `<<=`   `>>=`   `&=`  `^=`  `|=`</span><span class="sxs-lookup"><span data-stu-id="cfe77-183">`*=`   `/=`   `%=`   `+=`   `-=`   `<<=`   `>>=`   `&=`  `^=`  `|=`</span></span>
  - <span data-ttu-id="cfe77-184">`(T x) => y`: Funzione anonima (espressione lambda)</span><span class="sxs-lookup"><span data-stu-id="cfe77-184">`(T x) => y`: Anonymous function (lambda expression)</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="cfe77-185">[Precedente](types-and-variables.md)
> [Successivo](statements.md)</span><span class="sxs-lookup"><span data-stu-id="cfe77-185">[Previous](types-and-variables.md)
[Next](statements.md)</span></span>
