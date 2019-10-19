---
title: Istruzione Return (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Return
helpviewer_keywords:
- Return statement [Visual Basic], syntax
- control flow [Visual Basic], returning control to expressions
- Return statement [Visual Basic]
- expressions [Visual Basic], returning control to
ms.assetid: ac86e7f0-5a67-42c3-9834-0e0381efa3ec
ms.openlocfilehash: edaaf09f5a984344f7e89c9da988c529774934e9
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583262"
---
# <a name="return-statement-visual-basic"></a><span data-ttu-id="09d47-102">Istruzione Return (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="09d47-102">Return Statement (Visual Basic)</span></span>
<span data-ttu-id="09d47-103">Restituisce il controllo al codice che ha chiamato una procedura di `Function`, `Sub`, `Get`, `Set` o `Operator`.</span><span class="sxs-lookup"><span data-stu-id="09d47-103">Returns control to the code that called a `Function`, `Sub`, `Get`, `Set`, or `Operator` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09d47-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="09d47-104">Syntax</span></span>  
  
```vb  
Return  
' -or-  
Return expression  
```  
  
## <a name="part"></a><span data-ttu-id="09d47-105">Parte</span><span class="sxs-lookup"><span data-stu-id="09d47-105">Part</span></span>  
 `expression`  
 <span data-ttu-id="09d47-106">Obbligatorio in una procedura `Function`, `Get` o `Operator`.</span><span class="sxs-lookup"><span data-stu-id="09d47-106">Required in a `Function`, `Get`, or `Operator` procedure.</span></span> <span data-ttu-id="09d47-107">Espressione che rappresenta il valore da restituire al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="09d47-107">Expression that represents the value to be returned to the calling code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="09d47-108">Note</span><span class="sxs-lookup"><span data-stu-id="09d47-108">Remarks</span></span>  
 <span data-ttu-id="09d47-109">In una procedura `Sub` o `Set`, l'istruzione `Return` è equivalente a un'istruzione `Exit Sub` o `Exit Property` e non è necessario fornire `expression`.</span><span class="sxs-lookup"><span data-stu-id="09d47-109">In a `Sub` or `Set` procedure, the `Return` statement is equivalent to an `Exit Sub` or `Exit Property` statement, and `expression` must not be supplied.</span></span>  
  
 <span data-ttu-id="09d47-110">In una procedura `Function`, `Get` o `Operator`, l'istruzione `Return` deve includere `expression` e `expression` deve restituire un tipo di dati convertibile nel tipo restituito della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="09d47-110">In a `Function`, `Get`, or `Operator` procedure, the `Return` statement must include `expression`, and `expression` must evaluate to a data type that is convertible to the return type of the procedure.</span></span> <span data-ttu-id="09d47-111">In una procedura `Function` o `Get` è inoltre possibile assegnare un'espressione al nome della stored procedure per fungere da valore restituito, quindi eseguire un'istruzione `Exit Function` o `Exit Property`.</span><span class="sxs-lookup"><span data-stu-id="09d47-111">In a `Function` or `Get` procedure, you also have the alternative of assigning an expression to the procedure name to serve as the return value, and then executing an `Exit Function` or `Exit Property` statement.</span></span> <span data-ttu-id="09d47-112">In una procedura `Operator` è necessario usare `Return expression`.</span><span class="sxs-lookup"><span data-stu-id="09d47-112">In an `Operator` procedure, you must use `Return expression`.</span></span>  
  
 <span data-ttu-id="09d47-113">È possibile includere il numero di istruzioni `Return` appropriate nella stessa procedura.</span><span class="sxs-lookup"><span data-stu-id="09d47-113">You can include as many `Return` statements as appropriate in the same procedure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="09d47-114">Il codice in un blocco `Finally` viene eseguito dopo che è stata rilevata un'istruzione `Return` in un blocco `Try` o `Catch`, ma prima che venga eseguita l'istruzione `Return`.</span><span class="sxs-lookup"><span data-stu-id="09d47-114">The code in a `Finally` block runs after a `Return` statement in a `Try` or `Catch` block is encountered, but before that `Return` statement executes.</span></span> <span data-ttu-id="09d47-115">Non è possibile includere un'istruzione `Return` in un blocco di `Finally`.</span><span class="sxs-lookup"><span data-stu-id="09d47-115">A `Return` statement cannot be included in a `Finally` block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09d47-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="09d47-116">Example</span></span>  
 <span data-ttu-id="09d47-117">Nell'esempio seguente viene utilizzata l'istruzione `Return` più volte per tornare al codice chiamante quando la procedura non deve eseguire altre operazioni.</span><span class="sxs-lookup"><span data-stu-id="09d47-117">The following example uses the `Return` statement several times to return to the calling code when the procedure does not have to do anything else.</span></span>  
  
 [!code-vb[VbVbalrStatements#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#53)]  
  
## <a name="see-also"></a><span data-ttu-id="09d47-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09d47-118">See also</span></span>

- [<span data-ttu-id="09d47-119">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="09d47-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="09d47-120">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="09d47-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="09d47-121">Istruzione Get</span><span class="sxs-lookup"><span data-stu-id="09d47-121">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="09d47-122">Istruzione Set</span><span class="sxs-lookup"><span data-stu-id="09d47-122">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
- [<span data-ttu-id="09d47-123">Istruzione Operator</span><span class="sxs-lookup"><span data-stu-id="09d47-123">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="09d47-124">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="09d47-124">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="09d47-125">Istruzione Exit</span><span class="sxs-lookup"><span data-stu-id="09d47-125">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="09d47-126">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="09d47-126">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
