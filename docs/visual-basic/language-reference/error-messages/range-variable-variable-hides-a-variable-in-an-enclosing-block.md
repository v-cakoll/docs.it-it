---
title: Variabile di intervallo &lt;variabile&gt; nasconde una variabile in un blocco di inclusione, una variabile di intervallo precedentemente definita o una variabile dichiarata in modo implicito in un'espressione di query
ms.date: 07/20/2015
f1_keywords:
- bc36633
- vbc36633
helpviewer_keywords:
- BC36633
ms.assetid: 5d5470e4-3de5-49c2-8831-1087625f4a77
ms.openlocfilehash: f02533cf7cb79c34e5bb5a6d445aaef7ab0e86da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593126"
---
# <a name="range-variable-ltvariablegt-hides-a-variable-in-an-enclosing-block-a-previously-defined-range-variable-or-an-implicitly-declared-variable-in-a-query-expression"></a><span data-ttu-id="d6f43-102">Variabile di intervallo &lt;variabile&gt; nasconde una variabile in un blocco di inclusione, una variabile di intervallo precedentemente definita o una variabile dichiarata in modo implicito in un'espressione di query</span><span class="sxs-lookup"><span data-stu-id="d6f43-102">Range variable &lt;variable&gt; hides a variable in an enclosing block, a previously defined range variable, or an implicitly declared variable in a query expression</span></span>
<span data-ttu-id="d6f43-103">Un nome di variabile di intervallo specificato un `Select`, `From`, `Aggregate`, o `Let` clausola Duplica il nome di una variabile di intervallo già specificato nella query o il nome di una variabile dichiarata in modo implicito tramite la query, ad esempio un nome di campo o il nome di una funzione di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="d6f43-103">A range variable name specified in a `Select`, `From`, `Aggregate`, or `Let` clause duplicates the name of a range variable already specified previously in the query, or the name of a variable that is implicitly declared by the query, such as a field name or the name of an aggregate function.</span></span>  
  
 <span data-ttu-id="d6f43-104">**ID errore:** BC36633</span><span class="sxs-lookup"><span data-stu-id="d6f43-104">**Error ID:** BC36633</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d6f43-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="d6f43-105">To correct this error</span></span>  
  
-   <span data-ttu-id="d6f43-106">Verificare che tutte le variabili di intervallo in un particolare ambito di query abbiano nomi univoci.</span><span class="sxs-lookup"><span data-stu-id="d6f43-106">Ensure that all range variables in a particular query scope have unique names.</span></span> <span data-ttu-id="d6f43-107">È possibile racchiudere tra parentesi per garantire che le query annidate abbiano un ambito univoco di una query.</span><span class="sxs-lookup"><span data-stu-id="d6f43-107">You can enclose a query in parentheses to ensure that nested queries have a unique scope.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6f43-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6f43-108">See Also</span></span>  
 [<span data-ttu-id="d6f43-109">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d6f43-109">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="d6f43-110">Clausola From</span><span class="sxs-lookup"><span data-stu-id="d6f43-110">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="d6f43-111">Clausola Let</span><span class="sxs-lookup"><span data-stu-id="d6f43-111">Let Clause</span></span>](../../../visual-basic/language-reference/queries/let-clause.md)  
 [<span data-ttu-id="d6f43-112">Clausola Aggregate</span><span class="sxs-lookup"><span data-stu-id="d6f43-112">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 [<span data-ttu-id="d6f43-113">Clausola Select</span><span class="sxs-lookup"><span data-stu-id="d6f43-113">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
