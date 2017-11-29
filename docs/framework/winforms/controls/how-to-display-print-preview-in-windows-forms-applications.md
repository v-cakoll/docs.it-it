---
title: 'Procedura: Visualizzare l''anteprima di stampa nelle applicazioni Windows Forms'
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
- print preview [Windows Forms], displaying
- printing [Windows Forms], print preview
- examples [Windows Forms], print preview
ms.assetid: e394134c-0886-4517-bd8d-edc4a3749eb5
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e705575b8c3acdcc3d92b985c59b60e7310dce7b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-print-preview-in-windows-forms-applications"></a>Procedura: Visualizzare l'anteprima di stampa nelle applicazioni Windows Forms
È possibile utilizzare il <xref:System.Windows.Forms.PrintPreviewDialog> controllo per consentire agli utenti di visualizzare un documento, spesso prima che sia per la stampa.  
  
 A tale scopo, è necessario specificare un'istanza di <xref:System.Drawing.Printing.PrintDocument> ; classe che rappresenta il documento da stampare. Per ulteriori informazioni sull'utilizzo dell'anteprima di stampa con i <xref:System.Drawing.Printing.PrintDocument> componente, vedere [procedura: stampare in Windows Form utilizzando anteprima di stampa](../../../../docs/framework/winforms/advanced/how-to-print-in-windows-forms-using-print-preview.md).  
  
> [!NOTE]
>  Utilizzare il <xref:System.Windows.Forms.PrintPreviewDialog> controllo in fase di esecuzione, gli utenti devono disporre una stampante installata sul proprio computer, localmente o tramite una rete, quale il modo in cui il <xref:System.Windows.Forms.PrintPreviewDialog> componente determina un documento così come verrà stampato.  
  
 Il <xref:System.Windows.Forms.PrintPreviewDialog> controlli utilizza la <xref:System.Drawing.Printing.PrinterSettings> classe. Inoltre, il <xref:System.Windows.Forms.PrintPreviewDialog> controlli utilizza il <xref:System.Drawing.Printing.PageSettings> (classe), come il <xref:System.Windows.Forms.PrintPreviewDialog> del componente. Il documento di stampato specificato nella <xref:System.Windows.Forms.PrintPreviewDialog> del controllo <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> proprietà fa riferimento alle istanze di entrambe le <xref:System.Drawing.Printing.PrinterSettings> e <xref:System.Drawing.Printing.PageSettings> classi e questi vengono utilizzati per il rendering del documento nella finestra di anteprima.  
  
### <a name="to-view-pages-using-the-printpreviewdialog-control"></a>Per visualizzare le pagine con il controllo PrintPreviewDialog  
  
-   Usare il metodo <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> per aprire la finestra di dialogo, specificando l'oggetto <xref:System.Drawing.Printing.PrintDocument> desiderato.  
  
     Nell'esempio di codice seguente, il <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Click> gestore eventi per aprire un'istanza del <xref:System.Windows.Forms.PrintPreviewDialog> controllo. Viene specificato il documento nel <xref:System.Windows.Forms.PrintDialog.Document%2A> proprietà. Nell'esempio seguente viene specificato alcun documento.  
  
     Nell'esempio si presuppone che il form contenga un <xref:System.Windows.Forms.Button> (controllo), un <xref:System.Drawing.Printing.PrintDocument> componente denominato `myDocument`e un <xref:System.Windows.Forms.PrintPreviewDialog> controllo.  
  
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
  
     ([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]e [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 [PrintDocument (componente)](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)  
 [Controllo PrintPreviewDialog](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 [Supporto per la stampa in Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)  
 [Windows Form](../../../../docs/framework/winforms/index.md)
