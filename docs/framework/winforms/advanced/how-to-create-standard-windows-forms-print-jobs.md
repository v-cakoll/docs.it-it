---
title: Creazione di processi di stampa standard
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- printing [Windows Forms]
- printing [Windows Forms], creating print jobs
- printing [Visual Basic], in Windows applications
ms.assetid: 03342b90-9cfe-40b2-838b-b479a13c5dea
ms.openlocfilehash: d9607de7c74132e0d7dce605b16d62c79b7dbccb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182573"
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a><span data-ttu-id="f6271-102">Procedura: creare processi di stampa standard per Windows Form</span><span class="sxs-lookup"><span data-stu-id="f6271-102">How to: Create Standard Windows Forms Print Jobs</span></span>
<span data-ttu-id="f6271-103">La base della stampa in <xref:System.Drawing.Printing.PrintDocument> Windows Form è <xref:System.Drawing.Printing.PrintDocument.PrintPage> il componente, più specificamente, l'evento.</span><span class="sxs-lookup"><span data-stu-id="f6271-103">The foundation of printing in Windows Forms is the <xref:System.Drawing.Printing.PrintDocument> component—more specifically, the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span> <span data-ttu-id="f6271-104">Scrivendo il codice <xref:System.Drawing.Printing.PrintDocument.PrintPage> per gestire l'evento, è possibile specificare cosa stampare e come stamparlo.</span><span class="sxs-lookup"><span data-stu-id="f6271-104">By writing code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event, you can specify what to print and how to print it.</span></span>  
  
### <a name="to-create-a-print-job"></a><span data-ttu-id="f6271-105">Per creare un processo di stampa</span><span class="sxs-lookup"><span data-stu-id="f6271-105">To create a print job</span></span>  
  
1. <span data-ttu-id="f6271-106">Aggiungere <xref:System.Drawing.Printing.PrintDocument> un componente al form.</span><span class="sxs-lookup"><span data-stu-id="f6271-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2. <span data-ttu-id="f6271-107">Scrivere codice per gestire l'evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> .</span><span class="sxs-lookup"><span data-stu-id="f6271-107">Write code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>  
  
     <span data-ttu-id="f6271-108">Dovrai codificare la tua logica di stampa.</span><span class="sxs-lookup"><span data-stu-id="f6271-108">You will have to code your own printing logic.</span></span> <span data-ttu-id="f6271-109">Inoltre, è necessario specificare il materiale da stampare.</span><span class="sxs-lookup"><span data-stu-id="f6271-109">Additionally, you will have to specify the material to be printed.</span></span>  
  
     <span data-ttu-id="f6271-110">Nell'esempio di codice seguente, nel gestore eventi viene <xref:System.Drawing.Printing.PrintDocument.PrintPage> creato un elemento grafico di esempio a forma di rettangolo rosso per fungere da materiale da stampare.</span><span class="sxs-lookup"><span data-stu-id="f6271-110">In the following code example, a sample graphic in the shape of a red rectangle is created in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler to act as material to be printed.</span></span>  
  
    ```vb  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillRectangle(Brushes.Red, New Rectangle(500, 500, 500, 500))  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_PrintPage(object sender,
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Red,
         new Rectangle(500, 500, 500, 500));  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Red,  
             Rectangle(500, 500, 500, 500));  
       }  
    ```  
  
     <span data-ttu-id="f6271-111">(Visual Cè e Visual C Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="f6271-111">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    ```  
  
    ```cpp  
    printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    ```  
  
     <span data-ttu-id="f6271-112">È anche possibile scrivere codice <xref:System.Drawing.Printing.PrintDocument.BeginPrint> <xref:System.Drawing.Printing.PrintDocument.EndPrint> per gli eventi e , includendo ad esempio un numero intero che rappresenta il numero totale di pagine da stampare che viene decrementato durante la stampa di ogni pagina.</span><span class="sxs-lookup"><span data-stu-id="f6271-112">You may also want to write code for the <xref:System.Drawing.Printing.PrintDocument.BeginPrint> and <xref:System.Drawing.Printing.PrintDocument.EndPrint> events, perhaps including an integer representing the total number of pages to print that is decremented as each page prints.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="f6271-113">È possibile <xref:System.Windows.Forms.PrintDialog> aggiungere un componente al form per fornire agli utenti un'interfaccia utente pulita ed efficiente.</span><span class="sxs-lookup"><span data-stu-id="f6271-113">You can add a <xref:System.Windows.Forms.PrintDialog> component to your form to provide a clean and efficient user interface (UI) to your users.</span></span> <span data-ttu-id="f6271-114">L'impostazione <xref:System.Windows.Forms.PrintDialog.Document%2A> <xref:System.Windows.Forms.PrintDialog> della proprietà del componente consente di impostare le proprietà relative al documento di stampa che si sta lavorando nel modulo.</span><span class="sxs-lookup"><span data-stu-id="f6271-114">Setting the <xref:System.Windows.Forms.PrintDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintDialog> component enables you to set properties related to the print document you are working with on your form.</span></span> <span data-ttu-id="f6271-115">Per ulteriori informazioni <xref:System.Windows.Forms.PrintDialog> sul componente, vedere [PrintDialog Component](../controls/printdialog-component-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="f6271-115">For more information about the <xref:System.Windows.Forms.PrintDialog> component, see [PrintDialog Component](../controls/printdialog-component-windows-forms.md).</span></span>  
  
     <span data-ttu-id="f6271-116">Per ulteriori informazioni sulle specifiche dei processi di stampa di Windows Form, <xref:System.Drawing.Printing.PrintPageEventArgs>inclusa la creazione di un processo di stampa a livello di codice, vedere .</span><span class="sxs-lookup"><span data-stu-id="f6271-116">For more information about the specifics of Windows Forms print jobs, including how to create a print job programmatically, see <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6271-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6271-117">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="f6271-118">Supporto per la stampa in Windows Form</span><span class="sxs-lookup"><span data-stu-id="f6271-118">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
