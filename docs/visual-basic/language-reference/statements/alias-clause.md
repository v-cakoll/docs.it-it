---
title: Clausola Alias (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: 3b1a66ecfd3c023a12ac62191ca3671a195b45a6
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56978228"
---
# <a name="alias-clause-visual-basic"></a><span data-ttu-id="980dc-102">Clausola Alias (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="980dc-102">Alias Clause (Visual Basic)</span></span>
<span data-ttu-id="980dc-103">Indica che una routine esterna ha un altro nome nella relativa DLL.</span><span class="sxs-lookup"><span data-stu-id="980dc-103">Indicates that an external procedure has another name in its DLL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="980dc-104">Note</span><span class="sxs-lookup"><span data-stu-id="980dc-104">Remarks</span></span>  
 <span data-ttu-id="980dc-105">Il `Alias` parola chiave può essere usata in questo contesto:</span><span class="sxs-lookup"><span data-stu-id="980dc-105">The `Alias` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="980dc-106">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="980dc-106">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 <span data-ttu-id="980dc-107">Nell'esempio seguente, il `Alias` parola chiave viene usata per specificare il nome della funzione in advapi32.dll, `GetUserNameA`, che `getUserName` viene usato al posto di questo esempio.</span><span class="sxs-lookup"><span data-stu-id="980dc-107">In the following example, the `Alias` keyword is used to provide the name of the function in advapi32.dll, `GetUserNameA`, that `getUserName` is used in place of in this example.</span></span> <span data-ttu-id="980dc-108">Funzione `getUserName` viene chiamato nella sub `getUser`, che consente di visualizzare il nome dell'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="980dc-108">Function `getUserName` is called in sub `getUser`, which displays the name of the current user.</span></span>  
  
 [!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="980dc-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="980dc-109">See also</span></span>
- [<span data-ttu-id="980dc-110">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="980dc-110">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
