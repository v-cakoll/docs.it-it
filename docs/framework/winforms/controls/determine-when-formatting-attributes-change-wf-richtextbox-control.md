---
title: Determinare quando la formattazione degli attributi cambia nel controllo RichTextBoxDetermine When Formatting Attributes Change in RichTextBox Control
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
ms.openlocfilehash: a190c3479b58464763e0eefdd32d14e88a1f05e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142264"
---
# <a name="how-to-determine-when-formatting-attributes-change-in-the-windows-forms-richtextbox-control"></a>Procedura: individuare le modifiche degli attributi di formattazione nel controllo RichTextBox Windows Form
Un utilizzo comune del <xref:System.Windows.Forms.RichTextBox> controllo Windows Form è la formattazione del testo con attributi quali opzioni di carattere o stili di paragrafo. L'applicazione potrebbe essere necessario tenere traccia di eventuali modifiche nella formattazione del testo allo scopo di visualizzare una barra degli strumenti, come in molte applicazioni di elaborazione testi.  
  
### <a name="to-respond-to-changes-in-formatting-attributes"></a>Per rispondere alle modifiche apportate agli attributi di formattazione  
  
1. Scrivere il <xref:System.Windows.Forms.RichTextBox.SelectionChanged> codice nel gestore eventi per eseguire un'azione appropriata a seconda del valore dell'attributo. Nell'esempio seguente viene modificato l'aspetto di <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> un pulsante della barra degli strumenti in base al valore della proprietà . Il pulsante della barra degli strumenti verrà aggiornato solo quando il punto di inserimento viene spostato nel controllo.  
  
     Nell'esempio riportato di <xref:System.Windows.Forms.RichTextBox> seguito si <xref:System.Windows.Forms.ToolBar> presuppone che un form con un controllo e un controllo che contiene un pulsante della barra degli strumenti. Per ulteriori informazioni sulle barre degli strumenti e sui pulsanti della barra degli strumenti, vedere [Procedura: aggiungere pulsanti a un controllo ToolBar](how-to-add-buttons-to-a-toolbar-control.md).  
  
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
- [Controlli da utilizzare in Windows Form](controls-to-use-on-windows-forms.md)
