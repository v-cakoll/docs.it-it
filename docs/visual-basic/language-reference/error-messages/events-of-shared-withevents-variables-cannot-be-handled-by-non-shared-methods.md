---
title: Impossibile gestire gli eventi delle variabili WithEvents condivise mediante metodi non condivisi
ms.date: 07/20/2015
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords:
- BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
ms.openlocfilehash: 09f56d340322ee88afc54e7e8a53716777782d47
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54505770"
---
# <a name="events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a>Impossibile gestire gli eventi delle variabili WithEvents condivise mediante metodi non condivisi
Una variabile dichiarata con la `Shared` modificatore è una variabile condivisa. Una variabile condivisa identifica esattamente una posizione di archiviazione. Una variabile dichiarata con la `WithEvents` modificatore asserisce che il tipo a cui appartiene la variabile gestisce il set di eventi genera la variabile. Quando viene assegnato un valore alla variabile, la proprietà creata per il `WithEvents` dichiarazione qualsiasi gestore eventi esistente, scollega e collega il nuovo gestore di eventi tramite il `Add` (metodo).  
  
 **ID errore:** BC30594  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Dichiarare il gestore eventi `Shared`.  
  
## <a name="see-also"></a>Vedere anche
- [Shared](../../../visual-basic/language-reference/modifiers/shared.md)
- [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)
