---
title: 'Procedura: chiamare una routine che non restituisce un valore (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
ms.openlocfilehash: cf136f1486645d6e8e4b5856c0b1baf9e99f6c50
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649048"
---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a>Procedura: chiamare una routine che non restituisce un valore (Visual Basic)
Oggetto `Sub` routine non ha restituito un valore al codice chiamante. Si chiama in modo esplicito con un'istruzione di chiamata autonoma. È possibile effettuare la chiamata utilizzando semplicemente il nome all'interno di un'espressione.  
  
### <a name="to-call-a-sub-procedure"></a>Per chiamare una routine Sub  
  
1.  Nome del file di `Sub` procedura.  
  
2.  Aggiungere il nome tra parentesi per racchiudere l'elenco di argomenti. Se non sono presenti argomenti, è possibile omettere le parentesi. Tuttavia, l'utilizzo delle parentesi, il codice più facile da leggere.  
  
3.  Posizionare gli argomenti nell'elenco di argomenti all'interno delle parentesi, separate da virgole. Assicurarsi fornire gli argomenti nello stesso ordine in cui il `Sub` procedure definisce i parametri corrispondenti.  
  
     Nell'esempio seguente chiama Visual Basic <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> funzione per attivare una finestra dell'applicazione. <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> accetta il titolo della finestra come unico argomento. Non restituire un valore al codice chiamante. Se non è in esecuzione un processo Blocco note, viene generata una <xref:System.ArgumentException>. Il `Shell` procedura presuppone che le applicazioni siano nei percorsi specificati.  
  
     [!code-vb[VbVbalrCatRef#11](./codesnippet/VisualBasic/how-to-call-a-procedure-that-does-not-return-a-value_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.Interaction.Shell%2A>  
 <xref:System.ArgumentException>  
 [Routine](./index.md)  
 [Routine Sub](./sub-procedures.md)  
 [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)  
 [Istruzione Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Procedura: Creare una routine](./how-to-create-a-procedure.md)  
 [Procedura: Chiamare una routine che restituisce un valore](./how-to-call-a-procedure-that-returns-a-value.md)  
 [Procedura: chiamare un gestore eventi in Visual Basic](./how-to-call-an-event-handler.md)
