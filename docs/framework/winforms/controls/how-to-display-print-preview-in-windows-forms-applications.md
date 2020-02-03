---
title: Visualizza l'anteprima di stampa nelle app Windows Forms
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print preview [Windows Forms], displaying
- printing [Windows Forms], print preview
- examples [Windows Forms], print preview
ms.assetid: e394134c-0886-4517-bd8d-edc4a3749eb5
ms.openlocfilehash: ac02339ad86e491cd047dcd4b0c8841374b3bb2e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745578"
---
# <a name="how-to-display-print-preview-in-windows-forms-applications"></a>Procedura: Visualizzare l'anteprima di stampa nelle applicazioni di Windows Form
È possibile utilizzare il controllo <xref:System.Windows.Forms.PrintPreviewDialog> per consentire agli utenti di visualizzare un documento, spesso prima che sia stampato.  
  
 A tale scopo, è necessario specificare un'istanza della classe <xref:System.Drawing.Printing.PrintDocument>; si tratta del documento da stampare. Per altre informazioni sull'uso dell'anteprima di stampa con il componente <xref:System.Drawing.Printing.PrintDocument>, vedere [procedura: stampare in Windows Forms con l'anteprima di stampa](../advanced/how-to-print-in-windows-forms-using-print-preview.md).  
  
> [!NOTE]
> Per utilizzare il controllo <xref:System.Windows.Forms.PrintPreviewDialog> in fase di esecuzione, è necessario che gli utenti dispongano di una stampante installata sul proprio computer, localmente o tramite una rete, in quanto questo è il modo in cui il componente <xref:System.Windows.Forms.PrintPreviewDialog> determina la modalità di ricerca di un documento durante la stampa.  
  
 Il controllo <xref:System.Windows.Forms.PrintPreviewDialog> usa la classe <xref:System.Drawing.Printing.PrinterSettings>. Inoltre, il controllo <xref:System.Windows.Forms.PrintPreviewDialog> utilizza la classe <xref:System.Drawing.Printing.PageSettings>, proprio come il componente <xref:System.Windows.Forms.PrintPreviewDialog>. Il documento di stampa specificato nella proprietà <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> del controllo <xref:System.Windows.Forms.PrintPreviewDialog> si riferisce alle istanze delle classi <xref:System.Drawing.Printing.PrinterSettings> e <xref:System.Drawing.Printing.PageSettings> e vengono usate per eseguire il rendering del documento nella finestra di anteprima.  
  
### <a name="to-view-pages-using-the-printpreviewdialog-control"></a>Per visualizzare le pagine utilizzando il controllo PrintPreviewDialog  
  
- Usare il metodo <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> per aprire la finestra di dialogo, specificando l'oggetto <xref:System.Drawing.Printing.PrintDocument> desiderato.  
  
     Nell'esempio di codice seguente, il gestore dell'evento <xref:System.Windows.Forms.Control.Click> del controllo <xref:System.Windows.Forms.Button> apre un'istanza del controllo <xref:System.Windows.Forms.PrintPreviewDialog>. Il documento di stampa viene specificato nella proprietà <xref:System.Windows.Forms.PrintDialog.Document%2A>. Nell'esempio seguente non viene specificato alcun documento di stampa.  
  
     Per l'esempio è necessario che il form disponga di un controllo <xref:System.Windows.Forms.Button>, di un componente <xref:System.Drawing.Printing.PrintDocument> denominato `myDocument`e di un controllo <xref:System.Windows.Forms.PrintPreviewDialog>.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       ' The print document 'myDocument' used below  
       ' is merely for an example.  
       ' You will have to specify your own print document.  
       PrintPreviewDialog1.Document = myDocument  
       PrintPreviewDialog1.ShowDialog()  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       // The print document 'myDocument' used below  
       // is merely for an example.  
       // You will have to specify your own print document.  
       printPreviewDialog1.Document = myDocument;  
       printPreviewDialog1.ShowDialog();  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // The print document 'myDocument' used below  
          // is merely for an example.  
          // You will have to specify your own print document.  
          printPreviewDialog1->Document = myDocument;  
          printPreviewDialog1->ShowDialog();  
       }  
    ```  
  
     (Visual C#, Visual C++) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Componente PrintDocument](printdocument-component-windows-forms.md)
- [Controllo PrintPreviewDialog](printpreviewdialog-control-windows-forms.md)
- [Supporto per la stampa in Windows Forms](../advanced/windows-forms-print-support.md)
- [Windows Form](../index.md)
