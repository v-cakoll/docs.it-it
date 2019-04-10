---
title: Valutazione della funzione disabilitata a causa del timeout di una valutazione di funzione precedente
ms.date: 07/20/2015
f1_keywords:
- bc30957
- vbc30957
helpviewer_keywords:
- BC30957
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
ms.openlocfilehash: bc4d05e52434cf62fa90671d29b407c83114b5d2
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59315777"
---
# <a name="function-evaluation-is-disabled-because-a-previous-function-evaluation-timed-out"></a><span data-ttu-id="7d926-102">Valutazione della funzione disabilitata a causa del timeout di una valutazione di funzione precedente</span><span class="sxs-lookup"><span data-stu-id="7d926-102">Function evaluation is disabled because a previous function evaluation timed out</span></span>
<span data-ttu-id="7d926-103">Valutazione della funzione disabilitata a causa del timeout di una valutazione della funzione precedente. Per riabilitare la valutazione della funzione, ripetere l'operazione o riavviare il debug.</span><span class="sxs-lookup"><span data-stu-id="7d926-103">Function evaluation is disabled because a previous function evaluation timed out. To re-enable function evaluation, step again or restart debugging.</span></span>  
  
 <span data-ttu-id="7d926-104">Nel debugger di Visual Studio, un'espressione specifica una chiamata di routine, ma un altro valutazione è scaduta.</span><span class="sxs-lookup"><span data-stu-id="7d926-104">In the Visual Studio debugger, an expression specifies a procedure call, but another evaluation has timed out.</span></span>  
  
 <span data-ttu-id="7d926-105">Possibili cause per una chiamata di procedura timeout includono un ciclo infinito oppure *un ciclo infinito*.</span><span class="sxs-lookup"><span data-stu-id="7d926-105">Possible causes for a procedure call to time out include an infinite loop or *endless loop*.</span></span> <span data-ttu-id="7d926-106">Per altre informazioni, vedere [per... Istruzione Next](../../../visual-basic/language-reference/statements/for-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="7d926-106">For more information, see [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md).</span></span>  
  
 <span data-ttu-id="7d926-107">È un caso speciale di un ciclo infinito *ricorsione*.</span><span class="sxs-lookup"><span data-stu-id="7d926-107">A special case of an infinite loop is *recursion*.</span></span> <span data-ttu-id="7d926-108">Per altre informazioni, vedere [routine ricorsive](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="7d926-108">For more information, see [Recursive Procedures](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md).</span></span>  
  
 <span data-ttu-id="7d926-109">**ID errore:** BC30957</span><span class="sxs-lookup"><span data-stu-id="7d926-109">**Error ID:** BC30957</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7d926-110">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="7d926-110">To correct this error</span></span>  
  
1. <span data-ttu-id="7d926-111">Se possibile, determinare qual è la valutazione della funzione precedente e che lo ha generato al timeout. In caso contrario, questo errore potrebbe verificarsi nuovamente.</span><span class="sxs-lookup"><span data-stu-id="7d926-111">If possible, determine what the previous function evaluation was and what caused it to time out. Otherwise, you might encounter this error again.</span></span>  
  
2. <span data-ttu-id="7d926-112">Passaggio del debugger, oppure interrompere e riavviare il debug.</span><span class="sxs-lookup"><span data-stu-id="7d926-112">Either step the debugger again, or terminate and restart debugging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d926-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d926-113">See also</span></span>

- [<span data-ttu-id="7d926-114">Debug in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7d926-114">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)
- [<span data-ttu-id="7d926-115">Spostarsi nel codice con il Debugger</span><span class="sxs-lookup"><span data-stu-id="7d926-115">Navigating through Code with the Debugger</span></span>](/visualstudio/debugger/navigating-through-code-with-the-debugger)
