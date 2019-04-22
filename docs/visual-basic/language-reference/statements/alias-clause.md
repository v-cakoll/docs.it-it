---
title: Clausola Alias (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: 84c8f39e632eebbe5382492669820910b38bc360
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58839743"
---
# <a name="alias-clause-visual-basic"></a><span data-ttu-id="99579-102">Clausola Alias (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99579-102">Alias Clause (Visual Basic)</span></span>
<span data-ttu-id="99579-103">Indica che una routine esterna ha un altro nome nella relativa DLL.</span><span class="sxs-lookup"><span data-stu-id="99579-103">Indicates that an external procedure has another name in its DLL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99579-104">Note</span><span class="sxs-lookup"><span data-stu-id="99579-104">Remarks</span></span>  
 <span data-ttu-id="99579-105">Il `Alias` parola chiave può essere usata in questo contesto:</span><span class="sxs-lookup"><span data-stu-id="99579-105">The `Alias` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="99579-106">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="99579-106">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 <span data-ttu-id="99579-107">Nell'esempio seguente, il `Alias` parola chiave viene usata per specificare il nome della funzione in advapi32.dll, `GetUserNameA`, che `getUserName` viene usato al posto di questo esempio.</span><span class="sxs-lookup"><span data-stu-id="99579-107">In the following example, the `Alias` keyword is used to provide the name of the function in advapi32.dll, `GetUserNameA`, that `getUserName` is used in place of in this example.</span></span> <span data-ttu-id="99579-108">Funzione `getUserName` viene chiamato nella sub `getUser`, che consente di visualizzare il nome dell'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="99579-108">Function `getUserName` is called in sub `getUser`, which displays the name of the current user.</span></span>  
  
 [!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="99579-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99579-109">See also</span></span>

- [<span data-ttu-id="99579-110">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="99579-110">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
