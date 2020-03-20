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
ms.openlocfilehash: c68c8c88376cfe7295962264c466030115f2f3db
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182014"
---
# <a name="user-drawn-controls"></a>Controlli creati dall'utente
.NET Framework offre la possibilità di sviluppare facilmente controlli personalizzati. È possibile creare un controllo utente, ovvero un set di controlli standard associati dal codice, oppure è possibile progettare il proprio controllo da zero. È anche possibile usare l'ereditarietà per creare un controllo che eredita da un controllo esistente e aggiungere alla relativa funzionalità intrinseca. Indipendentemente dall'approccio utilizzato, .NET Framework fornisce la funzionalità per disegnare un'interfaccia grafica personalizzata per qualsiasi controllo creato.  
  
 Il disegno di un controllo viene eseguito dall'esecuzione di codice nel metodo del <xref:System.Windows.Forms.Control.OnPaint%2A> controllo. Il singolo argomento <xref:System.Windows.Forms.Control.OnPaint%2A> del <xref:System.Windows.Forms.PaintEventArgs> metodo è un oggetto che fornisce tutte le informazioni e le funzionalità necessarie per eseguire il rendering del controllo. L'oggetto <xref:System.Windows.Forms.PaintEventArgs> fornisce come proprietà due oggetti Principal che verranno utilizzati nel rendering del controllo:  
  
- <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>object - il rettangolo che rappresenta la parte del controllo che verrà disegnata. Può trattarsi dell'intero controllo o di parte del controllo a seconda di come viene disegnato il controllo.  
  
- <xref:System.Drawing.Graphics>object : incapsula diversi oggetti e metodi orientati alla grafica che forniscono la funzionalità necessaria per disegnare il controllo.  
  
 Per ulteriori informazioni <xref:System.Drawing.Graphics> sull'oggetto e su come utilizzarlo, vedere [Procedura: creare oggetti grafici per](../advanced/how-to-create-graphics-objects-for-drawing.md)il disegno .  
  
 L'evento <xref:System.Windows.Forms.Control.OnPaint%2A> viene generato ogni volta che il controllo <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> viene disegnato o aggiornato sullo schermo e l'oggetto rappresenta il rettangolo in cui verrà eseguito il disegno. Se è necessario aggiornare l'intero controllo, <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> la funzione rappresenterà la dimensione dell'intero controllo. Se solo una parte del controllo deve essere <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> aggiornata, tuttavia, l'oggetto rappresenterà solo l'area che deve essere ridisegnata. Un esempio di tale caso potrebbe essere quando un controllo è stato parzialmente oscurato da un altro controllo o form nell'interfaccia utente.  
  
 Quando si eredita <xref:System.Windows.Forms.Control> dalla classe , <xref:System.Windows.Forms.Control.OnPaint%2A> è necessario eseguire l'override del metodo e fornire il codice di rendering della grafica all'interno. Se si desidera fornire un'interfaccia grafica personalizzata a un controllo utente o a <xref:System.Windows.Forms.Control.OnPaint%2A> un controllo ereditato, è anche possibile eseguire l'override del metodo . Di seguito è riportato un esempio:  
  
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
  
 Nell'esempio precedente viene illustrato come eseguire il rendering di un controllo con una rappresentazione grafica molto semplice. Chiama il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo della classe base, <xref:System.Drawing.Pen> crea un oggetto con cui disegnare e infine <xref:System.Windows.Forms.Control.Location%2A> disegna un'ellisse nel rettangolo determinato dal e <xref:System.Windows.Forms.Control.Size%2A> del controllo. Anche se la maggior parte del codice di rendering sarà <xref:System.Drawing.Graphics> significativamente più <xref:System.Windows.Forms.PaintEventArgs> complicato di questo, in questo esempio viene illustrato l'utilizzo dell'oggetto contenuto all'oggetto. Si noti che se si eredita da una classe <xref:System.Windows.Forms.UserControl> che <xref:System.Windows.Forms.Button>dispone già di una rappresentazione grafica, ad esempio o , <xref:System.Windows.Forms.Control.OnPaint%2A> e non si desidera incorporare tale rappresentazione nel rendering, non è necessario chiamare il metodo della classe base.  
  
 Il codice <xref:System.Windows.Forms.Control.OnPaint%2A> nel metodo del controllo verrà eseguito quando il controllo viene disegnato per la prima volta e ogni volta che viene aggiornato. Per assicurarsi che il controllo venga ridisegnato ogni volta che viene ridimensionato, aggiungere la riga seguente al costruttore del controllo:  
  
```vb  
SetStyle(ControlStyles.ResizeRedraw, True)  
```  
  
```csharp  
SetStyle(ControlStyles.ResizeRedraw, true);  
```  
  
> [!NOTE]
> Utilizzare <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> la proprietà per implementare un controllo non rettangolare.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Control.Region%2A>
- <xref:System.Windows.Forms.ControlStyles>
- <xref:System.Drawing.Graphics>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Windows.Forms.PaintEventArgs>
- [Procedura: creare oggetti Graphics per disegnare](../advanced/how-to-create-graphics-objects-for-drawing.md)
- [Controlli costitutivi](constituent-controls.md)
- [Tipi di controlli personalizzati](varieties-of-custom-controls.md)
