---
title: "Procedura: passare una routine a un'altra routine in Visual Basic"
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 30264e0480b603b21f8f71893af0fd742af40286
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a><span data-ttu-id="4be7d-102">Procedura: passare una routine a un'altra routine in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4be7d-102">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>
<span data-ttu-id="4be7d-103">In questo esempio viene illustrato come utilizzare i delegati per passare una routine a un'altra routine.</span><span class="sxs-lookup"><span data-stu-id="4be7d-103">This example shows how to use delegates to pass a procedure to another procedure.</span></span>  
  
 <span data-ttu-id="4be7d-104">Un delegato è un tipo che è possibile utilizzare come qualsiasi altro tipo in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4be7d-104">A delegate is a type that you can use like any other type in Visual Basic.</span></span> <span data-ttu-id="4be7d-105">Il `AddressOf` operatore restituisce un oggetto delegato quando applicato a un nome della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="4be7d-105">The `AddressOf` operator returns a delegate object when applied to a procedure name.</span></span>  
  
 <span data-ttu-id="4be7d-106">L'esempio include una procedura con un parametro del delegato che può accettare un riferimento a un'altra routine, ottenuto con la `AddressOf` operatore.</span><span class="sxs-lookup"><span data-stu-id="4be7d-106">This example has a procedure with a delegate parameter that can take a reference to another procedure, obtained with the `AddressOf` operator.</span></span>  
  
### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="4be7d-107">Creare il delegato e le procedure corrispondenti</span><span class="sxs-lookup"><span data-stu-id="4be7d-107">Create the delegate and matching procedures</span></span>  
  
1.  <span data-ttu-id="4be7d-108">Crea un delegato denominato `MathOperator`.</span><span class="sxs-lookup"><span data-stu-id="4be7d-108">Create a delegate named `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_1.vb)]  
  
2.  <span data-ttu-id="4be7d-109">Creare una routine denominata `AddNumbers` con parametri e il valore restituito che corrispondono a quelle di `MathOperator`, in modo che le firme corrispondono.</span><span class="sxs-lookup"><span data-stu-id="4be7d-109">Create a procedure named `AddNumbers` with parameters and return value that match those of `MathOperator`, so that the signatures match.</span></span>  
  
     [!code-vb[VbVbalrDelegates#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_2.vb)]  
  
3.  <span data-ttu-id="4be7d-110">Creare una routine denominata `SubtractNumbers` con una firma corrispondente `MathOperator`.</span><span class="sxs-lookup"><span data-stu-id="4be7d-110">Create a procedure named `SubtractNumbers` with a signature that matches `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_3.vb)]  
  
4.  <span data-ttu-id="4be7d-111">Creare una routine denominata `DelegateTest` che accetta un delegato come parametro.</span><span class="sxs-lookup"><span data-stu-id="4be7d-111">Create a procedure named `DelegateTest` that takes a delegate as a parameter.</span></span>  
  
     <span data-ttu-id="4be7d-112">Questa procedura può accettare un riferimento a `AddNumbers` o `SubtractNumbers`, in quanto le relative firme corrispondono il `MathOperator` firma.</span><span class="sxs-lookup"><span data-stu-id="4be7d-112">This procedure can accept a reference to `AddNumbers` or `SubtractNumbers`, because their signatures match the `MathOperator` signature.</span></span>  
  
     [!code-vb[VbVbalrDelegates#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_4.vb)]  
  
5.  <span data-ttu-id="4be7d-113">Creare una routine denominata `Test` che chiama `DelegateTest` una volta con il delegato per `AddNumbers` come parametro e di nuovo con il delegato per `SubtractNumbers` come parametro.</span><span class="sxs-lookup"><span data-stu-id="4be7d-113">Create a procedure named `Test` that calls `DelegateTest` once with the delegate for `AddNumbers` as a parameter, and again with the delegate for `SubtractNumbers` as a parameter.</span></span>  
  
     [!code-vb[VbVbalrDelegates#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_5.vb)]  
  
     <span data-ttu-id="4be7d-114">Quando `Test` viene chiamato, viene innanzitutto visualizzato il risultato di `AddNumbers` applicata a `5` e `3`, ovvero 8.</span><span class="sxs-lookup"><span data-stu-id="4be7d-114">When `Test` is called, it first displays the result of `AddNumbers` acting on `5` and `3`, which is 8.</span></span> <span data-ttu-id="4be7d-115">Quindi il risultato di `SubtractNumbers` su `9` e `3` viene visualizzato, ovvero 6.</span><span class="sxs-lookup"><span data-stu-id="4be7d-115">Then the result of `SubtractNumbers` acting on `9` and `3` is displayed, which is 6.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4be7d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4be7d-116">See Also</span></span>  
 [<span data-ttu-id="4be7d-117">Delegati</span><span class="sxs-lookup"><span data-stu-id="4be7d-117">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [<span data-ttu-id="4be7d-118">Operatore AddressOf</span><span class="sxs-lookup"><span data-stu-id="4be7d-118">AddressOf Operator</span></span>](../../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [<span data-ttu-id="4be7d-119">Istruzione Delegate</span><span class="sxs-lookup"><span data-stu-id="4be7d-119">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [<span data-ttu-id="4be7d-120">Procedura: Richiamare un metodo delegato</span><span class="sxs-lookup"><span data-stu-id="4be7d-120">How to: Invoke a Delegate Method</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
