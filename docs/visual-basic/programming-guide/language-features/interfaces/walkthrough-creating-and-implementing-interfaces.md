---
title: Creazione e implementazione di interfacce (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [Visual Basic], walkthroughs
- interfaces [Visual Basic], testing
- interface implementation [Visual Basic], walkthrough
- interfaces [Visual Basic], creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
ms.openlocfilehash: 7a5694826e0fff82aceb8ad18f75f96f308e724c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680387"
---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a>Procedura dettagliata: Creazione e implementazione di interfacce (Visual Basic)

Le interfacce vengono descritte le caratteristiche della proprietà, metodi ed eventi, ma lasciare i dettagli di implementazione fino a strutture o classi.  
  
 Questa procedura dettagliata illustra come dichiarare e implementare un'interfaccia.  
  
> [!NOTE]
>  Questa procedura dettagliata non fornisce informazioni su come creare un'interfaccia utente.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-an-interface"></a>Per definire un'interfaccia
  
1.  Aprire un nuovo progetto Applicazione Windows in Visual Basic.  
  
2.  Aggiungere un nuovo modulo al progetto facendo clic **Aggiungi modulo** nel **progetto** menu.  
  
3.  Denominare il nuovo modulo `Module1.vb` e fare clic su **Add**. Viene visualizzato il codice per il nuovo modulo.  
  
4.  Definire un'interfaccia denominata `TestInterface` all'interno `Module1` digitando `Interface TestInterface` tra il `Module` e `End Module` istruzioni e quindi premere INVIO. Il **Editor di codice** rientri le `Interface` parola chiave e aggiunge un `End Interface` istruzione in modo da formare un blocco di codice.  
  
5.  Definire una proprietà, metodo ed eventi per l'interfaccia inserendo il codice seguente tra i `Interface` e `End Interface` istruzioni:  
  
     [!code-vb[VbVbalrOOP#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#98)]
  
## <a name="implementation"></a>Implementazione

 È possibile notare che la sintassi usata per dichiarare i membri di interfaccia è diversa da quella utilizzata per dichiarare i membri della classe. La differenza è dovuta al fatto che le interfacce non possono contenere codice di implementazione.  
  
### <a name="to-implement-the-interface"></a>Per implementare l'interfaccia
  
1.  Aggiungere una classe denominata `ImplementationClass` aggiungendo l'istruzione seguente alle `Module1`, dopo il `End Interface` istruzione ma prima di `End Module` istruzione e quindi premere INVIO:  
  
     [!code-vb[VbVbalrOOP#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#99)]
  
     Se si lavora all'interno dell'ambiente di sviluppo integrato, il **Editor di codice** fornisce un oggetto corrispondente `End Class` istruzione quando si preme INVIO.  
  
2.  Aggiungere il codice seguente `Implements` dell'istruzione `ImplementationClass`, quali nome dell'interfaccia implementata dalla classe:  
  
     [!code-vb[VbVbalrOOP#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#100)]
  
     Quando elencati separatamente dagli altri elementi nella parte superiore di una classe o struttura, il `Implements` istruzione indica che la classe o struttura implementa un'interfaccia.  
  
     Se si lavora all'interno dell'ambiente di sviluppo integrato, il **Editor di codice** implementa i membri della classe richiesti da `TestInterface` quando si preme INVIO, e si può ignorare il passaggio successivo.  
  
3.  Se non si lavora all'interno dell'ambiente di sviluppo integrato, è necessario implementare tutti i membri dell'interfaccia `MyInterface`. Aggiungere il codice seguente a `ImplementationClass` implementare `Event1`, `Method1`, e `Prop1`:  
  
     [!code-vb[VbVbalrOOP#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#101)]
  
     Il `Implements` l'istruzione viene assegnato l'interfaccia e un membro di interfaccia implementato.  
  
4.  Completare la definizione di `Prop1` aggiungendo un campo privato per la classe che è archiviato il valore della proprietà:  
  
     [!code-vb[VbVbalrOOP#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#102)]
  
     Restituire il valore di `pval` dalla proprietà di funzione di accesso get.  
  
     [!code-vb[VbVbalrOOP#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#103)]
  
     Impostare il valore di `pval` nel set di proprietà della funzione di accesso.  
  
     [!code-vb[VbVbalrOOP#104](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#104)]
  
5.  Completare la definizione di `Method1` aggiungendo il codice seguente.  
  
     [!code-vb[VbVbalrOOP#105](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#105)]
  
### <a name="to-test-the-implementation-of-the-interface"></a>Per testare l'implementazione dell'interfaccia
  
1.  Fare doppio clic su form di avvio per il progetto nel **Esplora soluzioni**, fare clic su **Visualizza codice**. L'editor consente di visualizzare la classe del form di avvio. Per impostazione predefinita, viene chiamato il modulo di avvio `Form1`.  
  
2.  Aggiungere il codice seguente `testInstance` campo per il `Form1` classe:  
  
     [!code-vb[VbVbalrOOP#120](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#120)]
  
     Dichiarando `testInstance` come `WithEvents`, il `Form1` classe può gestire gli eventi.  
  
3.  Aggiungere il seguente gestore eventi per il `Form1` classe per gestire gli eventi generati da `testInstance`:  
  
     [!code-vb[VbVbalrOOP#106](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#106)]
  
4.  Aggiungere una subroutine denominata `Test` per il `Form1` classe per testare la classe di implementazione:  
  
     [!code-vb[VbVbalrOOP#107](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#107)]
  
     Il `Test` routine crea un'istanza della classe che implementa `MyInterface`, assegna tale istanza per il `testInstance` imposta una proprietà, campo e viene eseguito un metodo tramite l'interfaccia.  
  
5.  Aggiungere il codice per chiamare il `Test` procedure dal `Form1 Load` routine del form di avvio:  
  
     [!code-vb[VbVbalrOOP#108](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#108)]
  
6.  Eseguire il `Test` procedura premendo F5. Viene visualizzato il messaggio "Prop1 è stato impostato su 9". Viene visualizzato dopo aver selezionato OK, il messaggio "il parametro X per Method1 is 5". Fare clic su OK e viene visualizzato il messaggio "il gestore dell'evento rilevato l'evento".  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Implements](../../../../visual-basic/language-reference/statements/implements-statement.md)
- [Interfacce](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)
- [Istruzione Interface](../../../../visual-basic/language-reference/statements/interface-statement.md)
- [Istruzione Event](../../../../visual-basic/language-reference/statements/event-statement.md)
