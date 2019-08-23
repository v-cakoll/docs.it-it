---
title: 'Procedura: Creare oggetti Graphics per disegnare'
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
ms.openlocfilehash: 3d3ab62896f6b799cd38a8180b90f33125a9929b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964347"
---
# <a name="how-to-create-graphics-objects-for-drawing"></a><span data-ttu-id="a92e1-102">Procedura: Creare oggetti Graphics per disegnare</span><span class="sxs-lookup"><span data-stu-id="a92e1-102">How to: Create Graphics Objects for Drawing</span></span>
<span data-ttu-id="a92e1-103">Prima di poter disegnare linee e forme, eseguire il rendering del testo o visualizzare e modificare le immagini con GDI+, è necessario <xref:System.Drawing.Graphics> creare un oggetto.</span><span class="sxs-lookup"><span data-stu-id="a92e1-103">Before you can draw lines and shapes, render text, or display and manipulate images with GDI+, you need to create a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="a92e1-104">L' <xref:System.Drawing.Graphics> oggetto rappresenta una superficie di disegno GDI+ e è l'oggetto utilizzato per creare immagini grafiche.</span><span class="sxs-lookup"><span data-stu-id="a92e1-104">The <xref:System.Drawing.Graphics> object represents a GDI+ drawing surface, and is the object that is used to create graphical images.</span></span>  
  
 <span data-ttu-id="a92e1-105">L'uso della grafica prevede due passaggi:</span><span class="sxs-lookup"><span data-stu-id="a92e1-105">There are two steps in working with graphics:</span></span>  
  
1. <span data-ttu-id="a92e1-106">Creazione di <xref:System.Drawing.Graphics> un oggetto.</span><span class="sxs-lookup"><span data-stu-id="a92e1-106">Creating a <xref:System.Drawing.Graphics> object.</span></span>  
  
2. <span data-ttu-id="a92e1-107">Utilizzo dell' <xref:System.Drawing.Graphics> oggetto per disegnare linee e forme, eseguire il rendering del testo o visualizzare e modificare le immagini.</span><span class="sxs-lookup"><span data-stu-id="a92e1-107">Using the <xref:System.Drawing.Graphics> object to draw lines and shapes, render text, or display and manipulate images.</span></span>  
  
## <a name="creating-a-graphics-object"></a><span data-ttu-id="a92e1-108">Creazione di un oggetto Graphics</span><span class="sxs-lookup"><span data-stu-id="a92e1-108">Creating a Graphics Object</span></span>  
 <span data-ttu-id="a92e1-109">Un oggetto Graphics può essere creato in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="a92e1-109">A graphics object can be created in a variety of ways.</span></span>  
  
#### <a name="to-create-a-graphics-object"></a><span data-ttu-id="a92e1-110">Per creare un oggetto Graphics</span><span class="sxs-lookup"><span data-stu-id="a92e1-110">To create a graphics object</span></span>  
  
- <span data-ttu-id="a92e1-111">Ricevere un riferimento a un oggetto Graphics come parte di <xref:System.Windows.Forms.PaintEventArgs> <xref:System.Windows.Forms.Control.Paint> nel caso di un form o di un controllo.</span><span class="sxs-lookup"><span data-stu-id="a92e1-111">Receive a reference to a graphics object as part of the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event of a form or control.</span></span> <span data-ttu-id="a92e1-112">Questo è in genere il modo in cui si ottiene un riferimento a un oggetto Graphics quando si crea il codice del disegno per un controllo.</span><span class="sxs-lookup"><span data-stu-id="a92e1-112">This is usually how you obtain a reference to a graphics object when creating painting code for a control.</span></span> <span data-ttu-id="a92e1-113">Analogamente, è anche possibile ottenere un oggetto Graphics come proprietà di <xref:System.Drawing.Printing.PrintPageEventArgs> quando si gestisce l' <xref:System.Drawing.Printing.PrintDocument.PrintPage> evento per un <xref:System.Drawing.Printing.PrintDocument>oggetto.</span><span class="sxs-lookup"><span data-stu-id="a92e1-113">Similarly, you can also obtain a graphics object as a property of the <xref:System.Drawing.Printing.PrintPageEventArgs> when handling the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event for a <xref:System.Drawing.Printing.PrintDocument>.</span></span>  
  
     <span data-ttu-id="a92e1-114">-oppure-</span><span class="sxs-lookup"><span data-stu-id="a92e1-114">-or-</span></span>  
  
