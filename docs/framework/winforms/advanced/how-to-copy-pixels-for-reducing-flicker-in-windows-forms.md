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
ms.openlocfilehash: 5a18539153c64a5059d8079f6e245115b026bb91
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950141"
---
# <a name="how-to-copy-pixels-for-reducing-flicker-in-windows-forms"></a>Procedura: Copiare i pixel per ridurre lo sfarfallio nei Windows Form
Quando si aggiunge un'animazione a un grafico semplice, gli utenti possono talvolta riscontrare sfarfallio o altri effetti visivi indesiderati. Un modo per limitare questo problema consiste nell'usare un processo "BitBlt" sul grafico. BitBlt è il "trasferimento a blocchi di bit" dei dati relativi ai colori da un rettangolo di origine di pixel a un rettangolo di destinazione di pixel.  
  
 Con Windows Forms, BitBlt viene eseguita utilizzando il <xref:System.Drawing.Graphics.CopyFromScreen%2A> metodo <xref:System.Drawing.Graphics> della classe. Nei parametri del metodo si specificano l'origine e la destinazione (come punti), le dimensioni dell'area da copiare e l'oggetto Graphics utilizzato per disegnare la nuova forma.  
  
 Nell'esempio seguente viene disegnata una forma sul form nel <xref:System.Windows.Forms.Control.Paint> gestore eventi. Viene quindi utilizzato <xref:System.Drawing.Graphics.CopyFromScreen%2A> il metodo per duplicare la forma.  
  
> [!NOTE]
> Se si imposta la <xref:System.Windows.Forms.Control.DoubleBuffered%2A> proprietà del `true` form su, il <xref:System.Windows.Forms.Control.Paint> codice basato su grafica nell'evento verrà sottoposta a doppio buffer. Sebbene non sia possibile ottenere miglioramenti in termini di prestazioni quando si usa il codice riportato di seguito, è opportuno tenere presente quando si lavora con codice di manipolazione grafica più complesso.  
  
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
 Il codice precedente viene eseguito nel gestore <xref:System.Windows.Forms.Control.Paint> eventi del form in modo che la grafica venga mantenute quando il modulo viene ridisegnato. Di conseguenza, non chiamare metodi correlati alla grafica nel <xref:System.Windows.Forms.Form.Load> gestore eventi, perché il contenuto disegnato non verrà ridisegnato se il form viene ridimensionato o nascosto da un altro form.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.CopyPixelOperation>
- <xref:System.Drawing.Graphics.FillRectangle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.OnPaint%2A?displayProperty=nameWithType>
- [Grafica e disegno in Windows Form](graphics-and-drawing-in-windows-forms.md)
- [Uso di un oggetto Pen per creare linee e forme](using-a-pen-to-draw-lines-and-shapes.md)
