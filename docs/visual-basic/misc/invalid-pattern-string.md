---
title: Stringa di ricerca non valida
ms.date: 07/20/2015
ms.assetid: ec1aecdb-5339-4a93-be71-eec56b1d7438
ms.openlocfilehash: aa408f4cecc2a2774cb98cba96cd04a67afcc546
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402213"
---
# <a name="invalid-pattern-string"></a>Stringa di ricerca non valida
La stringa di ricerca specificata nell'operazione `Like` di una ricerca non è valida.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Esaminare i valori validi per le espressioni dell'elenco.  
  
2. Verificare che il carattere iniziale dell'intervallo di modelli sia minore di quello finale, come in `[a-z]`.  
  
3. Verificare che nell'intervallo di modelli non ci siano più trattini contigui, come in `[a--z]`.  
  
4. Verificare che gli intervalli di modelli terminino con una parentesi quadra di chiusura.  
  
## <a name="see-also"></a>Vedere anche

- [Operatore Like](../language-reference/operators/like-operator.md)
