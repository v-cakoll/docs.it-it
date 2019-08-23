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
ms.openlocfilehash: 8252906de9a574f49617609a4cb08a1e8aa6a992
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929013"
---
# <a name="how-to-display-print-preview-in-windows-forms-applications"></a><span data-ttu-id="1be18-102">Procedura: Visualizzare l'anteprima di stampa nelle applicazioni Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1be18-102">How to: Display Print Preview in Windows Forms Applications</span></span>
<span data-ttu-id="1be18-103">È possibile utilizzare il <xref:System.Windows.Forms.PrintPreviewDialog> controllo per consentire agli utenti di visualizzare un documento, spesso prima che sia stampato.</span><span class="sxs-lookup"><span data-stu-id="1be18-103">You can use the <xref:System.Windows.Forms.PrintPreviewDialog> control to enable users to display a document, often before it is to be printed.</span></span>  
  
 <span data-ttu-id="1be18-104">A tale scopo, è necessario specificare un'istanza della <xref:System.Drawing.Printing.PrintDocument> classe. si tratta del documento da stampare.</span><span class="sxs-lookup"><span data-stu-id="1be18-104">To do this, you need to specify an instance of the <xref:System.Drawing.Printing.PrintDocument> class; this is the document to be printed.</span></span> <span data-ttu-id="1be18-105">Per ulteriori informazioni sull'utilizzo dell'anteprima di stampa <xref:System.Drawing.Printing.PrintDocument> con il componente [, vedere Procedura: Stampare in Windows Forms usando l'anteprima](../advanced/how-to-print-in-windows-forms-using-print-preview.md)di stampa.</span><span class="sxs-lookup"><span data-stu-id="1be18-105">For more information about using print preview with the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Print in Windows Forms Using Print Preview](../advanced/how-to-print-in-windows-forms-using-print-preview.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1be18-106">Per utilizzare il <xref:System.Windows.Forms.PrintPreviewDialog> controllo in fase di esecuzione, è necessario che gli utenti dispongano di una stampante installata sul proprio computer, localmente o tramite una rete, in <xref:System.Windows.Forms.PrintPreviewDialog> quanto si tratta in parte del modo in cui il componente determina il modo in cui un documento viene stampato.</span><span class="sxs-lookup"><span data-stu-id="1be18-106">To use the <xref:System.Windows.Forms.PrintPreviewDialog> control at run time, users must have a printer installed on their computer, either locally or through a network, as this is partly how the <xref:System.Windows.Forms.PrintPreviewDialog> component determines how a document will look when printed.</span></span>  
  
 <span data-ttu-id="1be18-107">Il <xref:System.Windows.Forms.PrintPreviewDialog> controllo Usa la <xref:System.Drawing.Printing.PrinterSettings> classe.</span><span class="sxs-lookup"><span data-stu-id="1be18-107">The <xref:System.Windows.Forms.PrintPreviewDialog> control uses the <xref:System.Drawing.Printing.PrinterSettings> class.</span></span> <span data-ttu-id="1be18-108">Inoltre, il <xref:System.Windows.Forms.PrintPreviewDialog> controllo Usa la <xref:System.Drawing.Printing.PageSettings> classe, proprio come il <xref:System.Windows.Forms.PrintPreviewDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="1be18-108">Additionally, the <xref:System.Windows.Forms.PrintPreviewDialog> control uses the <xref:System.Drawing.Printing.PageSettings> class, just as the <xref:System.Windows.Forms.PrintPreviewDialog> component does.</span></span> <span data-ttu-id="1be18-109">Il documento di stampa specificato nella <xref:System.Windows.Forms.PrintPreviewDialog> <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> proprietà del controllo si riferisce <xref:System.Drawing.Printing.PrinterSettings> alle istanze delle <xref:System.Drawing.Printing.PageSettings> classi e e vengono usate per eseguire il rendering del documento nella finestra di anteprima.</span><span class="sxs-lookup"><span data-stu-id="1be18-109">The print document specified in the <xref:System.Windows.Forms.PrintPreviewDialog> control's <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> property refers to instances of both the <xref:System.Drawing.Printing.PrinterSettings> and <xref:System.Drawing.Printing.PageSettings> classes, and these are used to render the document in the preview window.</span></span>  
  
### <a name="to-view-pages-using-the-printpreviewdialog-control"></a><span data-ttu-id="1be18-110">Per visualizzare le pagine utilizzando il controllo PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="1be18-110">To view pages using the PrintPreviewDialog control</span></span>  
  
- <span data-ttu-id="1be18-111">Usare il metodo <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> per aprire la finestra di dialogo, specificando l'oggetto <xref:System.Drawing.Printing.PrintDocument> desiderato.</span><span class="sxs-lookup"><span data-stu-id="1be18-111">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box, specifying the <xref:System.Drawing.Printing.PrintDocument> to use.</span></span>  
  
     <span data-ttu-id="1be18-112">Nell'esempio di codice seguente il <xref:System.Windows.Forms.Button> gestore <xref:System.Windows.Forms.Control.Click> eventi del controllo <xref:System.Windows.Forms.PrintPreviewDialog> apre un'istanza del controllo.</span><span class="sxs-lookup"><span data-stu-id="1be18-112">In the following code example, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens an instance of the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span> <span data-ttu-id="1be18-113">Il documento di stampa è specificato nella <xref:System.Windows.Forms.PrintDialog.Document%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="1be18-113">The print document is specified in the <xref:System.Windows.Forms.PrintDialog.Document%2A> property.</span></span> <span data-ttu-id="1be18-114">Nell'esempio seguente non viene specificato alcun documento di stampa.</span><span class="sxs-lookup"><span data-stu-id="1be18-114">In the example below, no print document is specified.</span></span>  
  
     <span data-ttu-id="1be18-115">Per l'esempio è necessario che il form <xref:System.Windows.Forms.Button> contenga un <xref:System.Drawing.Printing.PrintDocument> controllo, `myDocument`un componente denominato <xref:System.Windows.Forms.PrintPreviewDialog> e un controllo.</span><span class="sxs-lookup"><span data-stu-id="1be18-115">The example requires that your form has a <xref:System.Windows.Forms.Button> control, a <xref:System.Drawing.Printing.PrintDocument> component named `myDocument`, and a <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span>  
  
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
  
     <span data-ttu-id="1be18-116">(Visual C#, Visual C++) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="1be18-116">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1be18-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1be18-117">See also</span></span>

- [<span data-ttu-id="1be18-118">PrintDocument (componente)</span><span class="sxs-lookup"><span data-stu-id="1be18-118">PrintDocument Component</span></span>](printdocument-component-windows-forms.md)
- [<span data-ttu-id="1be18-119">Controllo PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="1be18-119">PrintPreviewDialog Control</span></span>](printpreviewdialog-control-windows-forms.md)
- [<span data-ttu-id="1be18-120">Supporto per la stampa in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1be18-120">Windows Forms Print Support</span></span>](../advanced/windows-forms-print-support.md)
- [<span data-ttu-id="1be18-121">Windows Form</span><span class="sxs-lookup"><span data-stu-id="1be18-121">Windows Forms</span></span>](../index.md)
