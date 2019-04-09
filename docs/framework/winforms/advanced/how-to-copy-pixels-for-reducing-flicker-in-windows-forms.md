---
title: 'Procedura: Copiare i pixel per ridurre lo sfarfallio nei Windows Form'
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
ms.openlocfilehash: e3d1c2b681e98dc7c45467683924dd4022eb377e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59094034"
---
# <a name="how-to-copy-pixels-for-reducing-flicker-in-windows-forms"></a>Procedura: Copiare i pixel per ridurre lo sfarfallio nei Windows Form
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
- [Grafica e disegno in Windows Form](graphics-and-drawing-in-windows-forms.md)
- [Utilizzo di un oggetto Pen per creare linee e forme](using-a-pen-to-draw-lines-and-shapes.md)
