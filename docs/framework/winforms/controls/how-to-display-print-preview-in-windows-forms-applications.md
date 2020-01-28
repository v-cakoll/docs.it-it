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
# <a name="how-to-display-print-preview-in-windows-forms-applications"></a><span data-ttu-id="bd8f3-102">Procedura: Visualizzare l'anteprima di stampa nelle applicazioni di Windows Form</span><span class="sxs-lookup"><span data-stu-id="bd8f3-102">How to: Display Print Preview in Windows Forms Applications</span></span>
<span data-ttu-id="bd8f3-103">È possibile utilizzare il controllo <xref:System.Windows.Forms.PrintPreviewDialog> per consentire agli utenti di visualizzare un documento, spesso prima che sia stampato.</span><span class="sxs-lookup"><span data-stu-id="bd8f3-103">You can use the <xref:System.Windows.Forms.PrintPreviewDialog> control to enable users to display a document, often before it is to be printed.</span></span>  
  
 <span data-ttu-id="bd8f3-104">A tale scopo, è necessario specificare un'istanza della classe <xref:System.Drawing.Printing.PrintDocument>; si tratta del documento da stampare.</span><span class="sxs-lookup"><span data-stu-id="bd8f3-104">To do this, you need to specify an instance of the <xref:System.Drawing.Printing.PrintDocument> class; this is the document to be printed.</span></span> <span data-ttu-id="bd8f3-105">Per altre informazioni sull'uso dell'anteprima di stampa con il componente <xref:System.Drawing.Printing.PrintDocument>, vedere [procedura: stampare in Windows Forms con l'anteprima di stampa](../advanced/how-to-print-in-windows-forms-using-print-preview.md).</span><span class="sxs-lookup"><span data-stu-id="bd8f3-105">For more information about using print preview with the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Print in Windows Forms Using Print Preview](../advanced/how-to-print-in-windows-forms-using-print-preview.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bd8f3-106">Per utilizzare il controllo <xref:System.Windows.Forms.PrintPreviewDialog> in fase di esecuzione, è necessario che gli utenti dispongano di una stampante installata sul proprio computer, localmente o tramite una rete, in quanto questo è il modo in cui il componente <xref:System.Windows.Forms.PrintPreviewDialog> determina la modalità di ricerca di un documento durante la stampa.</span><span class="sxs-lookup"><span data-stu-id="bd8f3-106">To use the <xref:System.Windows.Forms.PrintPreviewDialog> control at run time, users must have a printer installed on their computer, either locally or through a network, as this is partly how the <xref:System.Windows.Forms.PrintPreviewDialog> component determines how a document will look when printed.</span></span>  
  
 <span data-ttu-id="bd8f3-107">Il controllo <xref:System.Windows.Forms.PrintPreviewDialog> usa la classe <xref:System.Drawing.Printing.PrinterSettings>.</span><span class="sxs-lookup"><span data-stu-id="bd8f3-107">The <xref:System.Windows.Forms.PrintPreviewDialog> control uses the <xref:System.Drawing.Printing.PrinterSettings> class.</span></span> <span data-ttu-id="bd8f3-108">Inoltre, il controllo <xref:System.Windows.Forms.PrintPreviewDialog> utilizza la classe <xref:System.Drawing.Printing.PageSettings>, proprio come il componente <xref:System.Windows.Forms.PrintPreviewDialog>.</span><span class="sxs-lookup"><span data-stu-id="bd8f3-108">Additionally, the <xref:System.Windows.Forms.PrintPreviewDialog> control uses the <xref:System.Drawing.Printing.PageSettings> class, just as the <xref:System.Windows.Forms.PrintPreviewDialog> component does.</span></span> <span data-ttu-id="bd8f3-109">Il documento di stampa specificato nella proprietà <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> del controllo <xref:System.Windows.Forms.PrintPreviewDialog> si riferisce alle istanze delle classi <xref:System.Drawing.Printing.PrinterSettings> e <xref:System.Drawing.Printing.PageSettings> e vengono usate per eseguire il rendering del documento nella finestra di anteprima.</span><span class="sxs-lookup"><span data-stu-id="bd8f3-109">The print document specified in the <xref:System.Windows.Forms.PrintPreviewDialog> control's <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> property refers to instances of both the <xref:System.Drawing.Printing.PrinterSettings> and <xref:System.Drawing.Printing.PageSettings> classes, and these are used to render the document in the preview window.</span></span>  
  
### <a name="to-view-pages-using-the-printpreviewdialog-control"></a><span data-ttu-id="bd8f3-110">Per visualizzare le pagine utilizzando il controllo PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="bd8f3-110">To view pages using the PrintPreviewDialog control</span></span>  
  
- <span data-ttu-id="bd8f3-111">Usare il metodo <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> per aprire la finestra di dialogo, specificando l'oggetto <xref:System.Drawing.Printing.PrintDocument> desiderato.</span><span class="sxs-lookup"><span data-stu-id="bd8f3-111">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box, specifying the <xref:System.Drawing.Printing.PrintDocument> to use.</span></span>  
  
     <span data-ttu-id="bd8f3-112">Nell'esempio di codice seguente, il gestore dell'evento <xref:System.Windows.Forms.Control.Click> del controllo <xref:System.Windows.Forms.Button> apre un'istanza del controllo <xref:System.Windows.Forms.PrintPreviewDialog>.</span><span class="sxs-lookup"><span data-stu-id="bd8f3-112">In the following code example, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens an instance of the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span> <span data-ttu-id="bd8f3-113">Il documento di stampa viene specificato nella proprietà <xref:System.Windows.Forms.PrintDialog.Document%2A>.</span><span class="sxs-lookup"><span data-stu-id="bd8f3-113">The print document is specified in the <xref:System.Windows.Forms.PrintDialog.Document%2A> property.</span></span> <span data-ttu-id="bd8f3-114">Nell'esempio seguente non viene specificato alcun documento di stampa.</span><span class="sxs-lookup"><span data-stu-id="bd8f3-114">In the example below, no print document is specified.</span></span>  
  
     <span data-ttu-id="bd8f3-115">Per l'esempio è necessario che il form disponga di un controllo <xref:System.Windows.Forms.Button>, di un componente <xref:System.Drawing.Printing.PrintDocument> denominato `myDocument`e di un controllo <xref:System.Windows.Forms.PrintPreviewDialog>.</span><span class="sxs-lookup"><span data-stu-id="bd8f3-115">The example requires that your form has a <xref:System.Windows.Forms.Button> control, a <xref:System.Drawing.Printing.PrintDocument> component named `myDocument`, and a <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span>  
  
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
  
     <span data-ttu-id="bd8f3-116">(Visual C#, Visual C++) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="bd8f3-116">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="bd8f3-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd8f3-117">See also</span></span>

- [<span data-ttu-id="bd8f3-118">PrintDocument (componente)</span><span class="sxs-lookup"><span data-stu-id="bd8f3-118">PrintDocument Component</span></span>](printdocument-component-windows-forms.md)
- [<span data-ttu-id="bd8f3-119">Controllo PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="bd8f3-119">PrintPreviewDialog Control</span></span>](printpreviewdialog-control-windows-forms.md)
- [<span data-ttu-id="bd8f3-120">Supporto per la stampa in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bd8f3-120">Windows Forms Print Support</span></span>](../advanced/windows-forms-print-support.md)
- [<span data-ttu-id="bd8f3-121">Windows Form</span><span class="sxs-lookup"><span data-stu-id="bd8f3-121">Windows Forms</span></span>](../index.md)
