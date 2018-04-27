---
title: 'Procedura: chiamare un gestore eventi in Visual Basic'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- event handlers [Visual Basic], calling
- event handlers
- procedures [Visual Basic], event handlers
- procedures [Visual Basic], calling
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2b8a35459fdeb7cce0b494a9b3024a79bd4173cc
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a>Procedura: chiamare un gestore eventi in Visual Basic
Un *evento* è un'azione o un'occorrenza, ad esempio un mouse fare clic su un limite di credito è stato superato o: riconosciuto da un componente del programma, e per cui è possibile scrivere codice per rispondere. Un *gestore dell'evento* è il codice scritto in risposta a un evento.  
  
 Un gestore eventi in Visual Basic è un `Sub` stored procedure. Tuttavia, si non viene in genere chiamato lo stesso modo di altri `Sub` procedure. In alternativa, per identificare la procedura come un gestore per l'evento. È possibile eseguire questa operazione con un [gestisce](../../../../visual-basic/language-reference/statements/handles-clause.md) clausola e un [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) variabile, o con un [istruzione AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md). Utilizzando un `Handles` clausola è la modalità predefinita per dichiarare un gestore eventi in Visual Basic. Questo è il modo in cui che i gestori eventi vengono scritti dalle finestre di progettazione quando si programma nell'ambiente di sviluppo integrato (IDE). Il `AddHandler` istruzione è adatta per la generazione di eventi in modo dinamico in fase di esecuzione.  
  
 Quando si verifica l'evento, Visual Basic chiama automaticamente le routine del gestore eventi. Qualsiasi codice che ha accesso all'evento può causare la generazione mediante l'esecuzione di un [istruzione RaiseEvent](../../../../visual-basic/language-reference/statements/raiseevent-statement.md).  
  
 È possibile associare più gestori di eventi con lo stesso evento. In alcuni casi è possibile annullare l'associazione di un gestore a un evento. Per altre informazioni, vedere [Eventi](../../../../visual-basic/programming-guide/language-features/events/index.md).  
  
### <a name="to-call-an-event-handler-using-handles-and-withevents"></a>Per chiamare un gestore eventi mediante Handles e WithEvents  
  
1.  Verificare che l'evento è dichiarato con un [istruzione Event](../../../../visual-basic/language-reference/statements/event-statement.md).  
  
2.  Dichiarare una variabile oggetto livello di modulo o classe utilizzando il [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) (parola chiave). Il `As` clausola per questa variabile deve specificare la classe che genera l'evento.  
  
3.  Nella dichiarazione della gestione dell'evento `Sub` procedura, aggiungere un [gestisce](../../../../visual-basic/language-reference/statements/handles-clause.md) clausola che specifica il `WithEvents` variabile e il nome dell'evento.  
  
4.  Quando si verifica l'evento, Visual Basic chiama automaticamente il `Sub` stored procedure. Il codice può usare un `RaiseEvent` istruzione per generare l'evento.  
  
     L'esempio seguente definisce un evento e un `WithEvents` variabile che fa riferimento alla classe che genera l'evento. La gestione dell'evento `Sub` procedura vengono utilizzati un `Handles` clausola per specificare la classe di evento che gestisce.  
  
     [!code-vb[VbVbcnProcedures#4](./codesnippet/VisualBasic/how-to-call-an-event-handler_1.vb)]  
  
### <a name="to-call-an-event-handler-using-addhandler"></a>Per chiamare un gestore eventi mediante AddHandler  
  
1.  Verificare che l'evento è dichiarato con un `Event` istruzione.  
  
2.  Eseguire un [istruzione AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md) per connettersi in modo dinamico la gestione dell'evento `Sub` procedure con l'evento.  
  
3.  Quando si verifica l'evento, Visual Basic chiama automaticamente il `Sub` stored procedure. Il codice può usare un `RaiseEvent` istruzione per generare l'evento.  
  
     L'esempio seguente definisce un `Sub` procedure per gestire il <xref:System.Windows.Forms.Form.Closing> evento di un form. Viene quindi utilizzato il [istruzione AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md) per associare il `catchClose` routine come gestore eventi per <xref:System.Windows.Forms.Form.Closing>.  
  
     [!code-vb[VbVbcnProcedures#5](./codesnippet/VisualBasic/how-to-call-an-event-handler_2.vb)]  
  
     È possibile annullare l'associazione di un gestore eventi da un evento tramite l'esecuzione di [istruzione RemoveHandler](../../../../visual-basic/language-reference/statements/removehandler-statement.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Routine](./index.md)  
 [Routine Sub](./sub-procedures.md)  
 [Istruzione Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Operatore AddressOf](../../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Procedura: Creare una routine](./how-to-create-a-procedure.md)  
 [Procedura: Chiamare una routine che non restituisce un valore](./how-to-call-a-procedure-that-does-not-return-a-value.md)
