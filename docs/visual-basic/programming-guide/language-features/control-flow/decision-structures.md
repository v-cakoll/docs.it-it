---
title: Strutture decisionali (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- If statement [Visual Basic], decision structures
- If statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], decision structures
- decision structures [Visual Basic]
- conditional statements [Visual Basic], decision structures
ms.assetid: 2e2e0895-4483-442a-b17c-26aead751ec2
ms.openlocfilehash: 1ede40d196b470a351aca4c60b33f074df14b86a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648197"
---
# <a name="decision-structures-visual-basic"></a>Strutture decisionali (Visual Basic)
Visual Basic consente di condizioni di test ed eseguire diverse operazioni dipende dai risultati di tale test. È possibile testare una condizione è true o false per diversi valori di un'espressione o per diverse eccezioni generate quando si esegue una serie di istruzioni.  
  
 Nella figura seguente mostra una struttura decisionale che verifica una condizione è true e azioni diverse a seconda se è true o false.  
  
 ![Diagramma di flusso di un blocco If... Then... Costruzione else](../../../../visual-basic/programming-guide/language-features/control-flow/media/ifthenelse.gif "IfThenElse")  
Operazioni diverse quando una condizione è true e false  
  
## <a name="ifthenelse-construction"></a>Se... Quindi... Costruzione else  
 `If...Then...Else` consentono di verificare la presenza di una o più condizioni ed eseguire una o più istruzioni in base a ogni condizione. È possibile verificare le condizioni e intraprendere azioni nei modi seguenti:  
  
-   Eseguire una o più istruzioni se una condizione `True`  
  
-   Eseguire una o più istruzioni se una condizione `False`  
  
-   Eseguire alcune istruzioni se una condizione è `True` e ad altri se è `False`  
  
-   Verificare una condizione aggiuntiva se una condizione preliminare è `False`  
  
 È la struttura di controllo che offre tutte queste possibilità di [se... Quindi... Istruzione else](../../../../visual-basic/language-reference/statements/if-then-else-statement.md). Se si dispone di un'unica verifica e un'istruzione per l'esecuzione, è possibile utilizzare una versione a riga singola. Se si dispone di un set di condizioni e azioni più complesso, è possibile utilizzare la versione di più righe.  
  
## <a name="selectcase-construction"></a>Seleziona... Costruzione di case  
 Il `Select...Case` costruzione consente di valutare un'espressione una sola volta e di eseguire diversi set di istruzioni in base a diversi valori possibili. Per ulteriori informazioni, vedere [Seleziona... Istruzione case](../../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
## <a name="trycatchfinally-construction"></a>Try... Catch... Infine costruzione  
 `Try...Catch...Finally` consentono di eseguire un set di istruzioni in un ambiente che mantiene il controllo se una qualsiasi delle istruzioni genera un'eccezione. È possibile eseguire diverse azioni per le eccezioni diverse. È possibile specificare facoltativamente un blocco di codice che viene eseguito prima di terminare l'intera `Try...Catch...Finally` costruzione, indipendentemente da ciò che si verifica. Per altre informazioni, vedere [Istruzione Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
> [!NOTE]
>  Per molte strutture di controllo quando si fa clic su una parola chiave, vengono evidenziate tutte le parole chiave nella struttura. Ad esempio, quando fa clic su `If` in un `If...Then...Else` costruzione, tutte le istanze di `If`, `Then`, `ElseIf`, `Else`, e `End If` nella costruzione vengono evidenziati. Per spostarsi alla parola chiave evidenziata successiva o precedente, premere CTRL + MAIUSC + freccia giù o CTRL + MAIUSC + freccia su.  
  
## <a name="see-also"></a>Vedere anche  
 [Flusso di controllo](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [Strutture di ciclo](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [Altre strutture di controllo](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)  
 [Strutture di controllo annidate](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [Operatore If](../../../../visual-basic/language-reference/operators/if-operator.md)
