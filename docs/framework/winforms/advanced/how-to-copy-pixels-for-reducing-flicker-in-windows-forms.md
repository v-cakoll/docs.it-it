---
title: 'Procedura: copiare i pixel per ridurre lo sfarfallio in Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitblt
- graphics [Windows Forms], copying
- flicker [Windows Forms], reducing in Windows Forms
- graphics [Windows Forms], reducing flicker
- pixels [Windows Forms], copying
- flicker
- bit-block transfer
ms.assetid: 33b76910-13a3-4521-be98-5c097341ae3b
ms.openlocfilehash: dc5f05ff4ea9f3c2b828cbe37860e1bd241fc604
ms.sourcegitcommit: 3d42e1d73e21c35c540dd4adbea23efcbe1b8b0a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/20/2018
ms.locfileid: "36270435"
---
# <a name="how-to-copy-pixels-for-reducing-flicker-in-windows-forms"></a><span data-ttu-id="def1d-102">Procedura: copiare i pixel per ridurre lo sfarfallio in Windows Form</span><span class="sxs-lookup"><span data-stu-id="def1d-102">How to: Copy Pixels for Reducing Flicker in Windows Forms</span></span>
<span data-ttu-id="def1d-103">Quando si aggiunge un'animazione a un simbolo semplice, gli utenti possono verificarsi in alcuni casi lo sfarfallio o altri effetti visivi indesiderati.</span><span class="sxs-lookup"><span data-stu-id="def1d-103">When you animate a simple graphic, users can sometimes encounter flicker or other undesirable visual effects.</span></span> <span data-ttu-id="def1d-104">Un modo per limitare questo problema è necessario utilizzare un processo "bitblt" sull'oggetto grafico.</span><span class="sxs-lookup"><span data-stu-id="def1d-104">One way to limit this problem is to use a "bitblt" process on the graphic.</span></span> <span data-ttu-id="def1d-105">BitBlt è il "blocchi di bit trasferimento" di dati relativi al colore da un'origine a un rettangolo di pixel a un rettangolo di destinazione di pixel.</span><span class="sxs-lookup"><span data-stu-id="def1d-105">Bitblt is the "bit-block transfer" of the color data from an origin rectangle of pixels to a destination rectangle of pixels.</span></span>  
  
 <span data-ttu-id="def1d-106">In Windows Form, bitblt viene ottenuto utilizzando il <xref:System.Drawing.Graphics.CopyFromScreen%2A> metodo la <xref:System.Drawing.Graphics> classe.</span><span class="sxs-lookup"><span data-stu-id="def1d-106">With Windows Forms, bitblt is accomplished using the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="def1d-107">Nei parametri del metodo, specificare l'origine e destinazione (come punti), le dimensioni dell'area di copia e l'oggetto graphics utilizzato per disegnare la nuova forma.</span><span class="sxs-lookup"><span data-stu-id="def1d-107">In the parameters of the method, you specify the source and destination (as points), the size of the area to be copied, and the graphics object used to draw the new shape.</span></span>  
  
 <span data-ttu-id="def1d-108">Nell'esempio seguente, una forma viene disegnata sul form nel relativo <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="def1d-108">In the example below, a shape is drawn on the form in its <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="def1d-109">Quindi, <xref:System.Drawing.Graphics.CopyFromScreen%2A> metodo viene utilizzato per duplicare la forma.</span><span class="sxs-lookup"><span data-stu-id="def1d-109">Then, the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method is used to duplicate the shape.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="def1d-110">L'impostazione della maschera <xref:System.Windows.Forms.Control.DoubleBuffered%2A> proprietà `true` renderà codice basato su grafica il <xref:System.Windows.Forms.Control.Paint> evento essere doppio buffer.</span><span class="sxs-lookup"><span data-stu-id="def1d-110">Setting the form's <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true` will make graphics-based code in the <xref:System.Windows.Forms.Control.Paint> event be double-buffered.</span></span> <span data-ttu-id="def1d-111">Mentre ciò non avrà alcun miglioramento delle prestazioni apprezzabili quando si utilizza il codice riportato di seguito, è necessario tenere presenti quando si lavora con codice di manipolazione grafica più complesso.</span><span class="sxs-lookup"><span data-stu-id="def1d-111">While this will not have any discernible performance gains when using the code below, it is something to keep in mind when working with more complex graphics-manipulation code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="def1d-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="def1d-112">Example</span></span>  
  
```vb  
Private Sub Form1_Paint(ByVal sender As Object, ByVal e As _  
    System.Windows.Forms.PaintEventArgs) Handles MyBase.Paint  
    ' Draw a circle with a bar on top.  
        e.Graphics.FillEllipse(Brushes.DarkBlue, New Rectangle _  
             (10, 10, 60, 60))  
        e.Graphics.FillRectangle(Brushes.Khaki, New Rectangle _  
             (20, 30, 60, 10))  
    ' Copy the graphic to a new location.  
        e.Graphics.CopyFromScreen(New Point(10, 10), New Point _  
             (100, 100), New Size(70, 70))  
End Sub  
```  
  
```csharp  
private void Form1_Paint(System.Object sender,  
    System.Windows.Forms.PaintEventArgs e)  
        {  
        e.Graphics.FillEllipse(Brushes.DarkBlue, new  
            Rectangle(10,10,60,60));  
        e.Graphics.FillRectangle(Brushes.Khaki, new  
            Rectangle(20,30,60,10));  
        e.Graphics.CopyFromScreen(new Point(10, 10), new Point(100, 100),   
            new Size(70, 70));  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="def1d-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="def1d-113">Compiling the Code</span></span>  
 <span data-ttu-id="def1d-114">Il codice precedente viene eseguito il formato <xref:System.Windows.Forms.Control.Paint> gestore dell'evento in modo che gli elementi grafici permanenti quando il form viene ridisegnato.</span><span class="sxs-lookup"><span data-stu-id="def1d-114">The code above is run in the form's <xref:System.Windows.Forms.Control.Paint> event handler so that the graphics persist when the form is redrawn.</span></span> <span data-ttu-id="def1d-115">Di conseguenza, non chiamare metodi correlati a grafica <xref:System.Windows.Forms.Form.Load> gestore eventi, perché il contenuto disegnato non verrà ridisegnato se il form viene ridimensionato o nascosto da un altro formato.</span><span class="sxs-lookup"><span data-stu-id="def1d-115">As such, do not call graphics-related methods in the <xref:System.Windows.Forms.Form.Load> event handler, because the drawn content will not be redrawn if the form is resized or obscured by another form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="def1d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="def1d-116">See Also</span></span>  
 <xref:System.Drawing.CopyPixelOperation>  
 <xref:System.Drawing.Graphics.FillRectangle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Control.OnPaint%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="def1d-117">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="def1d-117">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="def1d-118">Uso di un oggetto Pen per creare linee e forme</span><span class="sxs-lookup"><span data-stu-id="def1d-118">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
