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
# <a name="39isnot39-operand-of-type-39typename39-can-only-be-compared-to-39nothing39-because-39typename39-is-a-nullable-type"></a>&#39;IsNot&#39; operando di tipo &#39;typename&#39; possono essere confrontati solo con &#39;non&#39;, perché &#39;typename&#39; è un tipo nullable
Una variabile dichiarata come nullable è stata confrontata con un'espressione diversa da `Nothing` utilizzando il `IsNot` operatore.  
  
 **ID errore:** BC32128  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Per confrontare un tipo nullable con un'espressione diversa da `Nothing` utilizzando il `IsNot` operatore, chiamare il `GetType` metodo sul tipo nullable e confrontare il risultato all'espressione, come illustrato nell'esempio seguente.  
  
```vb  
Dim number? As Integer = 5  
  
If number IsNot Nothing Then  
  If number.GetType() IsNot Type.GetType("System.Int32") Then   
  
  End If  
End If  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Tipi di valori nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [Operatore IsNot](../../../visual-basic/language-reference/operators/isnot-operator.md)
