---
title: 'Procedura: copiare i pixel per ridurre lo sfarfallio in Windows Form'
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
helpviewer_keywords:
- bitblt
- graphics [Windows Forms], copying
- flicker [Windows Forms], reducing in Windows Forms
- graphics [Windows Forms], reducing flicker
- pixels [Windows Forms], copying
- flicker
- bit-block transfer
ms.assetid: 33b76910-13a3-4521-be98-5c097341ae3b
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 17253e21739911d4aa0541fde9ae205b0be1c5a2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-copy-pixels-for-reducing-flicker-in-windows-forms"></a>Procedura: copiare i pixel per ridurre lo sfarfallio in Windows Form
Quando si aggiunge un'animazione a un simbolo semplice, gli utenti possono verificarsi in alcuni casi lo sfarfallio o altri effetti visivi indesiderati. Un modo per limitare questo problema è necessario utilizzare un processo "bitblt" sull'oggetto grafico. BitBlt è il "blocchi di bit trasferimento" di dati relativi al colore da un'origine a un rettangolo di pixel a un rettangolo di destinazione di pixel.  
  
 In Windows Form, bitblt viene ottenuto utilizzando il <xref:System.Drawing.Graphics.CopyFromScreen%2A> metodo la <xref:System.Drawing.Graphics> classe. Nei parametri del metodo, specificare l'origine e destinazione (come punti), le dimensioni dell'area di copia e l'oggetto graphics utilizzato per disegnare la nuova forma.  
  
 Nell'esempio seguente, una forma viene disegnata sul form nel relativo <xref:System.Windows.Forms.Control.Paint> gestore dell'evento. Quindi, <xref:System.Drawing.Graphics.CopyFromScreen%2A> metodo viene utilizzato per duplicare la forma.  
  
> [!NOTE]
>  L'impostazione della maschera <xref:System.Windows.Forms.Control.DoubleBuffered%2A> proprietà `true` renderà codice basato su grafica il <xref:System.Windows.Forms.Control.Paint> evento essere doppio buffer. Mentre ciò non avrà eventuali miglioramenti delle prestazioni possono essere facilmente distinte quando si utilizza il codice riportato di seguito, è necessario tenere presenti quando si utilizza codice manipolazione grafica più complessi.  
  
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
 Il codice precedente viene eseguito il formato <xref:System.Windows.Forms.Control.Paint> gestore dell'evento in modo che gli elementi grafici permanenti quando il form viene ridisegnato. Di conseguenza, non chiamare metodi correlati a grafica <xref:System.Windows.Forms.Form.Load> gestore eventi, perché il contenuto disegnato non verrà ridisegnato se il form viene ridimensionato o nascosto da un altro formato.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Drawing.CopyPixelOperation>  
 <xref:System.Drawing.Graphics.FillRectangle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Control.OnPaint%2A?displayProperty=nameWithType>  
 [Grafica e disegno in Windows Form](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Uso di un oggetto Pen per creare linee e forme](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
