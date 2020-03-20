---
title: 'Procedura: copiare i pixel per ridurre lo sfarfallioHow to: Copy Pixels for Reducing Flicker'
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
ms.openlocfilehash: a25295532d7123d92bcacc6828d3e8cfcc839d6e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182579"
---
# <a name="how-to-copy-pixels-for-reducing-flicker-in-windows-forms"></a>Procedura: copiare i pixel per ridurre lo sfarfallio in Windows Form
Quando si anima un elemento grafico semplice, gli utenti possono talvolta riscontrare sfarfallio o altri effetti visivi indesiderati. Un modo per limitare questo problema consiste nell'utilizzare un processo "bitblt" sul grafico. Bitblt è il "trasferimento a blocchi di bit" dei dati di colore da un rettangolo di origine di pixel a un rettangolo di destinazione di pixel.  
  
 Con Windows Form, bitblt viene <xref:System.Drawing.Graphics.CopyFromScreen%2A> eseguita <xref:System.Drawing.Graphics> utilizzando il metodo della classe. Nei parametri del metodo, specificare l'origine e la destinazione (come punti), le dimensioni dell'area da copiare e l'oggetto grafico utilizzato per disegnare la nuova forma.  
  
 Nell'esempio seguente, una forma viene disegnata nel form nel relativo <xref:System.Windows.Forms.Control.Paint> gestore eventi. Quindi, <xref:System.Drawing.Graphics.CopyFromScreen%2A> il metodo viene utilizzato per duplicare la forma.  
  
> [!NOTE]
> L'impostazione <xref:System.Windows.Forms.Control.DoubleBuffered%2A> della `true` proprietà del form su <xref:System.Windows.Forms.Control.Paint> renderà il codice basato sulla grafica nell'evento a doppio buffer. Anche se questo non avrà alcun miglioramento delle prestazioni distinguibile quando si utilizza il codice di seguito, è qualcosa da tenere a mente quando si lavora con codice di manipolazione grafica più complesso.  
  
## <a name="example"></a>Esempio  
  
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
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Il codice precedente viene eseguito <xref:System.Windows.Forms.Control.Paint> nel gestore eventi del form in modo che la grafica venga mantenuta quando il form viene ridisegnato. Di conseguenza, non chiamare metodi <xref:System.Windows.Forms.Form.Load> correlati alla grafica nel gestore eventi, perché il contenuto disegnato non verrà ridisegnato se il form viene ridimensionato o oscurato da un altro form.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.CopyPixelOperation>
- <xref:System.Drawing.Graphics.FillRectangle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.OnPaint%2A?displayProperty=nameWithType>
- [Grafica e disegno in Windows Form](graphics-and-drawing-in-windows-forms.md)
- [Utilizzo di un oggetto Pen per creare linee e forme](using-a-pen-to-draw-lines-and-shapes.md)
