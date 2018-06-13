---
title: Istruzione Stop (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Stop
helpviewer_keywords:
- breakpoints, Stop statements
- Stop statements [Visual Basic], syntax
- Stop statements [Visual Basic]
- execution [Visual Basic], suspending
- processing, interrupting
- processes, interrupting
- execution [Visual Basic], stopping
ms.assetid: c9a9fde0-d649-4662-9bef-bd0146ebc2a7
ms.openlocfilehash: 955a3b6a2f7dc1d0e9823ed6d500ab7f7f9fe5b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33599135"
---
# <a name="stop-statement-visual-basic"></a><span data-ttu-id="5b612-102">Istruzione Stop (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b612-102">Stop Statement (Visual Basic)</span></span>
<span data-ttu-id="5b612-103">Sospende l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5b612-103">Suspends execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b612-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5b612-104">Syntax</span></span>  
  
```  
Stop  
```  
  
## <a name="remarks"></a><span data-ttu-id="5b612-105">Note</span><span class="sxs-lookup"><span data-stu-id="5b612-105">Remarks</span></span>  
 <span data-ttu-id="5b612-106">È possibile inserire `Stop` istruzioni in un punto qualsiasi nelle procedure per sospendere l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5b612-106">You can place `Stop` statements anywhere in procedures to suspend execution.</span></span> <span data-ttu-id="5b612-107">Utilizzo di `Stop` istruzione è simile all'impostazione di un punto di interruzione nel codice.</span><span class="sxs-lookup"><span data-stu-id="5b612-107">Using the `Stop` statement is similar to setting a breakpoint in the code.</span></span>  
  
 <span data-ttu-id="5b612-108">Il `Stop` istruzione sospende l'esecuzione, ma a differenza `End`, non chiudere qualsiasi file o deselezionare tutte le variabili, a meno che non viene rilevata in un file eseguibile compilato (.exe).</span><span class="sxs-lookup"><span data-stu-id="5b612-108">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5b612-109">Se il `Stop` viene rilevata l'istruzione nel codice che è in esecuzione all'esterno dell'ambiente di sviluppo integrato (IDE), il debugger viene richiamato.</span><span class="sxs-lookup"><span data-stu-id="5b612-109">If the `Stop` statement is encountered in code that is running outside of the integrated development environment (IDE), the debugger is invoked.</span></span> <span data-ttu-id="5b612-110">Questo vale indipendentemente dal fatto che il codice è stato compilato in modalità di debug o finale.</span><span class="sxs-lookup"><span data-stu-id="5b612-110">This is true regardless of whether the code was compiled in debug or retail mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b612-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="5b612-111">Example</span></span>  
 <span data-ttu-id="5b612-112">Questo esempio viene utilizzato il `Stop` istruzione per sospendere l'esecuzione per ogni iterazione di `For...Next` ciclo.</span><span class="sxs-lookup"><span data-stu-id="5b612-112">This example uses the `Stop` statement to suspend execution for each iteration through the `For...Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#56](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/stop-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="5b612-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b612-113">See Also</span></span>  
 [<span data-ttu-id="5b612-114">Istruzione End</span><span class="sxs-lookup"><span data-stu-id="5b612-114">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
