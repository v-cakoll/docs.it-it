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
# <a name="user-drawn-controls"></a><span data-ttu-id="55ee7-102">Controlli creati dall'utente</span><span class="sxs-lookup"><span data-stu-id="55ee7-102">User-Drawn Controls</span></span>
<span data-ttu-id="55ee7-103">Il .NET Framework offre la possibilità di sviluppare facilmente controlli personalizzati.</span><span class="sxs-lookup"><span data-stu-id="55ee7-103">The .NET Framework provides you with the ability to easily develop your own controls.</span></span> <span data-ttu-id="55ee7-104">È possibile creare un controllo utente, ovvero un set di controlli standard associati dal codice, oppure è possibile progettare un controllo personalizzato da zero.</span><span class="sxs-lookup"><span data-stu-id="55ee7-104">You can create a user control, which is a set of standard controls bound together by code, or you can design your own control from the ground up.</span></span> <span data-ttu-id="55ee7-105">È anche possibile usare l'ereditarietà per creare un controllo che eredita da un controllo esistente e aggiungervi le funzionalità intrinseche.</span><span class="sxs-lookup"><span data-stu-id="55ee7-105">You can even use inheritance to create a control that inherits from an existing control and add to its inherent functionality.</span></span> <span data-ttu-id="55ee7-106">Indipendentemente dall'approccio usato, il .NET Framework fornisce la funzionalità per creare un'interfaccia grafica personalizzata per qualsiasi controllo creato.</span><span class="sxs-lookup"><span data-stu-id="55ee7-106">Whatever approach you use, the .NET Framework provides the functionality to draw a custom graphical interface for any control you create.</span></span>  
  
 <span data-ttu-id="55ee7-107">Il disegno di un controllo viene eseguito dall'esecuzione del codice nel <xref:System.Windows.Forms.Control.OnPaint%2A> metodo del controllo.</span><span class="sxs-lookup"><span data-stu-id="55ee7-107">Painting of a control is accomplished by the execution of code in the control's <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="55ee7-108">Il singolo argomento del <xref:System.Windows.Forms.Control.OnPaint%2A> metodo è un <xref:System.Windows.Forms.PaintEventArgs> oggetto che fornisce tutte le informazioni e le funzionalità necessarie per eseguire il rendering del controllo.</span><span class="sxs-lookup"><span data-stu-id="55ee7-108">The single argument of the <xref:System.Windows.Forms.Control.OnPaint%2A> method is a <xref:System.Windows.Forms.PaintEventArgs> object that provides all of the information and functionality required to render your control.</span></span> <span data-ttu-id="55ee7-109"><xref:System.Windows.Forms.PaintEventArgs> Fornisce come proprietà due oggetti Principal che verranno utilizzati nel rendering del controllo:</span><span class="sxs-lookup"><span data-stu-id="55ee7-109">The <xref:System.Windows.Forms.PaintEventArgs> provides as properties two principal objects that will be used in the rendering of your control:</span></span>  
  
- <span data-ttu-id="55ee7-110"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>oggetto: rettangolo che rappresenta la parte del controllo che verrà disegnata.</span><span class="sxs-lookup"><span data-stu-id="55ee7-110"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object - the rectangle that represents the part of the control that will be drawn.</span></span> <span data-ttu-id="55ee7-111">Può trattarsi dell'intero controllo o parte del controllo a seconda della modalità di disegno del controllo.</span><span class="sxs-lookup"><span data-stu-id="55ee7-111">This can be the entire control, or part of the control depending on how the control is drawn.</span></span>  
  
