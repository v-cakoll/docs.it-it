---
title: Espressioni C# - Panoramica del linguaggio C#
description: Le espressioni, gli operandi e gli operatori sono blocchi predefiniti del linguaggio C#
keywords: .NET, csharp, espressione, operatore, operando
author: BillWagner
ms.author: wiwagn
ms.date: 11/06/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 20d5eb10-7381-47b9-ad90-f1cc895aa27e
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 155804dd212d8eda8d81ce7e296a9fe308e9c69b
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---

# <a name="expressions"></a><span data-ttu-id="cadb0-104">Espressioni</span><span class="sxs-lookup"><span data-stu-id="cadb0-104">Expressions</span></span>

<span data-ttu-id="cadb0-105">Le *espressioni* sono costituite da *operandi* e *operatori*.</span><span class="sxs-lookup"><span data-stu-id="cadb0-105">*Expressions* are constructed from *operands* and *operators*.</span></span> <span data-ttu-id="cadb0-106">Gli operatori di un'espressione indicano le operazioni che devono essere eseguite sugli operandi.</span><span class="sxs-lookup"><span data-stu-id="cadb0-106">The operators of an expression indicate which operations to apply to the operands.</span></span> <span data-ttu-id="cadb0-107">Alcuni esempi di operatori sono `+`, `-`, `*`, `/` e `new`,</span><span class="sxs-lookup"><span data-stu-id="cadb0-107">Examples of operators include `+`, `-`, `*`, `/`, and `new`.</span></span> <span data-ttu-id="cadb0-108">mentre i valori effettivi, i campi, le variabili locali e le espressioni sono esempi di operandi.</span><span class="sxs-lookup"><span data-stu-id="cadb0-108">Examples of operands include literals, fields, local variables, and expressions.</span></span>

<span data-ttu-id="cadb0-109">Se un'espressione contiene più operatori, la *precedenza* degli operatori determina l'ordine in cui vengono valutati i singoli operatori.</span><span class="sxs-lookup"><span data-stu-id="cadb0-109">When an expression contains multiple operators, the *precedence* of the operators controls the order in which the individual operators are evaluated.</span></span> <span data-ttu-id="cadb0-110">L'espressione `x + y * z`, ad esempio, viene valutata come `x + (y * z)` poiché l'operatore `*` ha la precedenza sull'operatore `+`.</span><span class="sxs-lookup"><span data-stu-id="cadb0-110">For example, the expression `x + y * z` is evaluated as `x + (y * z)` because the `*` operator has higher precedence than the `+` operator.</span></span>

<span data-ttu-id="cadb0-111">Quando un operando si trova tra due operatori con la stessa precedenza, l'ordine di esecuzione delle operazioni viene determinato dall'*associatività* degli operatori:</span><span class="sxs-lookup"><span data-stu-id="cadb0-111">When an operand occurs between two operators with the same precedence, the *associativity* of the operators controls the order in which the operations are performed:</span></span>

*   <span data-ttu-id="cadb0-112">Ad eccezione degli operatori di assegnazione, tutti gli operatori binari *prevedono l'associazione all'operando a sinistra*. In altri termini, le operazioni vengono eseguite da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="cadb0-112">Except for the assignment operators, all binary operators are *left-associative*, meaning that operations are performed from left to right.</span></span> <span data-ttu-id="cadb0-113">L'espressione `x + y + z` viene ad esempio valutata come `(x + y) + z`.</span><span class="sxs-lookup"><span data-stu-id="cadb0-113">For example, `x + y + z` is evaluated as `(x + y) + z`.</span></span>
*   <span data-ttu-id="cadb0-114">Gli operatori di assegnazione e gli operatori condizionali (`?:`) *prevedono l'associazione all'operando a destra*. In altri termini, le operazioni vengono eseguite da destra a sinistra.</span><span class="sxs-lookup"><span data-stu-id="cadb0-114">The assignment operators and the conditional operator (`?:`) are *right-associative*, meaning that operations are performed from right to left.</span></span> <span data-ttu-id="cadb0-115">L'espressione `x = y = z` viene ad esempio valutata come `x = (y = z)`.</span><span class="sxs-lookup"><span data-stu-id="cadb0-115">For example, `x = y = z` is evaluated as `x = (y = z)`.</span></span>

