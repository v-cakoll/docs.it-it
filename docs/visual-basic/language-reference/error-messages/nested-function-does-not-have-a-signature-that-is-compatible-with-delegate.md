---
title: Funzione annidata non dispone di una firma compatibile con delegato &#39; &lt;NomeDelegato&gt;&#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 60cf15343023110561da3e3fcf202bd00394127a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-39ltdelegatenamegt39"></a>Funzione annidata non dispone di una firma compatibile con delegato &#39; &lt;NomeDelegato&gt;&#39;
Un'espressione lambda è stata assegnata a un delegato che ha una firma compatibile. Nel codice seguente, ad esempio, è consigliabile delegare `Del` presenta due parametri di tipo integer.  
  
```vb  
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer  
```  
  
 Se un'espressione lambda con un argomento è dichiarata come tipo, viene generato l'errore `Del`:  
  
```vb  
' Neither of these is valid.   
' Dim lambda1 As Del = Function(n As Integer) n + 1  
' Dim lambda2 As Del = Function(n) n + 1  
```  
  
 **ID errore:** BC36532  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Modificare la definizione del delegato o l'espressione lambda assegnata in modo che le firme compatibili.  
  
## <a name="see-also"></a>Vedere anche  
 [Conversione di tipo relaxed del delegato](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)  
 [Espressioni lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
