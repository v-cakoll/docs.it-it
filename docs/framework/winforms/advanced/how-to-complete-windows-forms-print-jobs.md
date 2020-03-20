---
title: Completamento dei processi di stampa
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print jobs [Windows Forms], completing in Windows Forms
- printing [Windows Forms], print jobs
ms.assetid: 23ec74f7-34c5-4710-82a0-ee2914518548
ms.openlocfilehash: 62f67002bfbaf46e73bae06fdaff26efde865c06
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182592"
---
# <a name="how-to-complete-windows-forms-print-jobs"></a><span data-ttu-id="58f33-102">Procedura: completare processi di stampa in Windows Form</span><span class="sxs-lookup"><span data-stu-id="58f33-102">How to: Complete Windows Forms Print Jobs</span></span>
<span data-ttu-id="58f33-103">Spesso, gli elaboratori di testo e altre applicazioni che implicano la stampa offrono la possibilità di visualizzare un messaggio agli utenti che indica che un processo di stampa è stato completato.</span><span class="sxs-lookup"><span data-stu-id="58f33-103">Frequently, word processors and other applications that involve printing will provide the option to display a message to users that a print job is complete.</span></span> <span data-ttu-id="58f33-104">È possibile fornire questa funzionalità in <xref:System.Drawing.Printing.PrintDocument.EndPrint> Windows Form <xref:System.Drawing.Printing.PrintDocument> gestendo l'evento del componente.</span><span class="sxs-lookup"><span data-stu-id="58f33-104">You can provide this functionality in your Windows Forms by handling the <xref:System.Drawing.Printing.PrintDocument.EndPrint> event of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
 <span data-ttu-id="58f33-105">La procedura seguente richiede la creazione di un'applicazione basata su Windows con un <xref:System.Drawing.Printing.PrintDocument> componente su di essa, che è il modo standard per abilitare la stampa da un'applicazione basata su Windows.The following procedure requires that you have created a Windows-based application with a component on it, which is the standard way of enabling printing from a Windows-based application.</span><span class="sxs-lookup"><span data-stu-id="58f33-105">The following procedure requires that you have created a Windows-based application with a <xref:System.Drawing.Printing.PrintDocument> component on it, which is the standard way of enabling printing from a Windows-based application.</span></span> <span data-ttu-id="58f33-106">Per ulteriori informazioni sulla stampa <xref:System.Drawing.Printing.PrintDocument> da Windows Form utilizzando il componente, vedere [Procedura: Creare processi](how-to-create-standard-windows-forms-print-jobs.md)di stampa standard di Windows Form .</span><span class="sxs-lookup"><span data-stu-id="58f33-106">For more information about printing from Windows Forms using the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Create Standard Windows Forms Print Jobs](how-to-create-standard-windows-forms-print-jobs.md).</span></span>  
  
### <a name="to-complete-a-print-job"></a><span data-ttu-id="58f33-107">Per completare un processo di stampa</span><span class="sxs-lookup"><span data-stu-id="58f33-107">To complete a print job</span></span>  
  
1. <span data-ttu-id="58f33-108">Impostare <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> la <xref:System.Drawing.Printing.PrintDocument> proprietà del componente.</span><span class="sxs-lookup"><span data-stu-id="58f33-108">Set the <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> property of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
    ```vb  
    PrintDocument1.DocumentName = "MyTextFile"  
    ```  
  
    ```csharp  
    printDocument1.DocumentName = "MyTextFile";  
    ```  
  
    ```cpp  
    printDocument1->DocumentName = "MyTextFile";  
    ```  
  
2. <span data-ttu-id="58f33-109">Scrivere codice per gestire l'evento <xref:System.Drawing.Printing.PrintDocument.EndPrint> .</span><span class="sxs-lookup"><span data-stu-id="58f33-109">Write code to handle the <xref:System.Drawing.Printing.PrintDocument.EndPrint> event.</span></span>  
  
     <span data-ttu-id="58f33-110">Nell'esempio di codice riportato di seguito viene visualizzata una finestra di messaggio che indica che la stampa del documento è terminata.</span><span class="sxs-lookup"><span data-stu-id="58f33-110">In the following code example, a message box is displayed, indicating that the document has finished printing.</span></span>  
  
    ```vb  
    Private Sub PrintDocument1_EndPrint(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintEventArgs) Handles PrintDocument1.EndPrint  
       MessageBox.Show(PrintDocument1.DocumentName + " has finished printing.")  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_EndPrint(object sender,
    System.Drawing.Printing.PrintEventArgs e)  
    {  
       MessageBox.Show(printDocument1.DocumentName +
          " has finished printing.");  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_EndPrint(System::Object ^ sender,  
          System::Drawing::Printing::PrintEventArgs ^ e)  
       {  
          MessageBox::Show(String::Concat(printDocument1->DocumentName,  
             " has finished printing."));  
       }  
    ```  
  
     <span data-ttu-id="58f33-111">(Visual Cè e Visual C Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="58f33-111">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.printDocument1.EndPrint += new  
       System.Drawing.Printing.PrintEventHandler  
       (this.printDocument1_EndPrint);  
    ```  
  
    ```cpp  
    this->printDocument1->EndPrint += gcnew  
       System::Drawing::Printing::PrintEventHandler  
       (this, &Form1::printDocument1_EndPrint);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="58f33-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58f33-112">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="58f33-113">Supporto per la stampa in Windows Form</span><span class="sxs-lookup"><span data-stu-id="58f33-113">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
