---
title: Routine ricorsive
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
ms.openlocfilehash: 646d4e29ed7a0b6367d4b35a7f8641bcf659e616
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352548"
---
# <a name="recursive-procedures-visual-basic"></a>Routine ricorsive (Visual Basic)

Una routine *ricorsiva* è una procedura che chiama se stessa. In generale, questo non è il modo più efficace per scrivere codice Visual Basic.  
  
 Nella procedura riportata di seguito viene utilizzata la ricorsione per calcolare il fattoriale dell'argomento originale.  
  
 [!code-vb[VbVbcnProcedures#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#51)]  
  
## <a name="considerations-with-recursive-procedures"></a>Considerazioni sulle procedure ricorsive

 **Condizioni di limitazione**. È necessario progettare una procedura ricorsiva per testare almeno una condizione in grado di terminare la ricorsione ed è inoltre necessario gestire il caso in cui la condizione non venga soddisfatta entro un numero ragionevole di chiamate ricorsive. Senza almeno una condizione che può essere soddisfatta senza esito negativo, la procedura esegue un elevato rischio di esecuzione in un ciclo infinito.

 **Utilizzo memoria**. L'applicazione dispone di una quantità limitata di spazio per le variabili locali. Ogni volta che una routine chiama se stessa, USA più spazio per le copie aggiuntive delle variabili locali. Se questo processo continua per un periodo illimitato, causa un errore di <xref:System.StackOverflowException>.

 **Efficienza**. È quasi sempre possibile sostituire un ciclo per la ricorsione. Un ciclo non ha il sovraccarico del passaggio di argomenti, l'inizializzazione di archiviazione aggiuntiva e la restituzione di valori. Le prestazioni possono essere molto migliori senza chiamate ricorsive.

 **Ricorsione reciproca**. Se due procedure si chiamano a vicenda, è possibile che si osservi un numero di prestazioni molto ridotto o anche un ciclo infinito. Tale progettazione presenta gli stessi problemi di una singola routine ricorsiva, ma può essere più difficile da rilevare ed eseguire il debug.

 **Chiamata con le parentesi**. Quando una `Function` routine chiama se stessa in modo ricorsivo, è necessario seguire il nome della procedura con le parentesi, anche se non è presente alcun elenco di argomenti. In caso contrario, il nome della funzione viene considerato come che rappresenta il valore restituito della funzione.

 **Test**. Se si scrive una routine ricorsiva, è consigliabile testarla con molta attenzione per assicurarsi che soddisfi sempre una condizione di limitazione. È inoltre necessario assicurarsi che non sia possibile esaurire la memoria a causa di un numero eccessivo di chiamate ricorsive.

## <a name="see-also"></a>Vedere anche

- <xref:System.StackOverflowException>
- [Routine](index.md)
- [Routine Sub](sub-procedures.md)
- [Routine Function](function-procedures.md)
- [Routine Property](property-procedures.md)
- [Routine di operatore](operator-procedures.md)
- [Parametri e argomenti delle routine](procedure-parameters-and-arguments.md)
- [Overload della routine](procedure-overloading.md)
- [Risoluzione dei problemi relativi alle routine](troubleshooting-procedures.md)
- [Strutture di ciclo](../control-flow/loop-structures.md)
