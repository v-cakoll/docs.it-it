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
ms.openlocfilehash: aad068b5857eb956ded63fa2a57cb163d3cf5c58
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013842"
---
# <a name="cannot-refer-to-an-instance-member-of-a-class-from-within-a-shared-method-or-shared-member-initializer-without-an-explicit-instance-of-the-class"></a>Impossibile fare riferimento a un membro di istanza di una classe all'interno di un metodo condiviso o di un inizializzatore di membri condivisi senza un'istanza esplicita della classe
Si è provato a fare riferimento a un membro non condiviso di una classe all'interno di una routine condivisa. L'esempio seguente illustra una situazione di questo tipo.  
  
```  
Class sample  
    Public x as Integer  
    Public Shared Sub setX()  
        x = 10  
    End Sub  
End Class  
```  
  
 Nell'esempio precedente, l'istruzione di assegnazione `x = 10` genera questo messaggio di errore. Questo avviene perché una procedura condivisa sta tentando di accedere a una variabile di istanza.  
  
 La variabile `x` è un membro di istanza perché non è dichiarato come [Shared](../../../visual-basic/language-reference/modifiers/shared.md). Ogni istanza della classe `sample` contiene il proprio variabile `x`. Quando di impostazione o modifica il valore di un'istanza `x`, non influenza il valore di `x` in qualsiasi altra istanza.  
  
 Tuttavia, la procedura `setX` viene `Shared` tra tutte le istanze della classe `sample`. Ciò significa non è associato ad alcuna istanza della classe, ma piuttosto opera indipendentemente dalle singole istanze. Poiché non dispone di alcuna connessione con una particolare istanza `setX` non può accedere a una variabile di istanza. E deve essere utilizzata solo in `Shared` variabili. Quando `setX` imposta o modifica il valore di una variabile condivisa, che nuovo valore è disponibile per tutte le istanze della classe.  
  
 **ID errore:** BC30369  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Decidere se il membro venga condiviso tra tutte le istanze della classe o mantenuto singoli per ogni istanza.  
  
2. Se si desidera che una singola copia del membro venga condiviso tra tutte le istanze, aggiungere il `Shared` parola chiave per la dichiarazione del membro. Mantenere il `Shared` parola chiave nella dichiarazione di routine.  
  
3. Se si vuole che ogni istanza per mantenere la propria copia del membro, non specificare `Shared` per la dichiarazione di membro. Rimuovere il `Shared` parola chiave dalla dichiarazione di routine.  
  
## <a name="see-also"></a>Vedere anche

- [Shared](../../../visual-basic/language-reference/modifiers/shared.md)
