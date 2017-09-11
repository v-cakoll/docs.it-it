---
title: 'Procedura: passare una routine a un&quot;altra routine in Visual Basic | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- AddressOf operator
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 95cbcf836b0dad875851052a367666c00cd54e37
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a><span data-ttu-id="62ad7-102">Procedura: passare una routine a un'altra routine in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="62ad7-102">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>
<span data-ttu-id="62ad7-103">In questo esempio viene illustrato come utilizzare i delegati per passare una routine a un'altra routine.</span><span class="sxs-lookup"><span data-stu-id="62ad7-103">This example shows how to use delegates to pass a procedure to another procedure.</span></span>  
  
 <span data-ttu-id="62ad7-104">Un delegato è un tipo che è possibile utilizzare come qualsiasi altro tipo in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="62ad7-104">A delegate is a type that you can use like any other type in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span> <span data-ttu-id="62ad7-105">Il `AddressOf` operatore restituisce un oggetto delegato quando viene applicato a un nome di procedura.</span><span class="sxs-lookup"><span data-stu-id="62ad7-105">The `AddressOf` operator returns a delegate object when applied to a procedure name.</span></span>  
  
 <span data-ttu-id="62ad7-106">L'esempio include una procedura con un parametro del delegato che può accettare un riferimento a un'altra routine, ottenuto con la `AddressOf` operatore.</span><span class="sxs-lookup"><span data-stu-id="62ad7-106">This example has a procedure with a delegate parameter that can take a reference to another procedure, obtained with the `AddressOf` operator.</span></span>  
  
### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="62ad7-107">Creare il delegato e le procedure corrispondenti</span><span class="sxs-lookup"><span data-stu-id="62ad7-107">Create the delegate and matching procedures</span></span>  
  
1.  <span data-ttu-id="62ad7-108">Crea un delegato denominato `MathOperator`.</span><span class="sxs-lookup"><span data-stu-id="62ad7-108">Create a delegate named `MathOperator`.</span></span>  
  
     <span data-ttu-id="62ad7-109">[!code-vb[VbVbalrDelegates n.&1;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="62ad7-109">[!code-vb[VbVbalrDelegates#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_1.vb)]</span></span>  
  
2.  <span data-ttu-id="62ad7-110">Creare una routine denominata `AddNumbers` con parametri e valore restituito che corrispondono a quelle di `MathOperator`, in modo che le firme corrispondono.</span><span class="sxs-lookup"><span data-stu-id="62ad7-110">Create a procedure named `AddNumbers` with parameters and return value that match those of `MathOperator`, so that the signatures match.</span></span>  
  
     <span data-ttu-id="62ad7-111">[!code-vb[VbVbalrDelegates n.&2;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="62ad7-111">[!code-vb[VbVbalrDelegates#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_2.vb)]</span></span>  
  
3.  <span data-ttu-id="62ad7-112">Creare una routine denominata `SubtractNumbers` con una firma corrispondente `MathOperator`.</span><span class="sxs-lookup"><span data-stu-id="62ad7-112">Create a procedure named `SubtractNumbers` with a signature that matches `MathOperator`.</span></span>  
  
     <span data-ttu-id="62ad7-113">[!code-vb[VbVbalrDelegates n.&3;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="62ad7-113">[!code-vb[VbVbalrDelegates#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_3.vb)]</span></span>  
  
4.  <span data-ttu-id="62ad7-114">Creare una routine denominata `DelegateTest` che accetta un delegato come parametro.</span><span class="sxs-lookup"><span data-stu-id="62ad7-114">Create a procedure named `DelegateTest` that takes a delegate as a parameter.</span></span>  
  
     <span data-ttu-id="62ad7-115">Questa routine può accettare un riferimento a `AddNumbers` o `SubtractNumbers`, in quanto le relative firme corrispondono il `MathOperator` firma.</span><span class="sxs-lookup"><span data-stu-id="62ad7-115">This procedure can accept a reference to `AddNumbers` or `SubtractNumbers`, because their signatures match the `MathOperator` signature.</span></span>  
  
     <span data-ttu-id="62ad7-116">[!code-vb[VbVbalrDelegates n.&4;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="62ad7-116">[!code-vb[VbVbalrDelegates#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_4.vb)]</span></span>  
  
5.  <span data-ttu-id="62ad7-117">Creare una routine denominata `Test` che chiama `DelegateTest` una volta con il delegato per `AddNumbers` come parametro e di nuovo con il delegato per `SubtractNumbers` come parametro.</span><span class="sxs-lookup"><span data-stu-id="62ad7-117">Create a procedure named `Test` that calls `DelegateTest` once with the delegate for `AddNumbers` as a parameter, and again with the delegate for `SubtractNumbers` as a parameter.</span></span>  
  
     <span data-ttu-id="62ad7-118">[!code-vb[VbVbalrDelegates n.&5;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="62ad7-118">[!code-vb[VbVbalrDelegates#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_5.vb)]</span></span>  
  
     <span data-ttu-id="62ad7-119">Quando `Test` viene chiamato, viene innanzitutto visualizzato il risultato di `AddNumbers` applicata a `5` e `3`, ovvero 8.</span><span class="sxs-lookup"><span data-stu-id="62ad7-119">When `Test` is called, it first displays the result of `AddNumbers` acting on `5` and `3`, which is 8.</span></span> <span data-ttu-id="62ad7-120">Quindi il risultato di `SubtractNumbers` su `9` e `3` viene visualizzato, ovvero 6.</span><span class="sxs-lookup"><span data-stu-id="62ad7-120">Then the result of `SubtractNumbers` acting on `9` and `3` is displayed, which is 6.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62ad7-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62ad7-121">See Also</span></span>  
 <span data-ttu-id="62ad7-122">[Delegati](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="62ad7-122">[Delegates](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span></span>  
<span data-ttu-id="62ad7-123"> [AddressOf (operatore)](../../../../visual-basic/language-reference/operators/addressof-operator.md) </span><span class="sxs-lookup"><span data-stu-id="62ad7-123"> [AddressOf Operator](../../../../visual-basic/language-reference/operators/addressof-operator.md) </span></span>  
<span data-ttu-id="62ad7-124"> [Delegate (istruzione)](../../../../visual-basic/language-reference/statements/delegate-statement.md) </span><span class="sxs-lookup"><span data-stu-id="62ad7-124"> [Delegate Statement](../../../../visual-basic/language-reference/statements/delegate-statement.md) </span></span>  
<span data-ttu-id="62ad7-125"> [Procedura: Richiamare un metodo delegato](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)</span><span class="sxs-lookup"><span data-stu-id="62ad7-125"> [How to: Invoke a Delegate Method](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)</span></span>
