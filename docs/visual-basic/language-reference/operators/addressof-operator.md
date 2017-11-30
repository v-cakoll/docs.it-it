---
title: Operatore AddressOf (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- AddressOf
- vb.AddressOf
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 52560a2d9071373fd28f7aad2e485da08324656d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="addressof-operator-visual-basic"></a><span data-ttu-id="f42fd-102">Operatore AddressOf (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f42fd-102">AddressOf Operator (Visual Basic)</span></span>
<span data-ttu-id="f42fd-103">Crea un'istanza di delegato di routine che fa riferimento la procedura specifica.</span><span class="sxs-lookup"><span data-stu-id="f42fd-103">Creates a procedure delegate instance that references the specific procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f42fd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f42fd-104">Syntax</span></span>  
  
```  
AddressOf procedurename  
```  
  
## <a name="parts"></a><span data-ttu-id="f42fd-105">Parti</span><span class="sxs-lookup"><span data-stu-id="f42fd-105">Parts</span></span>  
 `procedurename`  
 <span data-ttu-id="f42fd-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="f42fd-106">Required.</span></span> <span data-ttu-id="f42fd-107">Specifica la procedura per fare riferimento il delegato appena creato.</span><span class="sxs-lookup"><span data-stu-id="f42fd-107">Specifies the procedure to be referenced by the newly created procedure delegate.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f42fd-108">Note</span><span class="sxs-lookup"><span data-stu-id="f42fd-108">Remarks</span></span>  
 <span data-ttu-id="f42fd-109">Il `AddressOf` operatore crea un delegato della funzione che fa riferimento alla funzione specificata da `procedurename`.</span><span class="sxs-lookup"><span data-stu-id="f42fd-109">The `AddressOf` operator creates a function delegate that points to the function specified by `procedurename`.</span></span> <span data-ttu-id="f42fd-110">Quando la stored procedure specificata è che un metodo di istanza, quindi il delegato della funzione fa riferimento l'istanza sia il metodo.</span><span class="sxs-lookup"><span data-stu-id="f42fd-110">When the specified procedure is an instance method then the function delegate refers to both the instance and the method.</span></span> <span data-ttu-id="f42fd-111">Quindi, quando viene richiamato il delegato della funzione viene chiamato il metodo specificato dell'istanza specificata.</span><span class="sxs-lookup"><span data-stu-id="f42fd-111">Then, when the function delegate is invoked the specified method of the specified instance is called.</span></span>  
  
 <span data-ttu-id="f42fd-112">Il `AddressOf` operatore può essere usato come operando di un costruttore di delegato o può essere utilizzato in un contesto in cui il tipo del delegato può essere determinato dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="f42fd-112">The `AddressOf` operator can be used as the operand of a delegate constructor or it can be used in a context in which the type of the delegate can be determined by the compiler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f42fd-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="f42fd-113">Example</span></span>  
 <span data-ttu-id="f42fd-114">Questo esempio viene utilizzato il `AddressOf` operatore per designare un delegato per gestire il `Click` evento di un pulsante.</span><span class="sxs-lookup"><span data-stu-id="f42fd-114">This example uses the `AddressOf` operator to designate a delegate to handle the `Click` event of a button.</span></span>  
  
 [!code-vb[VbVbalrDelegates#8](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="f42fd-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="f42fd-115">Example</span></span>  
 <span data-ttu-id="f42fd-116">L'esempio seguente usa il `AddressOf` operatore per specificare la funzione di avvio per un thread.</span><span class="sxs-lookup"><span data-stu-id="f42fd-116">The following example uses the `AddressOf` operator to designate the startup function for a thread.</span></span>  
  
 [!code-vb[VbVbalrDelegates#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="f42fd-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f42fd-117">See Also</span></span>  
 [<span data-ttu-id="f42fd-118">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="f42fd-118">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [<span data-ttu-id="f42fd-119">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="f42fd-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="f42fd-120">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="f42fd-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="f42fd-121">Delegati</span><span class="sxs-lookup"><span data-stu-id="f42fd-121">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
