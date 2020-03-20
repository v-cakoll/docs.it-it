---
title: 'Procedura: creare oggetti Graphics per disegnare'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], creating
- images [Windows Forms], creating
- GDI+, creating images
ms.assetid: 162861f9-f050-445e-8abb-b2c43a918b8b
ms.openlocfilehash: d591d65904484e33285e5db7aa99760f3e1909d3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142433"
---
# <a name="how-to-create-graphics-objects-for-drawing"></a><span data-ttu-id="623ae-102">Procedura: creare oggetti Graphics per disegnare</span><span class="sxs-lookup"><span data-stu-id="623ae-102">How to: Create Graphics Objects for Drawing</span></span>
<span data-ttu-id="623ae-103">Prima di poter disegnare linee e forme, eseguire il rendering del testo o <xref:System.Drawing.Graphics> visualizzare e modificare le immagini con GDI, è necessario creare un oggetto.</span><span class="sxs-lookup"><span data-stu-id="623ae-103">Before you can draw lines and shapes, render text, or display and manipulate images with GDI+, you need to create a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="623ae-104">L'oggetto <xref:System.Drawing.Graphics> rappresenta una superficie di disegno GDI, ed è l'oggetto utilizzato per creare immagini grafiche.</span><span class="sxs-lookup"><span data-stu-id="623ae-104">The <xref:System.Drawing.Graphics> object represents a GDI+ drawing surface, and is the object that is used to create graphical images.</span></span>  
  
 <span data-ttu-id="623ae-105">L'utilizzo della grafica prevede due passaggi:</span><span class="sxs-lookup"><span data-stu-id="623ae-105">There are two steps in working with graphics:</span></span>  
  
1. <span data-ttu-id="623ae-106">Creazione <xref:System.Drawing.Graphics> di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="623ae-106">Creating a <xref:System.Drawing.Graphics> object.</span></span>  
  
2. <span data-ttu-id="623ae-107">Utilizzo <xref:System.Drawing.Graphics> dell'oggetto per disegnare linee e forme, eseguire il rendering del testo o visualizzare e manipolare le immagini.</span><span class="sxs-lookup"><span data-stu-id="623ae-107">Using the <xref:System.Drawing.Graphics> object to draw lines and shapes, render text, or display and manipulate images.</span></span>  
  
## <a name="creating-a-graphics-object"></a><span data-ttu-id="623ae-108">Creazione di un oggetto GraphicsCreating a Graphics Object</span><span class="sxs-lookup"><span data-stu-id="623ae-108">Creating a Graphics Object</span></span>  
 <span data-ttu-id="623ae-109">Un oggetto grafico può essere creato in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="623ae-109">A graphics object can be created in a variety of ways.</span></span>  
  
#### <a name="to-create-a-graphics-object"></a><span data-ttu-id="623ae-110">Per creare un oggetto grafico</span><span class="sxs-lookup"><span data-stu-id="623ae-110">To create a graphics object</span></span>  
  
- <span data-ttu-id="623ae-111">Ricevere un riferimento a un oggetto <xref:System.Windows.Forms.PaintEventArgs> grafico <xref:System.Windows.Forms.Control.Paint> come parte dell'evento di un form o di un controllo.</span><span class="sxs-lookup"><span data-stu-id="623ae-111">Receive a reference to a graphics object as part of the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event of a form or control.</span></span> <span data-ttu-id="623ae-112">In genere si ottiene un riferimento a un oggetto grafico durante la creazione di codice di disegno per un controllo.</span><span class="sxs-lookup"><span data-stu-id="623ae-112">This is usually how you obtain a reference to a graphics object when creating painting code for a control.</span></span> <span data-ttu-id="623ae-113">Analogamente, è anche possibile ottenere un <xref:System.Drawing.Printing.PrintPageEventArgs> oggetto grafico <xref:System.Drawing.Printing.PrintDocument.PrintPage> come <xref:System.Drawing.Printing.PrintDocument>proprietà dell'oggetto quando si gestisce l'evento per un oggetto .</span><span class="sxs-lookup"><span data-stu-id="623ae-113">Similarly, you can also obtain a graphics object as a property of the <xref:System.Drawing.Printing.PrintPageEventArgs> when handling the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event for a <xref:System.Drawing.Printing.PrintDocument>.</span></span>  
  
     <span data-ttu-id="623ae-114">-oppure-</span><span class="sxs-lookup"><span data-stu-id="623ae-114">-or-</span></span>  
  
