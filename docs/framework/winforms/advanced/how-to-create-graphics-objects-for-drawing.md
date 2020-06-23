---
title: 'Procedura: creare oggetti Graphics per disegnare'
description: Informazioni su come creare un oggetto grafico necessario per disegnare linee e forme, eseguire il rendering del testo o visualizzare e modificare le immagini con GDI+.
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
ms.openlocfilehash: 1a0884c1e9956dc6f4608e32372deeea24ef4670
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903207"
---
# <a name="how-to-create-graphics-objects-for-drawing"></a><span data-ttu-id="5c92a-103">Procedura: creare oggetti Graphics per disegnare</span><span class="sxs-lookup"><span data-stu-id="5c92a-103">How to: Create Graphics Objects for Drawing</span></span>
<span data-ttu-id="5c92a-104">Prima di poter disegnare linee e forme, eseguire il rendering del testo o visualizzare e modificare le immagini con GDI+, è necessario creare un <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="5c92a-104">Before you can draw lines and shapes, render text, or display and manipulate images with GDI+, you need to create a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="5c92a-105">L' <xref:System.Drawing.Graphics> oggetto rappresenta una superficie di disegno GDI+ e è l'oggetto utilizzato per creare immagini grafiche.</span><span class="sxs-lookup"><span data-stu-id="5c92a-105">The <xref:System.Drawing.Graphics> object represents a GDI+ drawing surface, and is the object that is used to create graphical images.</span></span>  
  
 <span data-ttu-id="5c92a-106">L'uso della grafica prevede due passaggi:</span><span class="sxs-lookup"><span data-stu-id="5c92a-106">There are two steps in working with graphics:</span></span>  
  
1. <span data-ttu-id="5c92a-107">Creazione di un <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="5c92a-107">Creating a <xref:System.Drawing.Graphics> object.</span></span>  
  
2. <span data-ttu-id="5c92a-108">Utilizzo dell' <xref:System.Drawing.Graphics> oggetto per disegnare linee e forme, eseguire il rendering del testo o visualizzare e modificare le immagini.</span><span class="sxs-lookup"><span data-stu-id="5c92a-108">Using the <xref:System.Drawing.Graphics> object to draw lines and shapes, render text, or display and manipulate images.</span></span>  
  
## <a name="creating-a-graphics-object"></a><span data-ttu-id="5c92a-109">Creazione di un oggetto Graphics</span><span class="sxs-lookup"><span data-stu-id="5c92a-109">Creating a Graphics Object</span></span>  
 <span data-ttu-id="5c92a-110">Un oggetto Graphics può essere creato in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="5c92a-110">A graphics object can be created in a variety of ways.</span></span>  
  
#### <a name="to-create-a-graphics-object"></a><span data-ttu-id="5c92a-111">Per creare un oggetto Graphics</span><span class="sxs-lookup"><span data-stu-id="5c92a-111">To create a graphics object</span></span>  
  
- <span data-ttu-id="5c92a-112">Ricevere un riferimento a un oggetto Graphics come parte di <xref:System.Windows.Forms.PaintEventArgs> nel <xref:System.Windows.Forms.Control.Paint> caso di un form o di un controllo.</span><span class="sxs-lookup"><span data-stu-id="5c92a-112">Receive a reference to a graphics object as part of the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event of a form or control.</span></span> <span data-ttu-id="5c92a-113">Questo è in genere il modo in cui si ottiene un riferimento a un oggetto Graphics quando si crea il codice del disegno per un controllo.</span><span class="sxs-lookup"><span data-stu-id="5c92a-113">This is usually how you obtain a reference to a graphics object when creating painting code for a control.</span></span> <span data-ttu-id="5c92a-114">Analogamente, è anche possibile ottenere un oggetto Graphics come proprietà di <xref:System.Drawing.Printing.PrintPageEventArgs> quando si gestisce l' <xref:System.Drawing.Printing.PrintDocument.PrintPage> evento per un oggetto <xref:System.Drawing.Printing.PrintDocument> .</span><span class="sxs-lookup"><span data-stu-id="5c92a-114">Similarly, you can also obtain a graphics object as a property of the <xref:System.Drawing.Printing.PrintPageEventArgs> when handling the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event for a <xref:System.Drawing.Printing.PrintDocument>.</span></span>  
  
     <span data-ttu-id="5c92a-115">-oppure-</span><span class="sxs-lookup"><span data-stu-id="5c92a-115">-or-</span></span>  
  
