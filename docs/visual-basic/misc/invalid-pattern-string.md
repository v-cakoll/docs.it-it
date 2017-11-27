---
title: Stringa di ricerca non valida
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: ec1aecdb-5339-4a93-be71-eec56b1d7438
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f824a5844d6d2b365358030119826266a4b42ef3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="invalid-pattern-string"></a>Stringa di ricerca non valida
La stringa di ricerca specificata nell'operazione `Like` di una ricerca non è valida.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Esaminare i valori validi per le espressioni dell'elenco.  
  
2.  Verificare che il carattere iniziale dell'intervallo di modelli sia minore di quello finale, come in `[a-z]`.  
  
3.  Verificare che nell'intervallo di modelli non ci siano più trattini contigui, come in `[a--z]`.  
  
4.  Verificare che gli intervalli di modelli terminino con una parentesi quadra di chiusura.  
  
## <a name="see-also"></a>Vedere anche  
 [Operatore Like](../../visual-basic/language-reference/operators/like-operator.md)
