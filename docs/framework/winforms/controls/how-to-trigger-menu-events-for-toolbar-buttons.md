---
title: 'Procedura: Attivare eventi di Menu per i pulsanti della barra degli strumenti'
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
ms.openlocfilehash: b6d0404f22c7db72b096ef130d9a9f4815db4059
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707547"
---
# <a name="how-to-trigger-menu-events-for-toolbar-buttons"></a>Procedura: Attivare eventi di Menu per i pulsanti della barra degli strumenti
> [!NOTE]
>  Benché il controllo <xref:System.Windows.Forms.ToolStrip> sostituisca il controllo <xref:System.Windows.Forms.ToolBar> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.ToolBar> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.  
  
 Se la funzionalità di Windows Form un <xref:System.Windows.Forms.ToolBar> controllo con i pulsanti della barra degli strumenti, è opportuno conoscere quale pulsante l'utente fa clic.  
  
 Nel <xref:System.Windows.Forms.ToolBar.ButtonClick> eventi del <xref:System.Windows.Forms.ToolBar> (controllo), è possibile valutare il <xref:System.Windows.Forms.ToolBarButtonClickEventArgs.Button%2A> proprietà del <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> classe. Nell'esempio seguente viene visualizzata una finestra di messaggio, che indica il pulsante selezionato. Per informazioni dettagliate, vedere <xref:System.Windows.Forms.MessageBox>.  
  
 Nell'esempio seguente si presuppone un <xref:System.Windows.Forms.ToolBar> controllo è stato aggiunto a un modulo di Windows.  
  
### <a name="to-handle-the-click-event-on-a-toolbar"></a>Per gestire l'evento Click in una barra degli strumenti  
  
1.  In una procedura, aggiungere i pulsanti della barra degli strumenti per la <xref:System.Windows.Forms.ToolBar> controllo.  
  
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
  
2.  Aggiungere un gestore eventi per il <xref:System.Windows.Forms.ToolBar> del controllo <xref:System.Windows.Forms.ToolBar.ButtonClick> evento. Usare un'istruzione case di passaggio e <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> classe per determinare il pulsante della barra degli strumenti che è stato fatto clic. Verrà visualizzata una finestra di messaggio appropriata.  
  
    > [!NOTE]
    >  In questo esempio la finestra di messaggio viene usata esclusivamente come segnaposto. È possibile aggiungere altro codice da eseguire quando vengono selezionati i pulsanti della barra degli strumenti.  
  
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
- [Procedura: Aggiungere pulsanti a un controllo ToolBar](how-to-add-buttons-to-a-toolbar-control.md)
- [Procedura: Definire un'icona per un pulsante della barra degli strumenti](how-to-define-an-icon-for-a-toolbar-button.md)
- [Controllo ToolBar](toolbar-control-windows-forms.md)