- <span data-ttu-id="623ae-115">Chiamare <xref:System.Windows.Forms.Control.CreateGraphics%2A> il metodo di un controllo o <xref:System.Drawing.Graphics> di un form per ottenere un riferimento a un oggetto che rappresenta la superficie di disegno di tale controllo o form.</span><span class="sxs-lookup"><span data-stu-id="623ae-115">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span> <span data-ttu-id="623ae-116">Utilizzare questo metodo se si desidera disegnare su un form o un controllo già esistente.</span><span class="sxs-lookup"><span data-stu-id="623ae-116">Use this method if you want to draw on a form or control that already exists.</span></span>  
  
     <span data-ttu-id="623ae-117">-oppure-</span><span class="sxs-lookup"><span data-stu-id="623ae-117">-or-</span></span>  
  
- <span data-ttu-id="623ae-118">Creare <xref:System.Drawing.Graphics> un oggetto da qualsiasi <xref:System.Drawing.Image>oggetto che eredita da .</span><span class="sxs-lookup"><span data-stu-id="623ae-118">Create a <xref:System.Drawing.Graphics> object from any object that inherits from <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="623ae-119">Questo approccio è utile quando si desidera modificare un'immagine già esistente.</span><span class="sxs-lookup"><span data-stu-id="623ae-119">This approach is useful when you want to alter an already existing image.</span></span>  
  
     <span data-ttu-id="623ae-120">Nelle sezioni seguenti vengono fornite informazioni dettagliate su ognuno di questi processi.</span><span class="sxs-lookup"><span data-stu-id="623ae-120">The following sections give details about each of these processes.</span></span>  
  
## <a name="painteventargs-in-the-paint-event-handler"></a><span data-ttu-id="623ae-121">PaintEventArgs nel gestore eventi Paint</span><span class="sxs-lookup"><span data-stu-id="623ae-121">PaintEventArgs in the Paint Event Handler</span></span>  
 <span data-ttu-id="623ae-122">Durante la <xref:System.Windows.Forms.PaintEventHandler> programmazione <xref:System.Drawing.Printing.PrintDocument.PrintPage> di <xref:System.Drawing.Printing.PrintDocument>controlli for o for a , <xref:System.Windows.Forms.PaintEventArgs> viene <xref:System.Drawing.Printing.PrintPageEventArgs>fornito un oggetto grafico come una delle proprietà di o .</span><span class="sxs-lookup"><span data-stu-id="623ae-122">When programming the <xref:System.Windows.Forms.PaintEventHandler> for controls or the <xref:System.Drawing.Printing.PrintDocument.PrintPage> for a <xref:System.Drawing.Printing.PrintDocument>, a graphics object is provided as one of the properties of <xref:System.Windows.Forms.PaintEventArgs> or <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a><span data-ttu-id="623ae-123">Per ottenere un riferimento a un Graphics oggetto dal PaintEventArgs nel Paint evento</span><span class="sxs-lookup"><span data-stu-id="623ae-123">To obtain a reference to a Graphics object from the PaintEventArgs in the Paint event</span></span>  
  
1. <span data-ttu-id="623ae-124">Dichiarare <xref:System.Drawing.Graphics> l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="623ae-124">Declare the <xref:System.Drawing.Graphics> object.</span></span>  
  