<span data-ttu-id="cadb0-116">È possibile controllare la precedenza e l'associatività usando le parentesi.</span><span class="sxs-lookup"><span data-stu-id="cadb0-116">Precedence and associativity can be controlled using parentheses.</span></span> <span data-ttu-id="cadb0-117">Ad esempio, `x + y * z` prima moltiplica `y` per `z` e quindi somma il risultato a `x`, ma `(x + y) * z` prima somma `x` e `y` e quindi moltiplica il risultato per `z`.</span><span class="sxs-lookup"><span data-stu-id="cadb0-117">For example, `x + y * z` first multiplies `y` by `z` and then adds the result to `x`, but `(x + y) * z` first adds `x` and `y` and then multiplies the result by `z`.</span></span>

<span data-ttu-id="cadb0-118">La maggior parte degli operatori può essere*in overload*.</span><span class="sxs-lookup"><span data-stu-id="cadb0-118">Most operators can be *overloaded*.</span></span> <span data-ttu-id="cadb0-119">L'overload degli operatori consente di specificare implementazioni di operatori definite dall'utente per le operazioni in cui uno o entrambi gli operandi appartengono a un tipo struct o a una classe definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="cadb0-119">Operator overloading permits user-defined operator implementations to be specified for operations where one or both of the operands are of a user-defined class or struct type.</span></span>

<span data-ttu-id="cadb0-120">Di seguito sono riepilogati gli operatori di C# e sono elencate le categorie di operatori in ordine di precedenza, a partire da quella più alta.</span><span class="sxs-lookup"><span data-stu-id="cadb0-120">The following summarizes C#’s operators, listing the operator categories in order of precedence from highest to lowest.</span></span> <span data-ttu-id="cadb0-121">Gli operatori della stessa categoria hanno uguale precedenza.</span><span class="sxs-lookup"><span data-stu-id="cadb0-121">Operators in the same category have equal precedence.</span></span> <span data-ttu-id="cadb0-122">Sotto ciascuna categoria è riportato il relativo elenco di espressioni e la descrizione di ogni tipo di espressione.</span><span class="sxs-lookup"><span data-stu-id="cadb0-122">Under each category is a list of expressions in that category along with the description of that expression type.</span></span>

