---
title: Routine ricorsive (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], that call themselves
- procedures [Visual Basic], recursive
- procedures [Visual Basic], calling
- recursive procedures
- functions [Visual Basic], calling recursively
- recursion
ms.assetid: ba1d3962-b4c3-48d3-875e-96fdb4198327
ms.openlocfilehash: b5cbe0dfa8053a93cde9c92ffe87f0eae15d3efd
ms.sourcegitcommit: facefcacd7ae2e5645e463bc841df213c505ffd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2019
ms.locfileid: "55739293"
---
# <a name="recursive-procedures-visual-basic"></a>Routine ricorsive (Visual Basic)
Oggetto *ricorsiva* routine è quella che chiama se stesso. In generale, questo non è il modo più efficace per scrivere il codice Visual Basic.  
  
 La procedura seguente usa la ricorsione per la quale calcolare il fattoriale del relativo argomento originale.  
  
 [!code-vb[VbVbcnProcedures#51](./codesnippet/VisualBasic/recursive-procedures_1.vb)]  
  
## <a name="considerations-with-recursive-procedures"></a>Considerazioni sulle routine ricorsive  
 **Le condizioni di limitazione**. È necessario progettare una routine ricorsiva da verificare per almeno una condizione che può terminare la ricorsione ed è anche necessario gestire il caso in cui nessun tale condizione viene soddisfatta entro un numero ragionevole di chiamate ricorsive. Senza almeno una condizione che può essere soddisfatti senza l'esito negativo, la routine esegue un elevato rischio di esecuzione in un ciclo infinito.  
  
 **Utilizzo memoria**. L'applicazione dispone di una quantità limitata di spazio per le variabili locali. Ogni volta che una routine chiama se stessa, utilizza una quantità di spazio per le altre copie delle variabili locali. Se questo processo continua per un periodo illimitato, provoca un <xref:System.StackOverflowException> errore.  
  
 **L'efficienza**. È quasi sempre possibile sostituire un ciclo di ricorsione. Un ciclo non ha l'overhead di passaggio di argomenti, l'inizializzazione ulteriore spazio di archiviazione e la restituzione di valori. Le prestazioni possono essere molto meglio senza le chiamate ricorsive.  
  
 **Ricorsione reciproca**. Si noterà probabilmente molto una riduzione delle prestazioni, o anche un ciclo infinito, se due procedure comunicano tra loro. Tale progettazione presenta gli stessi problemi come una singola routine ricorsiva, ma può essere difficile rilevare ed eseguire il debug.  
  
 **La chiamata con parentesi**. Quando un `Function` routine chiama se stessa in modo ricorsivo, è necessario seguire il nome della routine tra parentesi, anche se è presente alcun elenco di argomenti. In caso contrario, il nome della funzione viene eseguito in modo che rappresenti il valore restituito della funzione.  
  
 **Test**. Se si scrive una routine ricorsiva, è consigliabile testare con estrema attenzione per assicurarsi che soddisfi sempre una condizione di limitazione. È inoltre necessario assicurarsi che non è possibile eseguire esaurito la memoria a causa di un numero eccessivo di chiamate ricorsive.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.StackOverflowException>
- [Routine](./index.md)
- [Routine Sub](./sub-procedures.md)
- [Routine Function](./function-procedures.md)
- [Routine Property](./property-procedures.md)
- [Routine di operatore](./operator-procedures.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Overload della routine](./procedure-overloading.md)
- [Risoluzione dei problemi relativi alle routine](./troubleshooting-procedures.md)
- [Strutture di ciclo](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
