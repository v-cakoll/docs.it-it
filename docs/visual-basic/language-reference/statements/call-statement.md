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
ms.openlocfilehash: a04ebddc7db176188876da1082e1e6946e1e8eec
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005163"
---
# <a name="call-statement-visual-basic"></a><span data-ttu-id="a0b35-102">Istruzione Call (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a0b35-102">Call Statement (Visual Basic)</span></span>

<span data-ttu-id="a0b35-103">Trasferisce il controllo a una procedura di libreria a collegamento dinamico (DLL) `Function`, `Sub` o.</span><span class="sxs-lookup"><span data-stu-id="a0b35-103">Transfers control to a `Function`, `Sub`, or dynamic-link library (DLL) procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0b35-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a0b35-104">Syntax</span></span>  
  
```vb  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## <a name="parts"></a><span data-ttu-id="a0b35-105">Parti</span><span class="sxs-lookup"><span data-stu-id="a0b35-105">Parts</span></span>  

|||
|---|---|
|`procedureName`|<span data-ttu-id="a0b35-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a0b35-106">Required.</span></span> <span data-ttu-id="a0b35-107">Nome della procedura da chiamare.</span><span class="sxs-lookup"><span data-stu-id="a0b35-107">Name of the procedure to call.</span></span>|
|`argumentList`|<span data-ttu-id="a0b35-108">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="a0b35-108">Optional.</span></span> <span data-ttu-id="a0b35-109">Elenco di variabili o espressioni che rappresentano gli argomenti passati alla routine quando viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="a0b35-109">List of variables or expressions representing arguments that are passed to the procedure when it is called.</span></span> <span data-ttu-id="a0b35-110">Più argomenti sono separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="a0b35-110">Multiple arguments are separated by commas.</span></span> <span data-ttu-id="a0b35-111">Se si include `argumentList`, è necessario racchiuderlo tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="a0b35-111">If you include `argumentList`, you must enclose it in parentheses.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="a0b35-112">Note</span><span class="sxs-lookup"><span data-stu-id="a0b35-112">Remarks</span></span>

 <span data-ttu-id="a0b35-113">È possibile utilizzare la parola chiave `Call` quando si chiama una routine.</span><span class="sxs-lookup"><span data-stu-id="a0b35-113">You can use the `Call` keyword when you call a procedure.</span></span> <span data-ttu-id="a0b35-114">Per la maggior parte delle chiamate di procedura, non è necessario usare questa parola chiave.</span><span class="sxs-lookup"><span data-stu-id="a0b35-114">For most procedure calls, you aren’t required to use this  keyword.</span></span>

 <span data-ttu-id="a0b35-115">In genere si usa la parola chiave `Call` quando l'espressione chiamata non inizia con un identificatore.</span><span class="sxs-lookup"><span data-stu-id="a0b35-115">You typically use the `Call` keyword when the called expression doesn’t start with an identifier.</span></span> <span data-ttu-id="a0b35-116">Non è consigliabile usare la parola chiave `Call` per altri usi.</span><span class="sxs-lookup"><span data-stu-id="a0b35-116">Use of the `Call` keyword for other uses isn't recommended.</span></span>

 <span data-ttu-id="a0b35-117">Se la procedura restituisce un valore, l'istruzione `Call` lo ignora.</span><span class="sxs-lookup"><span data-stu-id="a0b35-117">If the procedure returns a value, the `Call` statement discards it.</span></span>

## <a name="example"></a><span data-ttu-id="a0b35-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="a0b35-118">Example</span></span>

 <span data-ttu-id="a0b35-119">Nel codice seguente vengono illustrati due esempi in cui la parola chiave `Call` è necessaria per chiamare una routine.</span><span class="sxs-lookup"><span data-stu-id="a0b35-119">The following code shows two examples where the `Call` keyword is necessary to call a procedure.</span></span> <span data-ttu-id="a0b35-120">In entrambi gli esempi, l'espressione chiamata non inizia con un identificatore.</span><span class="sxs-lookup"><span data-stu-id="a0b35-120">In both examples, the called expression doesn't start with an identifier.</span></span>

 [!code-vb[VbVbalrStatements#97](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#97)]  
  
## <a name="see-also"></a><span data-ttu-id="a0b35-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0b35-121">See also</span></span>

- [<span data-ttu-id="a0b35-122">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="a0b35-122">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="a0b35-123">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="a0b35-123">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="a0b35-124">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="a0b35-124">Declare Statement</span></span>](declare-statement.md)
- [<span data-ttu-id="a0b35-125">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="a0b35-125">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
