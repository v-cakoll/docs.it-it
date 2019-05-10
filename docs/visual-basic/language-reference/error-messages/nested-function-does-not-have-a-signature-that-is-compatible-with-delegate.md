---
title: La funzione annidata non dispone di una firma compatibile con il delegato '<delegatename>'
ms.date: 07/20/2015
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
ms.openlocfilehash: 912962e2ab39c4811294ccc225814b230100e12a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592008"
---
# <a name="nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-delegatename"></a>Funzione annidata non ha una firma compatibile con il delegato '\<NomeDelegato >'
Un'espressione lambda assegnata a un delegato che ha una firma compatibile. Nel codice seguente, ad esempio, è consigliabile delegare `Del` ha due parametri di tipo integer.  
  
```vb  
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer  
```  
  
 L'errore viene generato se un'espressione lambda con un argomento è dichiarata come tipo `Del`:  
  
```vb  
' Neither of these is valid.   
' Dim lambda1 As Del = Function(n As Integer) n + 1  
' Dim lambda2 As Del = Function(n) n + 1  
```  
  
 **ID errore:** BC36532  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Modificare la definizione del delegato o l'espressione lambda assegnata in modo che le firme sono compatibili.  
  
## <a name="see-also"></a>Vedere anche

- [Conversione di tipo relaxed del delegato](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [Espressioni lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
