---
title: Controlli costitutivi
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], constituent controls
- constituent controls [Windows Forms]
- user controls [Windows Forms], constituent controls
ms.assetid: 5565e720-198b-4bbd-a2bd-c447ba641798
ms.openlocfilehash: 2865a3d85bd56151038ee90c18d199d3a584b5d4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182420"
---
# <a name="constituent-controls"></a><span data-ttu-id="731d1-102">Controlli costitutivi</span><span class="sxs-lookup"><span data-stu-id="731d1-102">Constituent Controls</span></span>
<span data-ttu-id="731d1-103">I controlli che costituiscono un controllo utente, detti anche *controlli costitutivi*, offrono scarsa flessibilità in termini di rendering personalizzato della grafica.</span><span class="sxs-lookup"><span data-stu-id="731d1-103">The controls that make up a user control, or *constituent controls* as they are termed, are relatively inflexible when it comes to custom graphics rendering.</span></span> <span data-ttu-id="731d1-104">Tutti i controlli Windows Form gestiscono <xref:System.Windows.Forms.Control.OnPaint%2A> il proprio rendering tramite il proprio metodo.</span><span class="sxs-lookup"><span data-stu-id="731d1-104">All Windows Forms controls handle their own rendering through their own <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="731d1-105">Poiché questo metodo è protetto, non è accessibile allo sviluppatore e quindi non è possibile evitarne l'esecuzione quando il controllo viene disegnato.</span><span class="sxs-lookup"><span data-stu-id="731d1-105">Because this method is protected, it is not accessible to the developer, and thus cannot be prevented from executing when the control is painted.</span></span> <span data-ttu-id="731d1-106">Ciò non implica tuttavia che non sia possibile aggiungere codice per modificare l'aspetto dei controlli costitutivi.</span><span class="sxs-lookup"><span data-stu-id="731d1-106">This does not mean, however, that you cannot add code to affect the appearance of constituent controls.</span></span> <span data-ttu-id="731d1-107">Per eseguire un altro rendering, è possibile aggiungere un gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="731d1-107">Additional rendering can be accomplished by adding an event handler.</span></span> <span data-ttu-id="731d1-108">Si supponga, ad esempio, di creare un <xref:System.Windows.Forms.UserControl> con un pulsante denominato `MyButton`.</span><span class="sxs-lookup"><span data-stu-id="731d1-108">For example, suppose you were authoring a <xref:System.Windows.Forms.UserControl> with a button named `MyButton`.</span></span> <span data-ttu-id="731d1-109">Se si desidera disporre di un rendering <xref:System.Web.UI.WebControls.Button>aggiuntivo oltre a quello fornito da , è necessario aggiungere codice al controllo utente simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="731d1-109">If you wished to have additional rendering beyond what was provided by the <xref:System.Web.UI.WebControls.Button>, you would add code to your user control similar to the following:</span></span>  
  
```vb  
Public Sub MyPaint(ByVal sender as Object, e as PaintEventArgs) Handles _  
   MyButton.Paint  
   'Additional rendering code goes here  
End Sub  
```  
  
```csharp  
// Add the event handler to the button's Paint event.  
MyButton.Paint +=
   new System.Windows.Forms.PaintEventHandler (this.MyPaint);  
// Create the custom painting method.  
protected void MyPaint (object sender,
System.Windows.Forms.PaintEventArgs e)  
{  
   // Additional rendering code goes here.  
}  
```  
  
> [!NOTE]
> <span data-ttu-id="731d1-110">Alcuni controlli Windows Form, ad <xref:System.Windows.Forms.TextBox>esempio , vengono disegnati direttamente da Windows.</span><span class="sxs-lookup"><span data-stu-id="731d1-110">Some Windows Forms controls, such as <xref:System.Windows.Forms.TextBox>, are painted directly by Windows.</span></span> <span data-ttu-id="731d1-111">In questi casi, il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo non viene mai chiamato e pertanto l'esempio precedente non verrà mai chiamato.</span><span class="sxs-lookup"><span data-stu-id="731d1-111">In these instances, the <xref:System.Windows.Forms.Control.OnPaint%2A> method is never called, and thus the above example will never be called.</span></span>  
  
 <span data-ttu-id="731d1-112">Viene quindi creato un metodo eseguito ogni volta che viene eseguito l'evento `MyButton.Paint`, aggiungendo in tal modo un'altra rappresentazione grafica al controllo.</span><span class="sxs-lookup"><span data-stu-id="731d1-112">This creates a method that executes every time the `MyButton.Paint` event executes, thereby adding additional graphical representation to your control.</span></span> <span data-ttu-id="731d1-113">Si noti che ciò non impedisce l'esecuzione di `MyButton.OnPaint` e quindi tutti i disegni eseguiti normalmente da un pulsante continueranno a essere eseguiti in aggiunta al disegno personalizzato.</span><span class="sxs-lookup"><span data-stu-id="731d1-113">Note that this does not prevent the execution of `MyButton.OnPaint`, and thus all of the painting usually performed by a button will still be performed in addition to your custom painting.</span></span> <span data-ttu-id="731d1-114">Per informazioni dettagliate sulla tecnologia GDI+ e sul rendering personalizzato, vedere [Creazione di immagini grafiche con GDI+](../advanced/how-to-create-graphics-objects-for-drawing.md).</span><span class="sxs-lookup"><span data-stu-id="731d1-114">For details about GDI+ technology and custom rendering, see the [Creating Graphical Images with GDI+](../advanced/how-to-create-graphics-objects-for-drawing.md).</span></span> <span data-ttu-id="731d1-115">Per avere una rappresentazione univoca del controllo, è consigliabile creare un controllo ereditato per cui scrivere il codice di rendering personalizzato.</span><span class="sxs-lookup"><span data-stu-id="731d1-115">If you wish to have a unique representation of your control, your best course of action is to create an inherited control, and to write custom rendering code for it.</span></span> <span data-ttu-id="731d1-116">Per informazioni dettagliate, vedere [Controlli creati dall'utente](user-drawn-controls.md).</span><span class="sxs-lookup"><span data-stu-id="731d1-116">For details, see [User-Drawn Controls](user-drawn-controls.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="731d1-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="731d1-117">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [<span data-ttu-id="731d1-118">Controlli creati dall'utente</span><span class="sxs-lookup"><span data-stu-id="731d1-118">User-Drawn Controls</span></span>](user-drawn-controls.md)
- [<span data-ttu-id="731d1-119">Procedura: creare oggetti Graphics per disegnare</span><span class="sxs-lookup"><span data-stu-id="731d1-119">How to: Create Graphics Objects for Drawing</span></span>](../advanced/how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="731d1-120">Tipi di controlli personalizzati</span><span class="sxs-lookup"><span data-stu-id="731d1-120">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
