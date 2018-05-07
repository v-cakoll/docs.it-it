---
title: Definizione di classi (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- execution [Visual Basic], ending
- objects [Visual Basic], initializing
- Initialize event [Visual Basic]
- files [Visual Basic], closing
- programs [Visual Basic], quitting
- code, exiting
- objects [Visual Basic], creating
- program termination
- classes [Visual Basic], walkthroughs
- class modules, walkthroughs
- Terminate event [Visual Basic]
- execution [Visual Basic], stopping
ms.assetid: 07018828-2d49-4cf5-a44b-19fb15d9efea
ms.openlocfilehash: aac30a8b0272ae6c141138a91585953237ab8098
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-defining-classes-visual-basic"></a>Procedura dettagliata: definizione delle classi (Visual Basic)

Questa procedura dettagliata viene illustrato come definire le classi, che è quindi possibile utilizzare per creare oggetti. Inoltre viene illustrato come aggiungere proprietà e metodi alla nuova classe e viene illustrato come inizializzare un oggetto.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-a-class"></a>Per definire una classe
  
1.  Creare un progetto scegliendo **nuovo progetto** sul **File** menu. Verrà visualizzata la finestra di dialogo **Nuovo progetto** .  
  
2.  Selezionare dall'elenco dei modelli di progetto Visual Basic per visualizzare il nuovo progetto applicazione Windows.  
  
3.  Aggiungere una nuova classe al progetto, fare clic su **Aggiungi classe** sul **progetto** menu. Verrà visualizzata la finestra di dialogo **Aggiungi nuovo elemento**.  
  
4.  Selezionare il **classe** modello.  
  
5.  Denominare la nuova classe `UserNameInfo.vb`, quindi fare clic su **Aggiungi** per visualizzare il codice per la nuova classe.  
  
     [!code-vb[VbVbalrOOP#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#5)]
  
    > [!NOTE]
    >  È possibile usare Visual Basic **Editor di codice** per aggiungere una classe al form di avvio digitando il `Class` (parola chiave) seguito dal nome della nuova classe. Il **Editor di codice** fornisce un corrispondente `End Class` istruzione per l'utente.  
  
6.  Definire un campo privato per la classe aggiungendo il codice seguente tra i `Class` e `End Class` istruzioni:  
  
     [!code-vb[VbVbalrOOP#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#7)]
  
     La dichiarazione del campo come `Private` significa che può essere utilizzato solo all'interno della classe. È possibile rendere disponibili i campi all'esterno di una classe utilizzando i modificatori di accesso, ad esempio `Public` che forniscono maggiori diritti di accesso. Per ulteriori informazioni, vedere [accedere livelli in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
7.  Definire una proprietà per la classe aggiungendo il codice seguente:  
  
     [!code-vb[VbVbalrOOP#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#8)]
  
8.  Definire un metodo per la classe aggiungendo il codice seguente:  
  
     [!code-vb[VbVbalrOOP#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#9)]
  
9. Definire un costruttore con parametri per la nuova classe aggiungendo una routine denominata `Sub New`:  
  
     [!code-vb[VbVbalrOOP#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#10)]
  
     Il `Sub New` costruttore viene chiamato automaticamente quando viene creato un oggetto in base a questa classe. Questo costruttore imposta il valore del campo che contiene il nome utente.  
  
## <a name="to-create-a-button-to-test-the-class"></a>Per creare un pulsante per testare la classe
  
1.  Impostare il form di avvio in modalità progettazione facendo clic con il nome **Esplora** e quindi fare clic su **Visualizza finestra di progettazione**. Per impostazione predefinita, il form di avvio per i progetti di applicazione Windows denominato Form1. vb. Verrà quindi visualizzato il form principale.  
  
2.  Aggiungere un pulsante al form principale e fare doppio clic per visualizzare il codice per il `Button1_Click` gestore dell'evento. Aggiungere il codice seguente per chiamare la routine di test:  
  
     [!code-vb[VbVbalrOOP#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#12)]
  
## <a name="to-run-your-application"></a>Per eseguire l'applicazione
  
1.  Eseguire l'applicazione premendo F5. Fare clic sul pulsante sul form per chiamare la routine di test. Visualizza un messaggio che informa che originale `UserName` è "MOORE, BOBBY", perché la procedura chiamata il `Capitalize` metodo dell'oggetto.  
  
2.  Fare clic su **OK** per chiudere la finestra di messaggio. Il `Button1 Click` procedura consente di modificare il valore della `UserName` proprietà e viene visualizzato un messaggio indicante che il nuovo valore di `UserName` è "Worden, Joe".  
  
## <a name="see-also"></a>Vedere anche

[Programmazione orientata a oggetti (Visual Basic)](../../concepts/object-oriented-programming.md)  
[Oggetti e classi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)