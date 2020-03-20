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
# <a name="user-drawn-controls"></a><span data-ttu-id="7ed0c-102">Controlli creati dall'utente</span><span class="sxs-lookup"><span data-stu-id="7ed0c-102">User-Drawn Controls</span></span>
<span data-ttu-id="7ed0c-103">.NET Framework offre la possibilità di sviluppare facilmente controlli personalizzati.</span><span class="sxs-lookup"><span data-stu-id="7ed0c-103">The .NET Framework provides you with the ability to easily develop your own controls.</span></span> <span data-ttu-id="7ed0c-104">È possibile creare un controllo utente, ovvero un set di controlli standard associati dal codice, oppure è possibile progettare il proprio controllo da zero.</span><span class="sxs-lookup"><span data-stu-id="7ed0c-104">You can create a user control, which is a set of standard controls bound together by code, or you can design your own control from the ground up.</span></span> <span data-ttu-id="7ed0c-105">È anche possibile usare l'ereditarietà per creare un controllo che eredita da un controllo esistente e aggiungere alla relativa funzionalità intrinseca.</span><span class="sxs-lookup"><span data-stu-id="7ed0c-105">You can even use inheritance to create a control that inherits from an existing control and add to its inherent functionality.</span></span> <span data-ttu-id="7ed0c-106">Indipendentemente dall'approccio utilizzato, .NET Framework fornisce la funzionalità per disegnare un'interfaccia grafica personalizzata per qualsiasi controllo creato.</span><span class="sxs-lookup"><span data-stu-id="7ed0c-106">Whatever approach you use, the .NET Framework provides the functionality to draw a custom graphical interface for any control you create.</span></span>  
  
 <span data-ttu-id="7ed0c-107">Il disegno di un controllo viene eseguito dall'esecuzione di codice nel metodo del <xref:System.Windows.Forms.Control.OnPaint%2A> controllo.</span><span class="sxs-lookup"><span data-stu-id="7ed0c-107">Painting of a control is accomplished by the execution of code in the control's <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="7ed0c-108">Il singolo argomento <xref:System.Windows.Forms.Control.OnPaint%2A> del <xref:System.Windows.Forms.PaintEventArgs> metodo è un oggetto che fornisce tutte le informazioni e le funzionalità necessarie per eseguire il rendering del controllo.</span><span class="sxs-lookup"><span data-stu-id="7ed0c-108">The single argument of the <xref:System.Windows.Forms.Control.OnPaint%2A> method is a <xref:System.Windows.Forms.PaintEventArgs> object that provides all of the information and functionality required to render your control.</span></span> <span data-ttu-id="7ed0c-109">L'oggetto <xref:System.Windows.Forms.PaintEventArgs> fornisce come proprietà due oggetti Principal che verranno utilizzati nel rendering del controllo:</span><span class="sxs-lookup"><span data-stu-id="7ed0c-109">The <xref:System.Windows.Forms.PaintEventArgs> provides as properties two principal objects that will be used in the rendering of your control:</span></span>  
  
- <span data-ttu-id="7ed0c-110"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>object - il rettangolo che rappresenta la parte del controllo che verrà disegnata.</span><span class="sxs-lookup"><span data-stu-id="7ed0c-110"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object - the rectangle that represents the part of the control that will be drawn.</span></span> <span data-ttu-id="7ed0c-111">Può trattarsi dell'intero controllo o di parte del controllo a seconda di come viene disegnato il controllo.</span><span class="sxs-lookup"><span data-stu-id="7ed0c-111">This can be the entire control, or part of the control depending on how the control is drawn.</span></span>  
  
