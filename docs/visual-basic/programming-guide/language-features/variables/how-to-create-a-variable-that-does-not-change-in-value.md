---
title: 'Procedura: creare una variabile che non cambia di valore (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], read-only
- variables [Visual Basic], constant value
ms.assetid: 86b59266-25df-4635-ae15-9b59c411d036
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d1475553e64fef92ec3f3bb7e1b4fbfb357dbec8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
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
