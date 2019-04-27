---
title: Prevista dichiarazione
ms.date: 07/20/2015
f1_keywords:
- vbc30188
- bc30188
helpviewer_keywords:
- BC30188
ms.assetid: da6b1df3-fe6b-4415-88e6-0977e5189e0b
ms.openlocfilehash: 64ee75c93615f57b15fea29f06fff500a395ba0c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803831"
---
# <a name="declaration-expected"></a><span data-ttu-id="91656-102">Prevista dichiarazione</span><span class="sxs-lookup"><span data-stu-id="91656-102">Declaration expected</span></span>
<span data-ttu-id="91656-103">Un'istruzione non dichiarativa, ad esempio un'assegnazione o un'istruzione di ciclo, si verifica all'esterno di qualsiasi routine.</span><span class="sxs-lookup"><span data-stu-id="91656-103">A nondeclarative statement, such as an assignment or loop statement, occurs outside any procedure.</span></span> <span data-ttu-id="91656-104">Solo le dichiarazioni sono consentite alle routine esterne.</span><span class="sxs-lookup"><span data-stu-id="91656-104">Only declarations are allowed outside procedures.</span></span>  
  
 <span data-ttu-id="91656-105">In alternativa, un elemento di programmazione è dichiarato senza una parola chiave di dichiarazione, ad esempio `Dim` o `Const`.</span><span class="sxs-lookup"><span data-stu-id="91656-105">Alternatively, a programming element is declared without a declaration keyword such as `Dim` or `Const`.</span></span>  
  
 <span data-ttu-id="91656-106">**ID errore:** BC30188</span><span class="sxs-lookup"><span data-stu-id="91656-106">**Error ID:** BC30188</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="91656-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="91656-107">To correct this error</span></span>  
  
-   <span data-ttu-id="91656-108">Spostare l'istruzione non dichiarativa per il corpo di una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="91656-108">Move the nondeclarative statement to the body of a procedure.</span></span>  
  
-   <span data-ttu-id="91656-109">Iniziare la dichiarazione con una parola chiave di dichiarazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="91656-109">Begin the declaration with an appropriate declaration keyword.</span></span>  
  
-   <span data-ttu-id="91656-110">Assicurarsi che una parola chiave di dichiarazione non è errata.</span><span class="sxs-lookup"><span data-stu-id="91656-110">Ensure that a declaration keyword is not misspelled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91656-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91656-111">See also</span></span>

- [<span data-ttu-id="91656-112">Routine</span><span class="sxs-lookup"><span data-stu-id="91656-112">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="91656-113">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="91656-113">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
