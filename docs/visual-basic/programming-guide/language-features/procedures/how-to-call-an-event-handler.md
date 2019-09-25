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
ms.openlocfilehash: a9e090e83b180686ccb832aa6efb314c7e0fcc9a
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216623"
---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a>Procedura: Chiamare un gestore eventi in Visual Basic

Un *evento* è un'azione o un'occorrenza, ad esempio un clic del mouse o un limite di credito superato, riconosciuto da un componente del programma e per il quale è possibile scrivere codice per rispondere. Un *gestore eventi* è il codice scritto per rispondere a un evento.

 Un gestore eventi nel Visual Basic è una `Sub` routine. Tuttavia, in genere non viene chiamato come le altre `Sub` procedure. È invece possibile identificare la routine come gestore per l'evento. Questa operazione può essere eseguita con una clausola [Handles](../../../language-reference/statements/handles-clause.md) e una variabile [WithEvents](../../../language-reference/modifiers/withevents.md) oppure con un' [istruzione AddHandler](../../../language-reference/statements/addhandler-statement.md). L'uso `Handles` di una clausola è la modalità predefinita per dichiarare un gestore eventi in Visual Basic. Questo è il modo in cui i gestori eventi vengono scritti dalle finestre di progettazione quando si programma nel Integrated Development Environment (IDE). L' `AddHandler` istruzione è adatta per la generazione dinamica di eventi in fase di esecuzione.

 Quando si verifica l'evento, Visual Basic chiama automaticamente la routine del gestore eventi. Il codice che ha accesso all'evento può causare l'esecuzione di un' [istruzione RaiseEvent](../../../language-reference/statements/raiseevent-statement.md).

 È possibile associare più di un gestore eventi allo stesso evento. In alcuni casi è possibile annullare l'associazione di un gestore a un evento. Per altre informazioni, vedere [Eventi](../events/index.md).

### <a name="to-call-an-event-handler-using-handles-and-withevents"></a>Per chiamare un gestore eventi utilizzando Handles e WithEvents

1. Verificare che l'evento sia dichiarato con un' [istruzione Event](../../../language-reference/statements/event-statement.md).

2. Dichiarare una variabile oggetto a livello di modulo o di classe usando la parola chiave [WithEvents](../../../language-reference/modifiers/withevents.md) . La `As` clausola per questa variabile deve specificare la classe che genera l'evento.

3. Nella dichiarazione della procedura di gestione `Sub` degli eventi, aggiungere una clausola [Handles](../../../language-reference/statements/handles-clause.md) che specifichi la `WithEvents` variabile e il nome dell'evento.

4. Quando si verifica l'evento, Visual Basic chiama automaticamente `Sub` la stored procedure. Il codice può usare un' `RaiseEvent` istruzione per fare in modo che si verifichi l'evento.

     Nell'esempio seguente vengono definiti un evento e `WithEvents` una variabile che fa riferimento alla classe che genera l'evento. La procedura di gestione `Sub` degli eventi USA `Handles` una clausola per specificare la classe e l'evento gestito.

     [!code-vb[VbVbcnProcedures#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#4)]

### <a name="to-call-an-event-handler-using-addhandler"></a>Per chiamare un gestore eventi tramite AddHandler

1. Verificare che l'evento sia dichiarato con un' `Event` istruzione.

2. Eseguire un' [istruzione AddHandler](../../../language-reference/statements/addhandler-statement.md) per connettere dinamicamente la routine di gestione `Sub` degli eventi con l'evento.

3. Quando si verifica l'evento, Visual Basic chiama automaticamente `Sub` la stored procedure. Il codice può usare un' `RaiseEvent` istruzione per fare in modo che si verifichi l'evento.

     Nell'esempio seguente viene definita `Sub` una procedura per gestire <xref:System.Windows.Forms.Form.Closing> l'evento di un form. Viene quindi utilizzata l' [istruzione AddHandler](../../../language-reference/statements/addhandler-statement.md) per associare la `catchClose` routine come gestore eventi per. <xref:System.Windows.Forms.Form.Closing>

     [!code-vb[VbVbcnProcedures#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#5)]

     È possibile annullare l'associazione di un gestore eventi da un evento eseguendo l' [istruzione RemoveHandler](../../../language-reference/statements/removehandler-statement.md).

## <a name="see-also"></a>Vedere anche

- [Routine](index.md)
- [Routine Sub](sub-procedures.md)
- [Istruzione Sub](../../../language-reference/statements/sub-statement.md)
- [Operatore AddressOf](../../../language-reference/operators/addressof-operator.md)
- [Procedura: Creare una procedura](how-to-create-a-procedure.md)
- [Procedura: Chiamare una routine che non restituisce un valore](how-to-call-a-procedure-that-does-not-return-a-value.md)
