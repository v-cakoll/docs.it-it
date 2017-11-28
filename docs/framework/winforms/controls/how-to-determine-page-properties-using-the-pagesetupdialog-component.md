---
title: "Procedura: definire le proprietà della pagina con il componente PageSetupDialog"
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
- page properties
- page setup
- PageSetupDialog component
ms.assetid: 6dae05bc-c0fd-4357-bb93-841a1631d98f
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e7dc3603d37106c122f3e92503b37dcfc02d7fef
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-determine-page-properties-using-the-pagesetupdialog-component"></a><span data-ttu-id="23d6b-102">Procedura: definire le proprietà della pagina con il componente PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="23d6b-102">How to: Determine Page Properties Using the PageSetupDialog Component</span></span>
<span data-ttu-id="23d6b-103">Il componente [PageSetupDialog](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) presenta layout, dimensioni del foglio e altre opzioni relative al layout di pagina per un documento.</span><span class="sxs-lookup"><span data-stu-id="23d6b-103">The [PageSetupDialog](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) component presents layout, paper size, and other page layout choices to the user for a document.</span></span>  
  
 <span data-ttu-id="23d6b-104">È necessario specificare un'istanza della classe <xref:System.Drawing.Printing.PrintDocument> , che rappresenta il documento da stampare.</span><span class="sxs-lookup"><span data-stu-id="23d6b-104">You need to specify an instance of the <xref:System.Drawing.Printing.PrintDocument> class—this is the document to be printed.</span></span> <span data-ttu-id="23d6b-105">È inoltre necessario che sul computer dell'utente sia installata una stampante, locale o di rete, tramite la quale il componente <xref:System.Windows.Forms.PageSetupDialog> determina in parte le scelte di formattazione della pagina presentate all'utente.</span><span class="sxs-lookup"><span data-stu-id="23d6b-105">Additionally, users must have a printer installed on their computer, either locally or through a network, as this is partly how the <xref:System.Windows.Forms.PageSetupDialog> component determines the page formatting choices presented to the user.</span></span>  
  
 <span data-ttu-id="23d6b-106">Un aspetto importante dell'uso del componente <xref:System.Windows.Forms.PageSetupDialog> è dato dalla modalità di interazione con la classe <xref:System.Drawing.Printing.PageSettings> .</span><span class="sxs-lookup"><span data-stu-id="23d6b-106">An important aspect of working with the <xref:System.Windows.Forms.PageSetupDialog> component is how it interacts with the <xref:System.Drawing.Printing.PageSettings> class.</span></span> <span data-ttu-id="23d6b-107">La classe <xref:System.Drawing.Printing.PageSettings> viene usata per specificare le impostazioni che modificano la modalità di stampa di una pagina, come l'orientamento, le dimensioni e i margini.</span><span class="sxs-lookup"><span data-stu-id="23d6b-107">The <xref:System.Drawing.Printing.PageSettings> class is used to specify settings that modify the way a page will be printed, such as paper orientation, the size of the page, and the margins.</span></span> <span data-ttu-id="23d6b-108">Ciascuna di queste impostazioni è rappresentata come una proprietà della classe <xref:System.Drawing.Printing.PageSettings> .</span><span class="sxs-lookup"><span data-stu-id="23d6b-108">Each of these settings is represented as a property of the <xref:System.Drawing.Printing.PageSettings> class.</span></span> <span data-ttu-id="23d6b-109">La classe <xref:System.Windows.Forms.PageSetupDialog> modifica i valori delle proprietà per una determinata istanza della classe <xref:System.Drawing.Printing.PageSettings> , che è associata al documento ed è rappresentata come proprietà <xref:System.Drawing.Printing.PrintDocument.DefaultPageSettings%2A> .</span><span class="sxs-lookup"><span data-stu-id="23d6b-109">The <xref:System.Windows.Forms.PageSetupDialog> class modifies these property values for a given instance of the <xref:System.Drawing.Printing.PageSettings> class that is associated with the document (and is represented as a <xref:System.Drawing.Printing.PrintDocument.DefaultPageSettings%2A> property).</span></span>  
  
