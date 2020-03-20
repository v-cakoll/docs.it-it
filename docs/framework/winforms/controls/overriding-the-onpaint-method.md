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
# <a name="overriding-the-onpaint-method"></a><span data-ttu-id="061fd-102">Override del metodo OnPaint</span><span class="sxs-lookup"><span data-stu-id="061fd-102">Overriding the OnPaint Method</span></span>
<span data-ttu-id="061fd-103">I passaggi di base per eseguire l'override di qualsiasi evento definito in .NET Framework sono identici e sono riepilogati nell'elenco seguente.</span><span class="sxs-lookup"><span data-stu-id="061fd-103">The basic steps for overriding any event defined in the .NET Framework are identical and are summarized in the following list.</span></span>  
  
#### <a name="to-override-an-inherited-event"></a><span data-ttu-id="061fd-104">Per eseguire l'override di un evento ereditatoTo override an inherited event</span><span class="sxs-lookup"><span data-stu-id="061fd-104">To override an inherited event</span></span>  
  
1. <span data-ttu-id="061fd-105">Eseguire l'override del metodo `On` *Protetto EventName.*</span><span class="sxs-lookup"><span data-stu-id="061fd-105">Override the protected `On`*EventName* method.</span></span>  
  
2. <span data-ttu-id="061fd-106">Chiamare `On`il metodo *EventName* della classe `On`base dal metodo *EventName* sottoposto a override, in modo che i delegati registrati ricevano l'evento.</span><span class="sxs-lookup"><span data-stu-id="061fd-106">Call the `On`*EventName* method of the base class from the overridden `On`*EventName* method, so that registered delegates receive the event.</span></span>  
  
 <span data-ttu-id="061fd-107">L'evento <xref:System.Windows.Forms.Control.Paint> viene descritto in dettaglio perché <xref:System.Windows.Forms.Control.Paint> ogni controllo Windows <xref:System.Windows.Forms.Control>Form deve eseguire l'override dell'evento che eredita da .</span><span class="sxs-lookup"><span data-stu-id="061fd-107">The <xref:System.Windows.Forms.Control.Paint> event is discussed in detail here because every Windows Forms control must override the <xref:System.Windows.Forms.Control.Paint> event that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="061fd-108">La <xref:System.Windows.Forms.Control> classe base non sa come un controllo derivato deve essere <xref:System.Windows.Forms.Control.OnPaint%2A> disegnato e non fornisce alcuna logica di disegno nel metodo.</span><span class="sxs-lookup"><span data-stu-id="061fd-108">The base <xref:System.Windows.Forms.Control> class does not know how a derived control needs to be drawn and does not provide any painting logic in the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="061fd-109">Il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo <xref:System.Windows.Forms.Control> di inviare <xref:System.Windows.Forms.Control.Paint> semplicemente l'evento ai ricevitori di eventi registrati.</span><span class="sxs-lookup"><span data-stu-id="061fd-109">The <xref:System.Windows.Forms.Control.OnPaint%2A> method of <xref:System.Windows.Forms.Control> simply dispatches the <xref:System.Windows.Forms.Control.Paint> event to registered event receivers.</span></span>  
  
 <span data-ttu-id="061fd-110">Se si è utilizzato l'esempio in [Procedura: sviluppare un controllo Windows Form semplice,](how-to-develop-a-simple-windows-forms-control.md)è stato visualizzato un esempio di override del <xref:System.Windows.Forms.Control.OnPaint%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="061fd-110">If you worked through the sample in [How to: Develop a Simple Windows Forms Control](how-to-develop-a-simple-windows-forms-control.md), you have seen an example of overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="061fd-111">Il frammento di codice seguente è tratto da tale esempio.</span><span class="sxs-lookup"><span data-stu-id="061fd-111">The following code fragment is taken from that sample.</span></span>  
  
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
  
 <span data-ttu-id="061fd-112">La <xref:System.Windows.Forms.PaintEventArgs> classe contiene <xref:System.Windows.Forms.Control.Paint> i dati per l'evento.</span><span class="sxs-lookup"><span data-stu-id="061fd-112">The <xref:System.Windows.Forms.PaintEventArgs> class contains data for the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="061fd-113">Ha due proprietà, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="061fd-113">It has two properties, as shown in the following code.</span></span>  
  
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
  
 <span data-ttu-id="061fd-114"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>è il rettangolo da disegnare <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> e la <xref:System.Drawing.Graphics> proprietà fa riferimento a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="061fd-114"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> is the rectangle to be painted, and the <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> property refers to a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="061fd-115">Le classi <xref:System.Drawing?displayProperty=nameWithType> nello spazio dei nomi sono classi gestite che forniscono l'accesso alle funzionalità di GDI, la nuova libreria grafica di Windows.</span><span class="sxs-lookup"><span data-stu-id="061fd-115">The classes in the <xref:System.Drawing?displayProperty=nameWithType> namespace are managed classes that provide access to the functionality of GDI+, the new Windows graphics library.</span></span> <span data-ttu-id="061fd-116">L'oggetto <xref:System.Drawing.Graphics> dispone di metodi per disegnare punti, stringhe, linee, archi, ellissi e molte altre forme.</span><span class="sxs-lookup"><span data-stu-id="061fd-116">The <xref:System.Drawing.Graphics> object has methods to draw points, strings, lines, arcs, ellipses, and many other shapes.</span></span>  
  
 <span data-ttu-id="061fd-117">Un controllo richiama <xref:System.Windows.Forms.Control.OnPaint%2A> il metodo ogni volta che è necessario modificarne la visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="061fd-117">A control invokes its <xref:System.Windows.Forms.Control.OnPaint%2A> method whenever it needs to change its visual display.</span></span> <span data-ttu-id="061fd-118">Questo metodo a <xref:System.Windows.Forms.Control.Paint> sua volta genera l'evento.</span><span class="sxs-lookup"><span data-stu-id="061fd-118">This method in turn raises the <xref:System.Windows.Forms.Control.Paint> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="061fd-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="061fd-119">See also</span></span>

- [<span data-ttu-id="061fd-120">Events</span><span class="sxs-lookup"><span data-stu-id="061fd-120">Events</span></span>](../../../standard/events/index.md)
- [<span data-ttu-id="061fd-121">Rendering di un controllo Windows Form</span><span class="sxs-lookup"><span data-stu-id="061fd-121">Rendering a Windows Forms Control</span></span>](rendering-a-windows-forms-control.md)
- [<span data-ttu-id="061fd-122">Definizione di un evento</span><span class="sxs-lookup"><span data-stu-id="061fd-122">Defining an Event</span></span>](defining-an-event-in-windows-forms-controls.md)
