---
title: 'Procedura: Visualizzare un elenco di tipi di carattere con il componente FontDialog'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- fonts [Windows Forms], showing list
- FontDialog component [Windows Forms]
- fonts [Windows Forms], attributes
- Font property [Windows Forms], setting with FontDialog component
- Font dialog box [Windows Forms], displaying
- fonts [Windows Forms], selecting
ms.assetid: 35692c1b-0937-4b7a-9207-1ae6bdc244a0
ms.openlocfilehash: 40679136ea62a437009b308a8b206cf251b46222
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012984"
---
# <a name="how-to-show-a-font-list-with-the-fontdialog-component"></a>Procedura: Visualizzare un elenco di tipi di carattere con il componente FontDialog
Il [FontDialog](fontdialog-component-windows-forms.md) componente consente agli utenti di selezionare un tipo di carattere, nonché modificarne la visualizzazione, ad esempio il peso e dimensioni.  
  
 Il tipo di carattere selezionato nella finestra di dialogo viene restituito nel <xref:System.Windows.Forms.FontDialog.Font%2A> proprietà. Pertanto, sfruttando i vantaggi del tipo di carattere selezionato dall'utente è semplice quanto la lettura di una proprietà.  
  
### <a name="to-select-font-properties-using-the-fontdialog-component"></a>Selezionare le proprietà del tipo di carattere utilizzando il componente FontDialog  
  
1. Visualizzare la finestra di dialogo tramite il <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> (metodo).  
  
2. Usare il <xref:System.Windows.Forms.DialogResult> proprietà per determinare come è stata chiusa la finestra di dialogo.  
  
3. Usare il <xref:System.Windows.Forms.FontDialog.Font%2A> proprietà da impostare il tipo di carattere desiderato.  
  
     Nell'esempio seguente, il <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Click> gestore eventi apre un <xref:System.Windows.Forms.FontDialog> componente. Quando un tipo di carattere è selezionata e l'utente sceglie **OK**, il <xref:System.Windows.Forms.FontDialog.Font%2A> proprietà di un <xref:System.Windows.Forms.TextBox> controllo nel form è impostato per il tipo di carattere selezionato. L'esempio presuppone che il form contenga un <xref:System.Windows.Forms.Button> (controllo), una <xref:System.Windows.Forms.TextBox> (controllo) e un <xref:System.Windows.Forms.FontDialog> componente.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       If FontDialog1.ShowDialog() = DialogResult.OK Then  
          TextBox1.Font = FontDialog1.Font  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(fontDialog1.ShowDialog() == DialogResult.OK)  
       {  
          textBox1.Font = fontDialog1.Font;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if(fontDialog1->ShowDialog() == DialogResult::OK)  
          {  
             textBox1->Font = fontDialog1->Font;  
          }  
       }  
    ```  
  
     (Visual c# e [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) inserire il codice seguente nel costruttore del form per registrare il gestore dell'evento.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.FontDialog>
- [Componente FontDialog](fontdialog-component-windows-forms.md)