- <span data-ttu-id="a92e1-115">Chiamare il <xref:System.Windows.Forms.Control.CreateGraphics%2A> metodo di un controllo o di un form per ottenere un riferimento <xref:System.Drawing.Graphics> a un oggetto che rappresenta la superficie di disegno del controllo o del form.</span><span class="sxs-lookup"><span data-stu-id="a92e1-115">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span> <span data-ttu-id="a92e1-116">Utilizzare questo metodo se si desidera creare in un form o in un controllo già esistente.</span><span class="sxs-lookup"><span data-stu-id="a92e1-116">Use this method if you want to draw on a form or control that already exists.</span></span>  
  
     <span data-ttu-id="a92e1-117">-oppure-</span><span class="sxs-lookup"><span data-stu-id="a92e1-117">-or-</span></span>  
  
- <span data-ttu-id="a92e1-118">Creare un <xref:System.Drawing.Graphics> oggetto da qualsiasi oggetto che eredita da <xref:System.Drawing.Image>.</span><span class="sxs-lookup"><span data-stu-id="a92e1-118">Create a <xref:System.Drawing.Graphics> object from any object that inherits from <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="a92e1-119">Questo approccio è utile quando si desidera modificare un'immagine già esistente.</span><span class="sxs-lookup"><span data-stu-id="a92e1-119">This approach is useful when you want to alter an already existing image.</span></span>  
  
     <span data-ttu-id="a92e1-120">Le sezioni seguenti forniscono informazioni dettagliate su ognuno di questi processi.</span><span class="sxs-lookup"><span data-stu-id="a92e1-120">The following sections give details about each of these processes.</span></span>  
  
## <a name="painteventargs-in-the-paint-event-handler"></a><span data-ttu-id="a92e1-121">PaintEventArgs nel gestore eventi Paint</span><span class="sxs-lookup"><span data-stu-id="a92e1-121">PaintEventArgs in the Paint Event Handler</span></span>  
 <span data-ttu-id="a92e1-122">Quando si programma <xref:System.Windows.Forms.PaintEventHandler> per i controlli <xref:System.Drawing.Printing.PrintDocument.PrintPage> o per un <xref:System.Drawing.Printing.PrintDocument>, un oggetto Graphics viene fornito come una delle proprietà di <xref:System.Windows.Forms.PaintEventArgs> o <xref:System.Drawing.Printing.PrintPageEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="a92e1-122">When programming the <xref:System.Windows.Forms.PaintEventHandler> for controls or the <xref:System.Drawing.Printing.PrintDocument.PrintPage> for a <xref:System.Drawing.Printing.PrintDocument>, a graphics object is provided as one of the properties of <xref:System.Windows.Forms.PaintEventArgs> or <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a><span data-ttu-id="a92e1-123">Per ottenere un riferimento a un oggetto Graphics da PaintEventArgs nell'evento Paint</span><span class="sxs-lookup"><span data-stu-id="a92e1-123">To obtain a reference to a Graphics object from the PaintEventArgs in the Paint event</span></span>  
  
1. <span data-ttu-id="a92e1-124">Dichiarare l' <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="a92e1-124">Declare the <xref:System.Drawing.Graphics> object.</span></span>  
  
2. <span data-ttu-id="a92e1-125">Assegnare la variabile per fare riferimento <xref:System.Drawing.Graphics> all'oggetto passato come parte <xref:System.Windows.Forms.PaintEventArgs>di.</span><span class="sxs-lookup"><span data-stu-id="a92e1-125">Assign the variable to refer to the <xref:System.Drawing.Graphics> object passed as part of the <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
3. <span data-ttu-id="a92e1-126">Inserire il codice per disegnare il form o il controllo.</span><span class="sxs-lookup"><span data-stu-id="a92e1-126">Insert code to paint the form or control.</span></span>  
  
     <span data-ttu-id="a92e1-127">Nell'esempio seguente viene illustrato come fare riferimento <xref:System.Drawing.Graphics> a un oggetto <xref:System.Windows.Forms.PaintEventArgs> da nell' <xref:System.Windows.Forms.Control.Paint> evento:</span><span class="sxs-lookup"><span data-stu-id="a92e1-127">The following example shows how to reference a <xref:System.Drawing.Graphics> object from the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event:</span></span>  
  
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
  
