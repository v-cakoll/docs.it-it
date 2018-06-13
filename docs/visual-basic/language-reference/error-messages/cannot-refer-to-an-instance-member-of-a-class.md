---
title: Impossibile fare riferimento a un membro di istanza di una classe all'interno di un metodo condiviso o di un inizializzatore di membri condivisi senza un'istanza esplicita della classe
ms.date: 07/20/2015
f1_keywords:
- vbc30369
- bc30369
helpviewer_keywords:
- Shared
- BC30369
ms.assetid: 39d9466b-c1f3-4406-91a5-3d6c52d23a3d
ms.openlocfilehash: 368539ed24d9819c8d1ddbbb9e3e0dff21d27c32
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590183"
---
# <a name="cannot-refer-to-an-instance-member-of-a-class-from-within-a-shared-method-or-shared-member-initializer-without-an-explicit-instance-of-the-class"></a>Impossibile fare riferimento a un membro di istanza di una classe all'interno di un metodo condiviso o di un inizializzatore di membri condivisi senza un'istanza esplicita della classe
Si è tentato di fare riferimento a un membro non condiviso di una classe all'interno di una routine condivisa. L'esempio seguente illustra una situazione.  
  
```  
Class sample  
    Public x as Integer  
    Public Shared Sub setX()  
        x = 10  
    End Sub  
End Class  
```  
  
 Nell'esempio precedente, l'istruzione di assegnazione `x = 10` genera questo messaggio di errore. Questo avviene perché una routine condivisa sta tentando di accedere a una variabile di istanza.  
  
 La variabile `x` è un membro di istanza perché non è dichiarato come [Shared](../../../visual-basic/language-reference/modifiers/shared.md). Ogni istanza della classe `sample` contiene una specifica variabile `x`. Quando un'istanza imposta o modifica il valore di `x`, non si applica il valore di `x` nelle altre istanze.  
  
 Tuttavia, la procedura `setX` è `Shared` tra tutte le istanze della classe `sample`. Ciò significa non è associata a ogni istanza della classe, ma funziona in modo indipendente da singole istanze. Poiché dispone di alcuna connessione con una particolare istanza `setX` non è possibile accedere a una variabile di istanza. Deve essere utilizzata solo per `Shared` variabili. Quando `setX` imposta o modifica il valore di una variabile condivisa, che è disponibile per tutte le istanze della classe nuovo valore.  
  
 **ID errore:** BC30369  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Decidere se il membro condiviso tra tutte le istanze della classe o mantenuto singoli per ogni istanza.  
  
2.  Se si desidera una singola copia del membro per essere condivisi tra tutte le istanze, aggiungere il `Shared` (parola chiave) alla dichiarazione del membro. Mantenere il `Shared` parola chiave nella dichiarazione di routine.  
  
3.  Se si desidera che ogni istanza per la propria copia del membro singola, non specificare `Shared` per la dichiarazione di membro. Rimuovere il `Shared` parola chiave dalla dichiarazione di routine.  
  
## <a name="see-also"></a>Vedere anche  
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)
