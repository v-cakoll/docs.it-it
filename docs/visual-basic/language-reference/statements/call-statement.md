---
title: Istruzione Call (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Call
helpviewer_keywords:
- procedures [Visual Basic], Call statement
- Call statement [Visual Basic]
- procedures [Visual Basic], calling
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
ms.openlocfilehash: 755443a99a1ad8b0430a76d2dba1ff27472d4c9d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58832645"
---
# <a name="call-statement-visual-basic"></a><span data-ttu-id="e0be6-102">Istruzione Call (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0be6-102">Call Statement (Visual Basic)</span></span>
<span data-ttu-id="e0be6-103">Trasferisce il controllo a un `Function`, `Sub`, o una routine di libreria di collegamento dinamico (DLL).</span><span class="sxs-lookup"><span data-stu-id="e0be6-103">Transfers control to a `Function`, `Sub`, or dynamic-link library (DLL) procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0be6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e0be6-104">Syntax</span></span>  
  
```  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## <a name="parts"></a><span data-ttu-id="e0be6-105">Parti</span><span class="sxs-lookup"><span data-stu-id="e0be6-105">Parts</span></span>  
|||
|---|---|
|`procedureName`|<span data-ttu-id="e0be6-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="e0be6-106">Required.</span></span> <span data-ttu-id="e0be6-107">Nome della routine da chiamare.</span><span class="sxs-lookup"><span data-stu-id="e0be6-107">Name of the procedure to call.</span></span>|
|`argumentList`|<span data-ttu-id="e0be6-108">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="e0be6-108">Optional.</span></span> <span data-ttu-id="e0be6-109">Elenco di variabili o espressioni che rappresentano gli argomenti passati alla procedura quando viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="e0be6-109">List of variables or expressions representing arguments that are passed to the procedure when it is called.</span></span> <span data-ttu-id="e0be6-110">Più argomenti sono separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="e0be6-110">Multiple arguments are separated by commas.</span></span> <span data-ttu-id="e0be6-111">Se si includono `argumentList`, è necessario racchiuderlo tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="e0be6-111">If you include `argumentList`, you must enclose it in parentheses.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="e0be6-112">Note</span><span class="sxs-lookup"><span data-stu-id="e0be6-112">Remarks</span></span>  
 <span data-ttu-id="e0be6-113">È possibile usare il `Call` parola chiave quando si chiama una routine.</span><span class="sxs-lookup"><span data-stu-id="e0be6-113">You can use the `Call` keyword when you call a procedure.</span></span> <span data-ttu-id="e0be6-114">Per la maggior parte delle chiamate di routine, non è necessario utilizzare questa parola chiave.</span><span class="sxs-lookup"><span data-stu-id="e0be6-114">For most procedure calls, you aren’t required to use this  keyword.</span></span>  
  
 <span data-ttu-id="e0be6-115">In genere si usa il `Call` parola chiave quando l'espressione di chiamata non inizia con un identificatore.</span><span class="sxs-lookup"><span data-stu-id="e0be6-115">You typically use the `Call` keyword when the called expression doesn’t start with an identifier.</span></span> <span data-ttu-id="e0be6-116">Usare il `Call` non è consigliabile la parola chiave per altri usi.</span><span class="sxs-lookup"><span data-stu-id="e0be6-116">Use of the `Call` keyword for other uses isn’t recommended.</span></span>  
  
 <span data-ttu-id="e0be6-117">Se la routine restituisce un valore, il `Call` istruzione lo ignora.</span><span class="sxs-lookup"><span data-stu-id="e0be6-117">If the procedure returns a value, the `Call` statement discards it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0be6-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="e0be6-118">Example</span></span>  
 <span data-ttu-id="e0be6-119">Il codice seguente mostra due esempi in cui il `Call` parola chiave è necessario chiamare una routine.</span><span class="sxs-lookup"><span data-stu-id="e0be6-119">The following code shows two examples where the `Call` keyword is necessary to call a procedure.</span></span> <span data-ttu-id="e0be6-120">In entrambi gli esempi, l'espressione di chiamata non inizia con un identificatore.</span><span class="sxs-lookup"><span data-stu-id="e0be6-120">In both examples, the called expression doesn't start with an identifier.</span></span>  
  
 [!code-vb[VbVbalrStatements#97](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#97)]  
  
## <a name="see-also"></a><span data-ttu-id="e0be6-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0be6-121">See also</span></span>

- [<span data-ttu-id="e0be6-122">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="e0be6-122">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="e0be6-123">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="e0be6-123">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="e0be6-124">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="e0be6-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="e0be6-125">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="e0be6-125">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
