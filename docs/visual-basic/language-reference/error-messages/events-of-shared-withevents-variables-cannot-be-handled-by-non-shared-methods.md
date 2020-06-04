---
title: Impossibile gestire gli eventi delle variabili WithEvents condivise mediante metodi non condivisi
ms.date: 07/20/2015
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords:
- BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
ms.openlocfilehash: fc163c1069aa6f41766664e0fa5f5a9c34a1f73d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409569"
---
# <a name="events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a>Impossibile gestire gli eventi delle variabili WithEvents condivise mediante metodi non condivisi
Una variabile dichiarata con il `Shared` modificatore è una variabile condivisa. Una variabile condivisa identifica esattamente un percorso di archiviazione. Una variabile dichiarata con il `WithEvents` modificatore dichiara che il tipo a cui appartiene la variabile gestisce il set di eventi generato dalla variabile. Quando un valore viene assegnato alla variabile, la proprietà creata dalla `WithEvents` dichiarazione sgancia qualsiasi gestore eventi esistente e associa il nuovo gestore eventi tramite il `Add` metodo.  
  
 **ID errore:** BC30594  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Dichiarare il gestore dell'evento `Shared` .  
  
## <a name="see-also"></a>Vedere anche

- [Condivisa](../modifiers/shared.md)
- [WithEvents](../modifiers/withevents.md)
