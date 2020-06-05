---
title: Valutazione della funzione disabilitata a causa del timeout di una valutazione di funzione precedente
ms.date: 07/20/2015
f1_keywords:
- bc30957
- vbc30957
helpviewer_keywords:
- BC30957
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
ms.openlocfilehash: 7b0113e9c1018772da6dc180f7fc5beb0e922917
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402953"
---
# <a name="function-evaluation-is-disabled-because-a-previous-function-evaluation-timed-out"></a><span data-ttu-id="c8db7-102">Valutazione della funzione disabilitata a causa del timeout di una valutazione di funzione precedente</span><span class="sxs-lookup"><span data-stu-id="c8db7-102">Function evaluation is disabled because a previous function evaluation timed out</span></span>
<span data-ttu-id="c8db7-103">Valutazione della funzione disabilitata a causa del timeout di una valutazione di funzione precedente. Per riabilitare la valutazione della funzione, eseguire di nuovo l'istruzione o riavviare il debug.</span><span class="sxs-lookup"><span data-stu-id="c8db7-103">Function evaluation is disabled because a previous function evaluation timed out. To re-enable function evaluation, step again or restart debugging.</span></span>  
  
 <span data-ttu-id="c8db7-104">Nel debugger di Visual Studio un'espressione specifica una chiamata di routine, ma si è verificato il timeout di un'altra valutazione.</span><span class="sxs-lookup"><span data-stu-id="c8db7-104">In the Visual Studio debugger, an expression specifies a procedure call, but another evaluation has timed out.</span></span>  
  
 <span data-ttu-id="c8db7-105">Le possibili cause di una chiamata di routine a timeout includono *un ciclo infinito o infinito.*</span><span class="sxs-lookup"><span data-stu-id="c8db7-105">Possible causes for a procedure call to time out include an infinite loop or *endless loop*.</span></span> <span data-ttu-id="c8db7-106">Per ulteriori informazioni, vedere [per... Istruzione successiva](../statements/for-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c8db7-106">For more information, see [For...Next Statement](../statements/for-next-statement.md).</span></span>  
  
 <span data-ttu-id="c8db7-107">Un caso speciale di un ciclo infinito è la *ricorsione*.</span><span class="sxs-lookup"><span data-stu-id="c8db7-107">A special case of an infinite loop is *recursion*.</span></span> <span data-ttu-id="c8db7-108">Per ulteriori informazioni, vedere [procedure ricorsive](../../programming-guide/language-features/procedures/recursive-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="c8db7-108">For more information, see [Recursive Procedures](../../programming-guide/language-features/procedures/recursive-procedures.md).</span></span>  
  
 <span data-ttu-id="c8db7-109">**ID errore:** BC30957</span><span class="sxs-lookup"><span data-stu-id="c8db7-109">**Error ID:** BC30957</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c8db7-110">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="c8db7-110">To correct this error</span></span>  
  
1. <span data-ttu-id="c8db7-111">Se possibile, determinare la valutazione della funzione precedente e la causa del timeout. In caso contrario, è possibile che si verifichi questo errore.</span><span class="sxs-lookup"><span data-stu-id="c8db7-111">If possible, determine what the previous function evaluation was and what caused it to time out. Otherwise, you might encounter this error again.</span></span>  
  
2. <span data-ttu-id="c8db7-112">Eseguire di nuovo l'istruzione del debugger oppure terminare e riavviare il debug.</span><span class="sxs-lookup"><span data-stu-id="c8db7-112">Either step the debugger again, or terminate and restart debugging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8db7-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8db7-113">See also</span></span>

- [<span data-ttu-id="c8db7-114">Debug in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c8db7-114">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugger-feature-tour)
- [<span data-ttu-id="c8db7-115">Spostarsi nel codice con il Debugger</span><span class="sxs-lookup"><span data-stu-id="c8db7-115">Navigating through Code with the Debugger</span></span>](/visualstudio/debugger/navigating-through-code-with-the-debugger)
