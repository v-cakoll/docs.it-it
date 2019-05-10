---
title: Sub o Function non definita (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID35
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
ms.openlocfilehash: 3a56d5596c79900bb5818a6ed7f8736859b5ea15
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64593192"
---
# <a name="sub-or-function-not-defined-visual-basic"></a>Sub o Function non definita (Visual Basic)
Oggetto `Sub` o `Function` deve essere definito per essere chiamati. Alcune cause possibili di questo errore sono:  
  
- Errore di ortografia il nome della routine.  
  
- Tentativo di chiamare una routine da un altro progetto senza aggiungere in modo esplicito un riferimento al progetto nella **riferimenti** nella finestra di dialogo.  
  
- Specifica una routine che non è visibile alla routine chiamante.  
  
- Dichiara una routine di libreria a collegamento dinamico (DLL) Windows o routine Macintosh risorsa codice che non si trova la risorsa di libreria o codice specificata.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Assicurarsi che il nome della routine sia digitato correttamente.  
  
2. Trovare il nome del progetto contenente le procedure da chiamare **riferimenti** nella finestra di dialogo. Se non viene visualizzato, scegliere il **esplorare** pulsante per eseguire la ricerca. Selezionare la casella di controllo a sinistra del nome del progetto e quindi fare clic su **OK**.  
  
3. Controllare il nome della routine.  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di errore](../../../visual-basic/programming-guide/language-features/error-types.md)
- [Gestione dei riferimenti in un progetto](/visualstudio/ide/managing-references-in-a-project)
- [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)
