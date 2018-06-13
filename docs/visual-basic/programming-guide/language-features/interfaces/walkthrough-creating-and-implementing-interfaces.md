---
title: Creazione e implementazione di interfacce (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [Visual Basic], walkthroughs
- interfaces [Visual Basic], testing
- interface implementation [Visual Basic], walkthrough
- interfaces [Visual Basic], creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
ms.openlocfilehash: af9305deb60637b642d091501e743f2c7a57ccad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33653611"
---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a>Procedura dettagliata: creazione e implementazione di interfacce (Visual Basic)

Interfacce descrivono le caratteristiche di proprietà, metodi ed eventi, ma i dettagli relativi all'implementazione fino a strutture o classi.  
  
 Questa procedura dettagliata viene illustrato come dichiarare e implementare un'interfaccia.  
  
> [!NOTE]
>  Questa procedura dettagliata non fornisce informazioni su come creare un'interfaccia utente.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-an-interface"></a>Per definire un'interfaccia
  
1.  Aprire un nuovo progetto Applicazione Windows in Visual Basic.  
  
2.  Aggiungere un nuovo modulo al progetto, fare clic su **Aggiungi modulo** sul **progetto** menu.  
  
3.  Nome del nuovo modulo `Module1.vb` e fare clic su **Aggiungi**. Viene visualizzato il codice per il nuovo modulo.  
  
4.  Definire un'interfaccia denominata `TestInterface` all'interno di `Module1` digitando `Interface TestInterface` tra il `Module` e `End Module` istruzioni e quindi premere INVIO. Il **Editor di codice** rientri di `Interface` (parola chiave) e aggiunge un `End Interface` istruzione in modo da formare un blocco di codice.  
  
5.  Definire un proprietà, metodi ed eventi per l'interfaccia inserendo il codice seguente tra i `Interface` e `End Interface` istruzioni:  
  
     [!code-vb[VbVbalrOOP#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#98)]
  
## <a name="implementation"></a>Implementazione

 È possibile notare che la sintassi utilizzata per dichiarare i membri di interfaccia è diversa da quella utilizzata per dichiarare i membri di classe. Questa differenza è dovuto al fatto che le interfacce non possono contenere codice di implementazione.  
  
### <a name="to-implement-the-interface"></a>Per implementare l'interfaccia
  
1.  Aggiungere una classe denominata `ImplementationClass` aggiungendo l'istruzione seguente alle `Module1`, dopo il `End Interface` istruzione ma prima che il `End Module` istruzione e quindi premere INVIO:  
  
     [!code-vb[VbVbalrOOP#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#99)]
  
     Se si lavora all'interno dell'ambiente di sviluppo integrato, il **Editor di codice** fornisce un corrispondente `End Class` istruzione quando si preme INVIO.  
  
2.  Aggiungere il seguente `Implements` istruzione `ImplementationClass`, quali nome dell'interfaccia implementata dalla classe:  
  
     [!code-vb[VbVbalrOOP#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#100)]
  
     Quando elencata separatamente da altri elementi nella parte superiore di una classe o struttura, il `Implements` istruzione indica che la classe o struttura implementa un'interfaccia.  
  
     Se si lavora all'interno dell'ambiente di sviluppo integrato, il **Editor di codice** implementa i membri di classe richiesti da `TestInterface` quando si preme INVIO, ed è possibile ignorare il passaggio successivo.  
  
3.  Se non si lavora all'interno dell'ambiente di sviluppo integrato, è necessario implementare tutti i membri dell'interfaccia `MyInterface`. Aggiungere il seguente codice al `ImplementationClass` implementare `Event1`, `Method1`, e `Prop1`:  
  
     [!code-vb[VbVbalrOOP#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#101)]
  
     Il `Implements` istruzione assegna un nome di interfaccia e un membro di interfaccia implementato.  
  
4.  Completare la definizione di `Prop1` aggiungendo un campo privato per la classe che è archiviato il valore della proprietà:  
  
     [!code-vb[VbVbalrOOP#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#102)]
  
     Restituisce il valore di `pval` dalla proprietà get.  
  
     [!code-vb[VbVbalrOOP#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#103)]
  
     Impostare il valore di `pval` nel set di proprietà della funzione di accesso.  
  
     [!code-vb[VbVbalrOOP#104](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#104)]
  
5.  Completare la definizione di `Method1` aggiungendo il codice seguente.  
  
     [!code-vb[VbVbalrOOP#105](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#105)]
  
### <a name="to-test-the-implementation-of-the-interface"></a>Per testare l'implementazione dell'interfaccia
  
1.  Fare doppio clic su form di avvio per il progetto nel **Esplora**, fare clic su **Visualizza codice**. L'editor visualizza la classe del form di avvio. Per impostazione predefinita, viene chiamato il form di avvio `Form1`.  
  
2.  Aggiungere il seguente `testInstance` campo la `Form1` classe:  
  
     [!code-vb[VbVbalrOOP#120](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#120)]
  
     Dichiarando `testInstance` come `WithEvents`, `Form1` classe consente di gestire gli eventi.  
  
3.  Aggiungere il seguente gestore eventi per il `Form1` classe per gestire gli eventi generati da `testInstance`:  
  
     [!code-vb[VbVbalrOOP#106](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#106)]
  
4.  Aggiungere una subroutine denominata `Test` per la `Form1` classe per testare la classe di implementazione:  
  
     [!code-vb[VbVbalrOOP#107](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#107)]
  
     Il `Test` procedura consente di creare un'istanza della classe che implementa `MyInterface`, assegna l'istanza di `testInstance` imposta una proprietà, campo e viene eseguito un metodo tramite l'interfaccia.  
  
5.  Aggiungere codice per chiamare il `Test` stored procedure di `Form1 Load` routine del form di avvio:  
  
     [!code-vb[VbVbalrOOP#108](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#108)]
  
6.  Eseguire il `Test` procedura premendo F5. Viene visualizzato il messaggio "Prop1 è stato impostato su 9". Viene visualizzato dopo aver selezionato OK, il messaggio "il parametro X per Method1 is 5". Fare clic su OK e viene visualizzato il messaggio "il gestore dell'evento ha rilevato l'evento".  
  
## <a name="see-also"></a>Vedere anche

 [Istruzione Implements](../../../../visual-basic/language-reference/statements/implements-statement.md)  
 [Interfacce](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)  
 [Istruzione Interface](../../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Istruzione Event](../../../../visual-basic/language-reference/statements/event-statement.md)  