2. <span data-ttu-id="623ae-125">Assegnare la variabile <xref:System.Drawing.Graphics> per fare riferimento <xref:System.Windows.Forms.PaintEventArgs>all'oggetto passato come parte dell'oggetto .</span><span class="sxs-lookup"><span data-stu-id="623ae-125">Assign the variable to refer to the <xref:System.Drawing.Graphics> object passed as part of the <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
3. <span data-ttu-id="623ae-126">Inserire codice per disegnare il form o il controllo.</span><span class="sxs-lookup"><span data-stu-id="623ae-126">Insert code to paint the form or control.</span></span>  
  
     <span data-ttu-id="623ae-127">L'esempio seguente mostra <xref:System.Drawing.Graphics> come fare <xref:System.Windows.Forms.PaintEventArgs> riferimento <xref:System.Windows.Forms.Control.Paint> a un oggetto da nell'evento:</span><span class="sxs-lookup"><span data-stu-id="623ae-127">The following example shows how to reference a <xref:System.Drawing.Graphics> object from the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event:</span></span>  
  
    ```vb  
    Private Sub Form1_Paint(sender As Object, pe As PaintEventArgs) Handles _  
       MyBase.Paint  
       ' Declares the Graphics object and sets it to the Graphics object  
       ' supplied in the PaintEventArgs.  
       Dim g As Graphics = pe.Graphics  
       ' Insert code to paint the form here.  
    End Sub  
    ```  
  
    ```csharp  
    private void Form1_Paint(object sender,
       System.Windows.Forms.PaintEventArgs pe)
    {  
       // Declares the Graphics object and sets it to the Graphics object  
       // supplied in the PaintEventArgs.  
       Graphics g = pe.Graphics;  
       // Insert code to paint the form here.  
    }  
    ```  
  
    ```cpp  
    private:  
       void Form1_Paint(System::Object ^ sender,  
          System::Windows::Forms::PaintEventArgs ^ pe)  
       {  
          // Declares the Graphics object and sets it to the Graphics object  
          // supplied in the PaintEventArgs.  
          Graphics ^ g = pe->Graphics;  
          // Insert code to paint the form here.  
       }  
    ```  
  
## <a name="creategraphics-method"></a><span data-ttu-id="623ae-128">Metodo CreateGraphics</span><span class="sxs-lookup"><span data-stu-id="623ae-128">CreateGraphics Method</span></span>  
 <span data-ttu-id="623ae-129">È inoltre possibile <xref:System.Windows.Forms.Control.CreateGraphics%2A> utilizzare il metodo di un controllo <xref:System.Drawing.Graphics> o di una maschera per ottenere un riferimento a un oggetto che rappresenta la superficie di disegno di tale controllo o form.</span><span class="sxs-lookup"><span data-stu-id="623ae-129">You can also use the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span>  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a><span data-ttu-id="623ae-130">Per creare un graphics oggetto con il CreateGraphics metodo</span><span class="sxs-lookup"><span data-stu-id="623ae-130">To create a Graphics object with the CreateGraphics method</span></span>  
  
- <span data-ttu-id="623ae-131">Chiamare <xref:System.Windows.Forms.Control.CreateGraphics%2A> il metodo del form o del controllo su cui si desidera eseguire il rendering della grafica.</span><span class="sxs-lookup"><span data-stu-id="623ae-131">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of the form or control upon which you want to render graphics.</span></span>  
  
    ```vb  
    Dim g as Graphics  
    ' Sets g to a Graphics object representing the drawing surface of the  
    ' control or form g is a member of.  
    g = Me.CreateGraphics  
    ```  
  
    ```csharp  
    Graphics g;  
    // Sets g to a graphics object representing the drawing surface of the  
    // control or form g is a member of.  
    g = this.CreateGraphics();  
    ```  
  
    ```cpp  
    Graphics ^ g;  
    // Sets g to a graphics object representing the drawing surface of the  
    // control or form g is a member of.  
    g = this->CreateGraphics();  
    ```  
  
## <a name="create-from-an-image-object"></a><span data-ttu-id="623ae-132">Creazione da un oggetto immagine</span><span class="sxs-lookup"><span data-stu-id="623ae-132">Create from an Image Object</span></span>  
 <span data-ttu-id="623ae-133">Inoltre, è possibile creare un oggetto grafico da <xref:System.Drawing.Image> qualsiasi oggetto che deriva dalla classe .</span><span class="sxs-lookup"><span data-stu-id="623ae-133">Additionally, you can create a graphics object from any object that derives from the <xref:System.Drawing.Image> class.</span></span>  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a><span data-ttu-id="623ae-134">Per creare un Graphics oggetto da un Image</span><span class="sxs-lookup"><span data-stu-id="623ae-134">To create a Graphics object from an Image</span></span>  
  