## <a name="creategraphics-method"></a><span data-ttu-id="a92e1-128">Metodo CreateGraphics</span><span class="sxs-lookup"><span data-stu-id="a92e1-128">CreateGraphics Method</span></span>  
 <span data-ttu-id="a92e1-129">È anche possibile usare il <xref:System.Windows.Forms.Control.CreateGraphics%2A> metodo di un controllo o di un form per ottenere un riferimento <xref:System.Drawing.Graphics> a un oggetto che rappresenta la superficie di disegno del controllo o del form.</span><span class="sxs-lookup"><span data-stu-id="a92e1-129">You can also use the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span>  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a><span data-ttu-id="a92e1-130">Per creare un oggetto Graphics con il metodo CreateGraphics</span><span class="sxs-lookup"><span data-stu-id="a92e1-130">To create a Graphics object with the CreateGraphics method</span></span>  
  
- <span data-ttu-id="a92e1-131">Chiamare il <xref:System.Windows.Forms.Control.CreateGraphics%2A> metodo del form o del controllo su cui si desidera eseguire il rendering della grafica.</span><span class="sxs-lookup"><span data-stu-id="a92e1-131">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of the form or control upon which you want to render graphics.</span></span>  
  
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
  
## <a name="create-from-an-image-object"></a><span data-ttu-id="a92e1-132">Crea da un oggetto Image</span><span class="sxs-lookup"><span data-stu-id="a92e1-132">Create from an Image Object</span></span>  
 <span data-ttu-id="a92e1-133">Inoltre, è possibile creare un oggetto Graphics da qualsiasi oggetto derivato dalla <xref:System.Drawing.Image> classe.</span><span class="sxs-lookup"><span data-stu-id="a92e1-133">Additionally, you can create a graphics object from any object that derives from the <xref:System.Drawing.Image> class.</span></span>  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a><span data-ttu-id="a92e1-134">Per creare un oggetto Graphics da un'immagine</span><span class="sxs-lookup"><span data-stu-id="a92e1-134">To create a Graphics object from an Image</span></span>  
  
- <span data-ttu-id="a92e1-135">Chiamare il <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> metodo, specificando il nome della variabile di immagine dalla quale si desidera creare un <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="a92e1-135">Call the <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> method, supplying the name of the Image variable from which you want to create a <xref:System.Drawing.Graphics> object.</span></span>  
  
     <span data-ttu-id="a92e1-136">Nell'esempio seguente viene illustrato come utilizzare un <xref:System.Drawing.Bitmap> oggetto:</span><span class="sxs-lookup"><span data-stu-id="a92e1-136">The following example shows how to use a <xref:System.Drawing.Bitmap> object:</span></span>  
  
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
> <span data-ttu-id="a92e1-137">È possibile creare <xref:System.Drawing.Graphics> oggetti solo da file con estensione bmp non indicizzati, ad esempio file con estensione bmp a 16 bit, a 24 bit e a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="a92e1-137">You can only create <xref:System.Drawing.Graphics> objects from nonindexed .bmp files, such as 16-bit, 24-bit, and 32-bit .bmp files.</span></span> <span data-ttu-id="a92e1-138">Ogni pixel di file con estensione bmp non indicizzati include un colore, a differenza dei pixel dei file con estensione BMP indicizzati, che contengono un indice in una tabella dei colori.</span><span class="sxs-lookup"><span data-stu-id="a92e1-138">Each pixel of nonindexed .bmp files holds a color, in contrast to pixels of indexed .bmp files, which hold an index to a color table.</span></span>  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a><span data-ttu-id="a92e1-139">Creazione e modifica di forme e immagini</span><span class="sxs-lookup"><span data-stu-id="a92e1-139">Drawing and Manipulating Shapes and Images</span></span>  
 <span data-ttu-id="a92e1-140">Una volta creato, un <xref:System.Drawing.Graphics> oggetto può essere usato per disegnare linee e forme, eseguire il rendering del testo o visualizzare e modificare le immagini.</span><span class="sxs-lookup"><span data-stu-id="a92e1-140">After it is created, a <xref:System.Drawing.Graphics> object may be used to draw lines and shapes, render text, or display and manipulate images.</span></span> <span data-ttu-id="a92e1-141">Gli oggetti Principal utilizzati con l' <xref:System.Drawing.Graphics> oggetto sono:</span><span class="sxs-lookup"><span data-stu-id="a92e1-141">The principal objects that are used with the <xref:System.Drawing.Graphics> object are:</span></span>  
  
