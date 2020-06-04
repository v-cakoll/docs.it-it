---
title: Strutture decisionali
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- If statement [Visual Basic], decision structures
- If statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], decision structures
- decision structures [Visual Basic]
- conditional statements [Visual Basic], decision structures
ms.assetid: 2e2e0895-4483-442a-b17c-26aead751ec2
ms.openlocfilehash: aac9844240defc5a21a3f4e6090fa8f49e6348a1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403517"
---
# <a name="decision-structures-visual-basic"></a>Strutture decisionali (Visual Basic)
Visual Basic consente di verificare le condizioni ed eseguire diverse operazioni in base ai risultati del test. È possibile verificare se una condizione è true o false, per i diversi valori di un'espressione o per varie eccezioni generate quando si esegue una serie di istruzioni.  
  
 Nella figura seguente viene illustrata una struttura decisionale che verifica la presenza di una condizione true e che esegue azioni diverse a seconda che sia true o false.  
  
 ![Un diagramma di flusso di un if... Quindi... Costruzione else.](./media/decision-structures/if-then-else-construction.gif)  
  
## <a name="ifthenelse-construction"></a>Se... Quindi... Costruzione else  
 `If...Then...Else`le costruzioni consentono di testare una o più condizioni ed eseguire una o più istruzioni a seconda di ogni condizione. È possibile verificare le condizioni e intraprendere azioni nei modi seguenti:  
  
- Eseguire una o più istruzioni se una condizione è`True`  
  
- Eseguire una o più istruzioni se una condizione è`False`  
  
- Eseguire alcune istruzioni se una condizione è `True` e altre se è`False`  
  
- Testare una condizione aggiuntiva se una condizione precedente è`False`  
  
 La struttura di controllo che offre tutte queste possibilità è il [... Quindi... Else (istruzione](../../../language-reference/statements/if-then-else-statement.md)). È possibile utilizzare una versione a riga singola se si dispone solo di un test e di un'istruzione da eseguire. Se si dispone di un set più complesso di condizioni e azioni, è possibile usare la versione a più righe.  
  
## <a name="selectcase-construction"></a>Seleziona... Costruzione case  
 La `Select...Case` costruzione consente di valutare un'espressione una sola volta ed eseguire set di istruzioni diversi in base a valori possibili differenti. Per ulteriori informazioni, vedere [Select... Istruzione case](../../../language-reference/statements/select-case-statement.md).  
  
## <a name="trycatchfinally-construction"></a>Prova... Rileva... Costruzione definitiva  
 `Try...Catch...Finally`le costruzioni consentono di eseguire un set di istruzioni in un ambiente che mantiene il controllo se una qualsiasi delle istruzioni causa un'eccezione. È possibile eseguire azioni diverse per le diverse eccezioni. Facoltativamente, è possibile specificare un blocco di codice che viene eseguito prima di uscire dall'intera `Try...Catch...Finally` costruzione, indipendentemente da ciò che si verifica. Per altre informazioni, vedere [Istruzione Try...Catch...Finally](../../../language-reference/statements/try-catch-finally-statement.md).  
  
> [!NOTE]
> Per molte strutture di controllo, quando si fa clic su una parola chiave, vengono evidenziate tutte le parole chiave nella struttura. Ad esempio, quando si fa clic `If` in una `If...Then...Else` costruzione, vengono evidenziate tutte le istanze di `If` ,,, `Then` `ElseIf` `Else` e `End If` nella costruzione. Per passare alla parola chiave evidenziata successiva o precedente, premere CTRL + MAIUSC + freccia giù o CTRL + MAIUSC + freccia su.  
  
## <a name="see-also"></a>Vedere anche

- [Flusso di controllo](index.md)
- [Strutture di ciclo](loop-structures.md)
- [Altre strutture di controllo](other-control-structures.md)
- [Strutture di controllo annidate](nested-control-structures.md)
- [Operatore If](../../../language-reference/operators/if-operator.md)
