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
ms.openlocfilehash: af49ea95d7f9d01072190ac3ccf6ba2f1041347e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957669"
---
# <a name="return-statement-visual-basic"></a><span data-ttu-id="63624-102">Istruzione Return (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63624-102">Return Statement (Visual Basic)</span></span>
<span data-ttu-id="63624-103">Restituisce il controllo al codice che ha chiamato `Function`una `Sub`routine `Get`, `Set`,, `Operator` o.</span><span class="sxs-lookup"><span data-stu-id="63624-103">Returns control to the code that called a `Function`, `Sub`, `Get`, `Set`, or `Operator` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63624-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="63624-104">Syntax</span></span>  
  
```  
Return  
-or-  
Return expression  
```  
  
## <a name="part"></a><span data-ttu-id="63624-105">Parte</span><span class="sxs-lookup"><span data-stu-id="63624-105">Part</span></span>  
 `expression`  
 <span data-ttu-id="63624-106">Obbligatorio in una `Function`procedura `Get`, o `Operator` .</span><span class="sxs-lookup"><span data-stu-id="63624-106">Required in a `Function`, `Get`, or `Operator` procedure.</span></span> <span data-ttu-id="63624-107">Espressione che rappresenta il valore da restituire al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="63624-107">Expression that represents the value to be returned to the calling code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63624-108">Note</span><span class="sxs-lookup"><span data-stu-id="63624-108">Remarks</span></span>  
 <span data-ttu-id="63624-109">In una `Sub` routine `Set` o l' `Return` istruzione è equivalente a un' `Exit Sub` istruzione o `Exit Property` e `expression` non deve essere fornita.</span><span class="sxs-lookup"><span data-stu-id="63624-109">In a `Sub` or `Set` procedure, the `Return` statement is equivalent to an `Exit Sub` or `Exit Property` statement, and `expression` must not be supplied.</span></span>  
  
 <span data-ttu-id="63624-110">In una `Function`routine `Get`, o `Operator` , l' `Return` istruzione deve includere `expression`e `expression` deve restituire un tipo di dati convertibile nel tipo restituito della routine.</span><span class="sxs-lookup"><span data-stu-id="63624-110">In a `Function`, `Get`, or `Operator` procedure, the `Return` statement must include `expression`, and `expression` must evaluate to a data type that is convertible to the return type of the procedure.</span></span> <span data-ttu-id="63624-111">In una `Function` routine `Get` o è inoltre possibile assegnare un'espressione al nome della stored procedure per fungere da valore restituito e quindi eseguire un' `Exit Function` istruzione o `Exit Property` .</span><span class="sxs-lookup"><span data-stu-id="63624-111">In a `Function` or `Get` procedure, you also have the alternative of assigning an expression to the procedure name to serve as the return value, and then executing an `Exit Function` or `Exit Property` statement.</span></span> <span data-ttu-id="63624-112">In una `Operator` procedura è necessario utilizzare `Return expression`.</span><span class="sxs-lookup"><span data-stu-id="63624-112">In an `Operator` procedure, you must use `Return expression`.</span></span>  
  
 <span data-ttu-id="63624-113">È possibile includere `Return` tutte le istruzioni appropriate nella stessa procedura.</span><span class="sxs-lookup"><span data-stu-id="63624-113">You can include as many `Return` statements as appropriate in the same procedure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="63624-114">Il codice in un `Finally` blocco viene eseguito dopo `Return` che `Return` un'istruzione `Try` in `Catch` un blocco o viene rilevata, ma prima dell'esecuzione dell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="63624-114">The code in a `Finally` block runs after a `Return` statement in a `Try` or `Catch` block is encountered, but before that `Return` statement executes.</span></span> <span data-ttu-id="63624-115">Un' `Return` istruzione non può essere inclusa in `Finally` un blocco.</span><span class="sxs-lookup"><span data-stu-id="63624-115">A `Return` statement cannot be included in a `Finally` block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63624-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="63624-116">Example</span></span>  
 <span data-ttu-id="63624-117">Nell'esempio seguente l' `Return` istruzione viene utilizzata più volte per tornare al codice chiamante quando la procedura non deve eseguire altre operazioni.</span><span class="sxs-lookup"><span data-stu-id="63624-117">The following example uses the `Return` statement several times to return to the calling code when the procedure does not have to do anything else.</span></span>  
  
 [!code-vb[VbVbalrStatements#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#53)]  
  
## <a name="see-also"></a><span data-ttu-id="63624-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63624-118">See also</span></span>

- [<span data-ttu-id="63624-119">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="63624-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="63624-120">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="63624-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="63624-121">Istruzione Get</span><span class="sxs-lookup"><span data-stu-id="63624-121">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="63624-122">Istruzione Set</span><span class="sxs-lookup"><span data-stu-id="63624-122">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
- [<span data-ttu-id="63624-123">Istruzione Operator</span><span class="sxs-lookup"><span data-stu-id="63624-123">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="63624-124">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="63624-124">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="63624-125">Istruzione Exit</span><span class="sxs-lookup"><span data-stu-id="63624-125">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="63624-126">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="63624-126">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
