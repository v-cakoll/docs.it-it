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
ms.openlocfilehash: 863726a6264f01de9f00296b4a64b9fd1bb96765
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182039"
---
# <a name="overriding-the-onpaint-method"></a>Override del metodo OnPaint
I passaggi di base per eseguire l'override di qualsiasi evento definito in .NET Framework sono identici e sono riepilogati nell'elenco seguente.  
  
#### <a name="to-override-an-inherited-event"></a>Per eseguire l'override di un evento ereditatoTo override an inherited event  
  
1. Eseguire l'override del metodo `On` *Protetto EventName.*  
  
2. Chiamare `On`il metodo *EventName* della classe `On`base dal metodo *EventName* sottoposto a override, in modo che i delegati registrati ricevano l'evento.  
  
 L'evento <xref:System.Windows.Forms.Control.Paint> viene descritto in dettaglio perché <xref:System.Windows.Forms.Control.Paint> ogni controllo Windows <xref:System.Windows.Forms.Control>Form deve eseguire l'override dell'evento che eredita da . La <xref:System.Windows.Forms.Control> classe base non sa come un controllo derivato deve essere <xref:System.Windows.Forms.Control.OnPaint%2A> disegnato e non fornisce alcuna logica di disegno nel metodo. Il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo <xref:System.Windows.Forms.Control> di inviare <xref:System.Windows.Forms.Control.Paint> semplicemente l'evento ai ricevitori di eventi registrati.  
  
 Se si è utilizzato l'esempio in [Procedura: sviluppare un controllo Windows Form semplice,](how-to-develop-a-simple-windows-forms-control.md)è stato visualizzato un esempio di override del <xref:System.Windows.Forms.Control.OnPaint%2A> metodo. Il frammento di codice seguente è tratto da tale esempio.  
  
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
  
 La <xref:System.Windows.Forms.PaintEventArgs> classe contiene <xref:System.Windows.Forms.Control.Paint> i dati per l'evento. Ha due proprietà, come illustrato nel codice seguente.  
  
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
  
 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>è il rettangolo da disegnare <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> e la <xref:System.Drawing.Graphics> proprietà fa riferimento a un oggetto. Le classi <xref:System.Drawing?displayProperty=nameWithType> nello spazio dei nomi sono classi gestite che forniscono l'accesso alle funzionalità di GDI, la nuova libreria grafica di Windows. L'oggetto <xref:System.Drawing.Graphics> dispone di metodi per disegnare punti, stringhe, linee, archi, ellissi e molte altre forme.  
  
 Un controllo richiama <xref:System.Windows.Forms.Control.OnPaint%2A> il metodo ogni volta che è necessario modificarne la visualizzazione. Questo metodo a <xref:System.Windows.Forms.Control.Paint> sua volta genera l'evento.  
  
## <a name="see-also"></a>Vedere anche

- [Events](../../../standard/events/index.md)
- [Rendering di un controllo Windows Form](rendering-a-windows-forms-control.md)
- [Definizione di un evento](defining-an-event-in-windows-forms-controls.md)
