---
title: "Procedura: Visualizzare l'anteprima di stampa nelle applicazioni Windows Forms"
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
ms.openlocfilehash: cfdc8d21b3ddad19fd38eef9cb1c506920da9de6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64609890"
---
# <a name="how-to-display-print-preview-in-windows-forms-applications"></a>Procedura: Visualizzare l'anteprima di stampa nelle applicazioni Windows Forms
È possibile usare il <xref:System.Windows.Forms.PrintPreviewDialog> controllo per consentire agli utenti di visualizzare un documento, spesso prima che venga da stampare.  
  
 A tale scopo, è necessario specificare un'istanza di <xref:System.Drawing.Printing.PrintDocument> classe; questo è il documento da stampare. Per altre informazioni sull'uso dell'anteprima di stampa con il <xref:System.Drawing.Printing.PrintDocument> componente, vedere [come: Stampa in Windows Form tramite l'anteprima di stampa](../advanced/how-to-print-in-windows-forms-using-print-preview.md).  
  
> [!NOTE]
>  Usare la <xref:System.Windows.Forms.PrintPreviewDialog> controllo in fase di esecuzione, gli utenti devono avere una stampante installata sul proprio computer, localmente o tramite la rete, in parte il <xref:System.Windows.Forms.PrintPreviewDialog> componente determina l'aspetto del documento stampato.  
  
 Il <xref:System.Windows.Forms.PrintPreviewDialog> controlli utilizza il <xref:System.Drawing.Printing.PrinterSettings> classe. Inoltre, il <xref:System.Windows.Forms.PrintPreviewDialog> controlli utilizza il <xref:System.Drawing.Printing.PageSettings> (classe), proprio come il <xref:System.Windows.Forms.PrintPreviewDialog> del componente. Il documento di stampa specificato nella <xref:System.Windows.Forms.PrintPreviewDialog> del controllo <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> proprietà fa riferimento alle istanze di entrambe le <xref:System.Drawing.Printing.PrinterSettings> e <xref:System.Drawing.Printing.PageSettings> classi e questi vengono utilizzati per il rendering del documento nella finestra di anteprima.  
  
### <a name="to-view-pages-using-the-printpreviewdialog-control"></a>Per visualizzare le pagine usando il controllo PrintPreviewDialog  
  
- Usare il metodo <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> per aprire la finestra di dialogo, specificando l'oggetto <xref:System.Drawing.Printing.PrintDocument> desiderato.  
  
     Nell'esempio di codice seguente, il <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Click> gestore eventi apre un'istanza del <xref:System.Windows.Forms.PrintPreviewDialog> controllo. Il documento di stampa viene specificato nel <xref:System.Windows.Forms.PrintDialog.Document%2A> proprietà. Nell'esempio seguente viene specificato alcun documento.  
  
     Nell'esempio si presuppone che il form contenga un <xref:System.Windows.Forms.Button> (controllo), una <xref:System.Drawing.Printing.PrintDocument> componente denominato `myDocument`e un <xref:System.Windows.Forms.PrintPreviewDialog> controllo.  
  
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
  
     (Visual c#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) inserire il codice seguente nel costruttore del form per registrare il gestore dell'evento.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [PrintDocument (componente)](printdocument-component-windows-forms.md)
- [Controllo PrintPreviewDialog](printpreviewdialog-control-windows-forms.md)
- [Supporto per la stampa in Windows Forms](../advanced/windows-forms-print-support.md)
- [Windows Form](../index.md)
