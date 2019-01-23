---
title: 'Procedura: Determinare quando si formatta modifiche degli attributi nel controllo RichTextBox Windows Form'
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
ms.openlocfilehash: e746cd1d0f9f7d9850d0263ee6ed0a82472fcb5e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54504150"
---
# <a name="how-to-determine-when-formatting-attributes-change-in-the-windows-forms-richtextbox-control"></a>Procedura: Determinare quando si formatta modifiche degli attributi nel controllo RichTextBox Windows Form
Un uso comune dei Windows Form <xref:System.Windows.Forms.RichTextBox> controllo è la formattazione del testo con gli attributi, ad esempio opzioni del carattere o gli stili di paragrafo. L'applicazione potrebbe essere necessario tenere traccia delle modifiche di formattazione per la visualizzazione di una barra degli strumenti, come in molte applicazioni di elaborazione del testo.  
  
### <a name="to-respond-to-changes-in-formatting-attributes"></a>Per rispondere alle modifiche degli attributi di formattazione  
  
1.  Scrivere codice nel <xref:System.Windows.Forms.RichTextBox.SelectionChanged> gestore eventi per eseguire un'azione appropriata in base al valore dell'attributo. L'esempio seguente modifica l'aspetto di un pulsante della barra degli strumenti in base al valore di <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> proprietà. Il pulsante della barra degli strumenti verrà aggiornato solo quando il punto di inserimento viene spostato nel controllo.  
  
     L'esempio seguente si presuppone un form con un <xref:System.Windows.Forms.RichTextBox> controllo e un <xref:System.Windows.Forms.ToolBar> controllo che contiene un pulsante della barra degli strumenti. Per altre informazioni sulle barre degli strumenti e i pulsanti della barra degli strumenti, vedere [come: Aggiungere pulsanti a un controllo ToolBar](../../../../docs/framework/winforms/controls/how-to-add-buttons-to-a-toolbar-control.md).  
  
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
- [Controllo RichTextBox](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)
- [Controlli da usare in Windows Form](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
