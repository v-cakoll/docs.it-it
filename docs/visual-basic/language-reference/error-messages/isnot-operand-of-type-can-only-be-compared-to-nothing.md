---
title: È possibile confrontare l'operando 'IsNot' del tipo '' solo con 'Nothing' perché '' è un tipo nullable
ms.date: 07/20/2015
f1_keywords:
- bc32128
- vbc32128
helpviewer_keywords:
- BC32128
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
ms.openlocfilehash: f19b8cd5f80ba9fd6d1f5a9162b04ee409e24e28
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61921134"
---
# <a name="isnot-operand-of-type-typename-can-only-be-compared-to-nothing-because-typename-is-a-nullable-type"></a><span data-ttu-id="ed74e-102">È possibile confrontare l'operando 'IsNot' del tipo '' solo con 'Nothing' perché '' è un tipo nullable</span><span class="sxs-lookup"><span data-stu-id="ed74e-102">'IsNot' operand of type 'typename' can only be compared to 'Nothing', because 'typename' is a nullable type</span></span>
<span data-ttu-id="ed74e-103">Una variabile dichiarata come nullable è stata confrontata a un'espressione diversa `Nothing` utilizzando il `IsNot` operatore.</span><span class="sxs-lookup"><span data-stu-id="ed74e-103">A variable declared as nullable has been compared to an expression other than `Nothing` using the `IsNot` operator.</span></span>  
  
 <span data-ttu-id="ed74e-104">**ID errore:** BC32128</span><span class="sxs-lookup"><span data-stu-id="ed74e-104">**Error ID:** BC32128</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ed74e-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="ed74e-105">To correct this error</span></span>  
  
1. <span data-ttu-id="ed74e-106">Per confrontare un tipo nullable con un'espressione diversa da `Nothing` usando l'operatore `IsNot` , chiamare il metodo `GetType` sul tipo nullable e confrontare il risultato con l'espressione, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ed74e-106">To compare a nullable type to an expression other than `Nothing` by using the `IsNot` operator, call the `GetType` method on the nullable type and compare the result to the expression, as shown in the following example.</span></span>  
  
```vb  
Dim number? As Integer = 5  
  
If number IsNot Nothing Then  
  If number.GetType() IsNot Type.GetType("System.Int32") Then   
  
  End If  
End If  
```  
  
## <a name="see-also"></a><span data-ttu-id="ed74e-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed74e-107">See also</span></span>

- [<span data-ttu-id="ed74e-108">Tipi di valori nullable</span><span class="sxs-lookup"><span data-stu-id="ed74e-108">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="ed74e-109">Operatore IsNot</span><span class="sxs-lookup"><span data-stu-id="ed74e-109">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
