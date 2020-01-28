---
title: 'Procedura: copiare i pixel per ridurre lo sfarfallio'
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
ms.openlocfilehash: 299041e7038d5bd5b9824d668b3f47d842030ac7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746478"
---
# <a name="how-to-copy-pixels-for-reducing-flicker-in-windows-forms"></a>Procedura: copiare i pixel per ridurre lo sfarfallio in Windows Form
Quando si aggiunge un'animazione a un grafico semplice, gli utenti possono talvolta riscontrare sfarfallio o altri effetti visivi indesiderati. Un modo per limitare questo problema consiste nell'usare un processo "BitBlt" sul grafico. BitBlt è il "trasferimento a blocchi di bit" dei dati relativi ai colori da un rettangolo di origine di pixel a un rettangolo di destinazione di pixel.  
  
 Con Windows Forms, BitBlt viene eseguita utilizzando il metodo <xref:System.Drawing.Graphics.CopyFromScreen%2A> della classe <xref:System.Drawing.Graphics>. Nei parametri del metodo si specificano l'origine e la destinazione (come punti), le dimensioni dell'area da copiare e l'oggetto Graphics utilizzato per disegnare la nuova forma.  
  
 Nell'esempio seguente viene disegnata una forma sul form nel gestore dell'evento <xref:System.Windows.Forms.Control.Paint>. Viene quindi usato il metodo <xref:System.Drawing.Graphics.CopyFromScreen%2A> per duplicare la forma.  
  
> [!NOTE]
> Se si imposta la proprietà <xref:System.Windows.Forms.Control.DoubleBuffered%2A> del modulo su `true`, verrà creato un doppio buffer per il codice basato su grafica nell'evento <xref:System.Windows.Forms.Control.Paint>. Sebbene non sia possibile ottenere miglioramenti in termini di prestazioni quando si usa il codice riportato di seguito, è opportuno tenere presente quando si lavora con codice di manipolazione grafica più complesso.  
  
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
 Il codice precedente viene eseguito nel gestore dell'evento <xref:System.Windows.Forms.Control.Paint> del form in modo che la grafica venga mantenute quando il modulo viene ridisegnato. Di conseguenza, non chiamare metodi correlati alla grafica nel gestore dell'evento <xref:System.Windows.Forms.Form.Load>, perché il contenuto disegnato non verrà ridisegnato se il form viene ridimensionato o nascosto da un altro form.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.CopyPixelOperation>
- <xref:System.Drawing.Graphics.FillRectangle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.OnPaint%2A?displayProperty=nameWithType>
- [Grafica e disegno in Windows Form](graphics-and-drawing-in-windows-forms.md)
- [Uso di un oggetto Pen per creare linee e forme](using-a-pen-to-draw-lines-and-shapes.md)
