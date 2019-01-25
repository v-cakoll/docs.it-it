---
title: 'Procedura: Creare una variabile che non cambia di valore (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], read-only
- variables [Visual Basic], constant value
ms.assetid: 86b59266-25df-4635-ae15-9b59c411d036
ms.openlocfilehash: 626b46123e3047b391cd67d3e85c25c5432b2a69
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54640199"
---
# <a name="how-to-create-a-variable-that-does-not-change-in-value-visual-basic"></a>Procedura: Creare una variabile che non cambia di valore (Visual Basic)
Il concetto di una variabile che non cambia il relativo valore potrebbe sembrare contraddittorio. Ma esistono situazioni in cui una costante non è fattibile e risulta utile avere una variabile con un valore fisso. In tal caso è possibile definire una variabile membro con il [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) (parola chiave).  
  
 Non è possibile usare la [istruzione Const](../../../../visual-basic/language-reference/statements/const-statement.md) dichiarare e assegnare un valore costante nelle circostanze seguenti:  
  
-   Il `Const` istruzione non accetta il tipo di dati da usare  
  
-   Non si conosce il valore in fase di compilazione  
  
-   È in grado di calcolare il valore costante in fase di compilazione  
  
### <a name="to-create-a-variable-that-does-not-change-in-value"></a>Per creare una variabile che non cambia di valore  
  
1.  A livello di modulo, dichiarare una variabile membro con il [istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md)e includere le [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) (parola chiave).  
  
    ```  
    Dim ReadOnly timeStarted  
    ```  
  
     È possibile specificare `ReadOnly` solo su una variabile membro. Ciò significa che è necessario definire la variabile a livello di modulo, di fuori di qualsiasi routine.  
  
2.  Se è possibile calcolare il valore in un'unica istruzione in fase di compilazione, usare una clausola di inizializzazione nel `Dim` istruzione. Seguire le [come](../../../../visual-basic/language-reference/statements/as-clause.md) clausola con un segno di uguale (`=`), seguita da un'espressione. Assicurarsi che il compilatore può valutare questa espressione a un valore costante.  
  
    ```  
    Dim ReadOnly timeStarted As Date = Now  
    ```  
  
     È possibile assegnare un valore per un `ReadOnly` variabile una sola volta. Una volta in questo caso, nessun codice mai possibile modificarne il valore.  
  
     Se non si conosce il valore in fase di compilazione o non è possibile calcolare in fase di compilazione in un'unica istruzione, è possibile assegnarla ancora in fase di esecuzione in un costruttore. A tale scopo, è necessario dichiarare il `ReadOnly` variabili a livello di classe o struttura. Nel costruttore per quella classe o struttura, calcolare il valore della variabile fissa e assegnarlo alla variabile prima della restituzione dal costruttore.  
  
## <a name="see-also"></a>Vedere anche
- [WriteOnly](../../../../visual-basic/language-reference/modifiers/writeonly.md)
- [Istruzione Const](../../../../visual-basic/language-reference/statements/const-statement.md)
