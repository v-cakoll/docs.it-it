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
ms.openlocfilehash: 4a76b2565c343e69ac3c11441035a7682a8f08ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61907004"
---
# <a name="decision-structures-visual-basic"></a>Strutture decisionali (Visual Basic)
Visual Basic consente di testare condizioni ed eseguire operazioni diverse a seconda del risultato di un test. È possibile testare una condizione sia true o false, per diversi valori di un'espressione o di diverse eccezioni generate quando si esegue una serie di istruzioni.  
  
 La figura seguente illustra una struttura decisionale che verifica la presenza di una condizione sia true ed esegue azioni diverse a seconda che sia true o false.  
  
 ![Un diagramma di flusso di un blocco If... Quindi... Costruzione else.](./media/decision-structures/if-then-else-construction.gif)  
  
## <a name="ifthenelse-construction"></a>If... Quindi... Costruzione else  
 `If...Then...Else` consentono di verificare che una o più condizioni ed eseguire una o più istruzioni in base a ogni condizione. È possibile testare condizioni e intraprendere azioni nei modi seguenti:  
  
-   Eseguire una o più istruzioni se una condizione `True`  
  
-   Eseguire una o più istruzioni se una condizione `False`  
  
-   Eseguire alcune istruzioni se una condizione è `True` e ad altri utenti se si tratta di `False`  
  
-   Verificare una condizione aggiuntiva se la prima condizione è `False`  
  
 La struttura di controllo che offre tutte queste possibilità di [se... Quindi... Istruzione else](../../../../visual-basic/language-reference/statements/if-then-else-statement.md). Se si ha solo un test e una sola istruzione per l'esecuzione, è possibile utilizzare una versione a riga singola. Se si dispone di un set più complesso di condizioni e azioni, è possibile usare la versione più righe.  
  
## <a name="selectcase-construction"></a>Seleziona... Costruzione di case  
 Il `Select...Case` costruzione consente di valutare un'espressione una sola volta ed eseguire set diversi di istruzioni basate su diversi valori possibili. Per altre informazioni, vedere [Seleziona... Istruzione case](../../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
## <a name="trycatchfinally-construction"></a>Try... Catch... Infine costruzione  
 `Try...Catch...Finally` consentono di eseguire un set di istruzioni in un ambiente che manterrà il controllo se una delle istruzioni genera un'eccezione. È possibile eseguire azioni diverse per le eccezioni diverse. È possibile specificare facoltativamente un blocco di codice che viene eseguito prima di terminare l'intera `Try...Catch...Finally` costruzione, indipendentemente da ciò che si verifica. Per altre informazioni, vedere [Istruzione Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
> [!NOTE]
>  Per molte strutture di controllo, quando si fa clic su una parola chiave, sono evidenziate tutte le parole chiave nella struttura. Ad esempio, quando fa clic su `If` in un `If...Then...Else` costruzione, tutte le istanze di `If`, `Then`, `ElseIf`, `Else`, e `End If` nella costruzione di strutture vengono evidenziati. Per spostare alla parola chiave evidenziata successiva o precedente, premere CTRL + MAIUSC + freccia giù o CTRL + MAIUSC + freccia su.  
  
## <a name="see-also"></a>Vedere anche

- [Flusso di controllo](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [Strutture di ciclo](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Altre strutture di controllo](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [Strutture di controllo annidate](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Operatore If](../../../../visual-basic/language-reference/operators/if-operator.md)
