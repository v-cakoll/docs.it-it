---
title: Sub o Function non definita
ms.date: 07/20/2015
f1_keywords:
- vbrID35
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
ms.openlocfilehash: 9eb13d943f9f1cffc984847f7339111e06f5aa6b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84373927"
---
# <a name="sub-or-function-not-defined-visual-basic"></a>Sub o Function non definita (Visual Basic)
Per `Sub` poter `Function` essere chiamato, è necessario definire un oggetto o. Alcune cause possibili di questo errore sono:  
  
- Ortografia del nome della procedura.  
  
- Tentativo di chiamare una routine da un altro progetto senza aggiungere esplicitamente un riferimento a tale progetto nella finestra di dialogo **riferimenti** .  
  
- Specifica di una routine che non è visibile alla procedura chiamante.  
  
- Dichiarazione di una routine della libreria di collegamento dinamico (DLL) di Windows o di una routine di risorsa di codice Macintosh che non si trova nella libreria o nella risorsa di codice specificata.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Verificare che il nome della stored procedure sia stato digitato correttamente.  
  
2. Trovare il nome del progetto contenente la procedura che si desidera chiamare nella finestra di dialogo **riferimenti** . Se non viene visualizzato, fare clic sul pulsante **Sfoglia** per cercarlo. Selezionare la casella di controllo a sinistra del nome del progetto, quindi fare clic su **OK**.  
  
3. Verificare il nome della routine.  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di errore](../../programming-guide/language-features/error-types.md)
- [Gestione dei riferimenti in un progetto](/visualstudio/ide/managing-references-in-a-project)
- [Istruzione Sub](../statements/sub-statement.md)
- [Istruzione Function](../statements/function-statement.md)
