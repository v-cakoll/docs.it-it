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
ms.openlocfilehash: 22247c941eff575f0f3e5683e46376054ba13bb5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013414"
---
# <a name="how-to-display-print-preview-in-windows-forms-applications"></a><span data-ttu-id="35158-102">Procedura: Visualizzare l'anteprima di stampa nelle applicazioni Windows Forms</span><span class="sxs-lookup"><span data-stu-id="35158-102">How to: Display Print Preview in Windows Forms Applications</span></span>
<span data-ttu-id="35158-103">È possibile usare il <xref:System.Windows.Forms.PrintPreviewDialog> controllo per consentire agli utenti di visualizzare un documento, spesso prima che venga da stampare.</span><span class="sxs-lookup"><span data-stu-id="35158-103">You can use the <xref:System.Windows.Forms.PrintPreviewDialog> control to enable users to display a document, often before it is to be printed.</span></span>  
  
 <span data-ttu-id="35158-104">A tale scopo, è necessario specificare un'istanza di <xref:System.Drawing.Printing.PrintDocument> classe; questo è il documento da stampare.</span><span class="sxs-lookup"><span data-stu-id="35158-104">To do this, you need to specify an instance of the <xref:System.Drawing.Printing.PrintDocument> class; this is the document to be printed.</span></span> <span data-ttu-id="35158-105">Per altre informazioni sull'uso dell'anteprima di stampa con il <xref:System.Drawing.Printing.PrintDocument> componente, vedere [come: Stampa in Windows Form tramite l'anteprima di stampa](../advanced/how-to-print-in-windows-forms-using-print-preview.md).</span><span class="sxs-lookup"><span data-stu-id="35158-105">For more information about using print preview with the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Print in Windows Forms Using Print Preview](../advanced/how-to-print-in-windows-forms-using-print-preview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="35158-106">Usare la <xref:System.Windows.Forms.PrintPreviewDialog> controllo in fase di esecuzione, gli utenti devono avere una stampante installata sul proprio computer, localmente o tramite la rete, in parte il <xref:System.Windows.Forms.PrintPreviewDialog> componente determina l'aspetto del documento stampato.</span><span class="sxs-lookup"><span data-stu-id="35158-106">To use the <xref:System.Windows.Forms.PrintPreviewDialog> control at run time, users must have a printer installed on their computer, either locally or through a network, as this is partly how the <xref:System.Windows.Forms.PrintPreviewDialog> component determines how a document will look when printed.</span></span>  
  
 <span data-ttu-id="35158-107">Il <xref:System.Windows.Forms.PrintPreviewDialog> controlli utilizza il <xref:System.Drawing.Printing.PrinterSettings> classe.</span><span class="sxs-lookup"><span data-stu-id="35158-107">The <xref:System.Windows.Forms.PrintPreviewDialog> control uses the <xref:System.Drawing.Printing.PrinterSettings> class.</span></span> <span data-ttu-id="35158-108">Inoltre, il <xref:System.Windows.Forms.PrintPreviewDialog> controlli utilizza il <xref:System.Drawing.Printing.PageSettings> (classe), proprio come il <xref:System.Windows.Forms.PrintPreviewDialog> del componente.</span><span class="sxs-lookup"><span data-stu-id="35158-108">Additionally, the <xref:System.Windows.Forms.PrintPreviewDialog> control uses the <xref:System.Drawing.Printing.PageSettings> class, just as the <xref:System.Windows.Forms.PrintPreviewDialog> component does.</span></span> <span data-ttu-id="35158-109">Il documento di stampa specificato nella <xref:System.Windows.Forms.PrintPreviewDialog> del controllo <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> proprietà fa riferimento alle istanze di entrambe le <xref:System.Drawing.Printing.PrinterSettings> e <xref:System.Drawing.Printing.PageSettings> classi e questi vengono utilizzati per il rendering del documento nella finestra di anteprima.</span><span class="sxs-lookup"><span data-stu-id="35158-109">The print document specified in the <xref:System.Windows.Forms.PrintPreviewDialog> control's <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> property refers to instances of both the <xref:System.Drawing.Printing.PrinterSettings> and <xref:System.Drawing.Printing.PageSettings> classes, and these are used to render the document in the preview window.</span></span>  
  
### <a name="to-view-pages-using-the-printpreviewdialog-control"></a><span data-ttu-id="35158-110">Per visualizzare le pagine usando il controllo PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="35158-110">To view pages using the PrintPreviewDialog control</span></span>  
  
- <span data-ttu-id="35158-111">Usare il metodo <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> per aprire la finestra di dialogo, specificando l'oggetto <xref:System.Drawing.Printing.PrintDocument> desiderato.</span><span class="sxs-lookup"><span data-stu-id="35158-111">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box, specifying the <xref:System.Drawing.Printing.PrintDocument> to use.</span></span>  
  
     <span data-ttu-id="35158-112">Nell'esempio di codice seguente, il <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Click> gestore eventi apre un'istanza del <xref:System.Windows.Forms.PrintPreviewDialog> controllo.</span><span class="sxs-lookup"><span data-stu-id="35158-112">In the following code example, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens an instance of the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span> <span data-ttu-id="35158-113">Il documento di stampa viene specificato nel <xref:System.Windows.Forms.PrintDialog.Document%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="35158-113">The print document is specified in the <xref:System.Windows.Forms.PrintDialog.Document%2A> property.</span></span> <span data-ttu-id="35158-114">Nell'esempio seguente viene specificato alcun documento.</span><span class="sxs-lookup"><span data-stu-id="35158-114">In the example below, no print document is specified.</span></span>  
  
     <span data-ttu-id="35158-115">Nell'esempio si presuppone che il form contenga un <xref:System.Windows.Forms.Button> (controllo), una <xref:System.Drawing.Printing.PrintDocument> componente denominato `myDocument`e un <xref:System.Windows.Forms.PrintPreviewDialog> controllo.</span><span class="sxs-lookup"><span data-stu-id="35158-115">The example requires that your form has a <xref:System.Windows.Forms.Button> control, a <xref:System.Drawing.Printing.PrintDocument> component named `myDocument`, and a <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span>  
  
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
  
     <span data-ttu-id="35158-116">(Visual c#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) inserire il codice seguente nel costruttore del form per registrare il gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="35158-116">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="35158-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35158-117">See also</span></span>

- [<span data-ttu-id="35158-118">PrintDocument (componente)</span><span class="sxs-lookup"><span data-stu-id="35158-118">PrintDocument Component</span></span>](printdocument-component-windows-forms.md)
- [<span data-ttu-id="35158-119">Controllo PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="35158-119">PrintPreviewDialog Control</span></span>](printpreviewdialog-control-windows-forms.md)
- [<span data-ttu-id="35158-120">Supporto per la stampa in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="35158-120">Windows Forms Print Support</span></span>](../advanced/windows-forms-print-support.md)
- [<span data-ttu-id="35158-121">Windows Form</span><span class="sxs-lookup"><span data-stu-id="35158-121">Windows Forms</span></span>](../index.md)
