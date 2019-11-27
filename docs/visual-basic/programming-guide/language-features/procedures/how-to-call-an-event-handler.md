---
title: 'Procedura: chiamare un gestore eventi'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- event handlers [Visual Basic], calling
- event handlers
- procedures [Visual Basic], event handlers
- procedures [Visual Basic], calling
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
ms.openlocfilehash: 0c626a9ad92fe2cd0ea117a9abdd2965a09df2ea
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74340420"
---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a>Procedura: chiamare un gestore eventi in Visual Basic

Un *evento* è un'azione o un'occorrenza, ad esempio un clic del mouse o un limite di credito superato, riconosciuto da un componente del programma e per il quale è possibile scrivere codice per rispondere. Un *gestore eventi* è il codice scritto per rispondere a un evento.

 Un gestore eventi nel Visual Basic è una procedura `Sub`. Tuttavia, in genere non viene chiamato in modo analogo alle altre `Sub` procedure. È invece possibile identificare la routine come gestore per l'evento. Questa operazione può essere eseguita con una clausola [Handles](../../../language-reference/statements/handles-clause.md) e una variabile [WithEvents](../../../language-reference/modifiers/withevents.md) oppure con un' [istruzione AddHandler](../../../language-reference/statements/addhandler-statement.md). L'uso di una clausola `Handles` è la modalità predefinita per dichiarare un gestore eventi in Visual Basic. Questo è il modo in cui i gestori eventi vengono scritti dalle finestre di progettazione quando si programma nel Integrated Development Environment (IDE). L'istruzione `AddHandler` è adatta per la generazione dinamica di eventi in fase di esecuzione.

 Quando si verifica l'evento, Visual Basic chiama automaticamente la routine del gestore eventi. Il codice che ha accesso all'evento può causare l'esecuzione di un' [istruzione RaiseEvent](../../../language-reference/statements/raiseevent-statement.md).

 È possibile associare più di un gestore eventi allo stesso evento. In alcuni casi è possibile annullare l'associazione di un gestore a un evento. Per ulteriori informazioni, vedi [Eventi](../events/index.md).

### <a name="to-call-an-event-handler-using-handles-and-withevents"></a>Per chiamare un gestore eventi utilizzando Handles e WithEvents

1. Verificare che l'evento sia dichiarato con un' [istruzione Event](../../../language-reference/statements/event-statement.md).

2. Dichiarare una variabile oggetto a livello di modulo o di classe usando la parola chiave [WithEvents](../../../language-reference/modifiers/withevents.md) . La clausola `As` per questa variabile deve specificare la classe che genera l'evento.

3. Nella dichiarazione della procedura `Sub` di gestione degli eventi, aggiungere una clausola [Handles](../../../language-reference/statements/handles-clause.md) che specifichi la variabile `WithEvents` e il nome dell'evento.

4. Quando si verifica l'evento, Visual Basic chiama automaticamente la routine `Sub`. Il codice può usare un'istruzione `RaiseEvent` per fare in modo che si verifichi l'evento.

     Nell'esempio seguente vengono definiti un evento e una variabile `WithEvents` che fa riferimento alla classe che genera l'evento. La procedura di `Sub` per la gestione degli eventi usa una clausola `Handles` per specificare la classe e l'evento gestito.

     [!code-vb[VbVbcnProcedures#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#4)]

### <a name="to-call-an-event-handler-using-addhandler"></a>Per chiamare un gestore eventi tramite AddHandler

1. Verificare che l'evento sia dichiarato con un'istruzione `Event`.

2. Eseguire un' [istruzione AddHandler](../../../language-reference/statements/addhandler-statement.md) per connettere dinamicamente la routine di `Sub` di gestione degli eventi con l'evento.

3. Quando si verifica l'evento, Visual Basic chiama automaticamente la routine `Sub`. Il codice può usare un'istruzione `RaiseEvent` per fare in modo che si verifichi l'evento.

     Nell'esempio seguente viene definita una procedura `Sub` per gestire l'evento <xref:System.Windows.Forms.Form.Closing> di un form. Viene quindi utilizzata l' [istruzione AddHandler](../../../language-reference/statements/addhandler-statement.md) per associare la routine `catchClose` come gestore eventi per <xref:System.Windows.Forms.Form.Closing>.

     [!code-vb[VbVbcnProcedures#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#5)]

     È possibile annullare l'associazione di un gestore eventi da un evento eseguendo l' [istruzione RemoveHandler](../../../language-reference/statements/removehandler-statement.md).

## <a name="see-also"></a>Vedere anche

- [Routine](index.md)
- [Routine Sub](sub-procedures.md)
- [Istruzione Sub](../../../language-reference/statements/sub-statement.md)
- [Operatore AddressOf](../../../language-reference/operators/addressof-operator.md)
- [Procedura: Creare una routine](how-to-create-a-procedure.md)
- [Procedura: Chiamare una routine che non restituisce un valore](how-to-call-a-procedure-that-does-not-return-a-value.md)
