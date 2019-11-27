---
title: Definizione delle classi
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
ms.openlocfilehash: bd3f6e5cff41551240d9904ab93af8758eb104d2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346079"
---
# <a name="walkthrough-defining-classes-visual-basic"></a>Procedura dettagliata: definizione delle classi (Visual Basic)

In questa procedura dettagliata viene illustrato come definire le classi, che è possibile utilizzare per creare oggetti. Viene inoltre illustrato come aggiungere proprietà e metodi alla nuova classe e viene illustrato come inizializzare un oggetto.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-a-class"></a>Per definire una classe
  
1. Per creare un progetto, fare clic su **nuovo progetto** dal menu **file** . Viene visualizzata la finestra di dialogo **Nuovo progetto**.  
  
2. Selezionare applicazione Windows dall'elenco dei modelli di progetto Visual Basic per visualizzare il nuovo progetto.  
  
3. Per aggiungere una nuova classe al progetto, fare clic su **Aggiungi classe** dal menu **progetto** . Verrà visualizzata la finestra di dialogo **Aggiungi nuovo elemento**.  
  
4. Selezionare il modello di **classe** .  
  
5. Assegnare alla nuova classe il nome `UserNameInfo.vb`, quindi fare clic su **Aggiungi** per visualizzare il codice per la nuova classe.  
  
     [!code-vb[VbVbalrOOP#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#5)]
  
    > [!NOTE]
    > È possibile usare l' **editor di codice** Visual Basic per aggiungere una classe al form di avvio digitando la parola chiave `Class` seguita dal nome della nuova classe. L' **editor di codice** fornisce un'istruzione `End Class` corrispondente.  
  
6. Definire un campo privato per la classe aggiungendo il codice seguente tra le istruzioni `Class` e `End Class`:  
  
     [!code-vb[VbVbalrOOP#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#7)]
  
     Dichiarando il campo come `Private` significa che può essere utilizzato solo all'interno della classe. È possibile rendere disponibili i campi dall'esterno di una classe usando i modificatori di accesso, ad esempio `Public` che forniscono maggiore accesso. Per altre informazioni, vedere [livelli di accesso in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
7. Definire una proprietà per la classe aggiungendo il codice seguente:  
  
     [!code-vb[VbVbalrOOP#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#8)]
  
8. Definire un metodo per la classe aggiungendo il codice seguente:  
  
     [!code-vb[VbVbalrOOP#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#9)]
  
9. Definire un costruttore con parametri per la nuova classe aggiungendo una routine denominata `Sub New`:  
  
     [!code-vb[VbVbalrOOP#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#10)]
  
     Il costruttore `Sub New` viene chiamato automaticamente quando viene creato un oggetto basato su questa classe. Questo costruttore imposta il valore del campo che contiene il nome utente.  
  
## <a name="to-create-a-button-to-test-the-class"></a>Per creare un pulsante per testare la classe
  
1. Modificare il modulo di avvio in modalità progettazione facendo clic con il pulsante destro del mouse sul nome in **Esplora soluzioni** e quindi scegliendo **Visualizza finestra di progettazione**. Per impostazione predefinita, il form di avvio per i progetti di applicazioni Windows è denominato Form1. vb. Verrà visualizzato il form principale.  
  
2. Aggiungere un pulsante al form principale e fare doppio clic su di esso per visualizzare il codice per il gestore dell'evento `Button1_Click`. Aggiungere il codice seguente per chiamare la procedura di test:  
  
     [!code-vb[VbVbalrOOP#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#12)]
  
## <a name="to-run-your-application"></a>Per eseguire l'applicazione
  
1. Eseguire l'applicazione premendo F5. Fare clic sul pulsante nel form per chiamare la procedura di test. Viene visualizzato un messaggio che informa che il `UserName` originale è "MOORE, BOBBY", perché la procedura ha chiamato il metodo `Capitalize` dell'oggetto.  
  
2. Fare clic su **OK** per chiudere la finestra del messaggio. La procedura `Button1 Click` modifica il valore della proprietà `UserName` e visualizza un messaggio che informa che il nuovo valore di `UserName` è "worden, Joe".  
  
## <a name="see-also"></a>Vedere anche

- [Programmazione orientata a oggetti (Visual Basic)](../../concepts/object-oriented-programming.md)
- [Oggetti e classi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
