---
title: Cenni preliminari sul controllo TextBox (Windows Form)
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
f1_keywords: TextBox
helpviewer_keywords:
- TextBox control [Windows Forms], about TextBox controls
- text boxes [Windows Forms], adding
ms.assetid: d1a9c7f5-fa53-480a-a75c-158f8649ea2f
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e8c75392f12b87c7495b1fcdf5419f2463067161
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="textbox-control-overview-windows-forms"></a>Cenni preliminari sul controllo TextBox (Windows Form)
Caselle di testo di Windows Form vengono utilizzate per ottenere l'input dell'utente o per visualizzare il testo. Il <xref:System.Windows.Forms.TextBox> controllo viene in genere utilizzato per il testo modificabile, anche se può inoltre essere resa di sola lettura. Caselle di testo possono visualizzare più righe, a capo automatico per le dimensioni del controllo e aggiungere la formattazione di base. Il <xref:System.Windows.Forms.TextBox> controllo fornisce un unico stile di formattazione per il testo visualizzato o immesso nel controllo. Per visualizzare più tipi di testo formattato, utilizzare il <xref:System.Windows.Forms.RichTextBox> controllo. Per ulteriori informazioni, vedere [Cenni preliminari sul controllo RichTextBox](../../../../docs/framework/winforms/controls/richtextbox-control-overview-windows-forms.md).  
  
## <a name="working-with-the-textbox-control"></a>Utilizzo del controllo casella di testo  
 Cui è contenuto il testo visualizzato dal controllo di <xref:System.Windows.Forms.TextBox.Text%2A> proprietà. Per impostazione predefinita, è possibile immettere un massimo di 2048 caratteri in una casella di testo. Se si imposta la <xref:System.Windows.Forms.TextBox.Multiline%2A> proprietà `true`, è possibile immettere un massimo di 32 KB di testo. Il <xref:System.Windows.Forms.TextBox.Text%2A> proprietà può essere impostata in fase di progettazione nella finestra Proprietà, in fase di esecuzione nel codice o tramite l'input dell'utente in fase di esecuzione. Il contenuto corrente di una casella di testo può essere recuperato in fase di esecuzione leggendo il <xref:System.Windows.Forms.TextBox.Text%2A> proprietà.  
  
 Esempio di codice seguente imposta il testo nel controllo in fase di esecuzione. Il `InitializeMyControl` procedura non verrà eseguito automaticamente; deve essere chiamato.  
  
```vb  
Private Sub InitializeMyControl()  
   ' Put some text into the control first.  
   TextBox1.Text = "This is a TextBox control."  
End Sub  
```  
  
```csharp  
private void InitializeMyControl() {  
   // Put some text into the control first.  
   textBox1.Text = "This is a TextBox control.";  
}  
```  
  
```cpp  
private:  
   void InitializeMyControl()  
   {  
      // Put some text into the control first.  
      textBox1->Text = "This is a TextBox control.";  
   }  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.TextBox>  
 [Procedura: Controllare il punto di inserimento in un controllo TextBox di Windows Form](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [Procedura: Creare una casella di testo Password con il controllo TextBox di Windows Form](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [Procedura: Creare una casella di testo in sola lettura](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [Procedura: Inserire virgolette in una stringa](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [Procedura: Selezionare testo nel controllo TextBox di Windows Form](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [Procedura: Visualizzare più righe nel controllo TextBox di Windows Form](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [Controllo TextBox](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
