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
ms.openlocfilehash: e9eab78695db128c0538914c5364aaa54c135403
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54509961"
---
# <a name="user-drawn-controls"></a>Controlli creati dall'utente
.NET Framework offre la possibilità di sviluppare con facilità i propri controlli. È possibile creare un controllo utente, ovvero un set di controlli standard intercorrelate da codice, oppure è possibile progettare un controllo personalizzato da zero backup. È anche possibile utilizzare l'ereditarietà per creare un controllo che eredita da un controllo esistente e aggiungere estenderne le funzionalità intrinseche. Qualunque approccio si utilizza, .NET Framework fornisce la funzionalità per tracciare un'interfaccia grafica personalizzata per qualsiasi controllo creato.  
  
 Disegno di un controllo avviene tramite l'esecuzione del codice del controllo <xref:System.Windows.Forms.Control.OnPaint%2A> (metodo). L'unico argomento del <xref:System.Windows.Forms.Control.OnPaint%2A> metodo è un <xref:System.Windows.Forms.PaintEventArgs> oggetto che fornisce tutte le informazioni e le funzionalità necessarie per il rendering del controllo. Il <xref:System.Windows.Forms.PaintEventArgs> fornisce come proprietà di due oggetti principal che verranno usati per il rendering del controllo:  
  
-   <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> oggetto, il rettangolo che rappresenta la parte del controllo che verrà disegnata. Può trattarsi dell'intero controllo o parte del controllo a seconda del modo in cui il controllo viene disegnato.  
  
-   <xref:System.Drawing.Graphics> oggetto - incapsula diversi metodi che forniscono le funzionalità necessarie per disegnare il controllo e gli oggetti orientati alla grafica.  
  
 Per altre informazioni sul <xref:System.Drawing.Graphics> oggetto e come usarlo, vedere [come: Creare oggetti Graphics per disegnare](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).  
  
 Il <xref:System.Windows.Forms.Control.OnPaint%2A> evento viene generato ogni volta che il controllo viene disegnato o aggiornato nella schermata e <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> oggetto rappresenta il rettangolo in cui verrà eseguito il disegno. Se l'intero controllo deve essere aggiornato, il <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> rappresenterà la dimensione dell'intero controllo. Se solo parte del controllo deve essere aggiornato, tuttavia, il <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> oggetto rappresenterà solo nell'area che deve essere ridisegnato. Un esempio di questo caso sarebbe quando un controllo è stato parzialmente oscurato da un altro controllo o form nell'interfaccia utente.  
  
 Quando si eredita dal <xref:System.Windows.Forms.Control> (classe), è necessario eseguire l'override di <xref:System.Windows.Forms.Control.OnPaint%2A> metodo e fornire il codice di rendering della grafica all'interno. Se si desidera fornire un'interfaccia grafica personalizzata per un controllo utente o un controllo ereditato, è anche possibile farlo eseguendo l'override di <xref:System.Windows.Forms.Control.OnPaint%2A> (metodo). Di seguito è riportato un esempio:  
  
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
  
 Nell'esempio precedente viene illustrato come eseguire il rendering di un controllo con una rappresentazione grafica molto semplice. Chiama il <xref:System.Windows.Forms.Control.OnPaint%2A> il metodo della classe di base, crea un <xref:System.Drawing.Pen> dell'oggetto con cui disegnare e infine Disegna un ellisse nel rettangolo è determinato dalle <xref:System.Windows.Forms.Control.Location%2A> e <xref:System.Windows.Forms.Control.Size%2A> del controllo. Sebbene gran parte del codice per il rendering sarà molto più complessa rispetto a questo, in questo esempio illustra l'uso del <xref:System.Drawing.Graphics> oggetti contenuti all'interno di <xref:System.Windows.Forms.PaintEventArgs> oggetto. Si noti che se sta ereditando da una classe che dispone già di una rappresentazione grafica, ad esempio <xref:System.Windows.Forms.UserControl> oppure <xref:System.Windows.Forms.Button>e non si desidera incorporare il rendering di tale rappresentazione, non è necessario chiamare la classe di base <xref:System.Windows.Forms.Control.OnPaint%2A> metodo.  
  
 Il codice nel <xref:System.Windows.Forms.Control.OnPaint%2A> metodo del controllo, verrà eseguito quando il controllo prima viene disegnato e ogni volta che viene aggiornato. Per assicurarsi che il controllo viene ridisegnato ogni volta che viene ridimensionato, aggiungere la riga seguente al costruttore del controllo:  
  
```vb  
SetStyle(ControlStyles.ResizeRedraw, True)  
```  
  
```csharp  
SetStyle(ControlStyles.ResizeRedraw, true);  
```  
  
> [!NOTE]
>  Usare il <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> proprietà per implementare un controllo non rettangolari.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.Control.Region%2A>
- <xref:System.Windows.Forms.ControlStyles>
- <xref:System.Drawing.Graphics>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Windows.Forms.PaintEventArgs>
- [Procedura: Creare oggetti Graphics per disegnare](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)
- [Controlli costitutivi](../../../../docs/framework/winforms/controls/constituent-controls.md)
- [Tipi di controlli personalizzati](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
