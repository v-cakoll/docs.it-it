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
ms.openlocfilehash: e9382ee34842fc3a3b4b23f71848bda602c99780
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583227"
---
# <a name="stop-statement-visual-basic"></a><span data-ttu-id="afeb6-102">Istruzione Stop (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="afeb6-102">Stop Statement (Visual Basic)</span></span>
<span data-ttu-id="afeb6-103">Sospende l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="afeb6-103">Suspends execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afeb6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="afeb6-104">Syntax</span></span>  
  
```vb  
Stop  
```  
  
## <a name="remarks"></a><span data-ttu-id="afeb6-105">Note</span><span class="sxs-lookup"><span data-stu-id="afeb6-105">Remarks</span></span>  
 <span data-ttu-id="afeb6-106">Per sospendere l'esecuzione, è possibile inserire `Stop` istruzioni in qualsiasi punto delle procedure.</span><span class="sxs-lookup"><span data-stu-id="afeb6-106">You can place `Stop` statements anywhere in procedures to suspend execution.</span></span> <span data-ttu-id="afeb6-107">L'utilizzo dell'istruzione `Stop` è simile all'impostazione di un punto di interruzione nel codice.</span><span class="sxs-lookup"><span data-stu-id="afeb6-107">Using the `Stop` statement is similar to setting a breakpoint in the code.</span></span>  
  
 <span data-ttu-id="afeb6-108">L'istruzione `Stop` sospende l'esecuzione, ma a differenza di `End` non chiude alcun file né cancella alcuna variabile, a meno che non venga rilevata in un file eseguibile compilato (exe).</span><span class="sxs-lookup"><span data-stu-id="afeb6-108">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="afeb6-109">Se l'istruzione `Stop` viene rilevata nel codice in esecuzione all'esterno del Integrated Development Environment (IDE), il debugger viene richiamato.</span><span class="sxs-lookup"><span data-stu-id="afeb6-109">If the `Stop` statement is encountered in code that is running outside of the integrated development environment (IDE), the debugger is invoked.</span></span> <span data-ttu-id="afeb6-110">Questo vale indipendentemente dal fatto che il codice sia stato compilato in modalità debug o al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="afeb6-110">This is true regardless of whether the code was compiled in debug or retail mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="afeb6-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="afeb6-111">Example</span></span>  
 <span data-ttu-id="afeb6-112">In questo esempio viene utilizzata l'istruzione `Stop` per sospendere l'esecuzione per ogni iterazione nel ciclo di `For...Next`.</span><span class="sxs-lookup"><span data-stu-id="afeb6-112">This example uses the `Stop` statement to suspend execution for each iteration through the `For...Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="afeb6-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="afeb6-113">See also</span></span>

- [<span data-ttu-id="afeb6-114">Istruzione End</span><span class="sxs-lookup"><span data-stu-id="afeb6-114">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