- <span data-ttu-id="5c92a-116">Chiamare il <xref:System.Windows.Forms.Control.CreateGraphics%2A> metodo di un controllo o di un form per ottenere un riferimento a un <xref:System.Drawing.Graphics> oggetto che rappresenta la superficie di disegno del controllo o del form.</span><span class="sxs-lookup"><span data-stu-id="5c92a-116">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span> <span data-ttu-id="5c92a-117">Utilizzare questo metodo se si desidera creare in un form o in un controllo già esistente.</span><span class="sxs-lookup"><span data-stu-id="5c92a-117">Use this method if you want to draw on a form or control that already exists.</span></span>  
  
     <span data-ttu-id="5c92a-118">-oppure-</span><span class="sxs-lookup"><span data-stu-id="5c92a-118">-or-</span></span>  
  
- <span data-ttu-id="5c92a-119">Creare un <xref:System.Drawing.Graphics> oggetto da qualsiasi oggetto che eredita da <xref:System.Drawing.Image> .</span><span class="sxs-lookup"><span data-stu-id="5c92a-119">Create a <xref:System.Drawing.Graphics> object from any object that inherits from <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="5c92a-120">Questo approccio è utile quando si desidera modificare un'immagine già esistente.</span><span class="sxs-lookup"><span data-stu-id="5c92a-120">This approach is useful when you want to alter an already existing image.</span></span>  
  
     <span data-ttu-id="5c92a-121">Le sezioni seguenti forniscono informazioni dettagliate su ognuno di questi processi.</span><span class="sxs-lookup"><span data-stu-id="5c92a-121">The following sections give details about each of these processes.</span></span>  
  
## <a name="painteventargs-in-the-paint-event-handler"></a><span data-ttu-id="5c92a-122">PaintEventArgs nel gestore eventi Paint</span><span class="sxs-lookup"><span data-stu-id="5c92a-122">PaintEventArgs in the Paint Event Handler</span></span>  
 <span data-ttu-id="5c92a-123">Quando si programma <xref:System.Windows.Forms.PaintEventHandler> per i controlli o <xref:System.Drawing.Printing.PrintDocument.PrintPage> per un <xref:System.Drawing.Printing.PrintDocument> , un oggetto Graphics viene fornito come una delle proprietà di <xref:System.Windows.Forms.PaintEventArgs> o <xref:System.Drawing.Printing.PrintPageEventArgs> .</span><span class="sxs-lookup"><span data-stu-id="5c92a-123">When programming the <xref:System.Windows.Forms.PaintEventHandler> for controls or the <xref:System.Drawing.Printing.PrintDocument.PrintPage> for a <xref:System.Drawing.Printing.PrintDocument>, a graphics object is provided as one of the properties of <xref:System.Windows.Forms.PaintEventArgs> or <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a><span data-ttu-id="5c92a-124">Per ottenere un riferimento a un oggetto Graphics da PaintEventArgs nell'evento Paint</span><span class="sxs-lookup"><span data-stu-id="5c92a-124">To obtain a reference to a Graphics object from the PaintEventArgs in the Paint event</span></span>  
  
1. <span data-ttu-id="5c92a-125">Dichiarare l' <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="5c92a-125">Declare the <xref:System.Drawing.Graphics> object.</span></span>  
  
2. <span data-ttu-id="5c92a-126">Assegnare la variabile per fare riferimento all' <xref:System.Drawing.Graphics> oggetto passato come parte di <xref:System.Windows.Forms.PaintEventArgs> .</span><span class="sxs-lookup"><span data-stu-id="5c92a-126">Assign the variable to refer to the <xref:System.Drawing.Graphics> object passed as part of the <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
3. <span data-ttu-id="5c92a-127">Inserire il codice per disegnare il form o il controllo.</span><span class="sxs-lookup"><span data-stu-id="5c92a-127">Insert code to paint the form or control.</span></span>  
  
     <span data-ttu-id="5c92a-128">Nell'esempio seguente viene illustrato come fare riferimento a un <xref:System.Drawing.Graphics> oggetto da <xref:System.Windows.Forms.PaintEventArgs> nell' <xref:System.Windows.Forms.Control.Paint> evento:</span><span class="sxs-lookup"><span data-stu-id="5c92a-128">The following example shows how to reference a <xref:System.Drawing.Graphics> object from the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event:</span></span>  
  
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
  
