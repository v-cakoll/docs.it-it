---
title: '&#39;#ElseIf&#39; deve essere preceduto da un oggetto corrispondente &#39;#If&#39; o &#39;#ElseIf&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc30014
- bc30014
helpviewer_keywords:
- BC30014
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
ms.openlocfilehash: ef904173b1791309f6c2722bd959cabdad1d71da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="39elseif39-must-be-preceded-by-a-matching-39if39-or-39elseif39"></a>&#39;#ElseIf&#39; deve essere preceduto da un oggetto corrispondente &#39;#If&#39; o &#39;#ElseIf&#39;
`#ElseIf` è una direttiva di compilazione condizionale. Un `#ElseIf` clausola deve essere preceduta da un oggetto corrispondente `#If` o `#ElseIf` clausola.  
  
 **ID errore:** BC30014  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Verificare che un precedente `#If` o `#ElseIf` non è stato separato da questo `#ElseIf` da un blocco di compilazione condizionale o inserita in posizione errata `#End If`.  
  
2.  Se il `#ElseIf` è preceduto da un `#Else` direttiva, rimuovere il `#Else` o modificarla in modo che un `#ElseIf`.  
  
3.  Se tutti gli altri elementi sono in ordine, aggiungere una direttiva `#If` all'inizio del blocco di compilazione condizionale.  
  
## <a name="see-also"></a>Vedere anche  
 [Direttive #If...Then...#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
