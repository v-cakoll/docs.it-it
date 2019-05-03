---
title: La funzione di accesso 'Get' della proprietà '<propertyname>' non è accessibile
ms.date: 07/20/2015
f1_keywords:
- vbc31103
- bc31103
helpviewer_keywords:
- BC31103
ms.assetid: 3c346c32-7669-4b04-841d-7a9df9cb703e
ms.openlocfilehash: 8fb78f3c14708c79f1910e202287c25a3b2213b7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803051"
---
# <a name="get-accessor-of-property-propertyname-is-not-accessible"></a>'Get' della funzione di accesso della proprietà '\<NomeProprietà >' non è accessibile
Un'istruzione prova a recuperare il valore di una proprietà quando non ha accesso alla proprietà `Get` procedure.  
  
 Se il [l'istruzione Get](../../../visual-basic/language-reference/statements/get-statement.md) è contrassegnata con un accesso più restrittivo livello relativa [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md), tenta di leggere il valore della proprietà potrebbe non riuscire nei casi seguenti:  
  
- Il `Get` istruzione è contrassegnata [Private](../../../visual-basic/language-reference/modifiers/private.md) e il codice chiamante è di fuori della classe o struttura in cui la proprietà è definita.  
  
- Il `Get` istruzione è contrassegnata [Protected](../../../visual-basic/language-reference/modifiers/protected.md) e il codice chiamante non nella classe o struttura in cui la proprietà è definita, né in una classe derivata.  
  
- Il `Get` istruzione è contrassegnata [Friend](../../../visual-basic/language-reference/modifiers/friend.md) e il codice chiamante non è presente nello stesso assembly in cui la proprietà è definita.  
  
 **ID errore:** BC31103  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Se si ha il controllo del codice sorgente che definisce la proprietà, si consideri la dichiarazione di `Get` procedure con lo stesso livello di accesso della proprietà stessa.  
  
- Se non si ha il controllo del codice sorgente che definisce la proprietà o se è necessario limitare il `Get` procedure più la proprietà stessa, provare a spostare l'istruzione che legge il valore della proprietà da un'area di codice che ha un accesso migliore al livello di accesso di proprietà.  
  
## <a name="see-also"></a>Vedere anche

- [Routine Property](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [Procedura: Dichiarare una proprietà con livelli di accesso misti](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
