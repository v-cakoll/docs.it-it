---
title: "'#ElseIf' deve essere preceduto da un '#If' o '#ElseIf' corrispondente"
ms.date: 07/20/2015
f1_keywords:
- vbc30014
- bc30014
helpviewer_keywords:
- BC30014
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
ms.openlocfilehash: 4832fb80cfbe42c7a1303e0de69f36784711c05a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803363"
---
# <a name="elseif-must-be-preceded-by-a-matching-if-or-elseif"></a>'#ElseIf' deve essere preceduto da un '#If' o '#ElseIf' corrispondente
`#ElseIf` è una direttiva di compilazione condizionale. Un' `#ElseIf` clausola deve essere preceduta da un oggetto corrispondente `#If` o `#ElseIf` clausola.  
  
 **ID errore:** BC30014  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Verificare che un precedente `#If` oppure `#ElseIf` non sia stata separata da questo `#ElseIf` mediante un blocco di compilazione condizionale o inserita in posizione errata `#End If`.  
  
2. Se il `#ElseIf` è preceduto da un `#Else` direttiva, rimuovere il `#Else` oppure modificarlo in base a un `#ElseIf`.  
  
3. Se tutti gli altri elementi sono in ordine, aggiungere una direttiva `#If` all'inizio del blocco di compilazione condizionale.  
  
## <a name="see-also"></a>Vedere anche

- [Direttive #If...Then...#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
