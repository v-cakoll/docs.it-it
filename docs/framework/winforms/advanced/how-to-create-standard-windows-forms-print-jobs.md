---
title: 'Procedura: Creare processi di stampa standard per Windows Form'
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
ms.openlocfilehash: 44673e6b26f088e71813aaac26c4b9a03429597a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938234"
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a><span data-ttu-id="d2293-102">Procedura: Creare processi di stampa standard per Windows Form</span><span class="sxs-lookup"><span data-stu-id="d2293-102">How to: Create Standard Windows Forms Print Jobs</span></span>
<span data-ttu-id="d2293-103">Il fondamento della stampa in Windows Forms è il <xref:System.Drawing.Printing.PrintDocument> componente, più specificamente l' <xref:System.Drawing.Printing.PrintDocument.PrintPage> evento.</span><span class="sxs-lookup"><span data-stu-id="d2293-103">The foundation of printing in Windows Forms is the <xref:System.Drawing.Printing.PrintDocument> component—more specifically, the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span> <span data-ttu-id="d2293-104">Scrivendo il codice per gestire l' <xref:System.Drawing.Printing.PrintDocument.PrintPage> evento, è possibile specificare gli elementi da stampare e la relativa modalità di stampa.</span><span class="sxs-lookup"><span data-stu-id="d2293-104">By writing code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event, you can specify what to print and how to print it.</span></span>  
  
### <a name="to-create-a-print-job"></a><span data-ttu-id="d2293-105">Per creare un processo di stampa</span><span class="sxs-lookup"><span data-stu-id="d2293-105">To create a print job</span></span>  
  
1. <span data-ttu-id="d2293-106">Aggiungere un <xref:System.Drawing.Printing.PrintDocument> componente al form.</span><span class="sxs-lookup"><span data-stu-id="d2293-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2. <span data-ttu-id="d2293-107">Scrivere codice per gestire l'evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> .</span><span class="sxs-lookup"><span data-stu-id="d2293-107">Write code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>  
  
     <span data-ttu-id="d2293-108">Dovrai scrivere codice per la tua logica di stampa.</span><span class="sxs-lookup"><span data-stu-id="d2293-108">You will have to code your own printing logic.</span></span> <span data-ttu-id="d2293-109">Inoltre, sarà necessario specificare il materiale da stampare.</span><span class="sxs-lookup"><span data-stu-id="d2293-109">Additionally, you will have to specify the material to be printed.</span></span>  
  
     <span data-ttu-id="d2293-110">Nell'esempio di codice seguente viene creato un elemento grafico di esempio nella forma di un rettangolo rosso nel <xref:System.Drawing.Printing.PrintDocument.PrintPage> gestore eventi per agire come materiale da stampare.</span><span class="sxs-lookup"><span data-stu-id="d2293-110">In the following code example, a sample graphic in the shape of a red rectangle is created in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler to act as material to be printed.</span></span>  
  
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
  
     <span data-ttu-id="d2293-111">(Visual C# e Visual C++) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="d2293-111">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
     <span data-ttu-id="d2293-112">È anche possibile scrivere il codice per gli <xref:System.Drawing.Printing.PrintDocument.BeginPrint> eventi e <xref:System.Drawing.Printing.PrintDocument.EndPrint> , includendo ad esempio un Integer che rappresenta il numero totale di pagine da stampare che viene decrementato Man mano che ogni pagina viene stampata.</span><span class="sxs-lookup"><span data-stu-id="d2293-112">You may also want to write code for the <xref:System.Drawing.Printing.PrintDocument.BeginPrint> and <xref:System.Drawing.Printing.PrintDocument.EndPrint> events, perhaps including an integer representing the total number of pages to print that is decremented as each page prints.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="d2293-113">È possibile aggiungere un <xref:System.Windows.Forms.PrintDialog> componente al form per fornire agli utenti un'interfaccia utente pulita ed efficiente.</span><span class="sxs-lookup"><span data-stu-id="d2293-113">You can add a <xref:System.Windows.Forms.PrintDialog> component to your form to provide a clean and efficient user interface (UI) to your users.</span></span> <span data-ttu-id="d2293-114">L'impostazione <xref:System.Windows.Forms.PrintDialog.Document%2A> della proprietà <xref:System.Windows.Forms.PrintDialog> del componente consente di impostare le proprietà correlate al documento di stampa che si sta utilizzando nel form.</span><span class="sxs-lookup"><span data-stu-id="d2293-114">Setting the <xref:System.Windows.Forms.PrintDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintDialog> component enables you to set properties related to the print document you are working with on your form.</span></span> <span data-ttu-id="d2293-115">Per ulteriori informazioni sul <xref:System.Windows.Forms.PrintDialog> componente, vedere [componente PrintDialog](../controls/printdialog-component-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="d2293-115">For more information about the <xref:System.Windows.Forms.PrintDialog> component, see [PrintDialog Component](../controls/printdialog-component-windows-forms.md).</span></span>  
  
     <span data-ttu-id="d2293-116">Per ulteriori informazioni sulle specifiche di Windows Forms processi di stampa, inclusa la modalità di creazione di un processo di stampa a livello <xref:System.Drawing.Printing.PrintPageEventArgs>di codice, vedere.</span><span class="sxs-lookup"><span data-stu-id="d2293-116">For more information about the specifics of Windows Forms print jobs, including how to create a print job programmatically, see <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2293-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2293-117">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="d2293-118">Supporto per la stampa in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d2293-118">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
