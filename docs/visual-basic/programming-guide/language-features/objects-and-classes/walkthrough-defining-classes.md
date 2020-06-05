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
ms.openlocfilehash: 646c6ce307131f3edba194af19920eade9c1753c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84389114"
---
# <a name="walkthrough-defining-classes-visual-basic"></a>Procedura dettagliata: definizione delle classi (Visual Basic)

In questa procedura dettagliata viene illustrato come definire le classi, che è possibile utilizzare per creare oggetti. Viene inoltre illustrato come aggiungere proprietà e metodi alla nuova classe e viene illustrato come inizializzare un oggetto.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-a-class"></a>Per definire una classe
  
1. Per creare un progetto, fare clic su **nuovo progetto** dal menu **file** . Verrà visualizzata la finestra di dialogo **Nuovo progetto** .  
  
2. Selezionare applicazione Windows dall'elenco dei modelli di progetto Visual Basic per visualizzare il nuovo progetto.  
  
3. Per aggiungere una nuova classe al progetto, fare clic su **Aggiungi classe** dal menu **progetto** . Verrà visualizzata la finestra di dialogo **Aggiungi nuovo elemento** .  
  
4. Selezionare il modello di **classe** .  
  
5. Assegnare un nome alla nuova classe `UserNameInfo.vb` e quindi fare clic su **Aggiungi** per visualizzare il codice per la nuova classe.  
  
     [!code-vb[VbVbalrOOP#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#5)]
  
    > [!NOTE]
    > È possibile usare l' **editor di codice** Visual Basic per aggiungere una classe al form di avvio digitando la `Class` parola chiave seguita dal nome della nuova classe. L' **editor di codice** fornisce un' `End Class` istruzione corrispondente.  
  
6. Definire un campo privato per la classe aggiungendo il codice seguente tra le `Class` istruzioni e `End Class` :  
  
     [!code-vb[VbVbalrOOP#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#7)]
  
     Dichiarare il campo come `Private` significa che può essere utilizzato solo all'interno della classe. È possibile rendere disponibili i campi dall'esterno di una classe usando i modificatori di accesso, ad esempio, `Public` che forniscono maggiore accesso. Per altre informazioni, vedere [livelli di accesso in Visual Basic](../declared-elements/access-levels.md).  
  
7. Definire una proprietà per la classe aggiungendo il codice seguente:  
  
     [!code-vb[VbVbalrOOP#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#8)]
  
8. Definire un metodo per la classe aggiungendo il codice seguente:  
  
     [!code-vb[VbVbalrOOP#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#9)]
  
9. Definire un costruttore con parametri per la nuova classe aggiungendo una procedura denominata `Sub New` :  
  
     [!code-vb[VbVbalrOOP#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#10)]
  
     Il `Sub New` costruttore viene chiamato automaticamente quando viene creato un oggetto basato su questa classe. Questo costruttore imposta il valore del campo che contiene il nome utente.  
  
## <a name="to-create-a-button-to-test-the-class"></a>Per creare un pulsante per testare la classe
  
1. Modificare il modulo di avvio in modalità progettazione facendo clic con il pulsante destro del mouse sul nome in **Esplora soluzioni** e quindi scegliendo **Visualizza finestra di progettazione**. Per impostazione predefinita, il form di avvio per i progetti di applicazioni Windows è denominato Form1. vb. Verrà visualizzato il form principale.  
  
2. Aggiungere un pulsante al form principale e fare doppio clic su di esso per visualizzare il codice per il `Button1_Click` gestore eventi. Aggiungere il codice seguente per chiamare la procedura di test:  
  
     [!code-vb[VbVbalrOOP#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#12)]
  
## <a name="to-run-your-application"></a>Per eseguire l'applicazione
  
1. Eseguire l'applicazione premendo F5. Fare clic sul pulsante nel form per chiamare la procedura di test. Viene visualizzato un messaggio che informa che l'originale `UserName` è "Moore, Bobby", perché la procedura ha chiamato il `Capitalize` metodo dell'oggetto.  
  
2. Fare clic su **OK** per chiudere la finestra del messaggio. La `Button1 Click` stored procedure modifica il valore della `UserName` proprietà e visualizza un messaggio che informa che il nuovo valore di `UserName` è "worden, Joe".  
  
## <a name="see-also"></a>Vedere anche

- [Programmazione orientata a oggetti (Visual Basic)](../../concepts/object-oriented-programming.md)
- [Oggetti e classi](index.md)
