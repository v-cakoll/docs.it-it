---
title: Spazio dello stack insufficiente
ms.date: 07/20/2015
f1_keywords:
- vbrID28
ms.assetid: bfcd792b-ac29-4158-81fc-ea0c13f4ffa2
ms.openlocfilehash: 9ae604a9727413f2705d42a4b68f5a50b7dd3feb
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349189"
---
# <a name="out-of-stack-space-visual-basic"></a>Spazio dello stack insufficiente (Visual Basic)
Lo stack è un'area di lavoro di memoria che aumenta e compatta dinamicamente con le esigenze del programma in esecuzione. Sono stati superati i limiti.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Verificare che le procedure non siano annidate troppo profondamente.  
  
2. Verificare che le procedure ricorsive vengano terminate correttamente.  
  
3. Se le variabili locali richiedono più spazio variabile locale rispetto a quanto disponibile, provare a dichiarare alcune variabili a livello di modulo. È anche possibile dichiarare tutte le variabili nella procedura statica precedendo la parola chiave `Property`, `Sub`o `Function` con `Static`. In alternativa, è possibile usare l'istruzione `Static` per dichiarare singole variabili statiche all'interno delle procedure.  
  
4. Ridefinire alcune stringhe a lunghezza fissa come stringhe a lunghezza variabile, poiché le stringhe a lunghezza fissa utilizzano più spazio dello stack rispetto alle stringhe a lunghezza variabile. È anche possibile definire la stringa a livello di modulo, in cui non è necessario spazio dello stack.  
  
5. Controllare il numero di chiamate di funzione annidate `DoEvents` usando la finestra di dialogo `Calls` per visualizzare le procedure attive nello stack.  
  
6. Assicurarsi che non sia stato causato un evento "Cascade" tramite l'attivazione di un evento che chiama una routine di evento già presente nello stack. Un evento Cascade è simile a una chiamata di routine ricorsiva senza terminazione, ma è meno ovvio, perché la chiamata viene eseguita da Visual Basic anziché da una chiamata esplicita nel codice. Utilizzare la finestra di dialogo `Calls` per visualizzare le procedure attive nello stack.  
  
## <a name="see-also"></a>Vedere anche

- [Finestra Memoria](/visualstudio/debugger/memory-windows)
