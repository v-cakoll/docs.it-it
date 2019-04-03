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
ms.openlocfilehash: 80d6734945324f3f517b256051486273f6b687ec
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58827991"
---
# <a name="stop-statement-visual-basic"></a><span data-ttu-id="e010e-102">Istruzione Stop (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e010e-102">Stop Statement (Visual Basic)</span></span>
<span data-ttu-id="e010e-103">Sospende l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e010e-103">Suspends execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e010e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e010e-104">Syntax</span></span>  
  
```  
Stop  
```  
  
## <a name="remarks"></a><span data-ttu-id="e010e-105">Note</span><span class="sxs-lookup"><span data-stu-id="e010e-105">Remarks</span></span>  
 <span data-ttu-id="e010e-106">È possibile inserire `Stop` istruzioni in un punto qualsiasi nelle procedure per sospendere l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e010e-106">You can place `Stop` statements anywhere in procedures to suspend execution.</span></span> <span data-ttu-id="e010e-107">Uso di `Stop` istruzione è simile all'impostazione di un punto di interruzione nel codice.</span><span class="sxs-lookup"><span data-stu-id="e010e-107">Using the `Stop` statement is similar to setting a breakpoint in the code.</span></span>  
  
 <span data-ttu-id="e010e-108">Il `Stop` istruzione sospende l'esecuzione, ma a differenza `End`, non chiudere qualsiasi file o cancellare le variabili di qualsiasi tipo, a meno che non si è verificato in un file eseguibile compilato (.exe).</span><span class="sxs-lookup"><span data-stu-id="e010e-108">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e010e-109">Se il `Stop` viene rilevata l'istruzione nel codice che è in esecuzione all'esterno dell'ambiente di sviluppo integrato (IDE), il debugger viene richiamato.</span><span class="sxs-lookup"><span data-stu-id="e010e-109">If the `Stop` statement is encountered in code that is running outside of the integrated development environment (IDE), the debugger is invoked.</span></span> <span data-ttu-id="e010e-110">Questo vale indipendentemente dal fatto che il codice è stato compilato in modalità di debug o di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="e010e-110">This is true regardless of whether the code was compiled in debug or retail mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e010e-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="e010e-111">Example</span></span>  
 <span data-ttu-id="e010e-112">Questo esempio Usa la `Stop` istruzione per sospendere l'esecuzione per ogni iterazione attraverso la `For...Next` ciclo.</span><span class="sxs-lookup"><span data-stu-id="e010e-112">This example uses the `Stop` statement to suspend execution for each iteration through the `For...Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="e010e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e010e-113">See also</span></span>

- [<span data-ttu-id="e010e-114">Istruzione End</span><span class="sxs-lookup"><span data-stu-id="e010e-114">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
