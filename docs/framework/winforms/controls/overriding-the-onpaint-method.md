---
title: Override del metodo OnPaint
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Paint event [Windows Forms], handling in Windows Forms custom control
- OnPaint method [Windows Forms], overriding in Windows Forms custom controls
ms.assetid: e9ca2723-0107-4540-bb21-4f5ffb4a9906
ms.openlocfilehash: fbc0a82f82afcc59384246b58437d521d56d708b
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2018
ms.locfileid: "44756275"
---
# <a name="overriding-the-onpaint-method"></a>Override del metodo OnPaint
I passaggi di base per eseguire l'override di qualsiasi evento definito nel [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] sono identiche e sono riepilogate nell'elenco seguente.  
  
#### <a name="to-override-an-inherited-event"></a>Eseguire l'override di un evento ereditato  
  
1.  Sostituire il metodo protetto `On` *EventName* (metodo).  
  
2.  Chiamare il `On` *EventName* metodo della classe di base da sottoposto a override `On` *EventName* metodo, in modo che i delegati registrati ricevano l'evento.  
  
 Il <xref:System.Windows.Forms.Control.Paint> perché è necessario eseguire l'override di tutti i controlli Windows Form, l'evento è discusso in dettaglio di seguito il <xref:System.Windows.Forms.Control.Paint> evento che eredita da <xref:System.Windows.Forms.Control>. La base <xref:System.Windows.Forms.Control> classe non sa come un controllo derivato deve essere disegnato e non fornisce alcuna logica di disegno di <xref:System.Windows.Forms.Control.OnPaint%2A> (metodo). Il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo di <xref:System.Windows.Forms.Control> invia semplicemente il <xref:System.Windows.Forms.Control.Paint> ricevitori di eventi registrati dell'evento.  
  
 Se si è lavorato tramite l'esempio in [procedura: sviluppare un semplice controllo di Windows Form](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md), è stato illustrato un esempio di override di <xref:System.Windows.Forms.Control.OnPaint%2A> (metodo). Il frammento di codice seguente è tratto dall'esempio.  
  
```vb  
Public Class FirstControl  
   Inherits Control  
  
   Public Sub New()  
   End Sub  
  
   Protected Overrides Sub OnPaint(e As PaintEventArgs)  
      ' Call the OnPaint method of the base class.  
      MyBase.OnPaint(e)  
      ' Call methods of the System.Drawing.Graphics object.  
      e.Graphics.DrawString(Text, Font, New SolidBrush(ForeColor), RectangleF.op_Implicit(ClientRectangle))  
   End Sub  
End Class   
```  
  
```csharp  
public class FirstControl : Control {  
   public FirstControl() {}  
   protected override void OnPaint(PaintEventArgs e) {  
      // Call the OnPaint method of the base class.  
      base.OnPaint(e);  
      // Call methods of the System.Drawing.Graphics object.  
      e.Graphics.DrawString(Text, Font, new SolidBrush(ForeColor), ClientRectangle);  
   }   
}   
```  
  
 Il <xref:System.Windows.Forms.PaintEventArgs> classe contiene i dati per il <xref:System.Windows.Forms.Control.Paint> evento. Ha due proprietà, come illustrato nel codice seguente.  
  
```vb  
Public Class PaintEventArgs  
   Inherits EventArgs  
   ...  
   Public ReadOnly Property ClipRectangle() As System.Drawing.Rectangle  
      ...  
   End Property  
  
   Public ReadOnly Property Graphics() As System.Drawing.Graphics  
      ...  
   End Property   
   ...  
End Class  
```  
  
```csharp  
public class PaintEventArgs : EventArgs {  
...  
    public System.Drawing.Rectangle ClipRectangle {}  
    public System.Drawing.Graphics Graphics {}  
...  
}  
```  
  
 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> è il rettangolo da disegnare e il <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> proprietà fa riferimento a un <xref:System.Drawing.Graphics> oggetto. Le classi nel <xref:System.Drawing?displayProperty=nameWithType> dello spazio dei nomi vengono gestite le classi che forniscono l'accesso alle funzionalità di [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], la nuova libreria grafica di Windows. Il <xref:System.Drawing.Graphics> oggetto dispone di metodi per disegnare punti, stringhe, linee, archi, sui puntini di sospensione e molte altre forme.  
  
 Richiama un controllo relativo <xref:System.Windows.Forms.Control.OnPaint%2A> metodo ogni volta che è necessario modificare l'aspetto. Questo metodo è a sua volta genera il <xref:System.Windows.Forms.Control.Paint> evento.  
  
## <a name="see-also"></a>Vedere anche  
 [Eventi](../../../../docs/standard/events/index.md)  
 [Rendering di un controllo di Windows Form](../../../../docs/framework/winforms/controls/rendering-a-windows-forms-control.md)  
 [Definizione di un evento](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)
