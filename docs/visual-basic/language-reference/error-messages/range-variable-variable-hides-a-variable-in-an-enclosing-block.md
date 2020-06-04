---
title: La variabile di intervallo <variable> nasconde una variabile in un blocco di inclusione, una variabile di intervallo precedentemente definita o una variabile dichiarata in modo implicito in un'espressione di query
ms.date: 07/20/2015
f1_keywords:
- bc36633
- vbc36633
helpviewer_keywords:
- BC36633
ms.assetid: 5d5470e4-3de5-49c2-8831-1087625f4a77
ms.openlocfilehash: 290ca81dea500558ed73956c91bdf7bfec312014
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400396"
---
# <a name="range-variable-variable-hides-a-variable-in-an-enclosing-block-a-previously-defined-range-variable-or-an-implicitly-declared-variable-in-a-query-expression"></a><span data-ttu-id="0d70c-102">La variabile di intervallo \<variable> nasconde una variabile in un blocco di inclusione, una variabile di intervallo precedentemente definita o una variabile dichiarata in modo implicito in un'espressione di query</span><span class="sxs-lookup"><span data-stu-id="0d70c-102">Range variable \<variable> hides a variable in an enclosing block, a previously defined range variable, or an implicitly declared variable in a query expression</span></span>
<span data-ttu-id="0d70c-103">Un nome di variabile di intervallo specificato in una `Select` `From` clausola,, `Aggregate` o `Let` Duplica il nome di una variabile di intervallo già specificata in precedenza nella query o il nome di una variabile dichiarata in modo implicito dalla query, ad esempio un nome di campo o il nome di una funzione di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="0d70c-103">A range variable name specified in a `Select`, `From`, `Aggregate`, or `Let` clause duplicates the name of a range variable already specified previously in the query, or the name of a variable that is implicitly declared by the query, such as a field name or the name of an aggregate function.</span></span>  
  
 <span data-ttu-id="0d70c-104">**ID errore:** BC36633</span><span class="sxs-lookup"><span data-stu-id="0d70c-104">**Error ID:** BC36633</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0d70c-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="0d70c-105">To correct this error</span></span>  
  
- <span data-ttu-id="0d70c-106">Verificare che tutte le variabili di intervallo in un determinato ambito di query abbiano nomi univoci.</span><span class="sxs-lookup"><span data-stu-id="0d70c-106">Ensure that all range variables in a particular query scope have unique names.</span></span> <span data-ttu-id="0d70c-107">È possibile racchiudere una query tra parentesi per garantire che le query annidate abbiano un ambito univoco.</span><span class="sxs-lookup"><span data-stu-id="0d70c-107">You can enclose a query in parentheses to ensure that nested queries have a unique scope.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d70c-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d70c-108">See also</span></span>

- [<span data-ttu-id="0d70c-109">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0d70c-109">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="0d70c-110">Clausola from</span><span class="sxs-lookup"><span data-stu-id="0d70c-110">From Clause</span></span>](../queries/from-clause.md)
- [<span data-ttu-id="0d70c-111">Clausola Let</span><span class="sxs-lookup"><span data-stu-id="0d70c-111">Let Clause</span></span>](../queries/let-clause.md)
- [<span data-ttu-id="0d70c-112">Aggregate Clause</span><span class="sxs-lookup"><span data-stu-id="0d70c-112">Aggregate Clause</span></span>](../queries/aggregate-clause.md)
- [<span data-ttu-id="0d70c-113">Clausola SELECT</span><span class="sxs-lookup"><span data-stu-id="0d70c-113">Select Clause</span></span>](../queries/select-clause.md)
