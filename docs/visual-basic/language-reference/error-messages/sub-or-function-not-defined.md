---
title: Sub o Function non definita
ms.date: 07/20/2015
f1_keywords:
- vbrID35
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
ms.openlocfilehash: 8b81460eccb6be8baa2ea7bc68d0f80c9d16398e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349572"
---
# <a name="sub-or-function-not-defined-visual-basic"></a>Sub o Function non definita (Visual Basic)
Per poter essere chiamato, è necessario definire un `Sub` o `Function`. Alcune cause possibili di questo errore sono:  
  
- Ortografia del nome della procedura.  
  
- Tentativo di chiamare una routine da un altro progetto senza aggiungere esplicitamente un riferimento a tale progetto nella finestra di dialogo **riferimenti** .  
  
- Specifica di una routine che non è visibile alla procedura chiamante.  
  
- Dichiarazione di una routine della libreria di collegamento dinamico (DLL) di Windows o di una routine di risorsa di codice Macintosh che non si trova nella libreria o nella risorsa di codice specificata.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Verificare che il nome della stored procedure sia stato digitato correttamente.  
  
2. Trovare il nome del progetto contenente la procedura che si desidera chiamare nella finestra di dialogo **riferimenti** . Se non viene visualizzato, fare clic sul pulsante **Sfoglia** per cercarlo. Selezionare la casella di controllo a sinistra del nome del progetto, quindi fare clic su **OK**.  
  
3. Verificare il nome della routine.  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di errore](../../../visual-basic/programming-guide/language-features/error-types.md)
- [Gestione dei riferimenti in un progetto](/visualstudio/ide/managing-references-in-a-project)
- [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)
