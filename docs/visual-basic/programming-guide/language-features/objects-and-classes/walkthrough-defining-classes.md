---
title: Definizione di classi (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ec002e1709fa5fe31dfe7744fb91a230c32337a6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-defining-classes-visual-basic"></a>Procedura dettagliata: definizione delle classi (Visual Basic)
Questa procedura dettagliata viene illustrato come definire le classi, che è quindi possibile utilizzare per creare oggetti. Inoltre viene illustrato come aggiungere proprietà e metodi alla nuova classe e viene illustrato come inizializzare un oggetto.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-define-a-class"></a>Per definire una classe  
  
1.  Creare un progetto scegliendo **nuovo progetto** sul **File** menu. Verrà visualizzata la finestra di dialogo **Nuovo progetto** .  
  
2.  Selezionare nell'elenco di applicazioni di Windows [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] modelli per visualizzare il nuovo progetto di progetto.  
  
3.  Aggiungere una nuova classe al progetto, fare clic su **Aggiungi classe** sul **progetto** menu. Verrà visualizzata la finestra di dialogo **Aggiungi nuovo elemento**.  
  
4.  Selezionare il **classe** modello.  
  
5.  Denominare la nuova classe `UserNameInfo.vb`, quindi fare clic su **Aggiungi** per visualizzare il codice per la nuova classe.  
  
     [!code-vb[VbVbalrOOP#5](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_1.vb)]  
  
    > [!NOTE]
    >  È possibile utilizzare il [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] **Editor di codice** per aggiungere una classe al form di avvio digitando il `Class` (parola chiave) seguito dal nome della nuova classe. Il **Editor di codice** fornisce un corrispondente `End Class` istruzione per l'utente.  
  
6.  Definire un campo privato per la classe aggiungendo il codice seguente tra i `Class` e `End Class` istruzioni:  
  
     [!code-vb[VbVbalrOOP#7](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_2.vb)]  
  
     La dichiarazione del campo come `Private` significa che può essere utilizzato solo all'interno della classe. È possibile rendere disponibili i campi all'esterno di una classe utilizzando i modificatori di accesso, ad esempio `Public` che forniscono maggiori diritti di accesso. Per ulteriori informazioni, vedere [accedere livelli in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
7.  Definire una proprietà per la classe aggiungendo il codice seguente:  
  
     [!code-vb[VbVbalrOOP#8](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_3.vb)]  
  
8.  Definire un metodo per la classe aggiungendo il codice seguente:  
  
     [!code-vb[VbVbalrOOP#9](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_4.vb)]  
  
9. Definire un costruttore con parametri per la nuova classe aggiungendo una routine denominata `Sub New`:  
  
     [!code-vb[VbVbalrOOP#10](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_5.vb)]  
  
     Il `Sub New` costruttore viene chiamato automaticamente quando viene creato un oggetto in base a questa classe. Questo costruttore imposta il valore del campo che contiene il nome utente.  
  
### <a name="to-create-a-button-to-test-the-class"></a>Per creare un pulsante per testare la classe  
  
1.  Impostare il form di avvio in modalità progettazione facendo clic con il nome **Esplora** e quindi fare clic su **Visualizza finestra di progettazione**. Per impostazione predefinita, il form di avvio per i progetti di applicazione Windows denominato Form1. vb. Verrà quindi visualizzato il form principale.  
  
2.  Aggiungere un pulsante al form principale e fare doppio clic per visualizzare il codice per il `Button1_Click` gestore dell'evento. Aggiungere il codice seguente per chiamare la routine di test:  
  
     [!code-vb[VbVbalrOOP#12](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_6.vb)]  
  
### <a name="to-run-your-application"></a>Per eseguire l'applicazione  
  
1.  Eseguire l'applicazione premendo F5. Fare clic sul pulsante sul form per chiamare la routine di test. Visualizza un messaggio che informa che originale `UserName` è "MOORE, BOBBY", perché la procedura chiamata il `Capitalize` metodo dell'oggetto.  
  
2.  Fare clic su **OK** per chiudere la finestra di messaggio. Il `Button1 Click` procedura consente di modificare il valore della `UserName` proprietà e viene visualizzato un messaggio indicante che il nuovo valore di `UserName` è "Worden, Joe".  
  
## <a name="see-also"></a>Vedere anche  
 [Programmazione orientata ad oggetti](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)  
 [Oggetti e classi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
