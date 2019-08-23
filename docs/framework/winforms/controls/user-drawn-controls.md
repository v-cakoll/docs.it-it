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
ms.openlocfilehash: 50036f5bef323368b4970a080ca7a70cf94252d6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966492"
---
# <a name="user-drawn-controls"></a>Controlli creati dall'utente
Il .NET Framework offre la possibilità di sviluppare facilmente controlli personalizzati. È possibile creare un controllo utente, ovvero un set di controlli standard associati dal codice, oppure è possibile progettare un controllo personalizzato da zero. È anche possibile usare l'ereditarietà per creare un controllo che eredita da un controllo esistente e aggiungervi le funzionalità intrinseche. Indipendentemente dall'approccio usato, il .NET Framework fornisce la funzionalità per creare un'interfaccia grafica personalizzata per qualsiasi controllo creato.  
  
 Il disegno di un controllo viene eseguito dall'esecuzione del codice nel <xref:System.Windows.Forms.Control.OnPaint%2A> metodo del controllo. Il singolo argomento del <xref:System.Windows.Forms.Control.OnPaint%2A> metodo è un <xref:System.Windows.Forms.PaintEventArgs> oggetto che fornisce tutte le informazioni e le funzionalità necessarie per eseguire il rendering del controllo. <xref:System.Windows.Forms.PaintEventArgs> Fornisce come proprietà due oggetti Principal che verranno utilizzati nel rendering del controllo:  
  
- <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>oggetto: rettangolo che rappresenta la parte del controllo che verrà disegnata. Può trattarsi dell'intero controllo o parte del controllo a seconda della modalità di disegno del controllo.  
  
- <xref:System.Drawing.Graphics>oggetto: incapsula diversi oggetti e metodi orientati alla grafica che forniscono la funzionalità necessaria per creare il controllo.  
  
 Per altre informazioni sull' <xref:System.Drawing.Graphics> oggetto e su come usarlo, vedere [procedura: Creare oggetti grafici per il](../advanced/how-to-create-graphics-objects-for-drawing.md)disegno.  
  
 L' <xref:System.Windows.Forms.Control.OnPaint%2A> evento viene generato ogni volta che il controllo viene disegnato o aggiornato sullo schermo e l' <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> oggetto rappresenta il rettangolo in cui verrà eseguita la verniciatura. Se è necessario aggiornare l'intero controllo, il <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> rappresenterà le dimensioni dell'intero controllo. Se è necessario aggiornare solo parte del controllo, tuttavia, l' <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> oggetto rappresenterà solo l'area che deve essere ridisegnato. Un esempio di questo caso è che un controllo è stato parzialmente nascosto da un altro controllo o modulo nell'interfaccia utente.  
  
 Quando si eredita dalla <xref:System.Windows.Forms.Control> classe, è necessario eseguire l'override del metodo e fornire codice per il rendering della <xref:System.Windows.Forms.Control.OnPaint%2A> grafica all'interno di. Se si desidera fornire un'interfaccia grafica personalizzata a un controllo utente o a un controllo ereditato, è anche possibile eseguire questa operazione eseguendo l'override <xref:System.Windows.Forms.Control.OnPaint%2A> del metodo. Un esempio è illustrato di seguito:  
  
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
  
 Nell'esempio precedente viene illustrato come eseguire il rendering di un controllo con una rappresentazione grafica molto semplice. Viene chiamato il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo della classe di base, viene creato un <xref:System.Drawing.Pen> oggetto con il quale disegnare e infine viene disegnata un'ellisse nel rettangolo determinato da <xref:System.Windows.Forms.Control.Location%2A> e <xref:System.Windows.Forms.Control.Size%2A> del controllo. Sebbene la maggior parte del codice di rendering risulti significativamente più complicata, <xref:System.Drawing.Graphics> <xref:System.Windows.Forms.PaintEventArgs> in questo esempio viene illustrato l'utilizzo dell'oggetto contenuto nell'oggetto. Si noti che se si eredita da una classe che dispone già di una rappresentazione grafica, ad esempio <xref:System.Windows.Forms.UserControl> o <xref:System.Windows.Forms.Button>, e non si desidera incorporare tale rappresentazione nel rendering, non è necessario chiamare la classe di <xref:System.Windows.Forms.Control.OnPaint%2A> base Metodo.  
  
 Il codice nel <xref:System.Windows.Forms.Control.OnPaint%2A> metodo del controllo verrà eseguito quando il controllo viene creato per la prima volta e ogni volta che viene aggiornato. Per assicurarsi che il controllo venga ridisegnato ogni volta che viene ridimensionato, aggiungere la riga seguente al costruttore del controllo:  
  
```vb  
SetStyle(ControlStyles.ResizeRedraw, True)  
```  
  
```csharp  
SetStyle(ControlStyles.ResizeRedraw, true);  
```  
  
> [!NOTE]
> Utilizzare la <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> proprietà per implementare un controllo non rettangolare.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Control.Region%2A>
- <xref:System.Windows.Forms.ControlStyles>
- <xref:System.Drawing.Graphics>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Windows.Forms.PaintEventArgs>
- [Procedura: Creare oggetti grafici per il disegno](../advanced/how-to-create-graphics-objects-for-drawing.md)
- [Controlli costitutivi](constituent-controls.md)
- [Tipi di controlli personalizzati](varieties-of-custom-controls.md)