- <span data-ttu-id="623ae-135">Chiamare <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> il metodo , specificando il nome della variabile Image <xref:System.Drawing.Graphics> da cui si desidera creare un oggetto.</span><span class="sxs-lookup"><span data-stu-id="623ae-135">Call the <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> method, supplying the name of the Image variable from which you want to create a <xref:System.Drawing.Graphics> object.</span></span>  
  
     <span data-ttu-id="623ae-136">Nell'esempio seguente viene <xref:System.Drawing.Bitmap> illustrato come utilizzare un oggetto:The following example shows how to use a object:</span><span class="sxs-lookup"><span data-stu-id="623ae-136">The following example shows how to use a <xref:System.Drawing.Bitmap> object:</span></span>  
  
    ```vb  
    Dim myBitmap as New Bitmap("C:\Documents and Settings\Joe\Pics\myPic.bmp")  
    Dim g as Graphics = Graphics.FromImage(myBitmap)  
    ```  
  
    ```csharp  
    Bitmap myBitmap = new Bitmap(@"C:\Documents and
       Settings\Joe\Pics\myPic.bmp");  
    Graphics g = Graphics.FromImage(myBitmap);  
    ```  
  
    ```cpp  
    Bitmap ^ myBitmap = gcnew  
       Bitmap("D:\\Documents and Settings\\Joe\\Pics\\myPic.bmp");  
    Graphics ^ g = Graphics::FromImage(myBitmap);  
    ```  
  
> [!NOTE]
> <span data-ttu-id="623ae-137">È possibile <xref:System.Drawing.Graphics> creare oggetti solo da file bmp non indicizzati, ad esempio file bmp a 16 bit, a 24 bit e a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="623ae-137">You can only create <xref:System.Drawing.Graphics> objects from nonindexed .bmp files, such as 16-bit, 24-bit, and 32-bit .bmp files.</span></span> <span data-ttu-id="623ae-138">Ogni pixel dei file .bmp non indicizzati contiene un colore, a differenza dei pixel dei file .bmp indicizzati, che contengono un indice di una tabella dei colori.</span><span class="sxs-lookup"><span data-stu-id="623ae-138">Each pixel of nonindexed .bmp files holds a color, in contrast to pixels of indexed .bmp files, which hold an index to a color table.</span></span>  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a><span data-ttu-id="623ae-139">Disegno e manipolazione di forme e immagini</span><span class="sxs-lookup"><span data-stu-id="623ae-139">Drawing and Manipulating Shapes and Images</span></span>  
 <span data-ttu-id="623ae-140">Dopo la creazione, <xref:System.Drawing.Graphics> un oggetto può essere utilizzato per disegnare linee e forme, eseguire il rendering del testo o visualizzare e modificare le immagini.</span><span class="sxs-lookup"><span data-stu-id="623ae-140">After it is created, a <xref:System.Drawing.Graphics> object may be used to draw lines and shapes, render text, or display and manipulate images.</span></span> <span data-ttu-id="623ae-141">Gli oggetti principali utilizzati <xref:System.Drawing.Graphics> con l'oggetto sono:</span><span class="sxs-lookup"><span data-stu-id="623ae-141">The principal objects that are used with the <xref:System.Drawing.Graphics> object are:</span></span>  
  
- <span data-ttu-id="623ae-142">La <xref:System.Drawing.Pen> classe: utilizzata per disegnare linee, delineare forme o eseguire il rendering di altre rappresentazioni geometriche.</span><span class="sxs-lookup"><span data-stu-id="623ae-142">The <xref:System.Drawing.Pen> class—Used for drawing lines, outlining shapes, or rendering other geometric representations.</span></span>  
  
