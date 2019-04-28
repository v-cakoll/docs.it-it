---
title: Operatore AddressOf (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- AddressOf
- vb.AddressOf
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
ms.openlocfilehash: 9d8515b6d5b0caf3552ed05a7e0cd4a271efaf54
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61608346"
---
# <a name="addressof-operator-visual-basic"></a><span data-ttu-id="1b902-102">Operatore AddressOf (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1b902-102">AddressOf Operator (Visual Basic)</span></span>
<span data-ttu-id="1b902-103">Crea un'istanza di delegato di routine che fa riferimento la procedura specifica.</span><span class="sxs-lookup"><span data-stu-id="1b902-103">Creates a procedure delegate instance that references the specific procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b902-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1b902-104">Syntax</span></span>  
  
```  
AddressOf procedurename  
```  
  
## <a name="parts"></a><span data-ttu-id="1b902-105">Parti</span><span class="sxs-lookup"><span data-stu-id="1b902-105">Parts</span></span>  
 `procedurename`  
 <span data-ttu-id="1b902-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="1b902-106">Required.</span></span> <span data-ttu-id="1b902-107">Specifica la routine a cui fa riferimento il delegato appena creato.</span><span class="sxs-lookup"><span data-stu-id="1b902-107">Specifies the procedure to be referenced by the newly created procedure delegate.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b902-108">Note</span><span class="sxs-lookup"><span data-stu-id="1b902-108">Remarks</span></span>  
 <span data-ttu-id="1b902-109">Il `AddressOf` operatore crea un delegato della funzione che fa riferimento alla funzione specificata da `procedurename`.</span><span class="sxs-lookup"><span data-stu-id="1b902-109">The `AddressOf` operator creates a function delegate that points to the function specified by `procedurename`.</span></span> <span data-ttu-id="1b902-110">Quando la procedura specificata è che un metodo di istanza, quindi il delegato della funzione fa riferimento a sia l'istanza del metodo.</span><span class="sxs-lookup"><span data-stu-id="1b902-110">When the specified procedure is an instance method then the function delegate refers to both the instance and the method.</span></span> <span data-ttu-id="1b902-111">Quindi, quando viene richiamato il delegato della funzione viene chiamato il metodo specificato dell'istanza specificata.</span><span class="sxs-lookup"><span data-stu-id="1b902-111">Then, when the function delegate is invoked the specified method of the specified instance is called.</span></span>  
  
 <span data-ttu-id="1b902-112">Il `AddressOf` operatore può essere usato come operando di un costruttore di delegato o può essere usato in un contesto in cui il tipo del delegato può essere determinato dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="1b902-112">The `AddressOf` operator can be used as the operand of a delegate constructor or it can be used in a context in which the type of the delegate can be determined by the compiler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b902-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="1b902-113">Example</span></span>  
 <span data-ttu-id="1b902-114">Questo esempio Usa la `AddressOf` operatore per definire un delegato per gestire il `Click` eventi di un pulsante.</span><span class="sxs-lookup"><span data-stu-id="1b902-114">This example uses the `AddressOf` operator to designate a delegate to handle the `Click` event of a button.</span></span>  
  
 [!code-vb[VbVbalrDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="1b902-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="1b902-115">Example</span></span>  
 <span data-ttu-id="1b902-116">L'esempio seguente usa il `AddressOf` operatore per specificare la funzione di avvio per un thread.</span><span class="sxs-lookup"><span data-stu-id="1b902-116">The following example uses the `AddressOf` operator to designate the startup function for a thread.</span></span>  
  
 [!code-vb[VbVbalrDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="1b902-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b902-117">See also</span></span>

- [<span data-ttu-id="1b902-118">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="1b902-118">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="1b902-119">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="1b902-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="1b902-120">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="1b902-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="1b902-121">Delegati</span><span class="sxs-lookup"><span data-stu-id="1b902-121">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
