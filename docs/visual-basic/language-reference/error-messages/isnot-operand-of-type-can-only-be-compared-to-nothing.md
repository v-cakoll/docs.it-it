---
title: '&#39;IsNot&#39; operando di tipo &#39;nomeTipo&#39; può essere confrontato solo con &#39;Nothing&#39;, in quanto &#39;typename&#39; è un tipo nullable'
ms.date: 07/20/2015
f1_keywords:
- bc32128
- vbc32128
helpviewer_keywords:
- BC32128
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
ms.openlocfilehash: 65b04c85bccd169bbb2eea847d7b8af96c1a292f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54505718"
---
# <a name="39isnot39-operand-of-type-39typename39-can-only-be-compared-to-39nothing39-because-39typename39-is-a-nullable-type"></a><span data-ttu-id="03fc0-102">&#39;IsNot&#39; operando di tipo &#39;nomeTipo&#39; può essere confrontato solo con &#39;Nothing&#39;, in quanto &#39;typename&#39; è un tipo nullable</span><span class="sxs-lookup"><span data-stu-id="03fc0-102">&#39;IsNot&#39; operand of type &#39;typename&#39; can only be compared to &#39;Nothing&#39;, because &#39;typename&#39; is a nullable type</span></span>
<span data-ttu-id="03fc0-103">Una variabile dichiarata come nullable è stata confrontata a un'espressione diversa `Nothing` utilizzando il `IsNot` operatore.</span><span class="sxs-lookup"><span data-stu-id="03fc0-103">A variable declared as nullable has been compared to an expression other than `Nothing` using the `IsNot` operator.</span></span>  
  
 <span data-ttu-id="03fc0-104">**ID errore:** BC32128</span><span class="sxs-lookup"><span data-stu-id="03fc0-104">**Error ID:** BC32128</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="03fc0-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="03fc0-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="03fc0-106">Per confrontare un tipo nullable con un'espressione diversa da `Nothing` usando l'operatore `IsNot` , chiamare il metodo `GetType` sul tipo nullable e confrontare il risultato con l'espressione, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="03fc0-106">To compare a nullable type to an expression other than `Nothing` by using the `IsNot` operator, call the `GetType` method on the nullable type and compare the result to the expression, as shown in the following example.</span></span>  
  
```vb  
Dim number? As Integer = 5  
  
If number IsNot Nothing Then  
  If number.GetType() IsNot Type.GetType("System.Int32") Then   
  
  End If  
End If  
```  
  
## <a name="see-also"></a><span data-ttu-id="03fc0-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03fc0-107">See also</span></span>
- [<span data-ttu-id="03fc0-108">Tipi di valori nullable</span><span class="sxs-lookup"><span data-stu-id="03fc0-108">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="03fc0-109">Operatore IsNot</span><span class="sxs-lookup"><span data-stu-id="03fc0-109">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
