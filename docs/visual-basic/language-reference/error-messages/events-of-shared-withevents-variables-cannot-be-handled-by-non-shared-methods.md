---
title: Impossibile gestire gli eventi delle variabili WithEvents condivise mediante metodi non condivisi
ms.date: 07/20/2015
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords:
- BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
ms.openlocfilehash: f61f4cd17b1bb3088117e0a0d91b186fd40db3b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33585171"
---
# <a name="events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a>Impossibile gestire gli eventi delle variabili WithEvents condivise mediante metodi non condivisi
Una variabile dichiarata con la `Shared` modificatore è una variabile condivisa. Una variabile condivisa identifica esattamente una posizione di archiviazione. Una variabile dichiarata con la `WithEvents` modificatore asserisce che il tipo a cui appartiene la variabile gestisce il set di eventi che genera la variabile. Quando viene assegnato un valore alla variabile, la proprietà creato per il `WithEvents` dichiarazione disconnette qualsiasi gestore eventi esistente e associa il nuovo gestore eventi tramite il `Add` metodo.  
  
 **ID errore:** BC30594  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Dichiarare il gestore eventi `Shared`.  
  
## <a name="see-also"></a>Vedere anche  
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)  
 [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)