- <span data-ttu-id="7ed0c-112"><xref:System.Drawing.Graphics>object : incapsula diversi oggetti e metodi orientati alla grafica che forniscono la funzionalità necessaria per disegnare il controllo.</span><span class="sxs-lookup"><span data-stu-id="7ed0c-112"><xref:System.Drawing.Graphics> object - encapsulates several graphics-oriented objects and methods that provide the functionality necessary to draw your control.</span></span>  
  
 <span data-ttu-id="7ed0c-113">Per ulteriori informazioni <xref:System.Drawing.Graphics> sull'oggetto e su come utilizzarlo, vedere [Procedura: creare oggetti grafici per](../advanced/how-to-create-graphics-objects-for-drawing.md)il disegno .</span><span class="sxs-lookup"><span data-stu-id="7ed0c-113">For more information on the <xref:System.Drawing.Graphics> object and how to use it, see [How to: Create Graphics Objects for Drawing](../advanced/how-to-create-graphics-objects-for-drawing.md).</span></span>  
  
 <span data-ttu-id="7ed0c-114">L'evento <xref:System.Windows.Forms.Control.OnPaint%2A> viene generato ogni volta che il controllo <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> viene disegnato o aggiornato sullo schermo e l'oggetto rappresenta il rettangolo in cui verrà eseguito il disegno.</span><span class="sxs-lookup"><span data-stu-id="7ed0c-114">The <xref:System.Windows.Forms.Control.OnPaint%2A> event is fired whenever the control is drawn or refreshed on the screen, and the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object represents the rectangle in which painting will take place.</span></span> <span data-ttu-id="7ed0c-115">Se è necessario aggiornare l'intero controllo, <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> la funzione rappresenterà la dimensione dell'intero controllo.</span><span class="sxs-lookup"><span data-stu-id="7ed0c-115">If the entire control needs to be refreshed, the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> will represent the size of the entire control.</span></span> <span data-ttu-id="7ed0c-116">Se solo una parte del controllo deve essere <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> aggiornata, tuttavia, l'oggetto rappresenterà solo l'area che deve essere ridisegnata.</span><span class="sxs-lookup"><span data-stu-id="7ed0c-116">If only part of the control needs to be refreshed, however, the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object will represent only the region that needs to be redrawn.</span></span> <span data-ttu-id="7ed0c-117">Un esempio di tale caso potrebbe essere quando un controllo è stato parzialmente oscurato da un altro controllo o form nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="7ed0c-117">An example of such a case would be when a control was partially obscured by another control or form in the user interface.</span></span>  
  
 <span data-ttu-id="7ed0c-118">Quando si eredita <xref:System.Windows.Forms.Control> dalla classe , <xref:System.Windows.Forms.Control.OnPaint%2A> è necessario eseguire l'override del metodo e fornire il codice di rendering della grafica all'interno.</span><span class="sxs-lookup"><span data-stu-id="7ed0c-118">When inheriting from the <xref:System.Windows.Forms.Control> class, you must override the <xref:System.Windows.Forms.Control.OnPaint%2A> method and provide graphics-rendering code within.</span></span> <span data-ttu-id="7ed0c-119">Se si desidera fornire un'interfaccia grafica personalizzata a un controllo utente o a <xref:System.Windows.Forms.Control.OnPaint%2A> un controllo ereditato, è anche possibile eseguire l'override del metodo .</span><span class="sxs-lookup"><span data-stu-id="7ed0c-119">If you want to provide a custom graphical interface to a user control or an inherited control, you can also do so by overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="7ed0c-120">Di seguito è riportato un esempio:</span><span class="sxs-lookup"><span data-stu-id="7ed0c-120">An example is shown below:</span></span>  
  
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
  
 <span data-ttu-id="7ed0c-121">Nell'esempio precedente viene illustrato come eseguire il rendering di un controllo con una rappresentazione grafica molto semplice.</span><span class="sxs-lookup"><span data-stu-id="7ed0c-121">The preceding example demonstrates how to render a control with a very simple graphical representation.</span></span> <span data-ttu-id="7ed0c-122">Chiama il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo della classe base, <xref:System.Drawing.Pen> crea un oggetto con cui disegnare e infine <xref:System.Windows.Forms.Control.Location%2A> disegna un'ellisse nel rettangolo determinato dal e <xref:System.Windows.Forms.Control.Size%2A> del controllo.</span><span class="sxs-lookup"><span data-stu-id="7ed0c-122">It calls the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class, it creates a <xref:System.Drawing.Pen> object with which to draw, and finally draws an ellipse in the rectangle determined by the <xref:System.Windows.Forms.Control.Location%2A> and <xref:System.Windows.Forms.Control.Size%2A> of the control.</span></span> <span data-ttu-id="7ed0c-123">Anche se la maggior parte del codice di rendering sarà <xref:System.Drawing.Graphics> significativamente più <xref:System.Windows.Forms.PaintEventArgs> complicato di questo, in questo esempio viene illustrato l'utilizzo dell'oggetto contenuto all'oggetto.</span><span class="sxs-lookup"><span data-stu-id="7ed0c-123">Although most rendering code will be significantly more complicated than this, this example demonstrates the use of the <xref:System.Drawing.Graphics> object contained within the <xref:System.Windows.Forms.PaintEventArgs> object.</span></span> <span data-ttu-id="7ed0c-124">Si noti che se si eredita da una classe <xref:System.Windows.Forms.UserControl> che <xref:System.Windows.Forms.Button>dispone già di una rappresentazione grafica, ad esempio o , <xref:System.Windows.Forms.Control.OnPaint%2A> e non si desidera incorporare tale rappresentazione nel rendering, non è necessario chiamare il metodo della classe base.</span><span class="sxs-lookup"><span data-stu-id="7ed0c-124">Note that if you are inheriting from a class that already has a graphical representation, such as <xref:System.Windows.Forms.UserControl> or <xref:System.Windows.Forms.Button>, and you do not wish to incorporate that representation into your rendering, you should not call your base class's <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
 <span data-ttu-id="7ed0c-125">Il codice <xref:System.Windows.Forms.Control.OnPaint%2A> nel metodo del controllo verrà eseguito quando il controllo viene disegnato per la prima volta e ogni volta che viene aggiornato.</span><span class="sxs-lookup"><span data-stu-id="7ed0c-125">The code in the <xref:System.Windows.Forms.Control.OnPaint%2A> method of your control will execute when the control is first drawn, and whenever it is refreshed.</span></span> <span data-ttu-id="7ed0c-126">Per assicurarsi che il controllo venga ridisegnato ogni volta che viene ridimensionato, aggiungere la riga seguente al costruttore del controllo:</span><span class="sxs-lookup"><span data-stu-id="7ed0c-126">To ensure that your control is redrawn every time it is resized, add the following line to the constructor of your control:</span></span>  
  
