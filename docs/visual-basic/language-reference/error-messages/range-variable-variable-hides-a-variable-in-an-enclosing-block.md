---
title: Variabile di intervallo &lt;variabile&gt; nasconde una variabile in un blocco di inclusione, una variabile di intervallo precedentemente definita o una variabile dichiarata in modo implicito in un'espressione di query
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36633
- vbc36633
helpviewer_keywords:
- BC36633
ms.assetid: 5d5470e4-3de5-49c2-8831-1087625f4a77
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ccbac48694a13daa09f2511cf39d5dbd51cdaaf7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="range-variable-ltvariablegt-hides-a-variable-in-an-enclosing-block-a-previously-defined-range-variable-or-an-implicitly-declared-variable-in-a-query-expression"></a><span data-ttu-id="42787-102">Variabile di intervallo &lt;variabile&gt; nasconde una variabile in un blocco di inclusione, una variabile di intervallo precedentemente definita o una variabile dichiarata in modo implicito in un'espressione di query</span><span class="sxs-lookup"><span data-stu-id="42787-102">Range variable &lt;variable&gt; hides a variable in an enclosing block, a previously defined range variable, or an implicitly declared variable in a query expression</span></span>
<span data-ttu-id="42787-103">Un nome di variabile di intervallo specificato un `Select`, `From`, `Aggregate`, o `Let` clausola Duplica il nome di una variabile di intervallo già specificato nella query o il nome di una variabile dichiarata in modo implicito tramite la query, ad esempio un nome di campo o il nome di una funzione di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="42787-103">A range variable name specified in a `Select`, `From`, `Aggregate`, or `Let` clause duplicates the name of a range variable already specified previously in the query, or the name of a variable that is implicitly declared by the query, such as a field name or the name of an aggregate function.</span></span>  
  
 <span data-ttu-id="42787-104">**ID errore:** BC36633</span><span class="sxs-lookup"><span data-stu-id="42787-104">**Error ID:** BC36633</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="42787-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="42787-105">To correct this error</span></span>  
  
-   <span data-ttu-id="42787-106">Verificare che tutte le variabili di intervallo in un particolare ambito di query abbiano nomi univoci.</span><span class="sxs-lookup"><span data-stu-id="42787-106">Ensure that all range variables in a particular query scope have unique names.</span></span> <span data-ttu-id="42787-107">È possibile racchiudere tra parentesi per garantire che le query annidate abbiano un ambito univoco di una query.</span><span class="sxs-lookup"><span data-stu-id="42787-107">You can enclose a query in parentheses to ensure that nested queries have a unique scope.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42787-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42787-108">See Also</span></span>  
 [<span data-ttu-id="42787-109">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="42787-109">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="42787-110">Clausola From</span><span class="sxs-lookup"><span data-stu-id="42787-110">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="42787-111">Clausola Let</span><span class="sxs-lookup"><span data-stu-id="42787-111">Let Clause</span></span>](../../../visual-basic/language-reference/queries/let-clause.md)  
 [<span data-ttu-id="42787-112">Clausola Aggregate</span><span class="sxs-lookup"><span data-stu-id="42787-112">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 [<span data-ttu-id="42787-113">Clausola Select</span><span class="sxs-lookup"><span data-stu-id="42787-113">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
