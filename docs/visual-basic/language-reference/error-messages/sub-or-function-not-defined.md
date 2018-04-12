---
title: Sub o Function non definita (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID35
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6237ca26b06bdffa06499607e634b3222725c189
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="sub-or-function-not-defined-visual-basic"></a>Sub o Function non definita (Visual Basic)
Oggetto `Sub` o `Function` deve essere definito per essere chiamati. Alcune cause possibili di questo errore sono:  
  
-   Errore di ortografia il nome della stored procedure.  
  
-   Tentativo di chiamare una routine da un altro progetto senza aggiungere in modo esplicito un riferimento a progetto nel **riferimenti** la finestra di dialogo.  
  
-   Specifica una routine che non è visibile alla routine chiamante.  
  
-   Dichiarazione di una routine di libreria a collegamento dinamico (DLL) di Windows o di una routine di risorsa codice Macintosh che non si trova la risorsa di libreria o di codice specificata.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Assicurarsi che il nome della routine sia digitato correttamente.  
  
2.  Trovare il nome del progetto contenente la routine da chiamare **riferimenti** la finestra di dialogo. Se non è visualizzato, fare clic su di **Sfoglia** pulsante per eseguire la ricerca. Selezionare la casella di controllo a sinistra del nome del progetto e quindi fare clic su **OK**.  
  
3.  Controllare il nome della routine.  
  
## <a name="see-also"></a>Vedere anche  
 [Tipi di errore](../../../visual-basic/programming-guide/language-features/error-types.md)  
 [Gestione dei riferimenti in un progetto](/visualstudio/ide/managing-references-in-a-project)  
 [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)