### <a name="to-set-page-properties-using-the-pagesetupdialog-component"></a><span data-ttu-id="23d6b-110">Per impostare le proprietà della pagina mediante il componente PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="23d6b-110">To set page properties using the PageSetupDialog component</span></span>  
  
1.  <span data-ttu-id="23d6b-111">Usare il metodo <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> per aprire la finestra di dialogo, specificando l'oggetto <xref:System.Drawing.Printing.PrintDocument> desiderato.</span><span class="sxs-lookup"><span data-stu-id="23d6b-111">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box, specifying the <xref:System.Drawing.Printing.PrintDocument> to use.</span></span>  
  
     <span data-ttu-id="23d6b-112">Nell'esempio seguente il gestore eventi <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Click> apre un'istanza del componente <xref:System.Windows.Forms.PageSetupDialog> .</span><span class="sxs-lookup"><span data-stu-id="23d6b-112">In the example below, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens an instance of the <xref:System.Windows.Forms.PageSetupDialog> component.</span></span> <span data-ttu-id="23d6b-113">Un documento esistente è specificato nella proprietà <xref:System.Windows.Forms.PageSetupDialog.Document%2A> e la relativa proprietà <xref:System.Drawing.Printing.PageSettings.Color%2A?displayProperty=nameWithType> è impostata su `false`.</span><span class="sxs-lookup"><span data-stu-id="23d6b-113">An existing document is specified in the <xref:System.Windows.Forms.PageSetupDialog.Document%2A> property, and its <xref:System.Drawing.Printing.PageSettings.Color%2A?displayProperty=nameWithType> property is set to `false`.</span></span>  
  
     <span data-ttu-id="23d6b-114">Nell'esempio si presuppone il modulo contiene un <xref:System.Windows.Forms.Button> (controllo), un <xref:System.Drawing.Printing.PrintDocument> componente denominato `myDocument`e un <xref:System.Windows.Forms.PageSetupDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="23d6b-114">The example assumes your form has a <xref:System.Windows.Forms.Button> control, a <xref:System.Drawing.Printing.PrintDocument> component named `myDocument`, and a <xref:System.Windows.Forms.PageSetupDialog> component.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles Button1.Click  
       ' The print document 'myDocument' used below  
       ' is merely for an example.  
       'You will have to specify your own print document.  
       PageSetupDialog1.Document = myDocument  
       ' Sets the print document's color setting to false,  
       ' so that the page will not be printed in color.  
       PageSetupDialog1.Document.DefaultPageSettings.Color = False  
       PageSetupDialog1.ShowDialog()  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       // The print document 'myDocument' used below  
       // is merely for an example.  
       // You will have to specify your own print document.  
       pageSetupDialog1.Document = myDocument;  
       // Sets the print document's color setting to false,  
       // so that the page will not be printed in color.  
       pageSetupDialog1.Document.DefaultPageSettings.Color = false;  
       pageSetupDialog1.ShowDialog();  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void button1_Click(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          // The print document 'myDocument' used below  
          // is merely for an example.  
          // You will have to specify your own print document.  
          pageSetupDialog1->Document = myDocument;  
          // Sets the print document's color setting to false,  
          // so that the page will not be printed in color.  
          pageSetupDialog1->Document->DefaultPageSettings->Color = false;  
          pageSetupDialog1->ShowDialog();  
       }  
    ```  
  
     <span data-ttu-id="23d6b-115">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] e [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="23d6b-115">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew   
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="23d6b-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23d6b-116">See Also</span></span>  
 <xref:System.Windows.Forms.PageSetupDialog>  
 [<span data-ttu-id="23d6b-117">Procedura: Creare processi di stampa standard per Windows Form</span><span class="sxs-lookup"><span data-stu-id="23d6b-117">How to: Create Standard Windows Forms Print Jobs</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)  
 [<span data-ttu-id="23d6b-118">Componente PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="23d6b-118">PageSetupDialog Component</span></span>](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md)