## <a name="creategraphics-method"></a><span data-ttu-id="5c92a-129">Metodo CreateGraphics</span><span class="sxs-lookup"><span data-stu-id="5c92a-129">CreateGraphics Method</span></span>  
 <span data-ttu-id="5c92a-130">È anche possibile usare il <xref:System.Windows.Forms.Control.CreateGraphics%2A> metodo di un controllo o di un form per ottenere un riferimento a un <xref:System.Drawing.Graphics> oggetto che rappresenta la superficie di disegno del controllo o del form.</span><span class="sxs-lookup"><span data-stu-id="5c92a-130">You can also use the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span>  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a><span data-ttu-id="5c92a-131">Per creare un oggetto Graphics con il metodo CreateGraphics</span><span class="sxs-lookup"><span data-stu-id="5c92a-131">To create a Graphics object with the CreateGraphics method</span></span>  
  
- <span data-ttu-id="5c92a-132">Chiamare il <xref:System.Windows.Forms.Control.CreateGraphics%2A> metodo del form o del controllo su cui si desidera eseguire il rendering della grafica.</span><span class="sxs-lookup"><span data-stu-id="5c92a-132">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of the form or control upon which you want to render graphics.</span></span>  
  
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
  
## <a name="create-from-an-image-object"></a><span data-ttu-id="5c92a-133">Crea da un oggetto Image</span><span class="sxs-lookup"><span data-stu-id="5c92a-133">Create from an Image Object</span></span>  
 <span data-ttu-id="5c92a-134">Inoltre, è possibile creare un oggetto Graphics da qualsiasi oggetto derivato dalla <xref:System.Drawing.Image> classe.</span><span class="sxs-lookup"><span data-stu-id="5c92a-134">Additionally, you can create a graphics object from any object that derives from the <xref:System.Drawing.Image> class.</span></span>  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a><span data-ttu-id="5c92a-135">Per creare un oggetto Graphics da un'immagine</span><span class="sxs-lookup"><span data-stu-id="5c92a-135">To create a Graphics object from an Image</span></span>  
  
- <span data-ttu-id="5c92a-136">Chiamare il <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> metodo, specificando il nome della variabile di immagine dalla quale si desidera creare un <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="5c92a-136">Call the <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> method, supplying the name of the Image variable from which you want to create a <xref:System.Drawing.Graphics> object.</span></span>  
  
     <span data-ttu-id="5c92a-137">Nell'esempio seguente viene illustrato come utilizzare un <xref:System.Drawing.Bitmap> oggetto:</span><span class="sxs-lookup"><span data-stu-id="5c92a-137">The following example shows how to use a <xref:System.Drawing.Bitmap> object:</span></span>  
  
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
> <span data-ttu-id="5c92a-138">È possibile creare <xref:System.Drawing.Graphics> oggetti solo da file con estensione bmp non indicizzati, ad esempio file con estensione bmp a 16 bit, a 24 bit e a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="5c92a-138">You can only create <xref:System.Drawing.Graphics> objects from nonindexed .bmp files, such as 16-bit, 24-bit, and 32-bit .bmp files.</span></span> <span data-ttu-id="5c92a-139">Ogni pixel di file con estensione bmp non indicizzati include un colore, a differenza dei pixel dei file con estensione BMP indicizzati, che contengono un indice in una tabella dei colori.</span><span class="sxs-lookup"><span data-stu-id="5c92a-139">Each pixel of nonindexed .bmp files holds a color, in contrast to pixels of indexed .bmp files, which hold an index to a color table.</span></span>  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a><span data-ttu-id="5c92a-140">Creazione e modifica di forme e immagini</span><span class="sxs-lookup"><span data-stu-id="5c92a-140">Drawing and Manipulating Shapes and Images</span></span>  
 <span data-ttu-id="5c92a-141">Una volta creato, un <xref:System.Drawing.Graphics> oggetto può essere usato per disegnare linee e forme, eseguire il rendering del testo o visualizzare e modificare le immagini.</span><span class="sxs-lookup"><span data-stu-id="5c92a-141">After it is created, a <xref:System.Drawing.Graphics> object may be used to draw lines and shapes, render text, or display and manipulate images.</span></span> <span data-ttu-id="5c92a-142">Gli oggetti Principal utilizzati con l' <xref:System.Drawing.Graphics> oggetto sono:</span><span class="sxs-lookup"><span data-stu-id="5c92a-142">The principal objects that are used with the <xref:System.Drawing.Graphics> object are:</span></span>  
  
