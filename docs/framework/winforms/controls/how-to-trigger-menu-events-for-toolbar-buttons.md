---
title: 'Procedura: Attivare eventi di menu per i pulsanti di una barra degli strumenti'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], toolbars
- ToolBar control [Windows Forms], click event handlers
- ToolBar control [Windows Forms], coding button click events
- toolbars [Windows Forms], click event handlers
ms.assetid: 98374f70-993d-4ca4-89fb-48fea6ce5b45
ms.openlocfilehash: 99db077b41a59fe9263f7283b58b8c31959c7c79
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182083"
---
# <a name="how-to-trigger-menu-events-for-toolbar-buttons"></a>Procedura: Attivare eventi di menu per i pulsanti di una barra degli strumenti
> [!NOTE]
> Benché il controllo <xref:System.Windows.Forms.ToolStrip> sostituisca il controllo <xref:System.Windows.Forms.ToolBar> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.ToolBar> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.  
  
 Se il Windows <xref:System.Windows.Forms.ToolBar> Form dispone di un controllo con i pulsanti della barra degli strumenti, è necessario sapere su quale pulsante l'utente fa clic.  
  
 Nell'evento <xref:System.Windows.Forms.ToolBar.ButtonClick> del <xref:System.Windows.Forms.ToolBar> controllo, è <xref:System.Windows.Forms.ToolBarButtonClickEventArgs.Button%2A> possibile valutare <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> la proprietà della classe . Nell'esempio seguente viene visualizzata una finestra di messaggio, che indica il pulsante selezionato. Per informazioni dettagliate, vedere <xref:System.Windows.Forms.MessageBox>.  
  
 Nell'esempio riportato <xref:System.Windows.Forms.ToolBar> di seguito si presuppone che un controllo sia stato aggiunto a un Windows Form.The example below assumes a control has been added to a Windows Form.  
  
### <a name="to-handle-the-click-event-on-a-toolbar"></a>Per gestire l'evento Click in una barra degli strumenti  
  
1. In una procedura, aggiungere <xref:System.Windows.Forms.ToolBar> pulsanti della barra degli strumenti al controllo.  
  
    ```vb  
    Public Sub ToolBarConfig()  
    ' Instantiate the toolbar buttons, set their Text properties  
    ' and add them to the ToolBar control.  
       ToolBar1.Buttons.Add(New ToolBarButton("One"))  
       ToolBar1.Buttons.Add(New ToolBarButton("Two"))  
       ToolBar1.Buttons.Add(New ToolBarButton("Three"))  
    ' Add the event handler delegate.  
       AddHandler ToolBar1.ButtonClick, AddressOf Me.ToolBar1_ButtonClick  
    End Sub  
    ```  
  
    ```csharp  
    public void ToolBarConfig()
    {  
       toolBar1.Buttons.Add(new ToolBarButton("One"));  
       toolBar1.Buttons.Add(new ToolBarButton("Two"));  
       toolBar1.Buttons.Add(new ToolBarButton("Three"));  
  
       toolBar1.ButtonClick +=
          new ToolBarButtonClickEventHandler(this.toolBar1_ButtonClick);  
    }  
    ```  
  
    ```cpp  
    public:  
       void ToolBarConfig()  
       {  
          toolBar1->Buttons->Add(gcnew ToolBarButton("One"));  
          toolBar1->Buttons->Add(gcnew ToolBarButton("Two"));  
          toolBar1->Buttons->Add(gcnew ToolBarButton("Three"));  
  
          toolBar1->ButtonClick +=
             gcnew ToolBarButtonClickEventHandler(this,  
             &Form1::toolBar1_ButtonClick);  
       }  
    ```  
  
2. Aggiungere un gestore <xref:System.Windows.Forms.ToolBar> eventi <xref:System.Windows.Forms.ToolBar.ButtonClick> per l'evento del controllo. Utilizzare un'istruzione di <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> cambio maiuscole/minuscole e la classe per determinare il pulsante della barra degli strumenti su cui è stato fatto clic. Verrà visualizzata una finestra di messaggio appropriata.  
  
    > [!NOTE]
    > In questo esempio la finestra di messaggio viene usata esclusivamente come segnaposto. È possibile aggiungere altro codice da eseguire quando vengono selezionati i pulsanti della barra degli strumenti.  
  
    ```vb  
    Protected Sub ToolBar1_ButtonClick(ByVal sender As Object, _  
    ByVal e As ToolBarButtonClickEventArgs)  
    ' Evaluate the Button property of the ToolBarButtonClickEventArgs  
    ' to determine which button was clicked.  
       Select Case ToolBar1.Buttons.IndexOf(e.Button)  
         Case 0  
           MessageBox.Show("First toolbar button clicked")  
         Case 1  
           MessageBox.Show("Second toolbar button clicked")  
         Case 2  
           MessageBox.Show("Third toolbar button clicked")  
       End Select  
    End Sub  
    ```  
  
    ```csharp  
    protected void toolBar1_ButtonClick(object sender,  
    ToolBarButtonClickEventArgs e)  
    {  
       // Evaluate the Button property of the ToolBarButtonClickEventArgs  
       // to determine which button was clicked.  
       switch (toolBar1.Buttons.IndexOf(e.Button))  
       {  
          case 0 :  
             MessageBox.Show("First toolbar button clicked");  
             break;  
          case 1 :  
             MessageBox.Show("Second toolbar button clicked");  
             break;  
          case 2 :  
             MessageBox.Show("Third toolbar button clicked");  
             break;  
       }  
    }  
    ```  
  
    ```cpp  
    protected:  
       void toolBar1_ButtonClick(System::Object ^ sender,  
          ToolBarButtonClickEventArgs ^ e)  
       {  
         // Evaluate the Button property of the ToolBarButtonClickEventArgs  
         // to determine which button was clicked.  
          switch (toolBar1->Buttons->IndexOf(e->Button))  
          {  
             case 0 :  
                MessageBox::Show("First toolbar button clicked");  
                break;  
             case 1 :  
                MessageBox::Show("Second toolbar button clicked");  
                break;  
             case 2 :  
                MessageBox::Show("Third toolbar button clicked");  
                break;  
          }  
       }  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolBar>
- [Procedura: aggiungere pulsanti a un controllo ToolBar](how-to-add-buttons-to-a-toolbar-control.md)
- [Procedura: definire un'icona per un pulsante ToolBar](how-to-define-an-icon-for-a-toolbar-button.md)
- [Controllo ToolBar](toolbar-control-windows-forms.md)
