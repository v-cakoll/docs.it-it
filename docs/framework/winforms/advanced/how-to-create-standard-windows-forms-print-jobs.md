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
ms.openlocfilehash: 7ccebf128d533a0e0cf0a17e5702807371e1bea7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59170976"
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a><span data-ttu-id="e65f7-102">Procedura: Creare processi di stampa standard per Windows Form</span><span class="sxs-lookup"><span data-stu-id="e65f7-102">How to: Create Standard Windows Forms Print Jobs</span></span>
<span data-ttu-id="e65f7-103">Del processo di stampa in Windows Form è la <xref:System.Drawing.Printing.PrintDocument> componente, in particolare, il <xref:System.Drawing.Printing.PrintDocument.PrintPage> evento.</span><span class="sxs-lookup"><span data-stu-id="e65f7-103">The foundation of printing in Windows Forms is the <xref:System.Drawing.Printing.PrintDocument> component—more specifically, the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span> <span data-ttu-id="e65f7-104">Scrivendo codice per gestire il <xref:System.Drawing.Printing.PrintDocument.PrintPage> evento, è possibile specificare cosa stampare e come stamparlo.</span><span class="sxs-lookup"><span data-stu-id="e65f7-104">By writing code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event, you can specify what to print and how to print it.</span></span>  
  
### <a name="to-create-a-print-job"></a><span data-ttu-id="e65f7-105">Per creare un processo di stampa</span><span class="sxs-lookup"><span data-stu-id="e65f7-105">To create a print job</span></span>  
  
1.  <span data-ttu-id="e65f7-106">Aggiungere un <xref:System.Drawing.Printing.PrintDocument> al form.</span><span class="sxs-lookup"><span data-stu-id="e65f7-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2.  <span data-ttu-id="e65f7-107">Scrivere codice per gestire l'evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> .</span><span class="sxs-lookup"><span data-stu-id="e65f7-107">Write code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>  
  
     <span data-ttu-id="e65f7-108">Dovrai la propria logica di stampa di codice.</span><span class="sxs-lookup"><span data-stu-id="e65f7-108">You will have to code your own printing logic.</span></span> <span data-ttu-id="e65f7-109">Inoltre, è necessario specificare il materiale da stampare.</span><span class="sxs-lookup"><span data-stu-id="e65f7-109">Additionally, you will have to specify the material to be printed.</span></span>  
  
     <span data-ttu-id="e65f7-110">Nell'esempio di codice seguente, viene creato un grafico di esempio sotto forma di un rettangolo rosso nel <xref:System.Drawing.Printing.PrintDocument.PrintPage> gestore eventi per agire come materiale da stampare.</span><span class="sxs-lookup"><span data-stu-id="e65f7-110">In the following code example, a sample graphic in the shape of a red rectangle is created in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler to act as material to be printed.</span></span>  
  
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
  
     <span data-ttu-id="e65f7-111">(Visual c# e [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) inserire il codice seguente nel costruttore del form per registrare il gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="e65f7-111">(Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
     <span data-ttu-id="e65f7-112">È anche possibile scrivere codice per il <xref:System.Drawing.Printing.PrintDocument.BeginPrint> e <xref:System.Drawing.Printing.PrintDocument.EndPrint> eventi, includendo un intero che rappresenta il numero totale di pagine da stampare decrementato che mano che verrà stampate le pagine.</span><span class="sxs-lookup"><span data-stu-id="e65f7-112">You may also want to write code for the <xref:System.Drawing.Printing.PrintDocument.BeginPrint> and <xref:System.Drawing.Printing.PrintDocument.EndPrint> events, perhaps including an integer representing the total number of pages to print that is decremented as each page prints.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e65f7-113">È possibile aggiungere un <xref:System.Windows.Forms.PrintDialog> al form per fornire un'interfaccia utente pulita ed efficienti (UI) per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="e65f7-113">You can add a <xref:System.Windows.Forms.PrintDialog> component to your form to provide a clean and efficient user interface (UI) to your users.</span></span> <span data-ttu-id="e65f7-114">Impostando il <xref:System.Windows.Forms.PrintDialog.Document%2A> proprietà del <xref:System.Windows.Forms.PrintDialog> Abilita componente è possibile impostare le proprietà correlate alla stampa di documenti si lavora con sul form.</span><span class="sxs-lookup"><span data-stu-id="e65f7-114">Setting the <xref:System.Windows.Forms.PrintDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintDialog> component enables you to set properties related to the print document you are working with on your form.</span></span> <span data-ttu-id="e65f7-115">Per altre informazioni sul <xref:System.Windows.Forms.PrintDialog> componente, vedere [componente PrintDialog](../controls/printdialog-component-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="e65f7-115">For more information about the <xref:System.Windows.Forms.PrintDialog> component, see [PrintDialog Component](../controls/printdialog-component-windows-forms.md).</span></span>  
  
     <span data-ttu-id="e65f7-116">Per altre informazioni sulle specifiche di Windows Form i processi di stampa, incluse quelle sulla creazione di un processo di stampa a livello di codice, vedere <xref:System.Drawing.Printing.PrintPageEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="e65f7-116">For more information about the specifics of Windows Forms print jobs, including how to create a print job programmatically, see <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e65f7-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e65f7-117">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="e65f7-118">Supporto per la stampa in Windows Form</span><span class="sxs-lookup"><span data-stu-id="e65f7-118">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
