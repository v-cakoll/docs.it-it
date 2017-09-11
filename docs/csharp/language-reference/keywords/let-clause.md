---
title: Clausola let (Riferimento C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- let_CSharpKeyword
- let
dev_langs:
- CSharp
helpviewer_keywords:
- let keyword [C#]
- let clause [C#]
ms.assetid: 13c9c1a4-ce57-48ef-8e1b-4c2a59b99fb4
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 37ec0cb0c8c374a0b5250d82e880c96696b5584a
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="let-clause-c-reference"></a><span data-ttu-id="856ea-102">Clausola let (Riferimento C#)</span><span class="sxs-lookup"><span data-stu-id="856ea-102">let clause (C# Reference)</span></span>
<span data-ttu-id="856ea-103">In un'espressione di query, è utile talvolta archiviare il risultato di una sottoespressione per poterlo usare in clausole successive.</span><span class="sxs-lookup"><span data-stu-id="856ea-103">In a query expression, it is sometimes useful to store the result of a sub-expression in order to use it in subsequent clauses.</span></span> <span data-ttu-id="856ea-104">È possibile eseguire questa operazione con la parola chiave `let`, che crea una nuova variabile di intervallo e la inizializza con il risultato dell'espressione fornita.</span><span class="sxs-lookup"><span data-stu-id="856ea-104">You can do this with the `let` keyword, which creates a new range variable and initializes it with the result of the expression you supply.</span></span> <span data-ttu-id="856ea-105">Dopo essere stata inizializzata con un valore, la variabile di intervallo non può essere usata per archiviare un altro valore.</span><span class="sxs-lookup"><span data-stu-id="856ea-105">Once initialized with a value, the range variable cannot be used to store another value.</span></span> <span data-ttu-id="856ea-106">Può essere tuttavia sottoposta a query, se contiene un tipo che può essere sottoposto a query.</span><span class="sxs-lookup"><span data-stu-id="856ea-106">However, if the range variable holds a queryable type, it can be queried.</span></span>  
  
## <a name="example"></a><span data-ttu-id="856ea-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="856ea-107">Example</span></span>  
 <span data-ttu-id="856ea-108">Nell'esempio seguente, `let` viene usato in due modi:</span><span class="sxs-lookup"><span data-stu-id="856ea-108">In the following example `let` is used in two ways:</span></span>  
  
1.  <span data-ttu-id="856ea-109">Per creare un tipo enumerabile che può essere sottoposto a query.</span><span class="sxs-lookup"><span data-stu-id="856ea-109">To create an enumerable type that can itself be queried.</span></span>  
  
2.  <span data-ttu-id="856ea-110">Per consentire alla query di chiamare `ToLower` solo una volta sulla variabile di intervallo `word`.</span><span class="sxs-lookup"><span data-stu-id="856ea-110">To enable the query to call `ToLower` only one time on the range variable `word`.</span></span> <span data-ttu-id="856ea-111">Senza usare `let`, si dovrebbe chiamare `ToLower` in ogni predicato della clausola `where`.</span><span class="sxs-lookup"><span data-stu-id="856ea-111">Without using `let`, you would have to call `ToLower` in each predicate in the `where` clause.</span></span>  
  
 <span data-ttu-id="856ea-112">[!code-cs[cscsrefQueryKeywords#28](../../../csharp/language-reference/keywords/codesnippet/CSharp/let-clause_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="856ea-112">[!code-cs[cscsrefQueryKeywords#28](../../../csharp/language-reference/keywords/codesnippet/CSharp/let-clause_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="856ea-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="856ea-113">See Also</span></span>  
 <span data-ttu-id="856ea-114">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="856ea-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="856ea-115">[Parole chiave di query (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="856ea-115">[Query Keywords (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span></span>  
 <span data-ttu-id="856ea-116">[Espressioni di query LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="856ea-116">[LINQ Query Expressions](../../../csharp/programming-guide/linq-query-expressions/index.md) </span></span>  
 <span data-ttu-id="856ea-117">[Introduzione all'uso di LINQ in C#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md) </span><span class="sxs-lookup"><span data-stu-id="856ea-117">[Getting Started with LINQ in C#](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md) </span></span>  
 [<span data-ttu-id="856ea-118">Procedura: Gestire le eccezioni nelle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="856ea-118">How to: Handle Exceptions in Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/how-to-handle-exceptions-in-query-expressions.md)

