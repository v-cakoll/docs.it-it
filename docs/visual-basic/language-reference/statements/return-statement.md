---
title: Istruzione Return
ms.date: 07/20/2015
f1_keywords:
- vb.Return
helpviewer_keywords:
- Return statement [Visual Basic], syntax
- control flow [Visual Basic], returning control to expressions
- Return statement [Visual Basic]
- expressions [Visual Basic], returning control to
ms.assetid: ac86e7f0-5a67-42c3-9834-0e0381efa3ec
ms.openlocfilehash: efc85a3a844898345aa2d16926ba0e35d7346d1b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333020"
---
# <a name="return-statement-visual-basic"></a><span data-ttu-id="bcd94-102">Istruzione Return (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bcd94-102">Return Statement (Visual Basic)</span></span>
<span data-ttu-id="bcd94-103">Returns control to the code that called a `Function`, `Sub`, `Get`, `Set`, or `Operator` procedure.</span><span class="sxs-lookup"><span data-stu-id="bcd94-103">Returns control to the code that called a `Function`, `Sub`, `Get`, `Set`, or `Operator` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcd94-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bcd94-104">Syntax</span></span>  
  
```vb  
Return  
' -or-  
Return expression  
```  
  
## <a name="part"></a><span data-ttu-id="bcd94-105">Parte</span><span class="sxs-lookup"><span data-stu-id="bcd94-105">Part</span></span>  
 `expression`  
 <span data-ttu-id="bcd94-106">Required in a `Function`, `Get`, or `Operator` procedure.</span><span class="sxs-lookup"><span data-stu-id="bcd94-106">Required in a `Function`, `Get`, or `Operator` procedure.</span></span> <span data-ttu-id="bcd94-107">Expression that represents the value to be returned to the calling code.</span><span class="sxs-lookup"><span data-stu-id="bcd94-107">Expression that represents the value to be returned to the calling code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bcd94-108">Note</span><span class="sxs-lookup"><span data-stu-id="bcd94-108">Remarks</span></span>  
 <span data-ttu-id="bcd94-109">In a `Sub` or `Set` procedure, the `Return` statement is equivalent to an `Exit Sub` or `Exit Property` statement, and `expression` must not be supplied.</span><span class="sxs-lookup"><span data-stu-id="bcd94-109">In a `Sub` or `Set` procedure, the `Return` statement is equivalent to an `Exit Sub` or `Exit Property` statement, and `expression` must not be supplied.</span></span>  
  
 <span data-ttu-id="bcd94-110">In a `Function`, `Get`, or `Operator` procedure, the `Return` statement must include `expression`, and `expression` must evaluate to a data type that is convertible to the return type of the procedure.</span><span class="sxs-lookup"><span data-stu-id="bcd94-110">In a `Function`, `Get`, or `Operator` procedure, the `Return` statement must include `expression`, and `expression` must evaluate to a data type that is convertible to the return type of the procedure.</span></span> <span data-ttu-id="bcd94-111">In a `Function` or `Get` procedure, you also have the alternative of assigning an expression to the procedure name to serve as the return value, and then executing an `Exit Function` or `Exit Property` statement.</span><span class="sxs-lookup"><span data-stu-id="bcd94-111">In a `Function` or `Get` procedure, you also have the alternative of assigning an expression to the procedure name to serve as the return value, and then executing an `Exit Function` or `Exit Property` statement.</span></span> <span data-ttu-id="bcd94-112">In an `Operator` procedure, you must use `Return expression`.</span><span class="sxs-lookup"><span data-stu-id="bcd94-112">In an `Operator` procedure, you must use `Return expression`.</span></span>  
  
 <span data-ttu-id="bcd94-113">You can include as many `Return` statements as appropriate in the same procedure.</span><span class="sxs-lookup"><span data-stu-id="bcd94-113">You can include as many `Return` statements as appropriate in the same procedure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bcd94-114">The code in a `Finally` block runs after a `Return` statement in a `Try` or `Catch` block is encountered, but before that `Return` statement executes.</span><span class="sxs-lookup"><span data-stu-id="bcd94-114">The code in a `Finally` block runs after a `Return` statement in a `Try` or `Catch` block is encountered, but before that `Return` statement executes.</span></span> <span data-ttu-id="bcd94-115">A `Return` statement cannot be included in a `Finally` block.</span><span class="sxs-lookup"><span data-stu-id="bcd94-115">A `Return` statement cannot be included in a `Finally` block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bcd94-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="bcd94-116">Example</span></span>  
 <span data-ttu-id="bcd94-117">The following example uses the `Return` statement several times to return to the calling code when the procedure does not have to do anything else.</span><span class="sxs-lookup"><span data-stu-id="bcd94-117">The following example uses the `Return` statement several times to return to the calling code when the procedure does not have to do anything else.</span></span>  
  
 [!code-vb[VbVbalrStatements#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#53)]  
  
## <a name="see-also"></a><span data-ttu-id="bcd94-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bcd94-118">See also</span></span>

- [<span data-ttu-id="bcd94-119">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="bcd94-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="bcd94-120">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="bcd94-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="bcd94-121">Istruzione Get</span><span class="sxs-lookup"><span data-stu-id="bcd94-121">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="bcd94-122">Istruzione Set</span><span class="sxs-lookup"><span data-stu-id="bcd94-122">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
- [<span data-ttu-id="bcd94-123">Istruzione Operator</span><span class="sxs-lookup"><span data-stu-id="bcd94-123">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="bcd94-124">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="bcd94-124">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="bcd94-125">Istruzione Exit</span><span class="sxs-lookup"><span data-stu-id="bcd94-125">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="bcd94-126">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="bcd94-126">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