- <span data-ttu-id="a92e1-142">La <xref:System.Drawing.Pen> classe, utilizzata per disegnare linee, strutturare forme o per il rendering di altre rappresentazioni geometriche.</span><span class="sxs-lookup"><span data-stu-id="a92e1-142">The <xref:System.Drawing.Pen> class—Used for drawing lines, outlining shapes, or rendering other geometric representations.</span></span>  
  
- <span data-ttu-id="a92e1-143"><xref:System.Drawing.Brush> Classe, utilizzata per riempire aree di elementi grafici, ad esempio forme riempite, immagini o testo.</span><span class="sxs-lookup"><span data-stu-id="a92e1-143">The <xref:System.Drawing.Brush> class—Used for filling areas of graphics, such as filled shapes, images, or text.</span></span>  
  
- <span data-ttu-id="a92e1-144">La <xref:System.Drawing.Font> classe-fornisce una descrizione delle forme da usare per il rendering del testo.</span><span class="sxs-lookup"><span data-stu-id="a92e1-144">The <xref:System.Drawing.Font> class—Provides a description of what shapes to use when rendering text.</span></span>  
  
- <span data-ttu-id="a92e1-145">La <xref:System.Drawing.Color> struttura, che rappresenta i diversi colori da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="a92e1-145">The <xref:System.Drawing.Color> structure—Represents the different colors to display.</span></span>  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a><span data-ttu-id="a92e1-146">Per utilizzare l'oggetto Graphics creato</span><span class="sxs-lookup"><span data-stu-id="a92e1-146">To use the Graphics object you have created</span></span>  
  
- <span data-ttu-id="a92e1-147">Usare l'oggetto appropriato elencato sopra per creare gli elementi necessari.</span><span class="sxs-lookup"><span data-stu-id="a92e1-147">Work with the appropriate object listed above to draw what you need.</span></span>  
  
     <span data-ttu-id="a92e1-148">Per altre informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="a92e1-148">For more information, see the following topics:</span></span>  
  
    |<span data-ttu-id="a92e1-149">Per eseguire il rendering</span><span class="sxs-lookup"><span data-stu-id="a92e1-149">To render</span></span>|<span data-ttu-id="a92e1-150">Vedere</span><span class="sxs-lookup"><span data-stu-id="a92e1-150">See</span></span>|  
    |---------------|---------|  
    |<span data-ttu-id="a92e1-151">Linee</span><span class="sxs-lookup"><span data-stu-id="a92e1-151">Lines</span></span>|[<span data-ttu-id="a92e1-152">Procedura: Creare una linea in un Windows Form</span><span class="sxs-lookup"><span data-stu-id="a92e1-152">How to: Draw a Line on a Windows Form</span></span>](how-to-draw-a-line-on-a-windows-form.md)|  
    |<span data-ttu-id="a92e1-153">Forme</span><span class="sxs-lookup"><span data-stu-id="a92e1-153">Shapes</span></span>|[<span data-ttu-id="a92e1-154">Procedura: Disegnare una forma delineata</span><span class="sxs-lookup"><span data-stu-id="a92e1-154">How to: Draw an Outlined Shape</span></span>](how-to-draw-an-outlined-shape.md)|  
    |<span data-ttu-id="a92e1-155">Text</span><span class="sxs-lookup"><span data-stu-id="a92e1-155">Text</span></span>|[<span data-ttu-id="a92e1-156">Procedura: Creare testo in un Windows Form</span><span class="sxs-lookup"><span data-stu-id="a92e1-156">How to: Draw Text on a Windows Form</span></span>](how-to-draw-text-on-a-windows-form.md)|  
    |<span data-ttu-id="a92e1-157">Immagini</span><span class="sxs-lookup"><span data-stu-id="a92e1-157">Images</span></span>|[<span data-ttu-id="a92e1-158">Procedura: Rendering di immagini con GDI+</span><span class="sxs-lookup"><span data-stu-id="a92e1-158">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a><span data-ttu-id="a92e1-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a92e1-159">See also</span></span>

- [<span data-ttu-id="a92e1-160">Introduzione alla programmazione grafica</span><span class="sxs-lookup"><span data-stu-id="a92e1-160">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="a92e1-161">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="a92e1-161">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="a92e1-162">Linee, curve e forme</span><span class="sxs-lookup"><span data-stu-id="a92e1-162">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="a92e1-163">Procedura: Rendering di immagini con GDI+</span><span class="sxs-lookup"><span data-stu-id="a92e1-163">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)
