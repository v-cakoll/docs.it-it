---
title: 'Procedura: Stampare grafica in Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], printing
- printing [Windows Forms], graphics
ms.assetid: 32b891e6-52ff-4fea-a9ff-2ce5db20a4c6
ms.openlocfilehash: 55459482d0994c581164128b17c08a7ca90d0717
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59339099"
---
# <a name="how-to-print-graphics-in-windows-forms"></a><span data-ttu-id="524cf-102">Procedura: Stampare grafica in Windows Form</span><span class="sxs-lookup"><span data-stu-id="524cf-102">How to: Print Graphics in Windows Forms</span></span>
<span data-ttu-id="524cf-103">Spesso è necessario stampare grafica nelle tue applicazioni basate su Windows.</span><span class="sxs-lookup"><span data-stu-id="524cf-103">Frequently, you will want to print graphics in your Windows-based application.</span></span> <span data-ttu-id="524cf-104">Il <xref:System.Drawing.Graphics> classe fornisce metodi per disegnare oggetti in un dispositivo, ad esempio un monitor o una stampante.</span><span class="sxs-lookup"><span data-stu-id="524cf-104">The <xref:System.Drawing.Graphics> class provides methods for drawing objects to a device, such as a screen or printer.</span></span>  
  
### <a name="to-print-graphics"></a><span data-ttu-id="524cf-105">Per stampare la grafica</span><span class="sxs-lookup"><span data-stu-id="524cf-105">To print graphics</span></span>  
  
1. <span data-ttu-id="524cf-106">Aggiungere un <xref:System.Drawing.Printing.PrintDocument> al form.</span><span class="sxs-lookup"><span data-stu-id="524cf-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2. <span data-ttu-id="524cf-107">Nel <xref:System.Drawing.Printing.PrintDocument.PrintPage> gestore eventi, usare il <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> proprietà del <xref:System.Drawing.Printing.PrintPageEventArgs> classe per indicare la stampante su quale tipo di grafica da stampare.</span><span class="sxs-lookup"><span data-stu-id="524cf-107">In the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler, use the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class to instruct the printer on what kind of graphics to print.</span></span>  
  
     <span data-ttu-id="524cf-108">Esempio di codice seguente viene illustrato un gestore eventi utilizzato per creare una blu ellisse all'interno di un rettangolo di delimitazione.</span><span class="sxs-lookup"><span data-stu-id="524cf-108">The following code example shows an event handler used to create a blue ellipse within a bounding rectangle.</span></span> <span data-ttu-id="524cf-109">Il rettangolo contiene il percorso e delle dimensioni seguenti: inizia con 100, 150 con una larghezza pari a 250 e un'altezza pari a 250.</span><span class="sxs-lookup"><span data-stu-id="524cf-109">The rectangle has the following location and dimensions: beginning at 100, 150 with a width of 250 and a height of 250.</span></span>  
  
    ```vb  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillEllipse(Brushes.Blue, New Rectangle(100, 150, 250, 250))  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_PrintPage(object sender,   
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Blue,   
         new Rectangle(100, 150, 250, 250));  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Blue,  
             Rectangle(100, 150, 250, 250));  
       }  
    ```  
  
     <span data-ttu-id="524cf-110">(Visual c# e [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) inserire il codice seguente nel costruttore del form per registrare il gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="524cf-110">(Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    ```  
  
    ```cpp  
    this->printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="524cf-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="524cf-111">See also</span></span>

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Brush>
- [<span data-ttu-id="524cf-112">Supporto per la stampa in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="524cf-112">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
