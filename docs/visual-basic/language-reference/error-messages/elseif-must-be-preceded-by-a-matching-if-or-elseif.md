---
title: "'#ElseIf' deve essere preceduto da un '#If' o '#ElseIf' corrispondente"
ms.date: 07/20/2015
f1_keywords:
- vbc30014
- bc30014
helpviewer_keywords:
- BC30014
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
ms.openlocfilehash: 808cf35fb05da092cdef560721b2f667778aa78f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409660"
---
# <a name="elseif-must-be-preceded-by-a-matching-if-or-elseif"></a>'#ElseIf' deve essere preceduto da un '#If' o '#ElseIf' corrispondente
`#ElseIf` è una direttiva di compilazione condizionale. Una `#ElseIf` clausola deve essere preceduta da una `#If` clausola OR corrispondente `#ElseIf` .  
  
 **ID errore:** BC30014  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Verificare che un oggetto `#If` o precedente `#ElseIf` non sia stato separato da questo oggetto `#ElseIf` mediante un blocco di compilazione condizionale o un oggetto inserito in modo errato `#End If` .  
  
2. Se `#ElseIf` è preceduto da una `#Else` direttiva, rimuovere `#Else` o modificare il valore in un oggetto `#ElseIf` .  
  
3. Se tutti gli altri elementi sono in ordine, aggiungere una direttiva `#If` all'inizio del blocco di compilazione condizionale.  
  
## <a name="see-also"></a>Vedere anche

- [#If... Direttive then... #Else](../directives/if-then-else-directives.md)