```vb  
SetStyle(ControlStyles.ResizeRedraw, True)  
```  
  
```csharp  
SetStyle(ControlStyles.ResizeRedraw, true);  
```  
  
> [!NOTE]
> <span data-ttu-id="7ed0c-127">Utilizzare <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> la proprietà per implementare un controllo non rettangolare.</span><span class="sxs-lookup"><span data-stu-id="7ed0c-127">Use the <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> property to implement a non-rectangular control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ed0c-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ed0c-128">See also</span></span>

- <xref:System.Windows.Forms.Control.Region%2A>
- <xref:System.Windows.Forms.ControlStyles>
- <xref:System.Drawing.Graphics>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Windows.Forms.PaintEventArgs>
- [<span data-ttu-id="7ed0c-129">Procedura: creare oggetti Graphics per disegnare</span><span class="sxs-lookup"><span data-stu-id="7ed0c-129">How to: Create Graphics Objects for Drawing</span></span>](../advanced/how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="7ed0c-130">Controlli costitutivi</span><span class="sxs-lookup"><span data-stu-id="7ed0c-130">Constituent Controls</span></span>](constituent-controls.md)
- [<span data-ttu-id="7ed0c-131">Tipi di controlli personalizzati</span><span class="sxs-lookup"><span data-stu-id="7ed0c-131">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
