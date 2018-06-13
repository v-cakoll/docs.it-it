---
title: 'Procedura: creare una variabile che non cambia di valore (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], read-only
- variables [Visual Basic], constant value
ms.assetid: 86b59266-25df-4635-ae15-9b59c411d036
ms.openlocfilehash: d63c254abe6d12c094e0d1252c9721f668947f09
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651376"
---
# <a name="how-to-create-a-variable-that-does-not-change-in-value-visual-basic"></a>Procedura: creare una variabile che non cambia di valore (Visual Basic)
Il concetto di una variabile che non cambia il relativo valore potrebbe sembrare contraddittorio. Ma esistono situazioni in cui una costante non è fattibile ed è utile disporre di una variabile con un valore fisso. In questo caso è possibile definire una variabile membro con il [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) (parola chiave).  
  
 Non è possibile utilizzare il [istruzione Const](../../../../visual-basic/language-reference/statements/const-statement.md) per dichiarare e assegnare un valore costante nelle circostanze seguenti:  
  
-   Il `Const` istruzione non accetta il tipo di dati che si desidera utilizzare  
  
-   Non si conosce il valore in fase di compilazione  
  
-   Non è possibile calcolare il valore costante in fase di compilazione  
  
### <a name="to-create-a-variable-that-does-not-change-in-value"></a>Per creare una variabile che non cambia di valore  
  
1.  A livello di modulo, dichiarare una variabile membro con il [Dim (istruzione)](../../../../visual-basic/language-reference/statements/dim-statement.md)e includere il [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) (parola chiave).  
  
    ```  
    Dim ReadOnly timeStarted  
    ```  
  
     È possibile specificare `ReadOnly` solo in una variabile membro. Ciò significa che è necessario definire la variabile a livello di modulo, di fuori di qualsiasi routine.  
  
2.  Se è possibile calcolare il valore in un'unica istruzione in fase di compilazione, utilizzare una clausola di inizializzazione nel `Dim` istruzione. Seguire il [come](../../../../visual-basic/language-reference/statements/as-clause.md) clausola con un segno di uguale (`=`), seguito da un'espressione. Assicurarsi che il compilatore può valutare questa espressione a un valore costante.  
  
    ```  
    Dim ReadOnly timeStarted As Date = Now  
    ```  
  
     È possibile assegnare un valore per un `ReadOnly` variabile una sola volta. Una volta eseguita questa operazione, nessun codice può essere modificata il relativo valore.  
  
     Se si conosce il valore in fase di compilazione o non è possibile calcolare in fase di compilazione in un'unica istruzione, è possibile assegnarlo in fase di esecuzione in un costruttore. A tale scopo, è necessario dichiarare il `ReadOnly` variabile a livello di classe o struttura. Nel costruttore per quella classe o struttura, calcolare il valore della variabile fisso e assegnarlo alla variabile prima di restituire dal costruttore.  
  
## <a name="see-also"></a>Vedere anche  
 [WriteOnly](../../../../visual-basic/language-reference/modifiers/writeonly.md)  
 [Istruzione Const](../../../../visual-basic/language-reference/statements/const-statement.md)