- <span data-ttu-id="623ae-143">Classe: <xref:System.Drawing.Brush> utilizzata per riempire aree di grafica, ad esempio forme, immagini o testo riempiti.</span><span class="sxs-lookup"><span data-stu-id="623ae-143">The <xref:System.Drawing.Brush> class—Used for filling areas of graphics, such as filled shapes, images, or text.</span></span>  
  
- <span data-ttu-id="623ae-144">La <xref:System.Drawing.Font> classe: fornisce una descrizione delle forme da utilizzare per il rendering del testo.</span><span class="sxs-lookup"><span data-stu-id="623ae-144">The <xref:System.Drawing.Font> class—Provides a description of what shapes to use when rendering text.</span></span>  
  
- <span data-ttu-id="623ae-145">Struttura: <xref:System.Drawing.Color> rappresenta i diversi colori da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="623ae-145">The <xref:System.Drawing.Color> structure—Represents the different colors to display.</span></span>  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a><span data-ttu-id="623ae-146">Per utilizzare l'oggetto Graphics creato</span><span class="sxs-lookup"><span data-stu-id="623ae-146">To use the Graphics object you have created</span></span>  
  
- <span data-ttu-id="623ae-147">Lavora con l'oggetto appropriato elencato sopra per disegnare ciò di cui hai bisogno.</span><span class="sxs-lookup"><span data-stu-id="623ae-147">Work with the appropriate object listed above to draw what you need.</span></span>  
  
     <span data-ttu-id="623ae-148">Per altre informazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="623ae-148">For more information, see the following topics:</span></span>  
  
    |<span data-ttu-id="623ae-149">Per eseguire il rendering</span><span class="sxs-lookup"><span data-stu-id="623ae-149">To render</span></span>|<span data-ttu-id="623ae-150">Vedere</span><span class="sxs-lookup"><span data-stu-id="623ae-150">See</span></span>|  
    |---------------|---------|  
    |<span data-ttu-id="623ae-151">Linee</span><span class="sxs-lookup"><span data-stu-id="623ae-151">Lines</span></span>|[<span data-ttu-id="623ae-152">Procedura: disegnare una linea in un Windows Form</span><span class="sxs-lookup"><span data-stu-id="623ae-152">How to: Draw a Line on a Windows Form</span></span>](how-to-draw-a-line-on-a-windows-form.md)|  
    |<span data-ttu-id="623ae-153">Forme</span><span class="sxs-lookup"><span data-stu-id="623ae-153">Shapes</span></span>|[<span data-ttu-id="623ae-154">Procedura: creare una forma con contorno</span><span class="sxs-lookup"><span data-stu-id="623ae-154">How to: Draw an Outlined Shape</span></span>](how-to-draw-an-outlined-shape.md)|  
    |<span data-ttu-id="623ae-155">Text</span><span class="sxs-lookup"><span data-stu-id="623ae-155">Text</span></span>|[<span data-ttu-id="623ae-156">Procedura: disegnare testo in un Windows Form</span><span class="sxs-lookup"><span data-stu-id="623ae-156">How to: Draw Text on a Windows Form</span></span>](how-to-draw-text-on-a-windows-form.md)|  
    |<span data-ttu-id="623ae-157">Immagini</span><span class="sxs-lookup"><span data-stu-id="623ae-157">Images</span></span>|[<span data-ttu-id="623ae-158">Procedura: Eseguire il rendering delle immagini con GDI+</span><span class="sxs-lookup"><span data-stu-id="623ae-158">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a><span data-ttu-id="623ae-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="623ae-159">See also</span></span>

- [<span data-ttu-id="623ae-160">Introduzione alla programmazione grafica</span><span class="sxs-lookup"><span data-stu-id="623ae-160">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="623ae-161">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="623ae-161">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="623ae-162">Linee, curve e forme</span><span class="sxs-lookup"><span data-stu-id="623ae-162">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="623ae-163">Procedura: Eseguire il rendering delle immagini con GDI+</span><span class="sxs-lookup"><span data-stu-id="623ae-163">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)
