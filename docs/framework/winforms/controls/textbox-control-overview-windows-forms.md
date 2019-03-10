---
title: Cenni preliminari sul controllo TextBox (Windows Form)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- TextBox
helpviewer_keywords:
- TextBox control [Windows Forms], about TextBox controls
- text boxes [Windows Forms], adding
ms.assetid: d1a9c7f5-fa53-480a-a75c-158f8649ea2f
ms.openlocfilehash: 716195238e99938c8c416466fc84c2eff0bc7ba9
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709791"
---
# <a name="textbox-control-overview-windows-forms"></a>Cenni preliminari sul controllo TextBox (Windows Form)
Le caselle di testo di Windows Form vengono usate per ottenere l'input da parte dell'utente o per visualizzare il testo. Il <xref:System.Windows.Forms.TextBox> controllo viene generalmente utilizzato per il testo modificabile, anche se può essere reso anche sola lettura. Le caselle di testo possono visualizzare più righe, a capo automatico per le dimensioni del controllo e aggiungere la formattazione di base. Il <xref:System.Windows.Forms.TextBox> controllo fornisce un unico stile di formattazione per il testo visualizzato o inserito nel controllo. Per visualizzare più tipi di testo formattato, usare il <xref:System.Windows.Forms.RichTextBox> controllo. Per altre informazioni, vedere [Cenni preliminari sul controllo RichTextBox](richtextbox-control-overview-windows-forms.md).  
  
## <a name="working-with-the-textbox-control"></a>Utilizzo del controllo casella di testo  
 Il testo visualizzato dal controllo è contenuto nel <xref:System.Windows.Forms.TextBox.Text%2A> proprietà. Per impostazione predefinita, è possibile immettere fino a 2048 caratteri in una casella di testo. Se si impostano i <xref:System.Windows.Forms.TextBox.Multiline%2A> proprietà `true`, è possibile immettere fino a 32 KB del testo. Il <xref:System.Windows.Forms.TextBox.Text%2A> proprietà può essere impostata in fase di progettazione con la finestra Proprietà, in fase di esecuzione nel codice o tramite l'input dell'utente in fase di esecuzione. Il contenuto corrente di una casella di testo può essere recuperato in fase di esecuzione leggendo il <xref:System.Windows.Forms.TextBox.Text%2A> proprietà.  
  
 Esempio di codice seguente imposta il testo nel controllo in fase di esecuzione. Il `InitializeMyControl` procedure non verrà eseguiti automaticamente; deve essere chiamato.  
  
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
- <xref:System.Windows.Forms.TextBox>
- [Procedura: Controllare il punto di inserimento in un controllo TextBox di Windows Form](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Procedura: Creare una casella di testo Password con il controllo TextBox di Windows Form](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Procedura: Creare una casella di testo di sola lettura](how-to-create-a-read-only-text-box-windows-forms.md)
- [Procedura: Inserire virgolette in una stringa](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Procedura: Selezionare il testo nel controllo TextBox Windows Form](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Procedura: Visualizzare più righe nel controllo TextBox Windows Form](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [Controllo TextBox](textbox-control-windows-forms.md)
