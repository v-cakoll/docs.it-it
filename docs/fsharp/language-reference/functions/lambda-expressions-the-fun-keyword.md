---
title: 'Espressioni lambda: Parola chiave fun'
description: Informazioni su come usare la F# parola chiave "Fun" per definire un'espressione lambda, che è una funzione anonima.
ms.date: 05/16/2016
ms.openlocfilehash: 9818724686dd83a7e352fb36819289fa19b002df
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630672"
---
# <a name="lambda-expressions-the-fun-keyword-f"></a><span data-ttu-id="10d94-103">Espressioni lambda: Parola chiave fun (F#)</span><span class="sxs-lookup"><span data-stu-id="10d94-103">Lambda Expressions: The fun Keyword (F#)</span></span>

<span data-ttu-id="10d94-104">La `fun` parola chiave viene usata per definire un'espressione lambda, ovvero una funzione anonima.</span><span class="sxs-lookup"><span data-stu-id="10d94-104">The `fun` keyword is used to define a lambda expression, that is, an anonymous function.</span></span>

## <a name="syntax"></a><span data-ttu-id="10d94-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="10d94-105">Syntax</span></span>

```fsharp
fun parameter-list -> expression
```

## <a name="remarks"></a><span data-ttu-id="10d94-106">Note</span><span class="sxs-lookup"><span data-stu-id="10d94-106">Remarks</span></span>

<span data-ttu-id="10d94-107">Il *parametro-list* è in genere costituito da nomi e, facoltativamente, da tipi di parametri.</span><span class="sxs-lookup"><span data-stu-id="10d94-107">The *parameter-list* typically consists of names and, optionally, types of parameters.</span></span> <span data-ttu-id="10d94-108">Più in generale, l' *elenco di parametri* può essere composto da F# qualsiasi modello.</span><span class="sxs-lookup"><span data-stu-id="10d94-108">More generally, the *parameter-list* can be composed of any F# patterns.</span></span> <span data-ttu-id="10d94-109">Per un elenco completo dei modelli possibili [, vedere Criteri](../pattern-matching.md)di ricerca.</span><span class="sxs-lookup"><span data-stu-id="10d94-109">For a full list of possible patterns, see [Pattern Matching](../pattern-matching.md).</span></span> <span data-ttu-id="10d94-110">Gli elenchi di parametri validi includono gli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="10d94-110">Lists of valid parameters include the following examples.</span></span>

```fsharp
// Lambda expressions with parameter lists.
fun a b c -> ...
fun (a: int) b c -> ...
fun (a : int) (b : string) (c:float) -> ...

// A lambda expression with a tuple pattern.
fun (a, b) -> …

// A lambda expression with a list pattern.
fun head :: tail -> …
```

<span data-ttu-id="10d94-111">L' *espressione* è il corpo della funzione, l'ultima espressione di che genera un valore restituito.</span><span class="sxs-lookup"><span data-stu-id="10d94-111">The *expression* is the body of the function, the last expression of which generates a return value.</span></span> <span data-ttu-id="10d94-112">Di seguito sono riportati alcuni esempi di espressioni lambda valide:</span><span class="sxs-lookup"><span data-stu-id="10d94-112">Examples of valid lambda expressions include the following:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet301.fs)]

## <a name="using-lambda-expressions"></a><span data-ttu-id="10d94-113">Uso di espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="10d94-113">Using Lambda Expressions</span></span>

<span data-ttu-id="10d94-114">Le espressioni lambda sono particolarmente utili quando si desidera eseguire operazioni in un elenco o in un'altra raccolta e si desidera evitare il lavoro aggiuntivo di definizione di una funzione.</span><span class="sxs-lookup"><span data-stu-id="10d94-114">Lambda expressions are especially useful when you want to perform operations on a list or other collection and want to avoid the extra work of defining a function.</span></span> <span data-ttu-id="10d94-115">Molte F# funzioni della libreria accettano valori di funzione come argomenti e può essere particolarmente utile usare un'espressione lambda in tali casi.</span><span class="sxs-lookup"><span data-stu-id="10d94-115">Many F# library functions take function values as arguments, and it can be especially convenient to use a lambda expression in those cases.</span></span> <span data-ttu-id="10d94-116">Il codice seguente applica un'espressione lambda agli elementi di un elenco.</span><span class="sxs-lookup"><span data-stu-id="10d94-116">The following code applies a lambda expression to elements of a list.</span></span> <span data-ttu-id="10d94-117">In questo caso, la funzione anonima aggiunge 1 a ogni elemento di un elenco.</span><span class="sxs-lookup"><span data-stu-id="10d94-117">In this case, the anonymous function adds 1 to every element of a list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet302.fs)]

## <a name="see-also"></a><span data-ttu-id="10d94-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10d94-118">See also</span></span>

- [<span data-ttu-id="10d94-119">Funzioni</span><span class="sxs-lookup"><span data-stu-id="10d94-119">Functions</span></span>](index.md)
