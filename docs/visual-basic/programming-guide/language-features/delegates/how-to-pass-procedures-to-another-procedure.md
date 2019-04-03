---
title: "Procedura: Passare una routine a un'altra routine in Visual Basic"
ms.date: 07/20/2015
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
ms.openlocfilehash: c2305cd18cfaaa67355dfb342f22e39d37ae0e79
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818475"
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a><span data-ttu-id="5b25f-102">Procedura: Passare una routine a un'altra routine in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5b25f-102">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>
<span data-ttu-id="5b25f-103">In questo esempio viene illustrato come usare i delegati per passare una routine a un'altra routine.</span><span class="sxs-lookup"><span data-stu-id="5b25f-103">This example shows how to use delegates to pass a procedure to another procedure.</span></span>  
  
 <span data-ttu-id="5b25f-104">Un delegato è un tipo che è possibile usare come qualsiasi altro tipo in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5b25f-104">A delegate is a type that you can use like any other type in Visual Basic.</span></span> <span data-ttu-id="5b25f-105">Il `AddressOf` operatore restituisce un oggetto delegato quando viene applicato a un nome di routine.</span><span class="sxs-lookup"><span data-stu-id="5b25f-105">The `AddressOf` operator returns a delegate object when applied to a procedure name.</span></span>  
  
 <span data-ttu-id="5b25f-106">Questo esempio include una procedura con un parametro del delegato che può accettare un riferimento a un'altra routine, ottenuto con la `AddressOf` operatore.</span><span class="sxs-lookup"><span data-stu-id="5b25f-106">This example has a procedure with a delegate parameter that can take a reference to another procedure, obtained with the `AddressOf` operator.</span></span>  
  
### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="5b25f-107">Creare il delegato e le procedure corrispondente</span><span class="sxs-lookup"><span data-stu-id="5b25f-107">Create the delegate and matching procedures</span></span>  
  
1.  <span data-ttu-id="5b25f-108">Creare un delegato denominato `MathOperator`.</span><span class="sxs-lookup"><span data-stu-id="5b25f-108">Create a delegate named `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#1)]  
  
2.  <span data-ttu-id="5b25f-109">Creare una stored procedure denominata `AddNumbers` con parametri e il valore restituito che corrispondono a quelle di `MathOperator`, in modo che le firme corrispondono.</span><span class="sxs-lookup"><span data-stu-id="5b25f-109">Create a procedure named `AddNumbers` with parameters and return value that match those of `MathOperator`, so that the signatures match.</span></span>  
  
     [!code-vb[VbVbalrDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#2)]  
  
3.  <span data-ttu-id="5b25f-110">Creare una stored procedure denominata `SubtractNumbers` con una firma corrispondente `MathOperator`.</span><span class="sxs-lookup"><span data-stu-id="5b25f-110">Create a procedure named `SubtractNumbers` with a signature that matches `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#3)]  
  
4.  <span data-ttu-id="5b25f-111">Creare una routine denominata `DelegateTest` che accetta un delegato come parametro.</span><span class="sxs-lookup"><span data-stu-id="5b25f-111">Create a procedure named `DelegateTest` that takes a delegate as a parameter.</span></span>  
  
     <span data-ttu-id="5b25f-112">Questa procedura può accettare un riferimento a `AddNumbers` oppure `SubtractNumbers`, in quanto le relative firme corrispondono il `MathOperator` firma.</span><span class="sxs-lookup"><span data-stu-id="5b25f-112">This procedure can accept a reference to `AddNumbers` or `SubtractNumbers`, because their signatures match the `MathOperator` signature.</span></span>  
  
     [!code-vb[VbVbalrDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#4)]  
  
5.  <span data-ttu-id="5b25f-113">Creare una stored procedure denominata `Test` che chiama `DelegateTest` una volta con il delegato `AddNumbers` come parametro e nuovamente con il delegato per `SubtractNumbers` come parametro.</span><span class="sxs-lookup"><span data-stu-id="5b25f-113">Create a procedure named `Test` that calls `DelegateTest` once with the delegate for `AddNumbers` as a parameter, and again with the delegate for `SubtractNumbers` as a parameter.</span></span>  
  
     [!code-vb[VbVbalrDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#5)]  
  
     <span data-ttu-id="5b25f-114">Quando `Test` viene chiamato, viene innanzitutto visualizzato il risultato del `AddNumbers` che agisce sul `5` e `3`, ovvero 8.</span><span class="sxs-lookup"><span data-stu-id="5b25f-114">When `Test` is called, it first displays the result of `AddNumbers` acting on `5` and `3`, which is 8.</span></span> <span data-ttu-id="5b25f-115">Quindi il risultato del `SubtractNumbers` che agisce sul `9` e `3` è visualizzato, che è 6.</span><span class="sxs-lookup"><span data-stu-id="5b25f-115">Then the result of `SubtractNumbers` acting on `9` and `3` is displayed, which is 6.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b25f-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b25f-116">See also</span></span>

- [<span data-ttu-id="5b25f-117">Delegati</span><span class="sxs-lookup"><span data-stu-id="5b25f-117">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="5b25f-118">Operatore AddressOf</span><span class="sxs-lookup"><span data-stu-id="5b25f-118">AddressOf Operator</span></span>](../../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="5b25f-119">Istruzione Delegate</span><span class="sxs-lookup"><span data-stu-id="5b25f-119">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="5b25f-120">Procedura: Richiamare un metodo delegato</span><span class="sxs-lookup"><span data-stu-id="5b25f-120">How to: Invoke a Delegate Method</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
