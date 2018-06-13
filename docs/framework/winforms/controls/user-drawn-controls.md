---
title: Controlli creati dall'utente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], user-drawn
- OnPaint method [Windows Forms]
- user-drawn controls [Windows Forms]
ms.assetid: 034af4b5-457f-4160-a937-22891817faa8
ms.openlocfilehash: 26b4f062c120bf543a5e597fc8c734e8cc336bd8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33542197"
---
# <a name="user-drawn-controls"></a>Controlli creati dall'utente
.NET Framework offre la possibilità di sviluppare facilmente controlli personalizzati. È possibile creare un controllo utente, che è un set standard di controlli di raggruppati dal codice, oppure è possibile progettare un controllo personalizzato da zero backup. È anche possibile utilizzare l'ereditarietà per creare un controllo che eredita da un controllo esistente e aggiungere estenderne le funzionalità intrinseche. Il meccanismo adottato, .NET Framework fornisce la funzionalità per creare un'interfaccia grafica personalizzata per qualsiasi controllo creato.  
  
 Il disegno di un controllo viene realizzato mediante l'esecuzione di codice del controllo <xref:System.Windows.Forms.Control.OnPaint%2A> metodo. L'unico argomento del <xref:System.Windows.Forms.Control.OnPaint%2A> metodo è un <xref:System.Windows.Forms.PaintEventArgs> oggetto che fornisce tutte le informazioni e le funzionalità necessarie per il rendering del controllo. Il <xref:System.Windows.Forms.PaintEventArgs> fornisce come proprietà due oggetti principali che verranno utilizzati per il rendering del controllo:  
  
-   <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> oggetto, il rettangolo che rappresenta la parte del controllo che verrà disegnato. Può trattarsi dell'intero controllo, o parte del controllo a seconda di come viene disegnato il controllo.  
  
-   <xref:System.Drawing.Graphics> oggetto - incapsula diversi metodi che forniscono le funzionalità necessarie per disegnare il controllo e gli oggetti orientati alla grafica.  
  
 Per ulteriori informazioni sul <xref:System.Drawing.Graphics> oggetto e come usarlo, vedere [procedura: creare oggetti di grafica per il disegno](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).  
  
 Il <xref:System.Windows.Forms.Control.OnPaint%2A> evento viene generato ogni volta che il controllo viene creato o aggiornato nella schermata e <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> oggetto rappresenta il rettangolo in cui il disegno verrà eseguita. Se l'intero controllo deve essere aggiornato, il <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> rappresenterà la dimensione dell'intero controllo. Se solo parte del controllo deve essere aggiornato, tuttavia, il <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> oggetto rappresenterà solo l'area che deve essere ridisegnato. Un esempio di questo caso sarebbe quando un controllo è stato parzialmente nascosto da un altro controllo o un modulo nell'interfaccia utente.  
  
 Quando si eredita dal <xref:System.Windows.Forms.Control> (classe), è necessario eseguire l'override di <xref:System.Windows.Forms.Control.OnPaint%2A> (metodo) e fornire il codice del rendering della grafica. Se si desidera fornire un'interfaccia grafica personalizzata a un controllo utente o un controllo ereditato, è anche possibile eseguire l'override di <xref:System.Windows.Forms.Control.OnPaint%2A> metodo. Un esempio è illustrato di seguito:  
  
```vb  
Protected Overrides Sub OnPaint(ByVal e As PaintEventArgs)  
   ' Call the OnPaint method of the base class.  
   MyBase.OnPaint(e)  
  
   ' Declare and instantiate a drawing pen.  
   Using myPen As System.Drawing.Pen = New System.Drawing.Pen(Color.Aqua)  
      ' Draw an aqua rectangle in the rectangle represented by the control.  
      e.Graphics.DrawRectangle(myPen, New Rectangle(Me.Location, Me.Size))  
   End Using
End Sub  
```  
  
```csharp  
protected override void OnPaint(PaintEventArgs e)  
{  
   // Call the OnPaint method of the base class.  
   base.OnPaint(e);  
  
   // Declare and instantiate a new pen.  
   using (System.Drawing.Pen myPen = new System.Drawing.Pen(Color.Aqua))  
   {
      // Draw an aqua rectangle in the rectangle represented by the control.  
      e.Graphics.DrawRectangle(myPen, new Rectangle(this.Location,   
         this.Size));  
   }
}  
```  
  
 Nell'esempio precedente viene illustrato come eseguire il rendering di un controllo con una rappresentazione grafica molto semplice. Chiama il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo della classe di base, viene creato un <xref:System.Drawing.Pen> dell'oggetto con cui disegnare e infine Disegna un ellisse nel rettangolo determinato dal <xref:System.Windows.Forms.Control.Location%2A> e <xref:System.Windows.Forms.Control.Size%2A> del controllo. Sebbene la maggior parte del codice di rendering sarà molto più complesso, in questo esempio viene illustrato l'utilizzo del <xref:System.Drawing.Graphics> oggetto contenuto all'interno di <xref:System.Windows.Forms.PaintEventArgs> oggetto. Si noti che se sta ereditando da una classe che dispone già di una rappresentazione grafica, ad esempio <xref:System.Windows.Forms.UserControl> o <xref:System.Windows.Forms.Button>e non si desidera incorporare tale rappresentazione il rendering, non è necessario chiamare la classe base <xref:System.Windows.Forms.Control.OnPaint%2A> metodo.  
  
 Il codice di <xref:System.Windows.Forms.Control.OnPaint%2A> metodo del controllo verrà eseguito quando il controllo viene disegnato prima, e ogni volta che viene aggiornato. Per garantire che il controllo viene ridisegnato ogni volta che viene ridimensionato, aggiungere la riga seguente al costruttore del controllo:  
  
```vb  
SetStyle(ControlStyles.ResizeRedraw, True)  
```  
  
```csharp  
SetStyle(ControlStyles.ResizeRedraw, true);  
```  
  
> [!NOTE]
>  Utilizzare il <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> proprietà per implementare un controllo non rettangolari.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Control.Region%2A>  
 <xref:System.Windows.Forms.ControlStyles>  
 <xref:System.Drawing.Graphics>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 <xref:System.Windows.Forms.PaintEventArgs>  
 [Procedura: Creare oggetti Graphics per disegnare](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [Controlli costitutivi](../../../../docs/framework/winforms/controls/constituent-controls.md)  
 [Tipi di controlli personalizzati](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
