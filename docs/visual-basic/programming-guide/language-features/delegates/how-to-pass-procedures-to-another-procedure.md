---
title: "Procedura: Passare una routine a un'altra routine"
ms.date: 07/20/2015
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
ms.openlocfilehash: 36f623068372614ae034a8a7b31bffb7496f98b1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410695"
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a><span data-ttu-id="63194-102">Procedura: passare una routine a un'altra routine in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="63194-102">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>
<span data-ttu-id="63194-103">Questo esempio illustra come usare i delegati per passare una routine a un'altra routine.</span><span class="sxs-lookup"><span data-stu-id="63194-103">This example shows how to use delegates to pass a procedure to another procedure.</span></span>  
  
 <span data-ttu-id="63194-104">Un delegato è un tipo che può essere usato come qualsiasi altro tipo in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="63194-104">A delegate is a type that you can use like any other type in Visual Basic.</span></span> <span data-ttu-id="63194-105">L' `AddressOf` operatore restituisce un oggetto delegato quando viene applicato al nome di una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="63194-105">The `AddressOf` operator returns a delegate object when applied to a procedure name.</span></span>  
  
 <span data-ttu-id="63194-106">Questo esempio include una routine con un parametro delegate che può assumere un riferimento a un'altra routine, ottenuta con l' `AddressOf` operatore.</span><span class="sxs-lookup"><span data-stu-id="63194-106">This example has a procedure with a delegate parameter that can take a reference to another procedure, obtained with the `AddressOf` operator.</span></span>  
  
### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="63194-107">Creare il delegato e le procedure di corrispondenza</span><span class="sxs-lookup"><span data-stu-id="63194-107">Create the delegate and matching procedures</span></span>  
  
1. <span data-ttu-id="63194-108">Creare un delegato denominato `MathOperator` .</span><span class="sxs-lookup"><span data-stu-id="63194-108">Create a delegate named `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#1)]  
  
2. <span data-ttu-id="63194-109">Creare una routine denominata `AddNumbers` con i parametri e il valore restituito corrispondenti a quelli di `MathOperator` , in modo che le firme corrispondano.</span><span class="sxs-lookup"><span data-stu-id="63194-109">Create a procedure named `AddNumbers` with parameters and return value that match those of `MathOperator`, so that the signatures match.</span></span>  
  
     [!code-vb[VbVbalrDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#2)]  
  
3. <span data-ttu-id="63194-110">Creare una routine denominata `SubtractNumbers` con una firma corrispondente a `MathOperator` .</span><span class="sxs-lookup"><span data-stu-id="63194-110">Create a procedure named `SubtractNumbers` with a signature that matches `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#3)]  
  
4. <span data-ttu-id="63194-111">Creare una stored procedure denominata `DelegateTest` che accetta un delegato come parametro.</span><span class="sxs-lookup"><span data-stu-id="63194-111">Create a procedure named `DelegateTest` that takes a delegate as a parameter.</span></span>  
  
     <span data-ttu-id="63194-112">Questa procedura può accettare un riferimento a `AddNumbers` o `SubtractNumbers` , perché le relative firme corrispondono alla `MathOperator` firma.</span><span class="sxs-lookup"><span data-stu-id="63194-112">This procedure can accept a reference to `AddNumbers` or `SubtractNumbers`, because their signatures match the `MathOperator` signature.</span></span>  
  
     [!code-vb[VbVbalrDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#4)]  
  
5. <span data-ttu-id="63194-113">Creare una routine denominata `Test` che chiama `DelegateTest` una volta con il delegato per `AddNumbers` come parametro e di nuovo con il delegato per `SubtractNumbers` come parametro.</span><span class="sxs-lookup"><span data-stu-id="63194-113">Create a procedure named `Test` that calls `DelegateTest` once with the delegate for `AddNumbers` as a parameter, and again with the delegate for `SubtractNumbers` as a parameter.</span></span>  
  
     [!code-vb[VbVbalrDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#5)]  
  
     <span data-ttu-id="63194-114">Quando `Test` viene chiamato, viene prima visualizzato il risultato dell' `AddNumbers` azione su `5` e `3` , che è 8.</span><span class="sxs-lookup"><span data-stu-id="63194-114">When `Test` is called, it first displays the result of `AddNumbers` acting on `5` and `3`, which is 8.</span></span> <span data-ttu-id="63194-115">Viene quindi visualizzato il risultato dell' `SubtractNumbers` azione su `9` e `3` , che è 6.</span><span class="sxs-lookup"><span data-stu-id="63194-115">Then the result of `SubtractNumbers` acting on `9` and `3` is displayed, which is 6.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63194-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63194-116">See also</span></span>

- [<span data-ttu-id="63194-117">Delegati</span><span class="sxs-lookup"><span data-stu-id="63194-117">Delegates</span></span>](index.md)
- [<span data-ttu-id="63194-118">Operatore AddressOf</span><span class="sxs-lookup"><span data-stu-id="63194-118">AddressOf Operator</span></span>](../../../language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="63194-119">Istruzione Delegate</span><span class="sxs-lookup"><span data-stu-id="63194-119">Delegate Statement</span></span>](../../../language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="63194-120">Procedura: richiamare un metodo delegato</span><span class="sxs-lookup"><span data-stu-id="63194-120">How to: Invoke a Delegate Method</span></span>](how-to-invoke-a-delegate-method.md)
