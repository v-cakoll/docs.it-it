---
title: '&#39;IsNot&#39; operando di tipo &#39;typename&#39; possono essere confrontati solo con &#39;non&#39;, perché &#39;typename&#39; è un tipo nullable'
ms.date: 07/20/2015
f1_keywords:
- bc32128
- vbc32128
helpviewer_keywords:
- BC32128
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
ms.openlocfilehash: 44cc17c73b476e5e322b9b58b021bc7bcd63167f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587596"
---
# <a name="39isnot39-operand-of-type-39typename39-can-only-be-compared-to-39nothing39-because-39typename39-is-a-nullable-type"></a><span data-ttu-id="2bae1-102">&#39;IsNot&#39; operando di tipo &#39;typename&#39; possono essere confrontati solo con &#39;non&#39;, perché &#39;typename&#39; è un tipo nullable</span><span class="sxs-lookup"><span data-stu-id="2bae1-102">&#39;IsNot&#39; operand of type &#39;typename&#39; can only be compared to &#39;Nothing&#39;, because &#39;typename&#39; is a nullable type</span></span>
<span data-ttu-id="2bae1-103">Una variabile dichiarata come nullable è stata confrontata con un'espressione diversa da `Nothing` utilizzando il `IsNot` operatore.</span><span class="sxs-lookup"><span data-stu-id="2bae1-103">A variable declared as nullable has been compared to an expression other than `Nothing` using the `IsNot` operator.</span></span>  
  
 <span data-ttu-id="2bae1-104">**ID errore:** BC32128</span><span class="sxs-lookup"><span data-stu-id="2bae1-104">**Error ID:** BC32128</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2bae1-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="2bae1-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="2bae1-106">Per confrontare un tipo nullable con un'espressione diversa da `Nothing` utilizzando il `IsNot` operatore, chiamare il `GetType` metodo sul tipo nullable e confrontare il risultato all'espressione, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="2bae1-106">To compare a nullable type to an expression other than `Nothing` by using the `IsNot` operator, call the `GetType` method on the nullable type and compare the result to the expression, as shown in the following example.</span></span>  
  
```vb  
Dim number? As Integer = 5  
  
If number IsNot Nothing Then  
  If number.GetType() IsNot Type.GetType("System.Int32") Then   
  
  End If  
End If  
```  
  
## <a name="see-also"></a><span data-ttu-id="2bae1-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2bae1-107">See Also</span></span>  
 [<span data-ttu-id="2bae1-108">Tipi di valori nullable</span><span class="sxs-lookup"><span data-stu-id="2bae1-108">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [<span data-ttu-id="2bae1-109">Operatore IsNot</span><span class="sxs-lookup"><span data-stu-id="2bae1-109">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