* <span data-ttu-id="cadb0-123">Primario</span><span class="sxs-lookup"><span data-stu-id="cadb0-123">Primary</span></span>
    - <span data-ttu-id="cadb0-124">`x.m`: accesso a membri</span><span class="sxs-lookup"><span data-stu-id="cadb0-124">`x.m`: Member access</span></span>
    - <span data-ttu-id="cadb0-125">`x(...)`: chiamata a metodi e delegati</span><span class="sxs-lookup"><span data-stu-id="cadb0-125">`x(...)`: Method and delegate invocation</span></span>
    - <span data-ttu-id="cadb0-126">`x[...]`: accesso a matrici e indicizzatori</span><span class="sxs-lookup"><span data-stu-id="cadb0-126">`x[...]`: Array and indexer access</span></span>
    - <span data-ttu-id="cadb0-127">`x++`: post-incremento</span><span class="sxs-lookup"><span data-stu-id="cadb0-127">`x++`: Post-increment</span></span>
    - <span data-ttu-id="cadb0-128">`x--`: post-decremento</span><span class="sxs-lookup"><span data-stu-id="cadb0-128">`x--`: Post-decrement</span></span>
    - <span data-ttu-id="cadb0-129">`new T(...)`: creazione di oggetti e delegati</span><span class="sxs-lookup"><span data-stu-id="cadb0-129">`new T(...)`: Object and delegate creation</span></span>
    - <span data-ttu-id="cadb0-130">`new T(...){...}`: creazione di oggetti con inizializzatole</span><span class="sxs-lookup"><span data-stu-id="cadb0-130">`new T(...){...}`: Object creation with initializer</span></span>
    - <span data-ttu-id="cadb0-131">`new {...}`: inizializzatore di oggetti anonimo</span><span class="sxs-lookup"><span data-stu-id="cadb0-131">`new {...}`:  Anonymous object initializer</span></span>
    - <span data-ttu-id="cadb0-132">`new T[...]`: creazione di matrici</span><span class="sxs-lookup"><span data-stu-id="cadb0-132">`new T[...]`: Array creation</span></span>
    - <span data-ttu-id="cadb0-133">`typeof(T)`: ottiene l'oggetto @System.Type per `T`</span><span class="sxs-lookup"><span data-stu-id="cadb0-133">`typeof(T)`: Obtain @System.Type object for `T`</span></span>
    - <span data-ttu-id="cadb0-134">`checked(x)`: valuta l'espressione in un contesto controllato</span><span class="sxs-lookup"><span data-stu-id="cadb0-134">`checked(x)`: Evaluate expression in checked context</span></span>
    - <span data-ttu-id="cadb0-135">`unchecked(x)`: valuta l'espressione in un contesto non controllato</span><span class="sxs-lookup"><span data-stu-id="cadb0-135">`unchecked(x)`: Evaluate expression in unchecked context</span></span>
    - <span data-ttu-id="cadb0-136">`default(T)`: ottiene un valore predefinito di tipo `T`</span><span class="sxs-lookup"><span data-stu-id="cadb0-136">`default(T)`: Obtain default value of type `T`</span></span>
    - <span data-ttu-id="cadb0-137">`delegate {...}`: funzione anonima (metodo anonimo)</span><span class="sxs-lookup"><span data-stu-id="cadb0-137">`delegate {...}`: Anonymous function (anonymous method)</span></span>
* <span data-ttu-id="cadb0-138">Unario</span><span class="sxs-lookup"><span data-stu-id="cadb0-138">Unary</span></span>
    - <span data-ttu-id="cadb0-139">`+x`: identità</span><span class="sxs-lookup"><span data-stu-id="cadb0-139">`+x`: Identity</span></span>
    - <span data-ttu-id="cadb0-140">`-x`: negazione</span><span class="sxs-lookup"><span data-stu-id="cadb0-140">`-x`: Negation</span></span>
    - <span data-ttu-id="cadb0-141">`!x`: negazione logica</span><span class="sxs-lookup"><span data-stu-id="cadb0-141">`!x`: Logical negation</span></span>
    - <span data-ttu-id="cadb0-142">`~x`: negazione bit per bit</span><span class="sxs-lookup"><span data-stu-id="cadb0-142">`~x`: Bitwise negation</span></span>
    - <span data-ttu-id="cadb0-143">`++x`: pre-incremento</span><span class="sxs-lookup"><span data-stu-id="cadb0-143">`++x`: Pre-increment</span></span>
    - <span data-ttu-id="cadb0-144">`--x`: pre-decremento</span><span class="sxs-lookup"><span data-stu-id="cadb0-144">`--x`: Pre-decrement</span></span>
    - <span data-ttu-id="cadb0-145">`(T)x`: converte in modo esplicito `x` al tipo `T`</span><span class="sxs-lookup"><span data-stu-id="cadb0-145">`(T)x`: Explicitly convert `x` to type `T`</span></span>
    - <span data-ttu-id="cadb0-146">`await x`: attende in modo asincrono il completamento di `x`</span><span class="sxs-lookup"><span data-stu-id="cadb0-146">`await x`: Asynchronously wait for `x` to complete</span></span>
* <span data-ttu-id="cadb0-147">Moltiplicazione</span><span class="sxs-lookup"><span data-stu-id="cadb0-147">Multiplicative</span></span>
    - <span data-ttu-id="cadb0-148">`x * y`: moltiplicazione</span><span class="sxs-lookup"><span data-stu-id="cadb0-148">`x * y`: Multiplication</span></span>
    - <span data-ttu-id="cadb0-149">`x / y`: divisione</span><span class="sxs-lookup"><span data-stu-id="cadb0-149">`x / y`: Division</span></span>
    - <span data-ttu-id="cadb0-150">`x % y`: resto</span><span class="sxs-lookup"><span data-stu-id="cadb0-150">`x % y`: Remainder</span></span>
