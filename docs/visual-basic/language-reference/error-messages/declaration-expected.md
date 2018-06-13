---
title: Prevista dichiarazione
ms.date: 07/20/2015
f1_keywords:
- vbc30188
- bc30188
helpviewer_keywords:
- BC30188
ms.assetid: da6b1df3-fe6b-4415-88e6-0977e5189e0b
ms.openlocfilehash: c5c9b665b78c7c63c55292e38cc96ee8b2962a61
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33583890"
---
# <a name="declaration-expected"></a><span data-ttu-id="2977e-102">Prevista dichiarazione</span><span class="sxs-lookup"><span data-stu-id="2977e-102">Declaration expected</span></span>
<span data-ttu-id="2977e-103">Un'istruzione non dichiarativa, ad esempio un'assegnazione o istruzione di ciclo, si verifica all'esterno di qualsiasi routine.</span><span class="sxs-lookup"><span data-stu-id="2977e-103">A nondeclarative statement, such as an assignment or loop statement, occurs outside any procedure.</span></span> <span data-ttu-id="2977e-104">Solo le dichiarazioni sono consentite alle routine esterne.</span><span class="sxs-lookup"><span data-stu-id="2977e-104">Only declarations are allowed outside procedures.</span></span>  
  
 <span data-ttu-id="2977e-105">In alternativa, un elemento di programmazione è dichiarato senza una parola chiave di dichiarazione, ad esempio `Dim` o `Const`.</span><span class="sxs-lookup"><span data-stu-id="2977e-105">Alternatively, a programming element is declared without a declaration keyword such as `Dim` or `Const`.</span></span>  
  
 <span data-ttu-id="2977e-106">**ID errore:** BC30188</span><span class="sxs-lookup"><span data-stu-id="2977e-106">**Error ID:** BC30188</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2977e-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="2977e-107">To correct this error</span></span>  
  
-   <span data-ttu-id="2977e-108">Spostare l'istruzione non dichiarativa nel corpo di una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="2977e-108">Move the nondeclarative statement to the body of a procedure.</span></span>  
  
-   <span data-ttu-id="2977e-109">Iniziare la dichiarazione con una parola chiave di dichiarazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="2977e-109">Begin the declaration with an appropriate declaration keyword.</span></span>  
  
-   <span data-ttu-id="2977e-110">Verificare che una parola chiave di dichiarazione non sia digitato correttamente.</span><span class="sxs-lookup"><span data-stu-id="2977e-110">Ensure that a declaration keyword is not misspelled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2977e-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2977e-111">See Also</span></span>  
 [<span data-ttu-id="2977e-112">Routine</span><span class="sxs-lookup"><span data-stu-id="2977e-112">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="2977e-113">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="2977e-113">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
