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
ms.openlocfilehash: fc41158e9a3d5d331b391f0f28701612012becf7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537216"
---
# <a name="overriding-the-onpaint-method"></a><span data-ttu-id="4ee02-102">Override del metodo OnPaint</span><span class="sxs-lookup"><span data-stu-id="4ee02-102">Overriding the OnPaint Method</span></span>
<span data-ttu-id="4ee02-103">I passaggi di base per eseguire l'override di qualsiasi evento definito nel [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] sono identici e vengono riepilogate nell'elenco seguente.</span><span class="sxs-lookup"><span data-stu-id="4ee02-103">The basic steps for overriding any event defined in the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] are identical and are summarized in the following list.</span></span>  
  
#### <a name="to-override-an-inherited-event"></a><span data-ttu-id="4ee02-104">Per eseguire l'override di un evento ereditato</span><span class="sxs-lookup"><span data-stu-id="4ee02-104">To override an inherited event</span></span>  
  
1.  <span data-ttu-id="4ee02-105">Eseguire l'override protetto `On` *EventName* metodo.</span><span class="sxs-lookup"><span data-stu-id="4ee02-105">Override the protected `On`*EventName* method.</span></span>  
  
2.  <span data-ttu-id="4ee02-106">Chiamare il `On` *EventName* metodo della classe di base da sottoposto a override `On` *EventName* (metodo), in modo che i delegati registrati ricevano l'evento.</span><span class="sxs-lookup"><span data-stu-id="4ee02-106">Call the `On`*EventName* method of the base class from the overridden `On`*EventName* method, so that registered delegates receive the event.</span></span>  
  
 <span data-ttu-id="4ee02-107">Il <xref:System.Windows.Forms.Control.Paint> evento è illustrato in dettaglio di seguito perché è necessario eseguire l'override di tutti i controlli Windows Form di <xref:System.Windows.Forms.Control.Paint> evento che eredita da <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="4ee02-107">The <xref:System.Windows.Forms.Control.Paint> event is discussed in detail here because every Windows Forms control must override the <xref:System.Windows.Forms.Control.Paint> event that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="4ee02-108">La base <xref:System.Windows.Forms.Control> non sa come deve essere disegnato un controllo derivato di classe e non fornisce alcuna logica di disegno di <xref:System.Windows.Forms.Control.OnPaint%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="4ee02-108">The base <xref:System.Windows.Forms.Control> class does not know how a derived control needs to be drawn and does not provide any painting logic in the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="4ee02-109">Il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo <xref:System.Windows.Forms.Control> invia semplicemente il <xref:System.Windows.Forms.Control.Paint> ricevitori di eventi registrati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="4ee02-109">The <xref:System.Windows.Forms.Control.OnPaint%2A> method of <xref:System.Windows.Forms.Control> simply dispatches the <xref:System.Windows.Forms.Control.Paint> event to registered event receivers.</span></span>  
  
 <span data-ttu-id="4ee02-110">Se tramite l'esempio in cui si è lavorato [procedura: sviluppare un controllo Windows Form semplice](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md), è stato illustrato un esempio di override di <xref:System.Windows.Forms.Control.OnPaint%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="4ee02-110">If you worked through the sample in [How to: Develop a Simple Windows Forms Control](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md), you have seen an example of overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="4ee02-111">Frammento di codice seguente è tratto dall'esempio.</span><span class="sxs-lookup"><span data-stu-id="4ee02-111">The following code fragment is taken from that sample.</span></span>  
  
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
public class FirstControl : Control{  
   public FirstControl() {}  
   protected override void OnPaint(PaintEventArgs e) {  
      // Call the OnPaint method of the base class.  
      base.OnPaint(e);  
      // Call methods of the System.Drawing.Graphics object.  
      e.Graphics.DrawString(Text, Font, new SolidBrush(ForeColor), ClientRectangle);  
   }   
}   
```  
  
 <span data-ttu-id="4ee02-112">Il <xref:System.Windows.Forms.PaintEventArgs> classe contiene i dati per il <xref:System.Windows.Forms.Control.Paint> evento.</span><span class="sxs-lookup"><span data-stu-id="4ee02-112">The <xref:System.Windows.Forms.PaintEventArgs> class contains data for the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="4ee02-113">Include due proprietà, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="4ee02-113">It has two properties, as shown in the following code.</span></span>  
  
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
  
 <span data-ttu-id="4ee02-114"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> il rettangolo da disegnare e il <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> proprietà fa riferimento a un <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="4ee02-114"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> is the rectangle to be painted, and the <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> property refers to a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="4ee02-115">Le classi di <xref:System.Drawing?displayProperty=nameWithType> dello spazio dei nomi gestiti classi che forniscono accesso alle funzionalità di [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], nella nuova libreria di immagini di Windows.</span><span class="sxs-lookup"><span data-stu-id="4ee02-115">The classes in the <xref:System.Drawing?displayProperty=nameWithType> namespace are managed classes that provide access to the functionality of [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], the new Windows graphics library.</span></span> <span data-ttu-id="4ee02-116">Il <xref:System.Drawing.Graphics> oggetto dispone di metodi per disegnare punti, stringhe, linee, archi, puntini di sospensione e molte altre forme.</span><span class="sxs-lookup"><span data-stu-id="4ee02-116">The <xref:System.Drawing.Graphics> object has methods to draw points, strings, lines, arcs, ellipses, and many other shapes.</span></span>  
  
 <span data-ttu-id="4ee02-117">Richiama un controllo relativo <xref:System.Windows.Forms.Control.OnPaint%2A> metodo ogni volta che è necessario modificare l'aspetto.</span><span class="sxs-lookup"><span data-stu-id="4ee02-117">A control invokes its <xref:System.Windows.Forms.Control.OnPaint%2A> method whenever it needs to change its visual display.</span></span> <span data-ttu-id="4ee02-118">Questo metodo genera a sua volta il <xref:System.Windows.Forms.Control.Paint> evento.</span><span class="sxs-lookup"><span data-stu-id="4ee02-118">This method in turn raises the <xref:System.Windows.Forms.Control.Paint> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ee02-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ee02-119">See Also</span></span>  
 [<span data-ttu-id="4ee02-120">Eventi</span><span class="sxs-lookup"><span data-stu-id="4ee02-120">Events</span></span>](../../../../docs/standard/events/index.md)  
 [<span data-ttu-id="4ee02-121">Rendering di un controllo di Windows Form</span><span class="sxs-lookup"><span data-stu-id="4ee02-121">Rendering a Windows Forms Control</span></span>](../../../../docs/framework/winforms/controls/rendering-a-windows-forms-control.md)  
 [<span data-ttu-id="4ee02-122">Definizione di un evento</span><span class="sxs-lookup"><span data-stu-id="4ee02-122">Defining an Event</span></span>](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)
