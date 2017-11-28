---
title: Clausola let (Riferimento C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- let_CSharpKeyword
- let
helpviewer_keywords:
- let keyword [C#]
- let clause [C#]
ms.assetid: 13c9c1a4-ce57-48ef-8e1b-4c2a59b99fb4
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 077c5178946b85d0fb85aa8da94966e4c5821736
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="let-clause-c-reference"></a><span data-ttu-id="8fbe7-102">Clausola let (Riferimento C#)</span><span class="sxs-lookup"><span data-stu-id="8fbe7-102">let clause (C# Reference)</span></span>
<span data-ttu-id="8fbe7-103">In un'espressione di query, è utile talvolta archiviare il risultato di una sottoespressione per poterlo usare in clausole successive.</span><span class="sxs-lookup"><span data-stu-id="8fbe7-103">In a query expression, it is sometimes useful to store the result of a sub-expression in order to use it in subsequent clauses.</span></span> <span data-ttu-id="8fbe7-104">È possibile eseguire questa operazione con la parola chiave `let`, che crea una nuova variabile di intervallo e la inizializza con il risultato dell'espressione fornita.</span><span class="sxs-lookup"><span data-stu-id="8fbe7-104">You can do this with the `let` keyword, which creates a new range variable and initializes it with the result of the expression you supply.</span></span> <span data-ttu-id="8fbe7-105">Dopo essere stata inizializzata con un valore, la variabile di intervallo non può essere usata per archiviare un altro valore.</span><span class="sxs-lookup"><span data-stu-id="8fbe7-105">Once initialized with a value, the range variable cannot be used to store another value.</span></span> <span data-ttu-id="8fbe7-106">Può essere tuttavia sottoposta a query, se contiene un tipo che può essere sottoposto a query.</span><span class="sxs-lookup"><span data-stu-id="8fbe7-106">However, if the range variable holds a queryable type, it can be queried.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8fbe7-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="8fbe7-107">Example</span></span>  
 <span data-ttu-id="8fbe7-108">Nell'esempio seguente, `let` viene usato in due modi:</span><span class="sxs-lookup"><span data-stu-id="8fbe7-108">In the following example `let` is used in two ways:</span></span>  
  
1.  <span data-ttu-id="8fbe7-109">Per creare un tipo enumerabile che può essere sottoposto a query.</span><span class="sxs-lookup"><span data-stu-id="8fbe7-109">To create an enumerable type that can itself be queried.</span></span>  
  
2.  <span data-ttu-id="8fbe7-110">Per consentire alla query di chiamare `ToLower` solo una volta sulla variabile di intervallo `word`.</span><span class="sxs-lookup"><span data-stu-id="8fbe7-110">To enable the query to call `ToLower` only one time on the range variable `word`.</span></span> <span data-ttu-id="8fbe7-111">Senza usare `let`, si dovrebbe chiamare `ToLower` in ogni predicato della clausola `where`.</span><span class="sxs-lookup"><span data-stu-id="8fbe7-111">Without using `let`, you would have to call `ToLower` in each predicate in the `where` clause.</span></span>  
  
 [!code-csharp[cscsrefQueryKeywords#28](../../../csharp/language-reference/keywords/codesnippet/CSharp/let-clause_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="8fbe7-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8fbe7-112">See Also</span></span>  
 [<span data-ttu-id="8fbe7-113">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="8fbe7-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="8fbe7-114">Parole chiave di query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="8fbe7-114">Query Keywords (LINQ)</span></span>](../../../csharp/language-reference/keywords/query-keywords.md)  
 [<span data-ttu-id="8fbe7-115">Espressioni di query LINQ</span><span class="sxs-lookup"><span data-stu-id="8fbe7-115">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [<span data-ttu-id="8fbe7-116">Nozioni di base su LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="8fbe7-116">Getting Started with LINQ in C#</span></span>](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [<span data-ttu-id="8fbe7-117">Procedura: Gestire le eccezioni nelle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="8fbe7-117">How to: Handle Exceptions in Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/how-to-handle-exceptions-in-query-expressions.md)
