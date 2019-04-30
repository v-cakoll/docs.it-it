---
title: La variabile di intervallo <variable> nasconde una variabile in un blocco di inclusione, una variabile di intervallo precedentemente definita o una variabile dichiarata in modo implicito in un'espressione di query
ms.date: 07/20/2015
f1_keywords:
- bc36633
- vbc36633
helpviewer_keywords:
- BC36633
ms.assetid: 5d5470e4-3de5-49c2-8831-1087625f4a77
ms.openlocfilehash: e31f728de228bea743f6c7b5cbfef3cd73367262
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61971628"
---
# <a name="range-variable-variable-hides-a-variable-in-an-enclosing-block-a-previously-defined-range-variable-or-an-implicitly-declared-variable-in-a-query-expression"></a><span data-ttu-id="2ee37-102">Variabile di intervallo \<variabile > nasconde una variabile in un blocco di inclusione, una variabile di intervallo precedentemente definita o una variabile dichiarata in modo implicito in un'espressione di query</span><span class="sxs-lookup"><span data-stu-id="2ee37-102">Range variable \<variable> hides a variable in an enclosing block, a previously defined range variable, or an implicitly declared variable in a query expression</span></span>
<span data-ttu-id="2ee37-103">Un nome di variabile di intervallo specificato in un `Select`, `From`, `Aggregate`, o `Let` clausola Duplica il nome di una variabile di intervallo già specificato nella query o il nome di una variabile che viene dichiarato in modo implicito dalla query, ad esempio un nome di campo o il nome di una funzione di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="2ee37-103">A range variable name specified in a `Select`, `From`, `Aggregate`, or `Let` clause duplicates the name of a range variable already specified previously in the query, or the name of a variable that is implicitly declared by the query, such as a field name or the name of an aggregate function.</span></span>  
  
 <span data-ttu-id="2ee37-104">**ID errore:** BC36633</span><span class="sxs-lookup"><span data-stu-id="2ee37-104">**Error ID:** BC36633</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2ee37-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="2ee37-105">To correct this error</span></span>  
  
- <span data-ttu-id="2ee37-106">Assicurarsi che tutte le variabili di intervallo in un particolare ambito di query abbiano nomi univoci.</span><span class="sxs-lookup"><span data-stu-id="2ee37-106">Ensure that all range variables in a particular query scope have unique names.</span></span> <span data-ttu-id="2ee37-107">Una query è possibile racchiudere tra parentesi per garantire che le query annidate hanno un ambito univoco.</span><span class="sxs-lookup"><span data-stu-id="2ee37-107">You can enclose a query in parentheses to ensure that nested queries have a unique scope.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ee37-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ee37-108">See also</span></span>

- [<span data-ttu-id="2ee37-109">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2ee37-109">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="2ee37-110">Clausola From</span><span class="sxs-lookup"><span data-stu-id="2ee37-110">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="2ee37-111">Clausola Let</span><span class="sxs-lookup"><span data-stu-id="2ee37-111">Let Clause</span></span>](../../../visual-basic/language-reference/queries/let-clause.md)
- [<span data-ttu-id="2ee37-112">Clausola Aggregate</span><span class="sxs-lookup"><span data-stu-id="2ee37-112">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="2ee37-113">Clausola Select</span><span class="sxs-lookup"><span data-stu-id="2ee37-113">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
