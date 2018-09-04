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
ms.openlocfilehash: fe200add4e29fe4bbe0fdf335dcd94107b8ff1eb
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43537540"
---
# <a name="return-statement-visual-basic"></a><span data-ttu-id="d6a89-102">Istruzione Return (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d6a89-102">Return Statement (Visual Basic)</span></span>
<span data-ttu-id="d6a89-103">Restituisce il controllo al codice che ha chiamato un' `Function`, `Sub`, `Get`, `Set`, o `Operator` procedure.</span><span class="sxs-lookup"><span data-stu-id="d6a89-103">Returns control to the code that called a `Function`, `Sub`, `Get`, `Set`, or `Operator` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6a89-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d6a89-104">Syntax</span></span>  
  
```  
Return  
-or-  
Return expression  
```  
  
## <a name="part"></a><span data-ttu-id="d6a89-105">Parte</span><span class="sxs-lookup"><span data-stu-id="d6a89-105">Part</span></span>  
 `expression`  
 <span data-ttu-id="d6a89-106">Obbligatorio in un `Function`, `Get`, o `Operator` procedure.</span><span class="sxs-lookup"><span data-stu-id="d6a89-106">Required in a `Function`, `Get`, or `Operator` procedure.</span></span> <span data-ttu-id="d6a89-107">Espressione che rappresenta il valore deve essere restituito al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="d6a89-107">Expression that represents the value to be returned to the calling code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6a89-108">Note</span><span class="sxs-lookup"><span data-stu-id="d6a89-108">Remarks</span></span>  
 <span data-ttu-id="d6a89-109">In un `Sub` o `Set` procedure, il `Return` istruzione è equivalente a un `Exit Sub` o `Exit Property` istruzione, e `expression` non deve essere specificato.</span><span class="sxs-lookup"><span data-stu-id="d6a89-109">In a `Sub` or `Set` procedure, the `Return` statement is equivalent to an `Exit Sub` or `Exit Property` statement, and `expression` must not be supplied.</span></span>  
  
 <span data-ttu-id="d6a89-110">In un `Function`, `Get`, o `Operator` routine, il `Return` istruzione deve includere `expression`, e `expression` deve restituire un tipo di dati che è convertibile nel tipo restituito della procedura.</span><span class="sxs-lookup"><span data-stu-id="d6a89-110">In a `Function`, `Get`, or `Operator` procedure, the `Return` statement must include `expression`, and `expression` must evaluate to a data type that is convertible to the return type of the procedure.</span></span> <span data-ttu-id="d6a89-111">In un `Function` oppure `Get` procedura, è l'alternativa di assegnazione di un'espressione per il nome della routine come il valore restituito e quindi eseguendo un `Exit Function` o `Exit Property` istruzione.</span><span class="sxs-lookup"><span data-stu-id="d6a89-111">In a `Function` or `Get` procedure, you also have the alternative of assigning an expression to the procedure name to serve as the return value, and then executing an `Exit Function` or `Exit Property` statement.</span></span> <span data-ttu-id="d6a89-112">In un' `Operator` procedure, è necessario usare `Return expression`.</span><span class="sxs-lookup"><span data-stu-id="d6a89-112">In an `Operator` procedure, you must use `Return expression`.</span></span>  
  
 <span data-ttu-id="d6a89-113">È possibile includere un numero `Return` le istruzioni nel modo appropriato per la stessa procedura.</span><span class="sxs-lookup"><span data-stu-id="d6a89-113">You can include as many `Return` statements as appropriate in the same procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6a89-114">Il codice in un `Finally` blocco viene eseguito dopo un `Return` istruzione in un `Try` oppure `Catch` blocco viene rilevata, ma prima che `Return` istruzione viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="d6a89-114">The code in a `Finally` block runs after a `Return` statement in a `Try` or `Catch` block is encountered, but before that `Return` statement executes.</span></span> <span data-ttu-id="d6a89-115">Oggetto `Return` istruzione non può essere incluso in un `Finally` blocco.</span><span class="sxs-lookup"><span data-stu-id="d6a89-115">A `Return` statement cannot be included in a `Finally` block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6a89-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="d6a89-116">Example</span></span>  
 <span data-ttu-id="d6a89-117">L'esempio seguente usa il `Return` istruzione più volte per tornare al codice chiamante quando la procedura non è necessario eseguire altre operazioni.</span><span class="sxs-lookup"><span data-stu-id="d6a89-117">The following example uses the `Return` statement several times to return to the calling code when the procedure does not have to do anything else.</span></span>  
  
 [!code-vb[VbVbalrStatements#53](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/return-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d6a89-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6a89-118">See Also</span></span>  
 [<span data-ttu-id="d6a89-119">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="d6a89-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="d6a89-120">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="d6a89-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="d6a89-121">Istruzione Get</span><span class="sxs-lookup"><span data-stu-id="d6a89-121">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)  
 [<span data-ttu-id="d6a89-122">Istruzione Set</span><span class="sxs-lookup"><span data-stu-id="d6a89-122">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)  
 [<span data-ttu-id="d6a89-123">Istruzione Operator</span><span class="sxs-lookup"><span data-stu-id="d6a89-123">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="d6a89-124">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="d6a89-124">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="d6a89-125">Istruzione Exit</span><span class="sxs-lookup"><span data-stu-id="d6a89-125">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [<span data-ttu-id="d6a89-126">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="d6a89-126">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
