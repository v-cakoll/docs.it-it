---
title: Istruzione Call (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Call
helpviewer_keywords:
- procedures [Visual Basic], Call statement
- Call statement [Visual Basic]
- procedures [Visual Basic], calling
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c72450fd6f931f36f640d3e384a6fd38d57a7a23
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="call-statement-visual-basic"></a><span data-ttu-id="6593d-102">Istruzione Call (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6593d-102">Call Statement (Visual Basic)</span></span>
<span data-ttu-id="6593d-103">Trasferisce il controllo a un `Function`, `Sub`, o una routine di libreria a collegamento dinamico (DLL).</span><span class="sxs-lookup"><span data-stu-id="6593d-103">Transfers control to a `Function`, `Sub`, or dynamic-link library (DLL) procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6593d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6593d-104">Syntax</span></span>  
  
```  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## <a name="parts"></a><span data-ttu-id="6593d-105">Parti</span><span class="sxs-lookup"><span data-stu-id="6593d-105">Parts</span></span>  
 `procedureName`  
 <span data-ttu-id="6593d-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="6593d-106">Required.</span></span> <span data-ttu-id="6593d-107">Nome della routine da chiamare.</span><span class="sxs-lookup"><span data-stu-id="6593d-107">Name of the procedure to call.</span></span>  
  
 `argumentList`  
 <span data-ttu-id="6593d-108">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="6593d-108">Optional.</span></span> <span data-ttu-id="6593d-109">Elenco di variabili o espressioni che rappresentano gli argomenti passati alla procedura quando viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="6593d-109">List of variables or expressions representing arguments that are passed to the procedure when it is called.</span></span> <span data-ttu-id="6593d-110">Più argomenti sono separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="6593d-110">Multiple arguments are separated by commas.</span></span> <span data-ttu-id="6593d-111">Se si includono `argumentList`, è necessario racchiuderlo tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="6593d-111">If you include `argumentList`, you must enclose it in parentheses.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6593d-112">Note</span><span class="sxs-lookup"><span data-stu-id="6593d-112">Remarks</span></span>  
 <span data-ttu-id="6593d-113">È possibile utilizzare il `Call` parola chiave quando si chiama una routine.</span><span class="sxs-lookup"><span data-stu-id="6593d-113">You can use the `Call` keyword when you call a procedure.</span></span> <span data-ttu-id="6593d-114">Per la maggior parte delle chiamate di procedura, non è necessario utilizzare questa parola chiave.</span><span class="sxs-lookup"><span data-stu-id="6593d-114">For most procedure calls, you aren’t required to use this  keyword.</span></span>  
  
 <span data-ttu-id="6593d-115">In genere si usa il `Call` (parola chiave) quando l'espressione di chiamata non inizia con un identificatore.</span><span class="sxs-lookup"><span data-stu-id="6593d-115">You typically use the `Call` keyword when the called expression doesn’t start with an identifier.</span></span> <span data-ttu-id="6593d-116">Utilizzare il `Call` (parola chiave) per altri utilizzi non è consigliato.</span><span class="sxs-lookup"><span data-stu-id="6593d-116">Use of the `Call` keyword for other uses isn’t recommended.</span></span>  
  
 <span data-ttu-id="6593d-117">Se la routine restituisce un valore, il `Call` istruzione lo ignora.</span><span class="sxs-lookup"><span data-stu-id="6593d-117">If the procedure returns a value, the `Call` statement discards it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6593d-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="6593d-118">Example</span></span>  
 <span data-ttu-id="6593d-119">Il codice riportato di seguito sono illustrati due esempi in cui il `Call` parola chiave è necessaria chiamare una routine.</span><span class="sxs-lookup"><span data-stu-id="6593d-119">The following code shows two examples where the `Call` keyword is necessary to call a procedure.</span></span> <span data-ttu-id="6593d-120">In entrambi gli esempi, l'espressione di chiamata non inizia con un identificatore.</span><span class="sxs-lookup"><span data-stu-id="6593d-120">In both examples, the called expression doesn't start with an identifier.</span></span>  
  
 [!code-vb[VbVbalrStatements#97](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/call-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="6593d-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6593d-121">See Also</span></span>  
 [<span data-ttu-id="6593d-122">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="6593d-122">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="6593d-123">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="6593d-123">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="6593d-124">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="6593d-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [<span data-ttu-id="6593d-125">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="6593d-125">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
