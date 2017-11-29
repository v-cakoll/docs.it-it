---
title: 'Procedura: stampare grafica in Windows Form'
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
- graphics [Windows Forms], printing
- printing [Windows Forms], graphics
ms.assetid: 32b891e6-52ff-4fea-a9ff-2ce5db20a4c6
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5f495135b3210f430c887451844bec8b154db33c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-print-graphics-in-windows-forms"></a><span data-ttu-id="940e6-102">Procedura: stampare grafica in Windows Form</span><span class="sxs-lookup"><span data-stu-id="940e6-102">How to: Print Graphics in Windows Forms</span></span>
<span data-ttu-id="940e6-103">Spesso, è possibile stampare grafica nell'applicazione basata su Windows.</span><span class="sxs-lookup"><span data-stu-id="940e6-103">Frequently, you will want to print graphics in your Windows-based application.</span></span> <span data-ttu-id="940e6-104">La <xref:System.Drawing.Graphics> classe fornisce metodi per disegnare oggetti in un dispositivo, ad esempio un monitor o una stampante.</span><span class="sxs-lookup"><span data-stu-id="940e6-104">The <xref:System.Drawing.Graphics> class provides methods for drawing objects to a device, such as a screen or printer.</span></span>  
  
### <a name="to-print-graphics"></a><span data-ttu-id="940e6-105">Per stampare la grafica</span><span class="sxs-lookup"><span data-stu-id="940e6-105">To print graphics</span></span>  
  
1.  <span data-ttu-id="940e6-106">Aggiungere un <xref:System.Drawing.Printing.PrintDocument> componente al form.</span><span class="sxs-lookup"><span data-stu-id="940e6-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2.  <span data-ttu-id="940e6-107">Nel <xref:System.Drawing.Printing.PrintDocument.PrintPage> gestore dell'evento, utilizzare il <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> proprietà del <xref:System.Drawing.Printing.PrintPageEventArgs> classe per indicare la stampante nella quale tipo di grafica da stampare.</span><span class="sxs-lookup"><span data-stu-id="940e6-107">In the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler, use the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class to instruct the printer on what kind of graphics to print.</span></span>  
  
     <span data-ttu-id="940e6-108">Esempio di codice seguente viene illustrato un gestore eventi utilizzato per creare un'ellisse blu all'interno di un rettangolo di delimitazione.</span><span class="sxs-lookup"><span data-stu-id="940e6-108">The following code example shows an event handler used to create a blue ellipse within a bounding rectangle.</span></span> <span data-ttu-id="940e6-109">Il rettangolo è il percorso e delle dimensioni seguenti: a partire da 100, 150 con una larghezza pari a 250 e un'altezza pari a 250.</span><span class="sxs-lookup"><span data-stu-id="940e6-109">The rectangle has the following location and dimensions: beginning at 100, 150 with a width of 250 and a height of 250.</span></span>  
  
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
  
     <span data-ttu-id="940e6-110">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] e [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="940e6-110">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="940e6-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="940e6-111">See Also</span></span>  
 <xref:System.Drawing.Graphics>  
 <xref:System.Drawing.Brush>  
 [<span data-ttu-id="940e6-112">Supporto per la stampa in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="940e6-112">Windows Forms Print Support</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
