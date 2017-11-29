---
title: 'Procedura: individuare le modifiche degli attributi di formattazione nel controllo RichTextBox Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0dc272e26124acf5c6bd5cf3030941c26c021c49
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-determine-when-formatting-attributes-change-in-the-windows-forms-richtextbox-control"></a>Procedura: individuare le modifiche degli attributi di formattazione nel controllo RichTextBox Windows Form
Un utilizzo comune di Windows Form <xref:System.Windows.Forms.RichTextBox> controllo formattazione del testo con attributi, ad esempio le opzioni di tipo di carattere o gli stili dei paragrafi. L'applicazione potrebbe essere necessario tenere traccia delle modifiche per la visualizzazione di una barra degli strumenti, come in molte applicazioni di elaborazione testi di formattazione del testo.  
  
### <a name="to-respond-to-changes-in-formatting-attributes"></a>Per rispondere alle modifiche degli attributi di formattazione  
  
1.  Scrivere codice nel <xref:System.Windows.Forms.RichTextBox.SelectionChanged> gestore eventi per eseguire un'azione appropriata a seconda del valore dell'attributo. Nell'esempio seguente viene modificato l'aspetto di un pulsante della barra degli strumenti in base al valore di <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> proprietà. Pulsante della barra degli strumenti verrà aggiornato solo quando il punto di inserimento verrà spostato nel controllo.  
  
     Nell'esempio seguente si presuppone un form con un <xref:System.Windows.Forms.RichTextBox> controllo e un <xref:System.Windows.Forms.ToolBar> controllo contenente un pulsante della barra degli strumenti. Per ulteriori informazioni sulle barre degli strumenti e i pulsanti della barra degli strumenti, vedere [procedura: aggiungere pulsanti a un controllo ToolBar](../../../../docs/framework/winforms/controls/how-to-add-buttons-to-a-toolbar-control.md).  
  
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
 <xref:System.Windows.Forms.RichTextBox.SelectionChanged>  
 <xref:System.Windows.Forms.RichTextBox>  
 [Controllo RichTextBox](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [Controlli da usare in Windows Form](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
