---
title: Routine ricorsive (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], that call themselves
- procedures [Visual Basic], recursive
- procedures [Visual Basic], calling
- recursive procedures
- functions [Visual Basic], calling recursively
- recursion
ms.assetid: ba1d3962-b4c3-48d3-875e-96fdb4198327
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 444eeaf043cf3710c5154fd7e8577590e3ce7d1e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="recursive-procedures-visual-basic"></a>Routine ricorsive (Visual Basic)
Oggetto *ricorsiva* procedure è una classe che chiama se stessa. In generale, questo non è il modo più efficace per scrivere [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] codice.  
  
 La procedura seguente usa la ricorsione per calcolare il fattoriale del relativo argomento originale.  
  
 [!code-vb[VbVbcnProcedures#51](./codesnippet/VisualBasic/recursive-procedures_1.vb)]  
  
## <a name="considerations-with-recursive-procedures"></a>Considerazioni sulle routine ricorsive  
 **Le condizioni di limitazione**. È necessario progettare una routine ricorsiva per verificare la presenza di almeno una condizione in grado di terminare la ricorsione e, è necessario gestire anche nel caso in cui tale condizione non viene soddisfatta entro un numero ragionevole di chiamate ricorsive. Senza almeno una condizione che può essere soddisfatta senza errori, la stored procedure viene eseguito un rischio elevato dell'esecuzione in un ciclo infinito.  
  
 **Utilizzo memoria**. L'applicazione dispone di una quantità limitata di spazio per le variabili locali. Ogni volta che una routine chiama se stessa, viene utilizzato più lo spazio per le copie aggiuntive delle variabili locali. Se questo processo continua in modo indefinito, provoca un <xref:System.StackOverflowException> errore.  
  
 **L'efficienza**. È quasi sempre possibile sostituire un ciclo per la ricorsione. L'overhead del passaggio degli argomenti, l'inizializzazione di ulteriore spazio di archiviazione e la restituzione di valori non dispone di un ciclo. Le prestazioni migliorano in modo significativo senza chiamate ricorsive.  
  
 **Ricorsione reciproca**. Si noterà probabilmente prestazioni estremamente insufficienti o anche un ciclo infinito se due procedure comunicano tra loro. Tale progettazione presenta gli stessi problemi come una singola routine ricorsiva, ma può essere difficile rilevare ed eseguire il debug.  
  
 **La chiamata con parentesi**. Quando un `Function` routine chiama se stessa in modo ricorsivo, è necessario seguire il nome della routine con parentesi, anche se è presente alcun elenco di argomenti. In caso contrario, il nome della funzione viene eseguito come rappresenta il valore restituito della funzione.  
  
 **Test**. Se si scrive una routine ricorsiva, è necessario eseguirne il test con molta attenzione per assicurarsi che soddisfi sempre alcune condizioni di limitazione. È inoltre necessario assicurarsi che non è possibile eseguire esaurito la memoria a causa di un numero eccessivo di chiamate ricorsive.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.StackOverflowException>  
 [Routine](./index.md)  
 [Routine Sub](./sub-procedures.md)  
 [Routine Function](./function-procedures.md)  
 [Routine Property](./property-procedures.md)  
 [Routine di operatore](./operator-procedures.md)  
 [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)  
 [Overload della routine](./procedure-overloading.md)  
 [Risoluzione dei problemi relativi alle routine](./troubleshooting-procedures.md)  
 [Strutture di ciclo](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [Risoluzione dei problemi relativi ad eccezioni: System.StackOverflowException](http://msdn.microsoft.com/library/51b71217-c507-4f5b-bc35-0236180d7968)
