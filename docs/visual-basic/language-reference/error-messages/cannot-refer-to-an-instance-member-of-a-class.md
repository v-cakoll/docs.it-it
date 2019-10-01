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
ms.openlocfilehash: a2a5ab99ff68e6dce783a2fd986ee6e8c15ae858
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701169"
---
# <a name="cannot-refer-to-an-instance-member-of-a-class-from-within-a-shared-method-or-shared-member-initializer-without-an-explicit-instance-of-the-class"></a>Impossibile fare riferimento a un membro di istanza di una classe all'interno di un metodo condiviso o di un inizializzatore di membri condivisi senza un'istanza esplicita della classe
Si è tentato di fare riferimento a un membro non condiviso di una classe all'interno di una procedura condivisa. Nell'esempio seguente viene illustrata una situazione di questo tipo.  
  
```vb  
Class sample  
    Public x as Integer  
    Public Shared Sub setX()  
        x = 10  
    End Sub  
End Class  
```  
  
 Nell'esempio precedente, l'istruzione di assegnazione `x = 10` genera questo messaggio di errore. Questo perché una procedura condivisa sta tentando di accedere a una variabile di istanza.  
  
 La variabile `x` è un membro di istanza perché non è dichiarata come [condivisa](../../../visual-basic/language-reference/modifiers/shared.md). Ogni istanza della classe `sample` contiene la propria variabile singola `x`. Quando un'istanza imposta o modifica il valore di `x`, non influisce sul valore di `x` in nessun'altra istanza.  
  
 Tuttavia, la procedura `setX` è `Shared` tra tutte le istanze della classe `sample`. Ciò significa che non è associato a una sola istanza della classe, ma funziona in modo indipendente dalle singole istanze. Poiché non dispone di una connessione a un'istanza specifica, `setX` non è in grado di accedere a una variabile di istanza. Deve funzionare solo su variabili `Shared`. Quando `setX` imposta o modifica il valore di una variabile condivisa, il nuovo valore è disponibile per tutte le istanze della classe.  
  
 **ID errore:** BC30369  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Decidere se si desidera che il membro venga condiviso tra tutte le istanze della classe o mantenuti singoli per ogni istanza.  
  
2. Se si desidera che una sola copia del membro venga condivisa tra tutte le istanze, aggiungere la parola chiave `Shared` alla dichiarazione del membro. Mantenere la parola chiave `Shared` nella dichiarazione di routine.  
  
3. Se si desidera che ogni istanza disponga di una copia singola del membro, non specificare `Shared` per la dichiarazione del membro. Rimuovere la parola chiave `Shared` dalla dichiarazione di routine.  
  
## <a name="see-also"></a>Vedere anche

- [Shared](../../../visual-basic/language-reference/modifiers/shared.md)
