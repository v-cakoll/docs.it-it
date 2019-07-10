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
ms.openlocfilehash: 098ca95687d8b0e9f4ac90d5c7e0df9a9a0ad950
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760370"
---
# <a name="addressof-operator-visual-basic"></a><span data-ttu-id="62136-102">Operatore AddressOf (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="62136-102">AddressOf Operator (Visual Basic)</span></span>
<span data-ttu-id="62136-103">Crea un'istanza di delegato che fa riferimento la procedura specifica.</span><span class="sxs-lookup"><span data-stu-id="62136-103">Creates a delegate instance that references the specific procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62136-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="62136-104">Syntax</span></span>  
  
```  
AddressOf procedurename  
```  
  
## <a name="parts"></a><span data-ttu-id="62136-105">Parti</span><span class="sxs-lookup"><span data-stu-id="62136-105">Parts</span></span>  
 `procedurename`  
 <span data-ttu-id="62136-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="62136-106">Required.</span></span> <span data-ttu-id="62136-107">Specifica la routine a cui fa riferimento il delegato appena creato.</span><span class="sxs-lookup"><span data-stu-id="62136-107">Specifies the procedure to be referenced by the newly created delegate.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62136-108">Note</span><span class="sxs-lookup"><span data-stu-id="62136-108">Remarks</span></span>  
 <span data-ttu-id="62136-109">Il `AddressOf` operatore crea un delegato che fa riferimento a sub o function specificato da `procedurename`.</span><span class="sxs-lookup"><span data-stu-id="62136-109">The `AddressOf` operator creates a delegate that points to the sub or function specified by `procedurename`.</span></span> <span data-ttu-id="62136-110">Quando la procedura specificata è che un metodo di istanza, quindi il delegato fa riferimento a sia l'istanza del metodo.</span><span class="sxs-lookup"><span data-stu-id="62136-110">When the specified procedure is an instance method then the delegate refers to both the instance and the method.</span></span> <span data-ttu-id="62136-111">Quindi, quando viene richiamato il delegato viene chiamato il metodo specificato dell'istanza specificata.</span><span class="sxs-lookup"><span data-stu-id="62136-111">Then, when the  delegate is invoked the specified method of the specified instance is called.</span></span>  
  
 <span data-ttu-id="62136-112">Il `AddressOf` operatore può essere usato come operando di un costruttore di delegato o può essere usato in un contesto in cui il tipo del delegato può essere determinato dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="62136-112">The `AddressOf` operator can be used as the operand of a delegate constructor or it can be used in a context in which the type of the delegate can be determined by the compiler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62136-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="62136-113">Example</span></span>  
 <span data-ttu-id="62136-114">Questo esempio Usa la `AddressOf` operatore per definire un delegato per gestire il `Click` eventi di un pulsante.</span><span class="sxs-lookup"><span data-stu-id="62136-114">This example uses the `AddressOf` operator to designate a delegate to handle the `Click` event of a button.</span></span>  
  
 [!code-vb[VbVbalrDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="62136-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="62136-115">Example</span></span>  
 <span data-ttu-id="62136-116">L'esempio seguente usa il `AddressOf` operatore per specificare la funzione di avvio per un thread.</span><span class="sxs-lookup"><span data-stu-id="62136-116">The following example uses the `AddressOf` operator to designate the startup function for a thread.</span></span>  
  
 [!code-vb[VbVbalrDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="62136-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62136-117">See also</span></span>

- [<span data-ttu-id="62136-118">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="62136-118">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="62136-119">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="62136-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="62136-120">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="62136-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="62136-121">Delegati</span><span class="sxs-lookup"><span data-stu-id="62136-121">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
