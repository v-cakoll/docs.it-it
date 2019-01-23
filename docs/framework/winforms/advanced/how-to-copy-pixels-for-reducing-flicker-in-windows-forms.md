---
title: 'Procedura: Copiare i pixel per ridurre lo sfarfallio in Windows Form'
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
ms.openlocfilehash: cdcb64588f91ece02f1e7f446d4020d68262c93d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559450"
---
# <a name="how-to-copy-pixels-for-reducing-flicker-in-windows-forms"></a>Procedura: Copiare i pixel per ridurre lo sfarfallio in Windows Form
Quando si anima una semplice immagine, gli utenti possono a volte si verificano lo sfarfallio o altri effetti visivi indesiderati. Uno per limitare questo problema consiste nell'usare un processo di "bitblt" sull'oggetto grafico. BitBlt è il "blocchi di bit trasferimento" di dati relativi al colore da un'origine a un rettangolo di pixel a un rettangolo di destinazione del pixel.  
  
 Con Windows Forms, bitblt avviene utilizzando il <xref:System.Drawing.Graphics.CopyFromScreen%2A> metodo di <xref:System.Drawing.Graphics> classe. I parametri del metodo, si specifica l'origine e destinazione (come punti), le dimensioni dell'area di copia e l'oggetto graphics utilizzato per disegnare la nuova forma.  
  
 Nell'esempio seguente, una forma è disegnata nel form nel relativo <xref:System.Windows.Forms.Control.Paint> gestore dell'evento. Quindi, <xref:System.Drawing.Graphics.CopyFromScreen%2A> metodo viene utilizzato per duplicare la forma.  
  
> [!NOTE]
>  Impostazione della maschera <xref:System.Windows.Forms.Control.DoubleBuffered%2A> proprietà `true` renderà codice basato su grafico nel <xref:System.Windows.Forms.Control.Paint> evento essere doppio buffer. Sebbene ciò non avrà alcun miglioramento delle prestazioni apprezzabili quando si usa il codice seguente, è un aspetto da tenere presenti quando si lavora con codice di manipolazioni grafiche più complesso.  
  
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
 Il codice precedente viene eseguito in del modulo <xref:System.Windows.Forms.Control.Paint> gestore dell'evento in modo da rendere persistenti gli elementi grafici quando il form viene ridisegnato. Di conseguenza, non chiamare metodi correlati a grafici <xref:System.Windows.Forms.Form.Load> gestore eventi, in quanto il contenuto creato non verrà ridisegnato se il form viene ridimensionato o nascosto da un altro form.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Drawing.CopyPixelOperation>
- <xref:System.Drawing.Graphics.FillRectangle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.OnPaint%2A?displayProperty=nameWithType>
- [Grafica e disegno in Windows Form](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
- [Uso di un oggetto Pen per creare linee e forme](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
