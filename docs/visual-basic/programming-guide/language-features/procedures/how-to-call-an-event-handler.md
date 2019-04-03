---
title: 'Procedura: Chiamare un gestore eventi in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- event handlers [Visual Basic], calling
- event handlers
- procedures [Visual Basic], event handlers
- procedures [Visual Basic], calling
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
ms.openlocfilehash: dd21f80e4b3892cbd9db901b619ecff98f6b70bd
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58837767"
---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a>Procedura: Chiamare un gestore eventi in Visual Basic
Un' *evento* è un'azione o una occorrenza, ovvero, ad esempio un mouse superato un limite di credito o fare clic su, che viene riconosciuto da alcuni componenti del programma e per cui è possibile scrivere codice per rispondere. Un' *gestore dell'evento* è riportato il codice scritto in risposta a un evento.  
  
 Un gestore eventi in Visual Basic è un `Sub` procedure. Tuttavia, si non viene normalmente chiamato lo stesso modo di altri `Sub` procedure. Al contrario, la procedura per identificare come un gestore per l'evento. È possibile eseguire questa operazione con un [gestisce](../../../../visual-basic/language-reference/statements/handles-clause.md) clausola e una [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) variabile, o con un [istruzione AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md). Usando un `Handles` clausola è la modalità predefinita per dichiarare un gestore eventi in Visual Basic. Questo è il modo in cui che i gestori eventi vengono scritti dalle finestre di progettazione durante la programmazione nell'ambiente di sviluppo integrato (IDE). Il `AddHandler` istruzione è adatta per la generazione di eventi in modo dinamico in fase di esecuzione.  
  
 Quando si verifica l'evento, Visual Basic chiama automaticamente la routine del gestore eventi. Qualsiasi codice che dispone dell'accesso per l'evento può causare la generazione tramite l'esecuzione di un [istruzione RaiseEvent](../../../../visual-basic/language-reference/statements/raiseevent-statement.md).  
  
 È possibile associare più di un gestore eventi con lo stesso evento. In alcuni casi è possibile annullare l'associazione di un gestore da un evento. Per altre informazioni, vedere [Eventi](../../../../visual-basic/programming-guide/language-features/events/index.md).  
  
### <a name="to-call-an-event-handler-using-handles-and-withevents"></a>Per chiamare un gestore eventi utilizzano handle e WithEvents  
  
1.  Assicurarsi che l'evento viene dichiarato con un [istruzione Event](../../../../visual-basic/language-reference/statements/event-statement.md).  
  
2.  Dichiarare una variabile oggetto alla classe o modulo utilizzando la [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) (parola chiave). Il `As` clausola per questa variabile deve specificare la classe che genera l'evento.  
  
3.  Nella dichiarazione di gestione di eventi `Sub` routine, aggiungere un' [gestisce](../../../../visual-basic/language-reference/statements/handles-clause.md) clausola che specifica il `WithEvents` variabile e il nome dell'evento.  
  
4.  Quando si verifica l'evento, Visual Basic chiama automaticamente il `Sub` procedure. Il codice può usare un `RaiseEvent` istruzione per generare l'evento.  
  
     L'esempio seguente definisce un evento e un `WithEvents` variabile che fa riferimento alla classe che genera l'evento. La gestione degli eventi `Sub` procedure Usa una `Handles` clausola per specificare la classe che gestisce l'evento.  
  
     [!code-vb[VbVbcnProcedures#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#4)]  
  
### <a name="to-call-an-event-handler-using-addhandler"></a>Per chiamare un gestore evento mediante AddHandler  
  
1.  Assicurarsi che l'evento viene dichiarato con un `Event` istruzione.  
  
2.  Eseguire un' [istruzione AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md) per connettersi in modo dinamico la gestione degli eventi `Sub` procedure con l'evento.  
  
3.  Quando si verifica l'evento, Visual Basic chiama automaticamente il `Sub` procedure. Il codice può usare un `RaiseEvent` istruzione per generare l'evento.  
  
     L'esempio seguente definisce una `Sub` procedure per gestire il <xref:System.Windows.Forms.Form.Closing> eventi di un form. Quindi, utilizza il [istruzione AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md) per associare il `catchClose` routine come gestore eventi per <xref:System.Windows.Forms.Form.Closing>.  
  
     [!code-vb[VbVbcnProcedures#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#5)]  
  
     È possibile annullare l'associazione di un gestore eventi da un evento tramite l'esecuzione di [istruzione RemoveHandler](../../../../visual-basic/language-reference/statements/removehandler-statement.md).  
  
## <a name="see-also"></a>Vedere anche

- [Routine](./index.md)
- [Routine Sub](./sub-procedures.md)
- [Istruzione Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [Operatore AddressOf](../../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Procedura: Creare una stored Procedure](./how-to-create-a-procedure.md)
- [Procedura: Chiamare una routine che non restituisce un valore](./how-to-call-a-procedure-that-does-not-return-a-value.md)
