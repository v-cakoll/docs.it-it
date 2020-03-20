---
title: 'Procedura: scegliere le stampanti collegate al computer di un utente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- printing [Windows Forms], choosing printers
- printers [Windows Forms], choosing
ms.assetid: 63c1172b-2931-4ac0-953f-37f629494bbf
ms.openlocfilehash: 2afbccd02ef42a78d5eac1a01841516fca27c92e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182605"
---
# <a name="how-to-choose-the-printers-attached-to-a-users-computer-in-windows-forms"></a><span data-ttu-id="69ab5-102">Procedura: selezionare le stampanti connesse al computer dell'utente in Windows Form</span><span class="sxs-lookup"><span data-stu-id="69ab5-102">How to: Choose the Printers Attached to a User's Computer in Windows Forms</span></span>
<span data-ttu-id="69ab5-103">Spesso gli utenti vogliono scegliere una stampante diversa da quella predefinita.</span><span class="sxs-lookup"><span data-stu-id="69ab5-103">Often, users want to choose a printer other than the default printer to print to.</span></span> <span data-ttu-id="69ab5-104">È possibile consentire agli utenti di selezionare una stampante tra quelle attualmente installate usando il componente <xref:System.Windows.Forms.PrintDialog> .</span><span class="sxs-lookup"><span data-stu-id="69ab5-104">You can enable users to choose a printer from among those currently installed by using the <xref:System.Windows.Forms.PrintDialog> component.</span></span> <span data-ttu-id="69ab5-105">Tramite il componente <xref:System.Windows.Forms.PrintDialog> , l'oggetto <xref:System.Windows.Forms.DialogResult> del componente <xref:System.Windows.Forms.PrintDialog> viene acquisito e usato per selezionare la stampante.</span><span class="sxs-lookup"><span data-stu-id="69ab5-105">Through the <xref:System.Windows.Forms.PrintDialog> component, the <xref:System.Windows.Forms.DialogResult> of the <xref:System.Windows.Forms.PrintDialog> component is captured and used to select the printer.</span></span>  
  
 <span data-ttu-id="69ab5-106">Nella procedura seguente viene selezionato un file di testo da stampare sulla stampante predefinita.</span><span class="sxs-lookup"><span data-stu-id="69ab5-106">In the following procedure, a text file is selected to be printed to the default printer.</span></span> <span data-ttu-id="69ab5-107">Viene quindi creata un'istanza della classe <xref:System.Windows.Forms.PrintDialog> .</span><span class="sxs-lookup"><span data-stu-id="69ab5-107">The <xref:System.Windows.Forms.PrintDialog> class is then instantiated.</span></span>  
  
### <a name="to-choose-a-printer-and-then-print-a-file"></a><span data-ttu-id="69ab5-108">Per selezionare una stampante e stampare un file</span><span class="sxs-lookup"><span data-stu-id="69ab5-108">To choose a printer and then print a file</span></span>  
  
1. <span data-ttu-id="69ab5-109">Selezionare la stampante da <xref:System.Windows.Forms.PrintDialog> utilizzare utilizzando il componente.</span><span class="sxs-lookup"><span data-stu-id="69ab5-109">Select the printer to be used using the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
     <span data-ttu-id="69ab5-110">Nell'esempio di codice seguente vengono gestiti due eventi.</span><span class="sxs-lookup"><span data-stu-id="69ab5-110">In the following code example, there are two events being handled.</span></span> <span data-ttu-id="69ab5-111">Nel primo, <xref:System.Windows.Forms.Button> evento di <xref:System.Windows.Forms.Control.Click> un <xref:System.Windows.Forms.PrintDialog> controllo, viene creata un'istanza della classe <xref:System.Windows.Forms.DialogResult> e la stampante selezionata dall'utente viene acquisita nella proprietà .</span><span class="sxs-lookup"><span data-stu-id="69ab5-111">In the first, a <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event, the <xref:System.Windows.Forms.PrintDialog> class is instantiated and the printer selected by the user is captured in the <xref:System.Windows.Forms.DialogResult> property.</span></span>  
  
     <span data-ttu-id="69ab5-112">Nel secondo caso, <xref:System.Drawing.Printing.PrintDocument.PrintPage> nell'evento del <xref:System.Drawing.Printing.PrintDocument> componente, un documento di esempio viene stampato sulla stampante specificata.</span><span class="sxs-lookup"><span data-stu-id="69ab5-112">In the second event, the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event of the <xref:System.Drawing.Printing.PrintDocument> component, a sample document is printed to the printer specified.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles Button1.Click  
       Dim PrintDialog1 As New PrintDialog()  
       PrintDialog1.Document = PrintDocument1  
       Dim result As DialogResult = PrintDialog1.ShowDialog()  
  
       If (result = DialogResult.OK) Then  
         PrintDocument1.Print()  
       End If
  
    End Sub  
  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillRectangle(Brushes.Red, New Rectangle(500, 500, 500, 500))
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       PrintDialog printDialog1 = new PrintDialog();  
       printDialog1.Document = printDocument1;  
       DialogResult result = printDialog1.ShowDialog();  
       if (result == DialogResult.OK)  
       {  
          printDocument1.Print();  
       }  
    }  
  
    private void printDocument1_PrintPage(object sender,
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Red,
         new Rectangle(500, 500, 500, 500));  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          PrintDialog ^ printDialog1 = gcnew PrintDialog();  
          printDialog1->Document = printDocument1;  
          System::Windows::Forms::DialogResult result =
             printDialog1->ShowDialog();  
          if (result == DialogResult::OK)  
          {  
             printDocument1->Print();  
          }  
       }  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Red,  
             Rectangle(500, 500, 500, 500));  
       }  
    ```  
  
     <span data-ttu-id="69ab5-113">(Visual Cè e Visual C Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="69ab5-113">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="69ab5-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69ab5-114">See also</span></span>

- [<span data-ttu-id="69ab5-115">Supporto per la stampa in Windows Form</span><span class="sxs-lookup"><span data-stu-id="69ab5-115">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
