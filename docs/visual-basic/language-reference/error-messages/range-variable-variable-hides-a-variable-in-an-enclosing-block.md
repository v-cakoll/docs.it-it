---
title: Variabile di intervallo &lt;variabile&gt; nasconde una variabile in un blocco di inclusione, una variabile di intervallo precedentemente definita o una variabile dichiarata in modo implicito in un'espressione di query
ms.date: 07/20/2015
f1_keywords:
- bc36633
- vbc36633
helpviewer_keywords:
- BC36633
ms.assetid: 5d5470e4-3de5-49c2-8831-1087625f4a77
ms.openlocfilehash: aef52ea912a4180a6505949c8077296628592c72
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54748116"
---
# <a name="range-variable-ltvariablegt-hides-a-variable-in-an-enclosing-block-a-previously-defined-range-variable-or-an-implicitly-declared-variable-in-a-query-expression"></a><span data-ttu-id="ceaea-102">Variabile di intervallo &lt;variabile&gt; nasconde una variabile in un blocco di inclusione, una variabile di intervallo precedentemente definita o una variabile dichiarata in modo implicito in un'espressione di query</span><span class="sxs-lookup"><span data-stu-id="ceaea-102">Range variable &lt;variable&gt; hides a variable in an enclosing block, a previously defined range variable, or an implicitly declared variable in a query expression</span></span>
<span data-ttu-id="ceaea-103">Un nome di variabile di intervallo specificato in un `Select`, `From`, `Aggregate`, o `Let` clausola Duplica il nome di una variabile di intervallo già specificato nella query o il nome di una variabile che viene dichiarato in modo implicito dalla query, ad esempio un nome di campo o il nome di una funzione di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="ceaea-103">A range variable name specified in a `Select`, `From`, `Aggregate`, or `Let` clause duplicates the name of a range variable already specified previously in the query, or the name of a variable that is implicitly declared by the query, such as a field name or the name of an aggregate function.</span></span>  
  
 <span data-ttu-id="ceaea-104">**ID errore:** BC36633</span><span class="sxs-lookup"><span data-stu-id="ceaea-104">**Error ID:** BC36633</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ceaea-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="ceaea-105">To correct this error</span></span>  
  
-   <span data-ttu-id="ceaea-106">Assicurarsi che tutte le variabili di intervallo in un particolare ambito di query abbiano nomi univoci.</span><span class="sxs-lookup"><span data-stu-id="ceaea-106">Ensure that all range variables in a particular query scope have unique names.</span></span> <span data-ttu-id="ceaea-107">Una query è possibile racchiudere tra parentesi per garantire che le query annidate hanno un ambito univoco.</span><span class="sxs-lookup"><span data-stu-id="ceaea-107">You can enclose a query in parentheses to ensure that nested queries have a unique scope.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ceaea-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ceaea-108">See also</span></span>
- [<span data-ttu-id="ceaea-109">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ceaea-109">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="ceaea-110">Clausola From</span><span class="sxs-lookup"><span data-stu-id="ceaea-110">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="ceaea-111">Clausola Let</span><span class="sxs-lookup"><span data-stu-id="ceaea-111">Let Clause</span></span>](../../../visual-basic/language-reference/queries/let-clause.md)
- [<span data-ttu-id="ceaea-112">Clausola Aggregate</span><span class="sxs-lookup"><span data-stu-id="ceaea-112">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="ceaea-113">Clausola Select</span><span class="sxs-lookup"><span data-stu-id="ceaea-113">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
