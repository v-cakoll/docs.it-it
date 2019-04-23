---
title: Spazio dello stack insufficiente (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID28
ms.assetid: bfcd792b-ac29-4158-81fc-ea0c13f4ffa2
ms.openlocfilehash: 29dbdf74808fc98bb856483c3fd8e3a09a72113b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59318793"
---
# <a name="out-of-stack-space-visual-basic"></a>Spazio dello stack insufficiente (Visual Basic)
Lo stack è un'area di lavoro di memoria aumenta e si ridotta dinamicamente con le esigenze del programma in esecuzione. Sono stati superati i limiti massimi.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Verificare che le procedure non elaborati annidate troppo profondamente.  
  
2. Assicurarsi che le routine ricorsive terminino correttamente.  
  
3. Se le variabili locali richiedono uno spazio più a quello disponibile, provare a dichiarare alcune variabili a livello di modulo. È anche possibile dichiarare come statici tutte le variabili nella procedura facendo precedere il `Property`, `Sub`, o `Function` parola chiave with `Static`. In alternativa è possibile usare il `Static` dichiarare singole variabili statiche all'interno delle routine dell'istruzione.  
  
4. Ridefinire alcune delle stringhe a lunghezza fissa sotto forma di stringhe a lunghezza variabile, come stringhe a lunghezza fissa utilizzino più spazio di stack più stringhe a lunghezza variabile. È anche possibile definire la stringa a livello di modulo in cui è non necessario alcun spazio dello stack.  
  
5. Controllare il numero di annidato `DoEvents` chiamate a funzioni, usando il `Calls` finestra di dialogo per visualizzare quali procedure attive nello stack.  
  
6. Assicurarsi che non si ha provocato una "catena di eventi" generando un evento che chiama una routine evento già nello stack. Una catena di eventi è simile a una chiamata di routine ricorsive senza terminazione, ma è meno ovvio, poiché viene effettuata la chiamata da Visual Basic piuttosto che una chiamata esplicita nel codice. Usare il `Calls` finestra di dialogo per visualizzare quali procedure attive nello stack.  
  
## <a name="see-also"></a>Vedere anche

- [Finestra Memoria](/visualstudio/debugger/memory-windows)
