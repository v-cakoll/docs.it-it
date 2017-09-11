---
title: Valutazione della funzione disabilitata a causa del timeout di una valutazione della funzione precedente | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30957
- vbc30957
dev_langs:
- VB
helpviewer_keywords:
- BC30957
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 127f89f4c7ddaf794f58707d8925731a511f3740
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="function-evaluation-is-disabled-because-a-previous-function-evaluation-timed-out"></a><span data-ttu-id="f00ef-102">Valutazione della funzione disabilitata a causa del timeout di una valutazione di funzione precedente</span><span class="sxs-lookup"><span data-stu-id="f00ef-102">Function evaluation is disabled because a previous function evaluation timed out</span></span>
<span data-ttu-id="f00ef-103">Valutazione della funzione disabilitata a causa del timeout di una valutazione della funzione precedente.</span><span class="sxs-lookup"><span data-stu-id="f00ef-103">Function evaluation is disabled because a previous function evaluation timed out.</span></span> <span data-ttu-id="f00ef-104">Per abilitare nuovamente la valutazione della funzione, ripetere l'operazione o riavviare il debug.</span><span class="sxs-lookup"><span data-stu-id="f00ef-104">To re-enable function evaluation, step again or restart debugging.</span></span>  
  
 <span data-ttu-id="f00ef-105">Nel debugger di Visual Studio, un'espressione specifica una chiamata di procedura, ma un altro di valutazione è scaduta.</span><span class="sxs-lookup"><span data-stu-id="f00ef-105">In the Visual Studio debugger, an expression specifies a procedure call, but another evaluation has timed out.</span></span>  
  
 <span data-ttu-id="f00ef-106">Possibili cause per una chiamata di procedura timeout includono un ciclo infinito o *ciclo infinito*.</span><span class="sxs-lookup"><span data-stu-id="f00ef-106">Possible causes for a procedure call to time out include an infinite loop or *endless loop*.</span></span> <span data-ttu-id="f00ef-107">Per ulteriori informazioni, vedere [per... Istruzione successiva](../../../visual-basic/language-reference/statements/for-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f00ef-107">For more information, see [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md).</span></span>  
  
 <span data-ttu-id="f00ef-108">Un caso speciale di ciclo infinito è *ricorsione*.</span><span class="sxs-lookup"><span data-stu-id="f00ef-108">A special case of an infinite loop is *recursion*.</span></span> <span data-ttu-id="f00ef-109">Per ulteriori informazioni, vedere [routine ricorsive](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="f00ef-109">For more information, see [Recursive Procedures](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md).</span></span>  
  
 <span data-ttu-id="f00ef-110">**ID errore:** BC30957</span><span class="sxs-lookup"><span data-stu-id="f00ef-110">**Error ID:** BC30957</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f00ef-111">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="f00ef-111">To correct this error</span></span>  
  
1.  <span data-ttu-id="f00ef-112">Se possibile, stabilire qual è la valutazione della funzione precedente e la relativa causa il timeout.</span><span class="sxs-lookup"><span data-stu-id="f00ef-112">If possible, determine what the previous function evaluation was and what caused it to time out.</span></span> <span data-ttu-id="f00ef-113">In caso contrario, questo errore potrebbe verificarsi nuovamente.</span><span class="sxs-lookup"><span data-stu-id="f00ef-113">Otherwise, you might encounter this error again.</span></span>  
  
2.  <span data-ttu-id="f00ef-114">Eseguire nuovamente il debugger o terminare e riavviare il debug.</span><span class="sxs-lookup"><span data-stu-id="f00ef-114">Either step the debugger again, or terminate and restart debugging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f00ef-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f00ef-115">See Also</span></span>  
 <span data-ttu-id="f00ef-116">[Debugging in Visual Studio](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio)  (Debug in Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="f00ef-116">[Debugging in Visual Studio](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio) </span></span>  
<span data-ttu-id="f00ef-117"> [Spostarsi nel codice con il Debugger](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)</span><span class="sxs-lookup"><span data-stu-id="f00ef-117"> [Navigating through Code with the Debugger](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)</span></span>
