---
title: Clausola let (Riferimento C#)
ms.date: 07/20/2015
f1_keywords:
- let_CSharpKeyword
- let
helpviewer_keywords:
- let keyword [C#]
- let clause [C#]
ms.assetid: 13c9c1a4-ce57-48ef-8e1b-4c2a59b99fb4
ms.openlocfilehash: 3ce2b663e5678de6b53db610b489f85ab1427b9d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173588"
---
# <a name="let-clause-c-reference"></a><span data-ttu-id="e4177-102">Clausola let (Riferimento C#)</span><span class="sxs-lookup"><span data-stu-id="e4177-102">let clause (C# Reference)</span></span>

<span data-ttu-id="e4177-103">In un'espressione di query, è utile talvolta archiviare il risultato di una sottoespressione per poterlo usare in clausole successive.</span><span class="sxs-lookup"><span data-stu-id="e4177-103">In a query expression, it is sometimes useful to store the result of a sub-expression in order to use it in subsequent clauses.</span></span> <span data-ttu-id="e4177-104">È possibile eseguire questa operazione con la parola chiave `let`, che crea una nuova variabile di intervallo e la inizializza con il risultato dell'espressione fornita.</span><span class="sxs-lookup"><span data-stu-id="e4177-104">You can do this with the `let` keyword, which creates a new range variable and initializes it with the result of the expression you supply.</span></span> <span data-ttu-id="e4177-105">Dopo essere stata inizializzata con un valore, la variabile di intervallo non può essere usata per archiviare un altro valore.</span><span class="sxs-lookup"><span data-stu-id="e4177-105">Once initialized with a value, the range variable cannot be used to store another value.</span></span> <span data-ttu-id="e4177-106">Può essere tuttavia sottoposta a query, se contiene un tipo che può essere sottoposto a query.</span><span class="sxs-lookup"><span data-stu-id="e4177-106">However, if the range variable holds a queryable type, it can be queried.</span></span>

## <a name="example"></a><span data-ttu-id="e4177-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="e4177-107">Example</span></span>

<span data-ttu-id="e4177-108">Nell'esempio seguente, `let` viene usato in due modi:</span><span class="sxs-lookup"><span data-stu-id="e4177-108">In the following example `let` is used in two ways:</span></span>

1. <span data-ttu-id="e4177-109">Per creare un tipo enumerabile che può essere sottoposto a query.</span><span class="sxs-lookup"><span data-stu-id="e4177-109">To create an enumerable type that can itself be queried.</span></span>

2. <span data-ttu-id="e4177-110">Per consentire alla query di chiamare `ToLower` solo una volta sulla variabile di intervallo `word`.</span><span class="sxs-lookup"><span data-stu-id="e4177-110">To enable the query to call `ToLower` only one time on the range variable `word`.</span></span> <span data-ttu-id="e4177-111">Senza usare `let`, si dovrebbe chiamare `ToLower` in ogni predicato della clausola `where`.</span><span class="sxs-lookup"><span data-stu-id="e4177-111">Without using `let`, you would have to call `ToLower` in each predicate in the `where` clause.</span></span>

[!code-csharp[cscsrefQueryKeywords#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Let.cs#28)]

## <a name="see-also"></a><span data-ttu-id="e4177-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4177-112">See also</span></span>

- [<span data-ttu-id="e4177-113">Guida di riferimento a C</span><span class="sxs-lookup"><span data-stu-id="e4177-113">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="e4177-114">Parole chiave di query (LINQ)Query Keywords (LINQ)</span><span class="sxs-lookup"><span data-stu-id="e4177-114">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="e4177-115">LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="e4177-115">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="e4177-116">Language Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="e4177-116">Language Integrated Query (LINQ)</span></span>](../../programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="e4177-117">Gestire le eccezioni nelle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="e4177-117">Handle exceptions in query expressions</span></span>](../../linq/handle-exceptions-in-query-expressions.md)
