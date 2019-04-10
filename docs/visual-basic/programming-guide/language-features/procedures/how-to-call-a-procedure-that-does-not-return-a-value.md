---
title: 'Procedura: Chiamare una routine che non restituisce un valore (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
ms.openlocfilehash: 6e3ce2a184ca5411a6a016929a16bf3d67e669ca
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59335472"
---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a>Procedura: Chiamare una routine che non restituisce un valore (Visual Basic)
Oggetto `Sub` procedure non restituisce un valore al codice chiamante. Viene chiamato in modo esplicito con un'istruzione di chiamata autonoma. È possibile effettuare la chiamata utilizzando semplicemente il nome all'interno di un'espressione.  
  
### <a name="to-call-a-sub-procedure"></a>Per chiamare una routine Sub  
  
1. Specificare il nome del `Sub` procedure.  
  
2. Seguire il nome della routine tra parentesi per racchiudere l'elenco di argomenti. Se non sono presenti argomenti, è possibile omettere le parentesi. Tuttavia, usando le parentesi che rende il codice più facile da leggere.  
  
3. Posizionare gli argomenti nell'elenco di argomenti all'interno delle parentesi, separate da virgole. Assicurarsi di inserire gli argomenti nello stesso ordine in cui il `Sub` procedure definisce i parametri corrispondenti.  
  
     L'esempio seguente chiama il Visual Basic <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> funzione per attivare una finestra dell'applicazione. <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> accetta il titolo della finestra come unico argomento. Non viene restituito un valore al codice chiamante. Se un processo Notepad non è in esecuzione, l'esempio genera un <xref:System.ArgumentException>. Il `Shell` procedura presuppone che le applicazioni siano nei percorsi specificati.  
  
     [!code-vb[VbVbalrCatRef#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCatRef/VB/Class1.vb#11)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:System.ArgumentException>
- [Procedure](./index.md)
- [Routine Sub](./sub-procedures.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Istruzione Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [Procedura: Creare una routine](./how-to-create-a-procedure.md)
- [Procedura: Creare una routine che restituisce un valore](./how-to-call-a-procedure-that-returns-a-value.md)
- [Procedura: Chiamare un gestore eventi in Visual Basic](./how-to-call-an-event-handler.md)
