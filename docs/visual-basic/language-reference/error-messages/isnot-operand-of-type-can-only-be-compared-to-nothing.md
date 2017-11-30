---
title: "&#39; IsNot &#39; operando di tipo &#39; typename &#39; possono essere confrontati solo con &#39; Non &#39; perché &#39; typename &#39; è un tipo nullable"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32128
- vbc32128
helpviewer_keywords: BC32128
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ec0ae1561bfbee998e7c65f6023012c0f982a8a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="39isnot39-operand-of-type-39typename39-can-only-be-compared-to-39nothing39-because-39typename39-is-a-nullable-type"></a>&#39; IsNot &#39; operando di tipo &#39; typename &#39; possono essere confrontati solo con &#39; Non &#39; perché &#39; typename &#39; è un tipo nullable
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