- <span data-ttu-id="5c92a-143">La <xref:System.Drawing.Pen> classe, utilizzata per disegnare linee, strutturare forme o per il rendering di altre rappresentazioni geometriche.</span><span class="sxs-lookup"><span data-stu-id="5c92a-143">The <xref:System.Drawing.Pen> class—Used for drawing lines, outlining shapes, or rendering other geometric representations.</span></span>  
  
- <span data-ttu-id="5c92a-144"><xref:System.Drawing.Brush>Classe, utilizzata per riempire aree di elementi grafici, ad esempio forme riempite, immagini o testo.</span><span class="sxs-lookup"><span data-stu-id="5c92a-144">The <xref:System.Drawing.Brush> class—Used for filling areas of graphics, such as filled shapes, images, or text.</span></span>  
  
- <span data-ttu-id="5c92a-145">La <xref:System.Drawing.Font> classe-fornisce una descrizione delle forme da usare per il rendering del testo.</span><span class="sxs-lookup"><span data-stu-id="5c92a-145">The <xref:System.Drawing.Font> class—Provides a description of what shapes to use when rendering text.</span></span>  
  
- <span data-ttu-id="5c92a-146">La <xref:System.Drawing.Color> struttura, che rappresenta i diversi colori da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="5c92a-146">The <xref:System.Drawing.Color> structure—Represents the different colors to display.</span></span>  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a><span data-ttu-id="5c92a-147">Per utilizzare l'oggetto Graphics creato</span><span class="sxs-lookup"><span data-stu-id="5c92a-147">To use the Graphics object you have created</span></span>  
  
- <span data-ttu-id="5c92a-148">Usare l'oggetto appropriato elencato sopra per creare gli elementi necessari.</span><span class="sxs-lookup"><span data-stu-id="5c92a-148">Work with the appropriate object listed above to draw what you need.</span></span>  
  
     <span data-ttu-id="5c92a-149">Per altre informazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="5c92a-149">For more information, see the following topics:</span></span>  
  
    |<span data-ttu-id="5c92a-150">Per eseguire il rendering</span><span class="sxs-lookup"><span data-stu-id="5c92a-150">To render</span></span>|<span data-ttu-id="5c92a-151">Vedere</span><span class="sxs-lookup"><span data-stu-id="5c92a-151">See</span></span>|  
    |---------------|---------|  
    |<span data-ttu-id="5c92a-152">Linee</span><span class="sxs-lookup"><span data-stu-id="5c92a-152">Lines</span></span>|[<span data-ttu-id="5c92a-153">Procedura: disegnare una linea in un Windows Form</span><span class="sxs-lookup"><span data-stu-id="5c92a-153">How to: Draw a Line on a Windows Form</span></span>](how-to-draw-a-line-on-a-windows-form.md)|  
    |<span data-ttu-id="5c92a-154">Forme</span><span class="sxs-lookup"><span data-stu-id="5c92a-154">Shapes</span></span>|[<span data-ttu-id="5c92a-155">Procedura: creare una forma con contorno</span><span class="sxs-lookup"><span data-stu-id="5c92a-155">How to: Draw an Outlined Shape</span></span>](how-to-draw-an-outlined-shape.md)|  
    |<span data-ttu-id="5c92a-156">Text</span><span class="sxs-lookup"><span data-stu-id="5c92a-156">Text</span></span>|[<span data-ttu-id="5c92a-157">Procedura: disegnare testo in un Windows Form</span><span class="sxs-lookup"><span data-stu-id="5c92a-157">How to: Draw Text on a Windows Form</span></span>](how-to-draw-text-on-a-windows-form.md)|  
    |<span data-ttu-id="5c92a-158">Immagini</span><span class="sxs-lookup"><span data-stu-id="5c92a-158">Images</span></span>|[<span data-ttu-id="5c92a-159">Procedura: Eseguire il rendering delle immagini con GDI+</span><span class="sxs-lookup"><span data-stu-id="5c92a-159">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a><span data-ttu-id="5c92a-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c92a-160">See also</span></span>

- [<span data-ttu-id="5c92a-161">Introduzione alla programmazione grafica</span><span class="sxs-lookup"><span data-stu-id="5c92a-161">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="5c92a-162">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="5c92a-162">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="5c92a-163">Linee, curve e forme</span><span class="sxs-lookup"><span data-stu-id="5c92a-163">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="5c92a-164">Procedura: Eseguire il rendering delle immagini con GDI+</span><span class="sxs-lookup"><span data-stu-id="5c92a-164">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)
