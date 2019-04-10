---
title: 'Procedura: Aggiungere o rimuovere controlli da una raccolta in fase di esecuzione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- run time [Windows Forms], removing controls
- controls [Windows Forms], adding using collections
- controls collections
- collections [Windows Forms], adding items
- run time [Windows Forms], adding controls
- controls [Windows Forms], removing using collections
ms.assetid: 771bf895-3d5f-469b-a324-3528f343657e
ms.openlocfilehash: 85c1d398c1aabbb73d5ae34186775e2c63666cfb
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59309446"
---
# <a name="how-to-add-to-or-remove-from-a-collection-of-controls-at-run-time"></a>Procedura: Aggiungere o rimuovere controlli da una raccolta in fase di esecuzione
Attività comuni nello sviluppo di applicazioni sono controlli per l'aggiunta e rimozione di controlli da un controllo contenitore sui form (ad esempio la <xref:System.Windows.Forms.Panel> o <xref:System.Windows.Forms.GroupBox> controllo o il form stesso). In fase di progettazione è possibile trascinare i controlli direttamente in un pannello o una casella di gruppo. In fase di esecuzione questi controlli mantengono una raccolta `Controls`, che tiene traccia di quali controlli vengono posizionati su essi.  
  
> [!NOTE]
>  L'esempio di codice seguente si applica a qualsiasi controllo che mantiene una raccolta di controlli al suo interno.  
  
### <a name="to-add-a-control-to-a-collection-programmatically"></a>Per aggiungere un controllo a una raccolta a livello di codice  
  
1. Creare un'istanza del controllo da aggiungere.  
  
2. Impostare le proprietà del nuovo controllo.  
  
3. Aggiungere il controllo alla raccolta `Controls` del controllo padre.  
  
     Esempio di codice seguente viene illustrato come creare un'istanza di <xref:System.Windows.Forms.Button> controllo. Richiede un modulo con un <xref:System.Windows.Forms.Panel> controllo e che viene creato il metodo di gestione degli eventi per il pulsante, `NewPanelButton_Click`, esiste già.  
  
    ```vb  
    Public NewPanelButton As New Button()  
  
    Public Sub AddNewControl()  
       ' The Add method will accept as a parameter any object that derives  
       ' from the Control class. In this case, it is a Button control.  
       Panel1.Controls.Add(NewPanelButton)  
       ' The event handler indicated for the Click event in the code   
       ' below is used as an example. Substite the appropriate event  
       ' handler for your application.  
       AddHandler NewPanelButton.Click, AddressOf NewPanelButton_Click  
    End Sub  
    ```  
  
    ```csharp  
    public Button newPanelButton = new Button();  
  
    public void addNewControl()  
    {   
       // The Add method will accept as a parameter any object that derives  
       // from the Control class. In this case, it is a Button control.  
       panel1.Controls.Add(newPanelButton);  
       // The event handler indicated for the Click event in the code   
       // below is used as an example. Substitute the appropriate event  
       // handler for your application.  
       this.newPanelButton.Click += new System.EventHandler(this. NewPanelButton_Click);  
    }  
    ```  
  
### <a name="to-remove-controls-from-a-collection-programmatically"></a>Per rimuovere controlli da una raccolta a livello di codice  
  
1. Rimuovere il gestore eventi dall'evento. In Visual Basic, usare il [istruzione RemoveHandler](~/docs/visual-basic/language-reference/statements/removehandler-statement.md) parola chiave; nell'oggetto visivo C#, usare il [operatore-= (C# riferimento)](~/docs/csharp/language-reference/operators/subtraction-assignment-operator.md).  
  
2. Usare il metodo `Remove` per eliminare il controllo desiderato dalla raccolta del pannello `Controls`.  
  
3. Chiamare il <xref:System.Windows.Forms.Control.Dispose%2A> metodo per rilasciare tutte le risorse usate dal controllo.  
  
    ```vb  
    Public Sub RemoveControl()  
    ' NOTE: The code below uses the instance of   
    ' the button (NewPanelButton) from the previous example.  
       If Panel1.Controls.Contains(NewPanelButton) Then  
          RemoveHandler NewPanelButton.Click, AddressOf _   
             NewPanelButton_Click  
          Panel1.Controls.Remove(NewPanelButton)  
          NewPanelButton.Dispose()  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void removeControl(object sender, System.EventArgs e)  
    {  
    // NOTE: The code below uses the instance of   
    // the button (newPanelButton) from the previous example.  
       if(panel1.Controls.Contains(newPanelButton))  
       {  
          this.newPanelButton.Click -= new System.EventHandler(this.   
             NewPanelButton_Click);  
          panel1.Controls.Remove(newPanelButton);  
          newPanelButton.Dispose();  
       }  
    }  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Panel>
- [Controllo Panel](panel-control-windows-forms.md)
