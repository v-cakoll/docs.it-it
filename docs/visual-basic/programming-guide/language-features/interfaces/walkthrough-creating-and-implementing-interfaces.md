---
title: Creazione e implementazione di interfacce (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [Visual Basic], walkthroughs
- interfaces [Visual Basic], testing
- interface implementation [Visual Basic], walkthrough
- interfaces [Visual Basic], creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
ms.openlocfilehash: 62e301e9eb366d14b58088d3e2cda3b567d17f5b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923316"
---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a>Procedura dettagliata: Creazione e implementazione di interfacce (Visual Basic)

Le interfacce descrivono le caratteristiche di proprietà, metodi ed eventi, ma lasciano i dettagli di implementazione fino a strutture o classi.  
  
 In questa procedura dettagliata viene illustrato come dichiarare e implementare un'interfaccia.  
  
> [!NOTE]
> Questa procedura dettagliata non fornisce informazioni su come creare un'interfaccia utente.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-an-interface"></a>Per definire un'interfaccia
  
1. Aprire un nuovo progetto Applicazione Windows in Visual Basic.  
  
2. Per aggiungere un nuovo modulo al progetto, fare clic su **Aggiungi modulo** nel menu **progetto** .  
  
3. Assegnare un nome al `Module1.vb` nuovo modulo e fare clic su **Aggiungi**. Viene visualizzato il codice per il nuovo modulo.  
  
4. Definire un'interfaccia denominata `TestInterface` all' `Module1` interno di `Interface TestInterface` digitando `End Module` tra le `Module` istruzioni e e quindi premendo INVIO. Nell' **editor di codice** viene rientrato il valore `End Interface` della `Interface` parola chiave e viene aggiunta un'istruzione per formare un blocco di codice.  
  
5. Definire una proprietà, un metodo e un evento per l'interfaccia inserendo il codice seguente tra le `Interface` istruzioni `End Interface` e:  
  
     [!code-vb[VbVbalrOOP#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#98)]
  
## <a name="implementation"></a>Implementazione

 È possibile notare che la sintassi utilizzata per dichiarare i membri di interfaccia è diversa dalla sintassi utilizzata per dichiarare i membri della classe. Questa differenza riflette il fatto che le interfacce non possono contenere codice di implementazione.  
  
### <a name="to-implement-the-interface"></a>Per implementare l'interfaccia
  
1. Aggiungere una classe denominata `ImplementationClass` aggiungendo l'istruzione seguente a `Module1`, dopo l' `End Interface` istruzione, ma prima dell' `End Module` istruzione, quindi premendo INVIO:  
  
     [!code-vb[VbVbalrOOP#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#99)]
  
     Se si lavora all'interno dell'Integrated Development Environment, l' **editor di codice** fornisce un' `End Class` istruzione corrispondente quando si preme INVIO.  
  
2. Aggiungere l'istruzione `Implements` seguente a `ImplementationClass`, che denomina l'interfaccia implementata dalla classe:  
  
     [!code-vb[VbVbalrOOP#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#100)]
  
     Se elencato separatamente da altri elementi all'inizio di una classe o di una struttura, `Implements` l'istruzione indica che la classe o la struttura implementa un'interfaccia.  
  
     Se si lavora all'interno dell'Integrated Development Environment, l' **editor di codice** implementa i membri della classe `TestInterface` richiesti da quando si preme INVIO ed è possibile ignorare il passaggio successivo.  
  
3. Se non si lavora all'interno del Integrated Development Environment, è necessario implementare tutti i membri dell'interfaccia `MyInterface`. Aggiungere il codice seguente a `ImplementationClass` per implementare `Event1`, `Method1`e `Prop1`:  
  
     [!code-vb[VbVbalrOOP#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#101)]
  
     L' `Implements` istruzione denomina l'interfaccia e il membro di interfaccia in fase di implementazione.  
  
4. Completare la definizione di `Prop1` aggiungendo un campo privato alla classe in cui è archiviato il valore della proprietà:  
  
     [!code-vb[VbVbalrOOP#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#102)]
  
     Restituisce il valore di `pval` dalla funzione di accesso get della proprietà.  
  
     [!code-vb[VbVbalrOOP#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#103)]
  
     Impostare il valore di `pval` nella funzione di accesso set di proprietà.  
  
     [!code-vb[VbVbalrOOP#104](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#104)]
  
5. Completare la definizione di `Method1` aggiungendo il codice seguente.  
  
     [!code-vb[VbVbalrOOP#105](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#105)]
  
### <a name="to-test-the-implementation-of-the-interface"></a>Per testare l'implementazione dell'interfaccia
  
1. Fare clic con il pulsante destro del mouse sul modulo di avvio del progetto nella **Esplora soluzioni**, quindi scegliere **Visualizza codice**. Nell'editor viene visualizzata la classe per il form di avvio. Per impostazione predefinita, viene chiamato `Form1`il form di avvio.  
  
2. Aggiungere il campo `testInstance` seguente `Form1` alla classe:  
  
     [!code-vb[VbVbalrOOP#120](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#120)]
  
     Dichiarando `testInstance` come `WithEvents`, la `Form1` classe è in grado di gestire gli eventi.  
  
3. Aggiungere il gestore eventi seguente alla `Form1` classe per gestire gli eventi generati da: `testInstance`  
  
     [!code-vb[VbVbalrOOP#106](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#106)]
  
4. Aggiungere una subroutine denominata `Test` `Form1` alla classe per testare la classe di implementazione:  
  
     [!code-vb[VbVbalrOOP#107](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#107)]
  
     La `Test` stored procedure crea un'istanza della classe che implementa `MyInterface`, assegna tale istanza al `testInstance` campo, imposta una proprietà ed esegue un metodo tramite l'interfaccia.  
  
5. Aggiungere il codice per chiamare `Test` la procedura `Form1 Load` dalla procedura del form di avvio:  
  
     [!code-vb[VbVbalrOOP#108](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#108)]
  
6. Eseguire la `Test` procedura premendo F5. Viene visualizzato il messaggio "Prop1 è stato impostato su 9". Dopo aver fatto clic su OK, viene visualizzato il messaggio "il parametro X per Method1 è 5". Fare clic su OK e viene visualizzato il messaggio "il gestore eventi ha rilevato l'evento".  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Implements](../../../../visual-basic/language-reference/statements/implements-statement.md)
- [Interfacce](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)
- [Istruzione Interface](../../../../visual-basic/language-reference/statements/interface-statement.md)
- [Istruzione Event](../../../../visual-basic/language-reference/statements/event-statement.md)
