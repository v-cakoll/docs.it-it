---
title: Prevista dichiarazione
ms.date: 07/20/2015
f1_keywords:
- vbc30188
- bc30188
helpviewer_keywords:
- BC30188
ms.assetid: da6b1df3-fe6b-4415-88e6-0977e5189e0b
ms.openlocfilehash: e776d3d08ff7d63b094a71e6990d87ea454a4428
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54638431"
---
# <a name="declaration-expected"></a><span data-ttu-id="dbdee-102">Prevista dichiarazione</span><span class="sxs-lookup"><span data-stu-id="dbdee-102">Declaration expected</span></span>
<span data-ttu-id="dbdee-103">Un'istruzione non dichiarativa, ad esempio un'assegnazione o un'istruzione di ciclo, si verifica all'esterno di qualsiasi routine.</span><span class="sxs-lookup"><span data-stu-id="dbdee-103">A nondeclarative statement, such as an assignment or loop statement, occurs outside any procedure.</span></span> <span data-ttu-id="dbdee-104">Solo le dichiarazioni sono consentite alle routine esterne.</span><span class="sxs-lookup"><span data-stu-id="dbdee-104">Only declarations are allowed outside procedures.</span></span>  
  
 <span data-ttu-id="dbdee-105">In alternativa, un elemento di programmazione è dichiarato senza una parola chiave di dichiarazione, ad esempio `Dim` o `Const`.</span><span class="sxs-lookup"><span data-stu-id="dbdee-105">Alternatively, a programming element is declared without a declaration keyword such as `Dim` or `Const`.</span></span>  
  
 <span data-ttu-id="dbdee-106">**ID errore:** BC30188</span><span class="sxs-lookup"><span data-stu-id="dbdee-106">**Error ID:** BC30188</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="dbdee-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="dbdee-107">To correct this error</span></span>  
  
-   <span data-ttu-id="dbdee-108">Spostare l'istruzione non dichiarativa per il corpo di una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="dbdee-108">Move the nondeclarative statement to the body of a procedure.</span></span>  
  
-   <span data-ttu-id="dbdee-109">Iniziare la dichiarazione con una parola chiave di dichiarazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="dbdee-109">Begin the declaration with an appropriate declaration keyword.</span></span>  
  
-   <span data-ttu-id="dbdee-110">Assicurarsi che una parola chiave di dichiarazione non è errata.</span><span class="sxs-lookup"><span data-stu-id="dbdee-110">Ensure that a declaration keyword is not misspelled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbdee-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dbdee-111">See also</span></span>
- [<span data-ttu-id="dbdee-112">Routine</span><span class="sxs-lookup"><span data-stu-id="dbdee-112">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="dbdee-113">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="dbdee-113">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
