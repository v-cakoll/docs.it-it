---
title: 'Procedura: stampare grafica'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], printing
- printing [Windows Forms], graphics
ms.assetid: 32b891e6-52ff-4fea-a9ff-2ce5db20a4c6
ms.openlocfilehash: 2435b3bc14747a00d2a0fc03a9ebd21ae43c5369
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740650"
---
# <a name="how-to-print-graphics-in-windows-forms"></a><span data-ttu-id="60e3c-102">Procedura: Stampare grafica in Windows Form</span><span class="sxs-lookup"><span data-stu-id="60e3c-102">How to: Print Graphics in Windows Forms</span></span>
<span data-ttu-id="60e3c-103">Spesso è necessario stampare elementi grafici nell'applicazione basata su Windows.</span><span class="sxs-lookup"><span data-stu-id="60e3c-103">Frequently, you will want to print graphics in your Windows-based application.</span></span> <span data-ttu-id="60e3c-104">La classe <xref:System.Drawing.Graphics> fornisce metodi per disegnare oggetti in un dispositivo, ad esempio una schermata o una stampante.</span><span class="sxs-lookup"><span data-stu-id="60e3c-104">The <xref:System.Drawing.Graphics> class provides methods for drawing objects to a device, such as a screen or printer.</span></span>  
  
### <a name="to-print-graphics"></a><span data-ttu-id="60e3c-105">Per stampare grafica</span><span class="sxs-lookup"><span data-stu-id="60e3c-105">To print graphics</span></span>  
  
1. <span data-ttu-id="60e3c-106">Aggiungere un componente <xref:System.Drawing.Printing.PrintDocument> al modulo.</span><span class="sxs-lookup"><span data-stu-id="60e3c-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2. <span data-ttu-id="60e3c-107">Nel gestore dell'evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> usare la proprietà <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> della classe <xref:System.Drawing.Printing.PrintPageEventArgs> per indicare alla stampante il tipo di grafica da stampare.</span><span class="sxs-lookup"><span data-stu-id="60e3c-107">In the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler, use the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class to instruct the printer on what kind of graphics to print.</span></span>  
  
     <span data-ttu-id="60e3c-108">Nell'esempio di codice riportato di seguito viene illustrato un gestore eventi utilizzato per creare un'ellisse blu all'interno di un rettangolo di delimitazione.</span><span class="sxs-lookup"><span data-stu-id="60e3c-108">The following code example shows an event handler used to create a blue ellipse within a bounding rectangle.</span></span> <span data-ttu-id="60e3c-109">Il rettangolo presenta il percorso e le dimensioni seguenti: a partire da 100, 150 con larghezza 250 e altezza 250.</span><span class="sxs-lookup"><span data-stu-id="60e3c-109">The rectangle has the following location and dimensions: beginning at 100, 150 with a width of 250 and a height of 250.</span></span>  
  
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
  
     <span data-ttu-id="60e3c-110">(Visual C# e Visual C++) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="60e3c-110">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="60e3c-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60e3c-111">See also</span></span>

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Brush>
- [<span data-ttu-id="60e3c-112">Supporto per la stampa in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="60e3c-112">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
