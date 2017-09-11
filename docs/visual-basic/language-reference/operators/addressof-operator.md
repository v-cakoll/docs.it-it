---
title: Operatore AddressOf (Visual Basic) | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- AddressOf
- vb.AddressOf
dev_langs:
- VB
helpviewer_keywords:
- AddressOf operator
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
caps.latest.revision: 11
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
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: e29b7ae2a6f6040cfc8c6e0cd0c9eb055a6694e9
ms.contentlocale: it-it
ms.lasthandoff: 05/23/2017

---
# <a name="addressof-operator-visual-basic"></a><span data-ttu-id="d444d-102">Operatore AddressOf (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d444d-102">AddressOf Operator (Visual Basic)</span></span>
<span data-ttu-id="d444d-103">Crea un'istanza del delegato procedure che fa riferimento la procedura specifica.</span><span class="sxs-lookup"><span data-stu-id="d444d-103">Creates a procedure delegate instance that references the specific procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d444d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d444d-104">Syntax</span></span>  
  
```  
AddressOf procedurename  
```  
  
## <a name="parts"></a><span data-ttu-id="d444d-105">Parti</span><span class="sxs-lookup"><span data-stu-id="d444d-105">Parts</span></span>  
 `procedurename`  
 <span data-ttu-id="d444d-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d444d-106">Required.</span></span> <span data-ttu-id="d444d-107">Specifica la procedura per fare riferimento il delegato appena creato.</span><span class="sxs-lookup"><span data-stu-id="d444d-107">Specifies the procedure to be referenced by the newly created procedure delegate.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d444d-108">Note</span><span class="sxs-lookup"><span data-stu-id="d444d-108">Remarks</span></span>  
 <span data-ttu-id="d444d-109">Il `AddressOf` operatore crea un delegato della funzione che fa riferimento alla funzione specificata da `procedurename`.</span><span class="sxs-lookup"><span data-stu-id="d444d-109">The `AddressOf` operator creates a function delegate that points to the function specified by `procedurename`.</span></span> <span data-ttu-id="d444d-110">Quando la procedura specificata è che un metodo di istanza quindi delegato della funzione fa riferimento l'istanza sia il metodo.</span><span class="sxs-lookup"><span data-stu-id="d444d-110">When the specified procedure is an instance method then the function delegate refers to both the instance and the method.</span></span> <span data-ttu-id="d444d-111">Quindi, quando viene richiamato il delegato della funzione viene chiamato il metodo specificato dell'istanza specificata.</span><span class="sxs-lookup"><span data-stu-id="d444d-111">Then, when the function delegate is invoked the specified method of the specified instance is called.</span></span>  
  
 <span data-ttu-id="d444d-112">Il `AddressOf` operatore può essere utilizzato come operando di un costruttore di delegato o può essere utilizzato in un contesto in cui il tipo del delegato può essere determinato dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="d444d-112">The `AddressOf` operator can be used as the operand of a delegate constructor or it can be used in a context in which the type of the delegate can be determined by the compiler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d444d-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="d444d-113">Example</span></span>  
 <span data-ttu-id="d444d-114">Questo esempio viene utilizzato il `AddressOf` operatore per designare un delegato per gestire il `Click` evento di un pulsante.</span><span class="sxs-lookup"><span data-stu-id="d444d-114">This example uses the `AddressOf` operator to designate a delegate to handle the `Click` event of a button.</span></span>  
  
 <span data-ttu-id="d444d-115">[!code-vb[VbVbalrDelegates n.&8;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="d444d-115">[!code-vb[VbVbalrDelegates#8](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_1.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="d444d-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="d444d-116">Example</span></span>  
 <span data-ttu-id="d444d-117">Nell'esempio seguente viene utilizzata la `AddressOf` operatore per specificare la funzione di avvio per un thread.</span><span class="sxs-lookup"><span data-stu-id="d444d-117">The following example uses the `AddressOf` operator to designate the startup function for a thread.</span></span>  
  
 <span data-ttu-id="d444d-118">[!code-vb[9 VbVbalrDelegates](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="d444d-118">[!code-vb[VbVbalrDelegates#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d444d-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d444d-119">See Also</span></span>  
 <span data-ttu-id="d444d-120">[Declare (istruzione)](../../../visual-basic/language-reference/statements/declare-statement.md) </span><span class="sxs-lookup"><span data-stu-id="d444d-120">[Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) </span></span>  
<span data-ttu-id="d444d-121"> [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="d444d-121"> [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md) </span></span>  
<span data-ttu-id="d444d-122"> [Sub (istruzione)](../../../visual-basic/language-reference/statements/sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="d444d-122"> [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md) </span></span>  
<span data-ttu-id="d444d-123"> [Delegati](../../../visual-basic/programming-guide/language-features/delegates/index.md)</span><span class="sxs-lookup"><span data-stu-id="d444d-123"> [Delegates](../../../visual-basic/programming-guide/language-features/delegates/index.md)</span></span>

