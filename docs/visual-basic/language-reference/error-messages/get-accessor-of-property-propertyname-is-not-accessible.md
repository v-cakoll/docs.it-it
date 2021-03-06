---
title: La funzione di accesso 'Get' della proprietà '<propertyname>' non è accessibile
ms.date: 07/20/2015
f1_keywords:
- vbc31103
- bc31103
helpviewer_keywords:
- BC31103
ms.assetid: 3c346c32-7669-4b04-841d-7a9df9cb703e
ms.openlocfilehash: cb953671e624d5b9170aa0b3a9dd80c7ba8337e3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402914"
---
# <a name="get-accessor-of-property-propertyname-is-not-accessible"></a>La funzione di accesso 'Get' della proprietà '\<propertyname>' non è accessibile
Un'istruzione tenta di recuperare il valore di una proprietà quando non ha accesso alla routine della proprietà `Get` .  
  
 Se l' [istruzione Get](../statements/get-statement.md) è contrassegnata con un livello di accesso più restrittivo rispetto alla relativa [istruzione Property](../statements/property-statement.md), un tentativo di leggere il valore della proprietà potrebbe non riuscire nei casi seguenti:  
  
- L' `Get` istruzione è contrassegnata come [privata](../modifiers/private.md) e il codice chiamante è all'esterno della classe o della struttura in cui è definita la proprietà.  
  
- L' `Get` istruzione è contrassegnata come [protetta](../modifiers/protected.md) e il codice chiamante non si trova nella classe o nella struttura in cui è definita la proprietà, né in una classe derivata.  
  
- L' `Get` istruzione è contrassegnata come [Friend](../modifiers/friend.md) e il codice chiamante non si trova nello stesso assembly in cui è definita la proprietà.  
  
 **ID errore:** BC31103  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Se si ha il controllo del codice sorgente che definisce la proprietà, provare a dichiarare la `Get` routine con lo stesso livello di accesso della proprietà stessa.  
  
- Se non si ha il controllo del codice sorgente che definisce la proprietà o se è necessario limitare il `Get` livello di accesso della routine più della proprietà stessa, provare a spostare l'istruzione che legge il valore della proprietà in un'area di codice con un accesso migliore alla proprietà.  
  
## <a name="see-also"></a>Vedere anche

- [Routine Property](../../programming-guide/language-features/procedures/property-procedures.md)
- [Procedura: dichiarare una proprietà con livelli di accesso misti](../../programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
