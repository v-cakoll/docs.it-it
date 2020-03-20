---
title: 'Procedura: aggiungere o rimuovere controlli da una raccolta in fase di esecuzione'
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
ms.openlocfilehash: 369946581847b4bdcf8bc658aeb94b14c529061c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182282"
---
# <a name="how-to-add-to-or-remove-from-a-collection-of-controls-at-run-time"></a>Procedura: aggiungere o rimuovere controlli da una raccolta in fase di esecuzione
Attività comuni nello sviluppo di applicazioni sono l'aggiunta e la rimozione <xref:System.Windows.Forms.Panel> di <xref:System.Windows.Forms.GroupBox> controlli da qualsiasi controllo contenitore nei form (ad esempio il controllo o o o anche il form stesso). In fase di progettazione è possibile trascinare i controlli direttamente in un pannello o una casella di gruppo. In fase di esecuzione questi controlli mantengono una raccolta `Controls`, che tiene traccia di quali controlli vengono posizionati su essi.  
  
> [!NOTE]
> L'esempio di codice seguente si applica a qualsiasi controllo che mantiene una raccolta di controlli al suo interno.  
  
### <a name="to-add-a-control-to-a-collection-programmatically"></a>Per aggiungere un controllo a una raccolta a livello di codice  
  
1. Creare un'istanza del controllo da aggiungere.  
  
2. Impostare le proprietà del nuovo controllo.  
  
3. Aggiungere il controllo alla raccolta `Controls` del controllo padre.  
  
     Esempio di codice seguente viene illustrato <xref:System.Windows.Forms.Button> come creare un'istanza del controllo. Richiede un form <xref:System.Windows.Forms.Panel> con un controllo e che il metodo `NewPanelButton_Click`di gestione degli eventi per il pulsante creato, , esista già.  
  
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
  
1. Rimuovere il gestore eventi dall'evento. In Visual Basic utilizzare la parola chiave [RemoveHandler Statement](../../../visual-basic/language-reference/statements/removehandler-statement.md) ; nel linguaggio C, utilizzare [l'operatore -.](../../../csharp/language-reference/operators/subtraction-operator.md)  
  
2. Usare il metodo `Remove` per eliminare il controllo desiderato dalla raccolta del pannello `Controls`.  
  
3. Chiamare <xref:System.Windows.Forms.Control.Dispose%2A> il metodo per rilasciare tutte le risorse utilizzate dal controllo.  
  
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
