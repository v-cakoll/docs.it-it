---
title: Risoluzione dei problemi relativi ai gestori eventi ereditati in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting events [Visual Basic]
- inherited events [Visual Basic]
- troubleshooting Visual Basic, event handlers
- event handling, troubleshooting
- event handlers, troubleshooting
ms.assetid: e1c8759f-5370-4308-8476-8c48b73509bf
ms.openlocfilehash: 704ca667a6d14ade7be0192e872f5e40791cb864
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58830188"
---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a>Risoluzione dei problemi relativi ai gestori eventi ereditati in Visual Basic
Questo argomento elenca i problemi comuni che si verificano con i gestori eventi nei componenti ereditati.  
  
## <a name="procedures"></a>Procedure  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a>Viene eseguito due volte per ogni chiamata di codice nel gestore eventi  
  
-   Non deve includere un gestore eventi ereditato un [gestisce](../../../../visual-basic/language-reference/statements/handles-clause.md) clausola. Il metodo nella classe di base è già associato all'evento e verrà generato di conseguenza. Rimuovere il `Handles` clausola dal metodo ereditato.  
  
     [!code-vb[VbVbalrEvents#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#32)]  
  
-   Se il metodo ereditato non ha un `Handles` parola chiave, verificare che il codice non contenga un ulteriore [istruzione AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md) o qualsiasi altro metodo che gestisce l'evento stesso.  
  
## <a name="see-also"></a>Vedere anche

- [Eventi](../../../../visual-basic/programming-guide/language-features/events/index.md)
