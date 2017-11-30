---
title: Valutazione della funzione disabilitata a causa del timeout di una valutazione di funzione precedente
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30957
- vbc30957
helpviewer_keywords: BC30957
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 05067e730486b443b7a508adb499f34c060d5093
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="function-evaluation-is-disabled-because-a-previous-function-evaluation-timed-out"></a><span data-ttu-id="79267-102">Valutazione della funzione disabilitata a causa del timeout di una valutazione di funzione precedente</span><span class="sxs-lookup"><span data-stu-id="79267-102">Function evaluation is disabled because a previous function evaluation timed out</span></span>
<span data-ttu-id="79267-103">La valutazione della funzione è disabilitata a causa del timeout di una valutazione della funzione precedente. Per riabilitare la valutazione della funzione, riprovare o riavviare il debug.</span><span class="sxs-lookup"><span data-stu-id="79267-103">Function evaluation is disabled because a previous function evaluation timed out. To re-enable function evaluation, step again or restart debugging.</span></span>  
  
 <span data-ttu-id="79267-104">Nel debugger di Visual Studio, un'espressione specifica una chiamata di routine, ma un'altra valutazione è scaduta.</span><span class="sxs-lookup"><span data-stu-id="79267-104">In the Visual Studio debugger, an expression specifies a procedure call, but another evaluation has timed out.</span></span>  
  
 <span data-ttu-id="79267-105">Possibili cause per una chiamata di routine timeout includono un ciclo infinito o *ciclo infinito*.</span><span class="sxs-lookup"><span data-stu-id="79267-105">Possible causes for a procedure call to time out include an infinite loop or *endless loop*.</span></span> <span data-ttu-id="79267-106">Per ulteriori informazioni, vedere [per... Istruzione successiva](../../../visual-basic/language-reference/statements/for-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="79267-106">For more information, see [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md).</span></span>  
  
 <span data-ttu-id="79267-107">È un caso speciale di un ciclo infinito *ricorsione*.</span><span class="sxs-lookup"><span data-stu-id="79267-107">A special case of an infinite loop is *recursion*.</span></span> <span data-ttu-id="79267-108">Per ulteriori informazioni, vedere [routine ricorsive](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="79267-108">For more information, see [Recursive Procedures](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md).</span></span>  
  
 <span data-ttu-id="79267-109">**ID errore:** BC30957</span><span class="sxs-lookup"><span data-stu-id="79267-109">**Error ID:** BC30957</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="79267-110">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="79267-110">To correct this error</span></span>  
  
1.  <span data-ttu-id="79267-111">Se possibile, determinare qual era la valutazione della funzione precedente e la relativa causa il timeout. In caso contrario, questo errore potrebbe verificarsi nuovamente.</span><span class="sxs-lookup"><span data-stu-id="79267-111">If possible, determine what the previous function evaluation was and what caused it to time out. Otherwise, you might encounter this error again.</span></span>  
  
2.  <span data-ttu-id="79267-112">Eseguire nuovamente il debugger o terminare e riavviare il debug.</span><span class="sxs-lookup"><span data-stu-id="79267-112">Either step the debugger again, or terminate and restart debugging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79267-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79267-113">See Also</span></span>  
 [<span data-ttu-id="79267-114">Debug in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="79267-114">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)  
 [<span data-ttu-id="79267-115">Spostarsi nel codice con il Debugger</span><span class="sxs-lookup"><span data-stu-id="79267-115">Navigating through Code with the Debugger</span></span>](/visualstudio/debugger/navigating-through-code-with-the-debugger)
