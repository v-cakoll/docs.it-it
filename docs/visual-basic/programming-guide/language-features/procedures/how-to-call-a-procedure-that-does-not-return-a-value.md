---
title: 'Procedura: chiamare una routine che non restituisce un valore'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
ms.openlocfilehash: 514d6e576b9b782387840ae04dcefa00de876aa9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388738"
---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a>Procedura: chiamare una routine che non restituisce un valore (Visual Basic)
Una `Sub` routine non restituisce un valore al codice chiamante. Viene chiamato in modo esplicito con un'istruzione di chiamata autonoma. Non è possibile chiamarlo utilizzando semplicemente il nome all'interno di un'espressione.  
  
### <a name="to-call-a-sub-procedure"></a>Per chiamare una procedura secondaria  
  
1. Specificare il nome della `Sub` procedura.  
  
2. Seguire il nome della procedura con le parentesi per racchiudere l'elenco di argomenti. Se non è presente alcun argomento, è possibile omettere facoltativamente le parentesi. Tuttavia, l'utilizzo delle parentesi rende il codice più semplice da leggere.  
  
3. Inserire gli argomenti nell'elenco di argomenti tra parentesi, separate da virgole. Assicurarsi di specificare gli argomenti nello stesso ordine in cui la `Sub` procedura definisce i parametri corrispondenti.  
  
     Nell'esempio seguente viene chiamata la <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> funzione Visual Basic per attivare una finestra dell'applicazione. <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>accetta il titolo della finestra come unico argomento. Non restituisce un valore al codice chiamante. Se un processo del blocco note non è in esecuzione, nell'esempio viene generata un'eccezione <xref:System.ArgumentException> . Nella `Shell` procedura si presuppone che le applicazioni si trovino nei percorsi specificati.  
  
     [!code-vb[VbVbalrCatRef#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCatRef/VB/Class1.vb#11)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:System.ArgumentException>
- [Procedure](./index.md)
- [Routine Sub](./sub-procedures.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Istruzione Sub](../../../language-reference/statements/sub-statement.md)
- [Procedura: Creare una routine](./how-to-create-a-procedure.md)
- [Procedura: chiamare una routine che restituisce un valore](./how-to-call-a-procedure-that-returns-a-value.md)
- [Procedura: chiamare un gestore eventi in Visual Basic](./how-to-call-an-event-handler.md)
