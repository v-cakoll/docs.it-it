---
title: Risoluzione dei problemi relativi ai gestori eventi ereditati
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting events [Visual Basic]
- inherited events [Visual Basic]
- troubleshooting Visual Basic, event handlers
- event handling, troubleshooting
- event handlers, troubleshooting
ms.assetid: e1c8759f-5370-4308-8476-8c48b73509bf
ms.openlocfilehash: fd2ef1c25233cc1eaad6bcde68923688393b471d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345099"
---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a>Risoluzione dei problemi relativi ai gestori eventi ereditati in Visual Basic
In questo argomento vengono elencati i problemi comuni che si verificano con i gestori eventi nei componenti ereditati.  
  
## <a name="procedures"></a>Procedure  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a>Il codice nel gestore eventi viene eseguito due volte per ogni chiamata  
  
- Un gestore eventi ereditato non deve includere una clausola [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) . Il metodo nella classe base è già associato all'evento e verrà attivato di conseguenza. Rimuovere la clausola `Handles` dal metodo ereditato.  
  
     [!code-vb[VbVbalrEvents#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#32)]  
  
- Se il metodo ereditato non dispone di una parola chiave `Handles`, verificare che il codice non contenga un' [istruzione AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md) aggiuntiva o altri metodi che gestiscono lo stesso evento.  
  
## <a name="see-also"></a>Vedere anche

- [Eventi](../../../../visual-basic/programming-guide/language-features/events/index.md)
