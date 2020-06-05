---
title: La funzione di accesso 'Set' della proprietà '<propertyname>' non è accessibile
ms.date: 07/20/2015
f1_keywords:
- vbc31102
- bc31102
helpviewer_keywords:
- BC31102
ms.assetid: 6f7b31b7-3656-4ae1-8851-90f5f4c6950a
ms.openlocfilehash: 077533a5b1fe241b61ded9516ad8f450d7dbbf5e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400344"
---
# <a name="set-accessor-of-property-propertyname-is-not-accessible"></a>La funzione di accesso 'Set' della proprietà '\<propertyname>' non è accessibile
Un'istruzione tenta di archiviare il valore di una proprietà quando non ha accesso alla routine della proprietà `Set` .  
  
 Se l' [istruzione set](../statements/set-statement.md) è contrassegnata con un livello di accesso più restrittivo rispetto alla relativa [istruzione Property](../statements/property-statement.md), un tentativo di impostare il valore della proprietà potrebbe non riuscire nei casi seguenti:  
  
- L' `Set` istruzione è contrassegnata come [privata](../modifiers/private.md) e il codice chiamante è all'esterno della classe o della struttura in cui è definita la proprietà.  
  
- L' `Set` istruzione è contrassegnata come [protetta](../modifiers/protected.md) e il codice chiamante non si trova nella classe o nella struttura in cui è definita la proprietà, né in una classe derivata.  
  
- L' `Set` istruzione è contrassegnata come [Friend](../modifiers/friend.md) e il codice chiamante non si trova nello stesso assembly in cui è definita la proprietà.  
  
 **ID errore:** BC31102  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Se si ha il controllo del codice sorgente che definisce la proprietà, provare a dichiarare la `Set` routine con lo stesso livello di accesso della proprietà stessa.  
  
- Se non si ha il controllo del codice sorgente che definisce la proprietà o se è necessario limitare il `Set` livello di accesso della routine più della proprietà stessa, provare a spostare l'istruzione che imposta il valore della proprietà su un'area di codice che dispone di un accesso migliore alla proprietà.  
  
## <a name="see-also"></a>Vedere anche

- [Routine Property](../../programming-guide/language-features/procedures/property-procedures.md)
- [Procedura: dichiarare una proprietà con livelli di accesso misti](../../programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
