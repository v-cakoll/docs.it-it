---
title: Determinare quando modificare gli attributi di formattazione nel controllo RichTextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], text boxes
- RichTextBox control [Windows Forms], determining font changes
- text boxes [Windows Forms], determining font changes
- SelChange event
ms.assetid: bdfed015-f77a-41e5-b38f-f8629b2fa166
ms.openlocfilehash: f9b2a1028f79059ec7d4d6bf3683100455bb5dea
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746043"
---
# <a name="how-to-determine-when-formatting-attributes-change-in-the-windows-forms-richtextbox-control"></a>Procedura: individuare le modifiche degli attributi di formattazione nel controllo RichTextBox Windows Form
Un uso comune del controllo <xref:System.Windows.Forms.RichTextBox> Windows Forms consiste nel formattare il testo con attributi quali le opzioni del tipo di carattere o gli stili dei paragrafi. È possibile che l'applicazione debba tenere traccia delle modifiche apportate alla formattazione del testo allo scopo di visualizzare una barra degli strumenti, come in molte applicazioni di elaborazione di testi.  
  
### <a name="to-respond-to-changes-in-formatting-attributes"></a>Per rispondere alle modifiche degli attributi di formattazione  
  
1. Scrivere il codice nel gestore eventi <xref:System.Windows.Forms.RichTextBox.SelectionChanged> per eseguire un'azione appropriata a seconda del valore dell'attributo. Nell'esempio seguente viene modificato l'aspetto di un pulsante della barra degli strumenti a seconda del valore della proprietà <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A>. Il pulsante della barra degli strumenti verrà aggiornato solo quando il punto di inserimento viene spostato nel controllo.  
  
     Nell'esempio seguente si presuppone un form con un controllo <xref:System.Windows.Forms.RichTextBox> e un controllo <xref:System.Windows.Forms.ToolBar> che contiene un pulsante della barra degli strumenti. Per ulteriori informazioni sulle barre degli strumenti e sui pulsanti della barra degli strumenti, vedere [procedura: aggiungere pulsanti a un controllo Toolbar](how-to-add-buttons-to-a-toolbar-control.md).  
  
    ```vb  
    ' The following code assumes the existence of a toolbar control  
    ' with at least one toolbar button.  
    Private Sub RichTextBox1_SelectionChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles RichTextBox1.SelectionChanged  
       If RichTextBox1.SelectionBullet = True Then  
          ' Bullet button on toolbar should appear pressed  
          ToolBarButton1.Pushed = True  
       Else  
           ' Bullet button on toolbar should appear unpressed  
           ToolBarButton1.Pushed = False  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    // The following code assumes the existence of a toolbar control  
    // with at least one toolbar button.  
    private void richTextBox1_SelectionChanged(object sender,  
    System.EventArgs e)  
    {  
       if (richTextBox1.SelectionBullet == true)   
       {  
          // Bullet button on toolbar should appear pressed  
          toolBarButton1.Pushed = true;  
       }  
       else   
       {  
          // Bullet button on toolbar should appear unpressed  
          toolBarButton1.Pushed = false;  
       }  
    }  
    ```  
  
    ```cpp  
    // The following code assumes the existence of a toolbar control  
    // with at least one toolbar button.  
    private:  
       System::Void richTextBox1_SelectionChanged(  
          System::Object ^  sender, System::EventArgs ^  e)  
       {  
          if (richTextBox1->SelectionBullet == true)  
          {  
             // Bullet button on toolbar should appear pressed  
             toolBarButton1->Pushed = true;  
          }  
          else  
          {  
             // Bullet button on toolbar should appear unpressed  
             toolBarButton1->Pushed = false;  
          }  
       }  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.RichTextBox.SelectionChanged>
- <xref:System.Windows.Forms.RichTextBox>
- [Controllo RichTextBox](richtextbox-control-windows-forms.md)
- [Controlli da usare in Windows Form](controls-to-use-on-windows-forms.md)