- <span data-ttu-id="55ee7-112"><xref:System.Drawing.Graphics>oggetto: incapsula diversi oggetti e metodi orientati alla grafica che forniscono la funzionalità necessaria per creare il controllo.</span><span class="sxs-lookup"><span data-stu-id="55ee7-112"><xref:System.Drawing.Graphics> object - encapsulates several graphics-oriented objects and methods that provide the functionality necessary to draw your control.</span></span>  
  
 <span data-ttu-id="55ee7-113">Per altre informazioni sull' <xref:System.Drawing.Graphics> oggetto e su come usarlo, vedere [procedura: Creare oggetti grafici per il](../advanced/how-to-create-graphics-objects-for-drawing.md)disegno.</span><span class="sxs-lookup"><span data-stu-id="55ee7-113">For more information on the <xref:System.Drawing.Graphics> object and how to use it, see [How to: Create Graphics Objects for Drawing](../advanced/how-to-create-graphics-objects-for-drawing.md).</span></span>  
  
 <span data-ttu-id="55ee7-114">L' <xref:System.Windows.Forms.Control.OnPaint%2A> evento viene generato ogni volta che il controllo viene disegnato o aggiornato sullo schermo e l' <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> oggetto rappresenta il rettangolo in cui verrà eseguita la verniciatura.</span><span class="sxs-lookup"><span data-stu-id="55ee7-114">The <xref:System.Windows.Forms.Control.OnPaint%2A> event is fired whenever the control is drawn or refreshed on the screen, and the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object represents the rectangle in which painting will take place.</span></span> <span data-ttu-id="55ee7-115">Se è necessario aggiornare l'intero controllo, il <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> rappresenterà le dimensioni dell'intero controllo.</span><span class="sxs-lookup"><span data-stu-id="55ee7-115">If the entire control needs to be refreshed, the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> will represent the size of the entire control.</span></span> <span data-ttu-id="55ee7-116">Se è necessario aggiornare solo parte del controllo, tuttavia, l' <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> oggetto rappresenterà solo l'area che deve essere ridisegnato.</span><span class="sxs-lookup"><span data-stu-id="55ee7-116">If only part of the control needs to be refreshed, however, the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object will represent only the region that needs to be redrawn.</span></span> <span data-ttu-id="55ee7-117">Un esempio di questo caso è che un controllo è stato parzialmente nascosto da un altro controllo o modulo nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="55ee7-117">An example of such a case would be when a control was partially obscured by another control or form in the user interface.</span></span>  
  
 <span data-ttu-id="55ee7-118">Quando si eredita dalla <xref:System.Windows.Forms.Control> classe, è necessario eseguire l'override del metodo e fornire codice per il rendering della <xref:System.Windows.Forms.Control.OnPaint%2A> grafica all'interno di.</span><span class="sxs-lookup"><span data-stu-id="55ee7-118">When inheriting from the <xref:System.Windows.Forms.Control> class, you must override the <xref:System.Windows.Forms.Control.OnPaint%2A> method and provide graphics-rendering code within.</span></span> <span data-ttu-id="55ee7-119">Se si desidera fornire un'interfaccia grafica personalizzata a un controllo utente o a un controllo ereditato, è anche possibile eseguire questa operazione eseguendo l'override <xref:System.Windows.Forms.Control.OnPaint%2A> del metodo.</span><span class="sxs-lookup"><span data-stu-id="55ee7-119">If you want to provide a custom graphical interface to a user control or an inherited control, you can also do so by overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="55ee7-120">Un esempio è illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="55ee7-120">An example is shown below:</span></span>  
  
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
  
 <span data-ttu-id="55ee7-121">Nell'esempio precedente viene illustrato come eseguire il rendering di un controllo con una rappresentazione grafica molto semplice.</span><span class="sxs-lookup"><span data-stu-id="55ee7-121">The preceding example demonstrates how to render a control with a very simple graphical representation.</span></span> <span data-ttu-id="55ee7-122">Viene chiamato il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo della classe di base, viene creato un <xref:System.Drawing.Pen> oggetto con il quale disegnare e infine viene disegnata un'ellisse nel rettangolo determinato da <xref:System.Windows.Forms.Control.Location%2A> e <xref:System.Windows.Forms.Control.Size%2A> del controllo.</span><span class="sxs-lookup"><span data-stu-id="55ee7-122">It calls the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class, it creates a <xref:System.Drawing.Pen> object with which to draw, and finally draws an ellipse in the rectangle determined by the <xref:System.Windows.Forms.Control.Location%2A> and <xref:System.Windows.Forms.Control.Size%2A> of the control.</span></span> <span data-ttu-id="55ee7-123">Sebbene la maggior parte del codice di rendering risulti significativamente più complicata, <xref:System.Drawing.Graphics> <xref:System.Windows.Forms.PaintEventArgs> in questo esempio viene illustrato l'utilizzo dell'oggetto contenuto nell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="55ee7-123">Although most rendering code will be significantly more complicated than this, this example demonstrates the use of the <xref:System.Drawing.Graphics> object contained within the <xref:System.Windows.Forms.PaintEventArgs> object.</span></span> <span data-ttu-id="55ee7-124">Si noti che se si eredita da una classe che dispone già di una rappresentazione grafica, ad esempio <xref:System.Windows.Forms.UserControl> o <xref:System.Windows.Forms.Button>, e non si desidera incorporare tale rappresentazione nel rendering, non è necessario chiamare la classe di <xref:System.Windows.Forms.Control.OnPaint%2A> base Metodo.</span><span class="sxs-lookup"><span data-stu-id="55ee7-124">Note that if you are inheriting from a class that already has a graphical representation, such as <xref:System.Windows.Forms.UserControl> or <xref:System.Windows.Forms.Button>, and you do not wish to incorporate that representation into your rendering, you should not call your base class's <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
 <span data-ttu-id="55ee7-125">Il codice nel <xref:System.Windows.Forms.Control.OnPaint%2A> metodo del controllo verrà eseguito quando il controllo viene creato per la prima volta e ogni volta che viene aggiornato.</span><span class="sxs-lookup"><span data-stu-id="55ee7-125">The code in the <xref:System.Windows.Forms.Control.OnPaint%2A> method of your control will execute when the control is first drawn, and whenever it is refreshed.</span></span> <span data-ttu-id="55ee7-126">Per assicurarsi che il controllo venga ridisegnato ogni volta che viene ridimensionato, aggiungere la riga seguente al costruttore del controllo:</span><span class="sxs-lookup"><span data-stu-id="55ee7-126">To ensure that your control is redrawn every time it is resized, add the following line to the constructor of your control:</span></span>  
  
```vb  
SetStyle(ControlStyles.ResizeRedraw, True)  
```  
  
```csharp  
SetStyle(ControlStyles.ResizeRedraw, true);  
```  
  
> [!NOTE]
> <span data-ttu-id="55ee7-127">Utilizzare la <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> proprietà per implementare un controllo non rettangolare.</span><span class="sxs-lookup"><span data-stu-id="55ee7-127">Use the <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> property to implement a non-rectangular control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55ee7-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55ee7-128">See also</span></span>

- <xref:System.Windows.Forms.Control.Region%2A>
- <xref:System.Windows.Forms.ControlStyles>
- <xref:System.Drawing.Graphics>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Windows.Forms.PaintEventArgs>
- [<span data-ttu-id="55ee7-129">Procedura: Creare oggetti grafici per il disegno</span><span class="sxs-lookup"><span data-stu-id="55ee7-129">How to: Create Graphics Objects for Drawing</span></span>](../advanced/how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="55ee7-130">Controlli costitutivi</span><span class="sxs-lookup"><span data-stu-id="55ee7-130">Constituent Controls</span></span>](constituent-controls.md)
- [<span data-ttu-id="55ee7-131">Tipi di controlli personalizzati</span><span class="sxs-lookup"><span data-stu-id="55ee7-131">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
