---
title: Valutazione della funzione disabilitata a causa del timeout di una valutazione di funzione precedente
ms.date: 07/20/2015
f1_keywords:
- bc30957
- vbc30957
helpviewer_keywords:
- BC30957
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
ms.openlocfilehash: 6231d48f3f90d8e436dc80bf4670886c1d030387
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587659"
---
# <a name="function-evaluation-is-disabled-because-a-previous-function-evaluation-timed-out"></a><span data-ttu-id="570db-102">Valutazione della funzione disabilitata a causa del timeout di una valutazione di funzione precedente</span><span class="sxs-lookup"><span data-stu-id="570db-102">Function evaluation is disabled because a previous function evaluation timed out</span></span>
<span data-ttu-id="570db-103">La valutazione della funzione è disabilitata a causa del timeout di una valutazione della funzione precedente. Per riabilitare la valutazione della funzione, riprovare o riavviare il debug.</span><span class="sxs-lookup"><span data-stu-id="570db-103">Function evaluation is disabled because a previous function evaluation timed out. To re-enable function evaluation, step again or restart debugging.</span></span>  
  
 <span data-ttu-id="570db-104">Nel debugger di Visual Studio, un'espressione specifica una chiamata di routine, ma un'altra valutazione è scaduta.</span><span class="sxs-lookup"><span data-stu-id="570db-104">In the Visual Studio debugger, an expression specifies a procedure call, but another evaluation has timed out.</span></span>  
  
 <span data-ttu-id="570db-105">Possibili cause per una chiamata di routine timeout includono un ciclo infinito o *ciclo infinito*.</span><span class="sxs-lookup"><span data-stu-id="570db-105">Possible causes for a procedure call to time out include an infinite loop or *endless loop*.</span></span> <span data-ttu-id="570db-106">Per ulteriori informazioni, vedere [per... Istruzione successiva](../../../visual-basic/language-reference/statements/for-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="570db-106">For more information, see [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md).</span></span>  
  
 <span data-ttu-id="570db-107">È un caso speciale di un ciclo infinito *ricorsione*.</span><span class="sxs-lookup"><span data-stu-id="570db-107">A special case of an infinite loop is *recursion*.</span></span> <span data-ttu-id="570db-108">Per ulteriori informazioni, vedere [routine ricorsive](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="570db-108">For more information, see [Recursive Procedures](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md).</span></span>  
  
 <span data-ttu-id="570db-109">**ID errore:** BC30957</span><span class="sxs-lookup"><span data-stu-id="570db-109">**Error ID:** BC30957</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="570db-110">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="570db-110">To correct this error</span></span>  
  
1.  <span data-ttu-id="570db-111">Se possibile, determinare qual era la valutazione della funzione precedente e la relativa causa il timeout. In caso contrario, questo errore potrebbe verificarsi nuovamente.</span><span class="sxs-lookup"><span data-stu-id="570db-111">If possible, determine what the previous function evaluation was and what caused it to time out. Otherwise, you might encounter this error again.</span></span>  
  
2.  <span data-ttu-id="570db-112">Eseguire nuovamente il debugger o terminare e riavviare il debug.</span><span class="sxs-lookup"><span data-stu-id="570db-112">Either step the debugger again, or terminate and restart debugging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="570db-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="570db-113">See Also</span></span>  
 [<span data-ttu-id="570db-114">Debug in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="570db-114">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)  
 [<span data-ttu-id="570db-115">Spostarsi nel codice con il Debugger</span><span class="sxs-lookup"><span data-stu-id="570db-115">Navigating through Code with the Debugger</span></span>](/visualstudio/debugger/navigating-through-code-with-the-debugger)
