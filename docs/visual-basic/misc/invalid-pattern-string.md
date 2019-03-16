---
title: Stringa di ricerca non valida
ms.date: 07/20/2015
ms.assetid: ec1aecdb-5339-4a93-be71-eec56b1d7438
ms.openlocfilehash: bc2e91060ca1b0e21ea28b0f08febc3e0c54f4f1
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2019
ms.locfileid: "58027310"
---
# <a name="invalid-pattern-string"></a>Stringa di ricerca non valida
La stringa di ricerca specificata nell'operazione `Like` di una ricerca non è valida.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Esaminare i valori validi per le espressioni dell'elenco.  
  
2.  Verificare che il carattere iniziale dell'intervallo di modelli sia minore di quello finale, come in `[a-z]`.  
  
3.  Verificare che nell'intervallo di modelli non ci siano più trattini contigui, come in `[a--z]`.  
  
4.  Verificare che gli intervalli di modelli terminino con una parentesi quadra di chiusura.  
  
## <a name="see-also"></a>Vedere anche

- [Operatore Like](../../visual-basic/language-reference/operators/like-operator.md)