* <span data-ttu-id="cadb0-151">Addizione</span><span class="sxs-lookup"><span data-stu-id="cadb0-151">Additive</span></span>
    - <span data-ttu-id="cadb0-152">`x + y`: addizione, concatenazione di stringhe, combinazione di delegati</span><span class="sxs-lookup"><span data-stu-id="cadb0-152">`x + y`: Addition, string concatenation, delegate combination</span></span>
    - <span data-ttu-id="cadb0-153">`x – y`: sottrazione, rimozione di delegati</span><span class="sxs-lookup"><span data-stu-id="cadb0-153">`x – y`: Subtraction, delegate removal</span></span>
* <span data-ttu-id="cadb0-154">Shift</span><span class="sxs-lookup"><span data-stu-id="cadb0-154">Shift</span></span>
    - <span data-ttu-id="cadb0-155">`x << y`: spostamento a sinistra</span><span class="sxs-lookup"><span data-stu-id="cadb0-155">`x << y`: Shift left</span></span>
    - <span data-ttu-id="cadb0-156">`x >> y`: spostamento a destra</span><span class="sxs-lookup"><span data-stu-id="cadb0-156">`x >> y`: Shift right</span></span>
* <span data-ttu-id="cadb0-157">Operatori relazionali e operatori di test del tipo</span><span class="sxs-lookup"><span data-stu-id="cadb0-157">Relational and type testing</span></span>
    - <span data-ttu-id="cadb0-158">`x < y`: minore di</span><span class="sxs-lookup"><span data-stu-id="cadb0-158">`x < y`: Less than</span></span>
    - <span data-ttu-id="cadb0-159">`x > y`: maggiore di</span><span class="sxs-lookup"><span data-stu-id="cadb0-159">`x > y`: Greater than</span></span>
    - <span data-ttu-id="cadb0-160">`x <= y`: minore o uguale a</span><span class="sxs-lookup"><span data-stu-id="cadb0-160">`x <= y`: Less than or equal</span></span>
    - <span data-ttu-id="cadb0-161">`x >= y`: maggiore o uguale a</span><span class="sxs-lookup"><span data-stu-id="cadb0-161">`x >= y`: Greater than or equal</span></span>
    - <span data-ttu-id="cadb0-162">`x is T`: restituisce `true` se `x` è un oggetto `T`, altrimenti `false`</span><span class="sxs-lookup"><span data-stu-id="cadb0-162">`x is T`: Return `true` if `x` is a `T`, `false` otherwise</span></span>
    - <span data-ttu-id="cadb0-163">`x as T`: restituisce `x` tipizzato come `T` oppure `null` se `x` non è un oggetto `T`</span><span class="sxs-lookup"><span data-stu-id="cadb0-163">`x as T`: Return `x` typed as `T`, or `null` if `x` is not a `T`</span></span>
* <span data-ttu-id="cadb0-164">Uguaglianza</span><span class="sxs-lookup"><span data-stu-id="cadb0-164">Equality</span></span>
    - <span data-ttu-id="cadb0-165">`x == y`: uguale</span><span class="sxs-lookup"><span data-stu-id="cadb0-165">`x == y`: Equal</span></span>
    - <span data-ttu-id="cadb0-166">`x != y`: non uguale</span><span class="sxs-lookup"><span data-stu-id="cadb0-166">`x != y`: Not equal</span></span>
* <span data-ttu-id="cadb0-167">AND logico</span><span class="sxs-lookup"><span data-stu-id="cadb0-167">Logical AND</span></span>
    - <span data-ttu-id="cadb0-168">`x & y`: AND Integer bit per bit, AND logico booleano</span><span class="sxs-lookup"><span data-stu-id="cadb0-168">`x & y`: Integer bitwise AND, boolean logical AND</span></span>
