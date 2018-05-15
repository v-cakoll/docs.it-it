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
ms.openlocfilehash: 9d625db1231687cdad2e24303b2e08ecf736a50c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="let-clause-c-reference"></a><span data-ttu-id="56d11-102">Clausola let (Riferimento C#)</span><span class="sxs-lookup"><span data-stu-id="56d11-102">let clause (C# Reference)</span></span>
<span data-ttu-id="56d11-103">In un'espressione di query, è utile talvolta archiviare il risultato di una sottoespressione per poterlo usare in clausole successive.</span><span class="sxs-lookup"><span data-stu-id="56d11-103">In a query expression, it is sometimes useful to store the result of a sub-expression in order to use it in subsequent clauses.</span></span> <span data-ttu-id="56d11-104">È possibile eseguire questa operazione con la parola chiave `let`, che crea una nuova variabile di intervallo e la inizializza con il risultato dell'espressione fornita.</span><span class="sxs-lookup"><span data-stu-id="56d11-104">You can do this with the `let` keyword, which creates a new range variable and initializes it with the result of the expression you supply.</span></span> <span data-ttu-id="56d11-105">Dopo essere stata inizializzata con un valore, la variabile di intervallo non può essere usata per archiviare un altro valore.</span><span class="sxs-lookup"><span data-stu-id="56d11-105">Once initialized with a value, the range variable cannot be used to store another value.</span></span> <span data-ttu-id="56d11-106">Può essere tuttavia sottoposta a query, se contiene un tipo che può essere sottoposto a query.</span><span class="sxs-lookup"><span data-stu-id="56d11-106">However, if the range variable holds a queryable type, it can be queried.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56d11-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="56d11-107">Example</span></span>  
 <span data-ttu-id="56d11-108">Nell'esempio seguente, `let` viene usato in due modi:</span><span class="sxs-lookup"><span data-stu-id="56d11-108">In the following example `let` is used in two ways:</span></span>  
  
1.  <span data-ttu-id="56d11-109">Per creare un tipo enumerabile che può essere sottoposto a query.</span><span class="sxs-lookup"><span data-stu-id="56d11-109">To create an enumerable type that can itself be queried.</span></span>  
  
2.  <span data-ttu-id="56d11-110">Per consentire alla query di chiamare `ToLower` solo una volta sulla variabile di intervallo `word`.</span><span class="sxs-lookup"><span data-stu-id="56d11-110">To enable the query to call `ToLower` only one time on the range variable `word`.</span></span> <span data-ttu-id="56d11-111">Senza usare `let`, si dovrebbe chiamare `ToLower` in ogni predicato della clausola `where`.</span><span class="sxs-lookup"><span data-stu-id="56d11-111">Without using `let`, you would have to call `ToLower` in each predicate in the `where` clause.</span></span>  
  
 [!code-csharp[cscsrefQueryKeywords#28](../../../csharp/language-reference/keywords/codesnippet/CSharp/let-clause_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="56d11-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="56d11-112">See Also</span></span>  
 [<span data-ttu-id="56d11-113">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="56d11-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="56d11-114">Parole chiave di query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="56d11-114">Query Keywords (LINQ)</span></span>](../../../csharp/language-reference/keywords/query-keywords.md)  
 [<span data-ttu-id="56d11-115">Espressioni di query LINQ</span><span class="sxs-lookup"><span data-stu-id="56d11-115">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [<span data-ttu-id="56d11-116">Nozioni di base su LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="56d11-116">Getting Started with LINQ in C#</span></span>](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [<span data-ttu-id="56d11-117">Procedura: Gestire le eccezioni nelle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="56d11-117">How to: Handle Exceptions in Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/how-to-handle-exceptions-in-query-expressions.md)
