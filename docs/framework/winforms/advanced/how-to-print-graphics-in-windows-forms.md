---
title: 'Procedura: stampare elementi graficiHow to: Print Graphics'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], printing
- printing [Windows Forms], graphics
ms.assetid: 32b891e6-52ff-4fea-a9ff-2ce5db20a4c6
ms.openlocfilehash: 15f3a507839430ce058302e7f5abd317ef84626f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182527"
---
# <a name="how-to-print-graphics-in-windows-forms"></a><span data-ttu-id="b6388-102">Procedura: stampare grafica in Windows Form</span><span class="sxs-lookup"><span data-stu-id="b6388-102">How to: Print Graphics in Windows Forms</span></span>
<span data-ttu-id="b6388-103">Spesso, è consigliabile stampare grafica nell'applicazione basata su Windows.</span><span class="sxs-lookup"><span data-stu-id="b6388-103">Frequently, you will want to print graphics in your Windows-based application.</span></span> <span data-ttu-id="b6388-104">La <xref:System.Drawing.Graphics> classe fornisce metodi per disegnare oggetti a un dispositivo, ad esempio uno schermo o una stampante.</span><span class="sxs-lookup"><span data-stu-id="b6388-104">The <xref:System.Drawing.Graphics> class provides methods for drawing objects to a device, such as a screen or printer.</span></span>  
  
### <a name="to-print-graphics"></a><span data-ttu-id="b6388-105">Per stampare elementi grafici</span><span class="sxs-lookup"><span data-stu-id="b6388-105">To print graphics</span></span>  
  
1. <span data-ttu-id="b6388-106">Aggiungere <xref:System.Drawing.Printing.PrintDocument> un componente al form.</span><span class="sxs-lookup"><span data-stu-id="b6388-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2. <span data-ttu-id="b6388-107"><xref:System.Drawing.Printing.PrintDocument.PrintPage> Nel gestore eventi <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> utilizzare la <xref:System.Drawing.Printing.PrintPageEventArgs> proprietà della classe per indicare alla stampante il tipo di grafica da stampare.</span><span class="sxs-lookup"><span data-stu-id="b6388-107">In the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler, use the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class to instruct the printer on what kind of graphics to print.</span></span>  
  
     <span data-ttu-id="b6388-108">Esempio di codice seguente viene illustrato un gestore eventi utilizzato per creare un'ellisse blu all'interno di un rettangolo di delimitazione.</span><span class="sxs-lookup"><span data-stu-id="b6388-108">The following code example shows an event handler used to create a blue ellipse within a bounding rectangle.</span></span> <span data-ttu-id="b6388-109">Il rettangolo ha la seguente posizione e dimensioni: a partire da 100, 150 con una larghezza di 250 e un'altezza di 250.</span><span class="sxs-lookup"><span data-stu-id="b6388-109">The rectangle has the following location and dimensions: beginning at 100, 150 with a width of 250 and a height of 250.</span></span>  
  
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
  
     <span data-ttu-id="b6388-110">(Visual Cè e Visual C Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="b6388-110">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b6388-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6388-111">See also</span></span>

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Brush>
- [<span data-ttu-id="b6388-112">Supporto per la stampa in Windows Form</span><span class="sxs-lookup"><span data-stu-id="b6388-112">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