* <span data-ttu-id="cadb0-169">XOR logico</span><span class="sxs-lookup"><span data-stu-id="cadb0-169">Logical XOR</span></span>
    - <span data-ttu-id="cadb0-170">`x ^ y`: XOR Integer bit per bit, XOR logico booleano</span><span class="sxs-lookup"><span data-stu-id="cadb0-170">`x ^ y`: Integer bitwise XOR, boolean logical XOR</span></span>
* <span data-ttu-id="cadb0-171">OR logico</span><span class="sxs-lookup"><span data-stu-id="cadb0-171">Logical OR</span></span>
    - <span data-ttu-id="cadb0-172">`x | y`: OR Integer bit per bit, OR logico booleano</span><span class="sxs-lookup"><span data-stu-id="cadb0-172">`x | y`: Integer bitwise OR, boolean logical OR</span></span>
* <span data-ttu-id="cadb0-173">AND condizionale</span><span class="sxs-lookup"><span data-stu-id="cadb0-173">Conditional AND</span></span>
    - <span data-ttu-id="cadb0-174">`x && y`: restituisce `y` solo se `x` non è `false`</span><span class="sxs-lookup"><span data-stu-id="cadb0-174">`x && y`: Evaluates `y` only if `x` is not `false`</span></span>
* <span data-ttu-id="cadb0-175">OR condizionale</span><span class="sxs-lookup"><span data-stu-id="cadb0-175">Conditional OR</span></span>
    - <span data-ttu-id="cadb0-176">`x || y`: restituisce `y` solo se `x` non è `true`</span><span class="sxs-lookup"><span data-stu-id="cadb0-176">`x || y`: Evaluates `y` only if `x` is not `true`</span></span>
* <span data-ttu-id="cadb0-177">Null-coalescing</span><span class="sxs-lookup"><span data-stu-id="cadb0-177">Null coalescing</span></span>
    - <span data-ttu-id="cadb0-178">`x ?? y`: Restituisce `y` se `x` è null, altrimenti `x`</span><span class="sxs-lookup"><span data-stu-id="cadb0-178">`x ?? y`: Evaluates to `y` if `x` is null, to `x` otherwise</span></span>
* <span data-ttu-id="cadb0-179">Condizionale</span><span class="sxs-lookup"><span data-stu-id="cadb0-179">Conditional</span></span>
    - <span data-ttu-id="cadb0-180">`x ? y : z`: restituisce `y` se `x` è `true`, `z` se `x` è `false`</span><span class="sxs-lookup"><span data-stu-id="cadb0-180">`x ? y : z`: Evaluates `y` if `x` is `true`, `z` if `x` is `false`</span></span>
* <span data-ttu-id="cadb0-181">Assegnazione o funzione anonima</span><span class="sxs-lookup"><span data-stu-id="cadb0-181">Assignment or anonymous function</span></span>
    - <span data-ttu-id="cadb0-182">`x = y`: assegnazione</span><span class="sxs-lookup"><span data-stu-id="cadb0-182">`x = y`: Assignment</span></span>
    - <span data-ttu-id="cadb0-183">`x op= y`: assegnazione composta. Gli operatori supportati sono</span><span class="sxs-lookup"><span data-stu-id="cadb0-183">`x op= y`: Compound assignment; supported operators are</span></span>
        - <span data-ttu-id="cadb0-184">`*=`   `/=`   `%=`   `+=`   `-=`   `<<=`   `>>=`   `&=`  `^=`  `|=`</span><span class="sxs-lookup"><span data-stu-id="cadb0-184">`*=`   `/=`   `%=`   `+=`   `-=`   `<<=`   `>>=`   `&=`  `^=`  `|=`</span></span>
    - <span data-ttu-id="cadb0-185">`(T x) => y`: funzione anonima (espressione lambda)</span><span class="sxs-lookup"><span data-stu-id="cadb0-185">`(T x) => y`: Anonymous function (lambda expression)</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="cadb0-186">[Precedente](types-and-variables.md)
[Successivo](statements.md)</span><span class="sxs-lookup"><span data-stu-id="cadb0-186">[Previous](types-and-variables.md)
[Next](statements.md)</span></span>

