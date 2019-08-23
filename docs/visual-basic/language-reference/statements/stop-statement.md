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
ms.openlocfilehash: a617038ec51d98c62b6cf7e3c124c8af01305bac
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957625"
---
# <a name="stop-statement-visual-basic"></a><span data-ttu-id="0e1cd-102">Istruzione Stop (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0e1cd-102">Stop Statement (Visual Basic)</span></span>
<span data-ttu-id="0e1cd-103">Sospende l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0e1cd-103">Suspends execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e1cd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0e1cd-104">Syntax</span></span>  
  
```  
Stop  
```  
  
## <a name="remarks"></a><span data-ttu-id="0e1cd-105">Note</span><span class="sxs-lookup"><span data-stu-id="0e1cd-105">Remarks</span></span>  
 <span data-ttu-id="0e1cd-106">È possibile inserire `Stop` istruzioni in qualsiasi punto delle procedure per sospendere l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0e1cd-106">You can place `Stop` statements anywhere in procedures to suspend execution.</span></span> <span data-ttu-id="0e1cd-107">L'utilizzo `Stop` dell'istruzione è simile all'impostazione di un punto di interruzione nel codice.</span><span class="sxs-lookup"><span data-stu-id="0e1cd-107">Using the `Stop` statement is similar to setting a breakpoint in the code.</span></span>  
  
 <span data-ttu-id="0e1cd-108">L' `Stop` istruzione sospende l'esecuzione, ma, a `End`differenza di, non chiude alcun file né cancella alcuna variabile, a meno che non venga rilevata in un file eseguibile compilato (exe).</span><span class="sxs-lookup"><span data-stu-id="0e1cd-108">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0e1cd-109">Se l' `Stop` istruzione viene rilevata nel codice in esecuzione all'esterno del Integrated Development Environment (IDE), il debugger viene richiamato.</span><span class="sxs-lookup"><span data-stu-id="0e1cd-109">If the `Stop` statement is encountered in code that is running outside of the integrated development environment (IDE), the debugger is invoked.</span></span> <span data-ttu-id="0e1cd-110">Questo vale indipendentemente dal fatto che il codice sia stato compilato in modalità debug o al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="0e1cd-110">This is true regardless of whether the code was compiled in debug or retail mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e1cd-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="0e1cd-111">Example</span></span>  
 <span data-ttu-id="0e1cd-112">In questo esempio viene `Stop` utilizzata l'istruzione per sospendere l'esecuzione per `For...Next` ogni iterazione del ciclo.</span><span class="sxs-lookup"><span data-stu-id="0e1cd-112">This example uses the `Stop` statement to suspend execution for each iteration through the `For...Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="0e1cd-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e1cd-113">See also</span></span>

- [<span data-ttu-id="0e1cd-114">Istruzione End</span><span class="sxs-lookup"><span data-stu-id="0e1cd-114">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
