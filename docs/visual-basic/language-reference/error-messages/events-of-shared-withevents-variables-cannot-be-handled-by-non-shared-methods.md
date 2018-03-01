---
title: Impossibile gestire gli eventi delle variabili WithEvents condivise mediante metodi non condivisi
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords:
- BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 53372927b88df3946583564492df42170f302739
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a>Impossibile gestire gli eventi delle variabili WithEvents condivise mediante metodi non condivisi
Una variabile dichiarata con la `Shared` modificatore è una variabile condivisa. Una variabile condivisa identifica esattamente una posizione di archiviazione. Una variabile dichiarata con la `WithEvents` modificatore asserisce che il tipo a cui appartiene la variabile gestisce il set di eventi che genera la variabile. Quando viene assegnato un valore alla variabile, la proprietà creato per il `WithEvents` dichiarazione disconnette qualsiasi gestore eventi esistente e associa il nuovo gestore eventi tramite il `Add` metodo.  
  
 **ID errore:** BC30594  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Dichiarare il gestore eventi `Shared`.  
  
## <a name="see-also"></a>Vedere anche  
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)  
 [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)
