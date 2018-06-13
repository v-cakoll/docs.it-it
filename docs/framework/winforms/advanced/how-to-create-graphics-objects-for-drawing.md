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
ms.openlocfilehash: 3c25ddcfb3a566055afd5e233c2a69b3b7a8c66e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526488"
---
# <a name="how-to-create-graphics-objects-for-drawing"></a><span data-ttu-id="9691f-102">Procedura: creare oggetti Graphics per disegnare</span><span class="sxs-lookup"><span data-stu-id="9691f-102">How to: Create Graphics Objects for Drawing</span></span>
<span data-ttu-id="9691f-103">Prima di poter creare linee e forme, il rendering del testo, visualizzare e modificare immagini con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], è necessario creare un <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="9691f-103">Before you can draw lines and shapes, render text, or display and manipulate images with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you need to create a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="9691f-104">Il <xref:System.Drawing.Graphics> oggetto rappresenta un [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] superficie di disegno ed è l'oggetto che viene utilizzato per creare immagini grafiche.</span><span class="sxs-lookup"><span data-stu-id="9691f-104">The <xref:System.Drawing.Graphics> object represents a [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] drawing surface, and is the object that is used to create graphical images.</span></span>  
  
 <span data-ttu-id="9691f-105">Durante l'utilizzo di grafici sono disponibili due passaggi:</span><span class="sxs-lookup"><span data-stu-id="9691f-105">There are two steps in working with graphics:</span></span>  
  
1.  <span data-ttu-id="9691f-106">Creazione di un <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="9691f-106">Creating a <xref:System.Drawing.Graphics> object.</span></span>  
  
2.  <span data-ttu-id="9691f-107">Utilizzo di <xref:System.Drawing.Graphics> oggetto disegnare linee e forme, il rendering del testo, o visualizzare e modificare immagini.</span><span class="sxs-lookup"><span data-stu-id="9691f-107">Using the <xref:System.Drawing.Graphics> object to draw lines and shapes, render text, or display and manipulate images.</span></span>  
  
## <a name="creating-a-graphics-object"></a><span data-ttu-id="9691f-108">Creazione di un oggetto Graphics</span><span class="sxs-lookup"><span data-stu-id="9691f-108">Creating a Graphics Object</span></span>  
 <span data-ttu-id="9691f-109">Può creare un oggetto graphics in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="9691f-109">A graphics object can be created in a variety of ways.</span></span>  
  
#### <a name="to-create-a-graphics-object"></a><span data-ttu-id="9691f-110">Per creare un oggetto graphics</span><span class="sxs-lookup"><span data-stu-id="9691f-110">To create a graphics object</span></span>  
  
-   <span data-ttu-id="9691f-111">Ricevere un riferimento a un oggetto grafico come parte di <xref:System.Windows.Forms.PaintEventArgs> nel <xref:System.Windows.Forms.Control.Paint> evento di un form o controllo.</span><span class="sxs-lookup"><span data-stu-id="9691f-111">Receive a reference to a graphics object as part of the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event of a form or control.</span></span> <span data-ttu-id="9691f-112">Si tratta in genere come ottenere un riferimento a un oggetto grafico durante la creazione di codice di disegno di un controllo.</span><span class="sxs-lookup"><span data-stu-id="9691f-112">This is usually how you obtain a reference to a graphics object when creating painting code for a control.</span></span> <span data-ttu-id="9691f-113">Analogamente, è possibile ottenere un oggetto graphics come proprietà del <xref:System.Drawing.Printing.PrintPageEventArgs> quando si gestisce il <xref:System.Drawing.Printing.PrintDocument.PrintPage> evento per un <xref:System.Drawing.Printing.PrintDocument>.</span><span class="sxs-lookup"><span data-stu-id="9691f-113">Similarly, you can also obtain a graphics object as a property of the <xref:System.Drawing.Printing.PrintPageEventArgs> when handling the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event for a <xref:System.Drawing.Printing.PrintDocument>.</span></span>  
  
     <span data-ttu-id="9691f-114">oppure</span><span class="sxs-lookup"><span data-stu-id="9691f-114">-or-</span></span>  
  
-   <span data-ttu-id="9691f-115">Chiamare il <xref:System.Windows.Forms.Control.CreateGraphics%2A> metodo di un controllo o un form per ottenere un riferimento a un <xref:System.Drawing.Graphics> oggetto che rappresenta l'area di disegno di tale controllo o un form.</span><span class="sxs-lookup"><span data-stu-id="9691f-115">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span> <span data-ttu-id="9691f-116">Utilizzare questo metodo se si desidera disegnare su un form o controllo che esiste già.</span><span class="sxs-lookup"><span data-stu-id="9691f-116">Use this method if you want to draw on a form or control that already exists.</span></span>  
  
     <span data-ttu-id="9691f-117">oppure</span><span class="sxs-lookup"><span data-stu-id="9691f-117">-or-</span></span>  
  
-   <span data-ttu-id="9691f-118">Creare un <xref:System.Drawing.Graphics> oggetto da qualsiasi oggetto che eredita da <xref:System.Drawing.Image>.</span><span class="sxs-lookup"><span data-stu-id="9691f-118">Create a <xref:System.Drawing.Graphics> object from any object that inherits from <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="9691f-119">Questo approccio è utile quando si desidera modificare un'immagine già esistente.</span><span class="sxs-lookup"><span data-stu-id="9691f-119">This approach is useful when you want to alter an already existing image.</span></span>  
  
     <span data-ttu-id="9691f-120">Le sezioni seguenti forniscono informazioni dettagliate su ciascuno di questi processi.</span><span class="sxs-lookup"><span data-stu-id="9691f-120">The following sections give details about each of these processes.</span></span>  
  
## <a name="painteventargs-in-the-paint-event-handler"></a><span data-ttu-id="9691f-121">PaintEventArgs nel gestore dell'evento Paint</span><span class="sxs-lookup"><span data-stu-id="9691f-121">PaintEventArgs in the Paint Event Handler</span></span>  
 <span data-ttu-id="9691f-122">Durante la programmazione di <xref:System.Windows.Forms.PaintEventHandler> per i controlli o <xref:System.Drawing.Printing.PrintDocument.PrintPage> per un <xref:System.Drawing.Printing.PrintDocument>, viene fornito un oggetto grafico come una delle proprietà di <xref:System.Windows.Forms.PaintEventArgs> o <xref:System.Drawing.Printing.PrintPageEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="9691f-122">When programming the <xref:System.Windows.Forms.PaintEventHandler> for controls or the <xref:System.Drawing.Printing.PrintDocument.PrintPage> for a <xref:System.Drawing.Printing.PrintDocument>, a graphics object is provided as one of the properties of <xref:System.Windows.Forms.PaintEventArgs> or <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a><span data-ttu-id="9691f-123">Per ottenere un riferimento a un oggetto Graphics da PaintEventArgs nell'evento di disegno</span><span class="sxs-lookup"><span data-stu-id="9691f-123">To obtain a reference to a Graphics object from the PaintEventArgs in the Paint event</span></span>  
  
1.  <span data-ttu-id="9691f-124">Dichiarare il <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="9691f-124">Declare the <xref:System.Drawing.Graphics> object.</span></span>  
  
2.  <span data-ttu-id="9691f-125">Assegnare la variabile per fare riferimento al <xref:System.Drawing.Graphics> oggetto passato come parte di <xref:System.Windows.Forms.PaintEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="9691f-125">Assign the variable to refer to the <xref:System.Drawing.Graphics> object passed as part of the <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
3.  <span data-ttu-id="9691f-126">Inserire il codice per disegnare il form o controllo.</span><span class="sxs-lookup"><span data-stu-id="9691f-126">Insert code to paint the form or control.</span></span>  
  
     <span data-ttu-id="9691f-127">Nell'esempio seguente viene illustrato come fare riferimento a un <xref:System.Drawing.Graphics> dall'oggetto di <xref:System.Windows.Forms.PaintEventArgs> nel <xref:System.Windows.Forms.Control.Paint> evento:</span><span class="sxs-lookup"><span data-stu-id="9691f-127">The following example shows how to reference a <xref:System.Drawing.Graphics> object from the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event:</span></span>  
  
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
  
## <a name="creategraphics-method"></a><span data-ttu-id="9691f-128">Metodo CreateGraphics</span><span class="sxs-lookup"><span data-stu-id="9691f-128">CreateGraphics Method</span></span>  
 <span data-ttu-id="9691f-129">È inoltre possibile utilizzare il <xref:System.Windows.Forms.Control.CreateGraphics%2A> metodo di un controllo o un form per ottenere un riferimento a un <xref:System.Drawing.Graphics> oggetto che rappresenta l'area di disegno di tale controllo o un form.</span><span class="sxs-lookup"><span data-stu-id="9691f-129">You can also use the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span>  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a><span data-ttu-id="9691f-130">Per creare un oggetto grafico con il metodo CreateGraphics</span><span class="sxs-lookup"><span data-stu-id="9691f-130">To create a Graphics object with the CreateGraphics method</span></span>  
  
-   <span data-ttu-id="9691f-131">Chiamare il <xref:System.Windows.Forms.Control.CreateGraphics%2A> metodo del form o controllo su cui si desidera eseguire il rendering di grafica.</span><span class="sxs-lookup"><span data-stu-id="9691f-131">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of the form or control upon which you want to render graphics.</span></span>  
  
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
  
## <a name="create-from-an-image-object"></a><span data-ttu-id="9691f-132">Il nome di un oggetto Image</span><span class="sxs-lookup"><span data-stu-id="9691f-132">Create from an Image Object</span></span>  
 <span data-ttu-id="9691f-133">Inoltre, è possibile creare un oggetto graphics da qualsiasi oggetto che deriva dalla <xref:System.Drawing.Image> classe.</span><span class="sxs-lookup"><span data-stu-id="9691f-133">Additionally, you can create a graphics object from any object that derives from the <xref:System.Drawing.Image> class.</span></span>  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a><span data-ttu-id="9691f-134">Per creare un oggetto Graphics da un'immagine</span><span class="sxs-lookup"><span data-stu-id="9691f-134">To create a Graphics object from an Image</span></span>  
  
-   <span data-ttu-id="9691f-135">Chiamare il <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> metodo, specificando il nome della variabile di immagine da cui si desidera creare un <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="9691f-135">Call the <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> method, supplying the name of the Image variable from which you want to create a <xref:System.Drawing.Graphics> object.</span></span>  
  
     <span data-ttu-id="9691f-136">Nell'esempio seguente viene illustrato come utilizzare un <xref:System.Drawing.Bitmap> oggetto:</span><span class="sxs-lookup"><span data-stu-id="9691f-136">The following example shows how to use a <xref:System.Drawing.Bitmap> object:</span></span>  
  
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
>  <span data-ttu-id="9691f-137">È possibile creare solo <xref:System.Drawing.Graphics> oggetti dai file BMP non indicizzati, ad esempio file con estensione bmp a 16 bit, a 24 bit e a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="9691f-137">You can only create <xref:System.Drawing.Graphics> objects from nonindexed .bmp files, such as 16-bit, 24-bit, and 32-bit .bmp files.</span></span> <span data-ttu-id="9691f-138">Ogni pixel del file con estensione BMP non indicizzata contiene un colore, a differenza di pixel del file BMP indicizzati che contengono un indice per una tabella a colori.</span><span class="sxs-lookup"><span data-stu-id="9691f-138">Each pixel of nonindexed .bmp files holds a color, in contrast to pixels of indexed .bmp files, which hold an index to a color table.</span></span>  
  
-  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a><span data-ttu-id="9691f-139">Creazione e modifica di immagini e forme</span><span class="sxs-lookup"><span data-stu-id="9691f-139">Drawing and Manipulating Shapes and Images</span></span>  
 <span data-ttu-id="9691f-140">Dopo averlo creato, un <xref:System.Drawing.Graphics> oggetto può essere utilizzato per disegnare linee e forme, il rendering del testo, o visualizzare e modificare immagini.</span><span class="sxs-lookup"><span data-stu-id="9691f-140">After it is created, a <xref:System.Drawing.Graphics> object may be used to draw lines and shapes, render text, or display and manipulate images.</span></span> <span data-ttu-id="9691f-141">Gli oggetti principali utilizzati con il <xref:System.Drawing.Graphics> oggetto sono:</span><span class="sxs-lookup"><span data-stu-id="9691f-141">The principal objects that are used with the <xref:System.Drawing.Graphics> object are:</span></span>  
  
-   <span data-ttu-id="9691f-142">La <xref:System.Drawing.Pen> classe, utilizzati per disegno di linee, tracciare forme o per il rendering di altre rappresentazioni geometriche.</span><span class="sxs-lookup"><span data-stu-id="9691f-142">The <xref:System.Drawing.Pen> class—Used for drawing lines, outlining shapes, or rendering other geometric representations.</span></span>  
  
-   <span data-ttu-id="9691f-143">La <xref:System.Drawing.Brush> classe, utilizzata per riempire le aree di grafica, ad esempio testo, immagini o forme piene.</span><span class="sxs-lookup"><span data-stu-id="9691f-143">The <xref:System.Drawing.Brush> class—Used for filling areas of graphics, such as filled shapes, images, or text.</span></span>  
  
-   <span data-ttu-id="9691f-144">La <xref:System.Drawing.Font> classe, viene fornita una descrizione delle forme da utilizzare durante il rendering di testo.</span><span class="sxs-lookup"><span data-stu-id="9691f-144">The <xref:System.Drawing.Font> class—Provides a description of what shapes to use when rendering text.</span></span>  
  
-   <span data-ttu-id="9691f-145">Il <xref:System.Drawing.Color> struttura, ovvero rappresenta i diversi colori da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="9691f-145">The <xref:System.Drawing.Color> structure—Represents the different colors to display.</span></span>  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a><span data-ttu-id="9691f-146">Utilizzare l'oggetto di grafica che è stato creato</span><span class="sxs-lookup"><span data-stu-id="9691f-146">To use the Graphics object you have created</span></span>  
  
-   <span data-ttu-id="9691f-147">Utilizzare l'oggetto appropriato elencata in precedenza per disegnare gli elementi necessari.</span><span class="sxs-lookup"><span data-stu-id="9691f-147">Work with the appropriate object listed above to draw what you need.</span></span>  
  
     <span data-ttu-id="9691f-148">Per altre informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="9691f-148">For more information, see the following topics:</span></span>  
  
    |<span data-ttu-id="9691f-149">Per eseguire il rendering</span><span class="sxs-lookup"><span data-stu-id="9691f-149">To render</span></span>|<span data-ttu-id="9691f-150">Vedere</span><span class="sxs-lookup"><span data-stu-id="9691f-150">See</span></span>|  
    |---------------|---------|  
    |<span data-ttu-id="9691f-151">Linee</span><span class="sxs-lookup"><span data-stu-id="9691f-151">Lines</span></span>|[<span data-ttu-id="9691f-152">Procedura: Disegnare una linea in un Windows Form</span><span class="sxs-lookup"><span data-stu-id="9691f-152">How to: Draw a Line on a Windows Form</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-line-on-a-windows-form.md)|  
    |<span data-ttu-id="9691f-153">Forme</span><span class="sxs-lookup"><span data-stu-id="9691f-153">Shapes</span></span>|[<span data-ttu-id="9691f-154">Procedura: Creare una forma con contorno</span><span class="sxs-lookup"><span data-stu-id="9691f-154">How to: Draw an Outlined Shape</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)|  
    |<span data-ttu-id="9691f-155">Testo</span><span class="sxs-lookup"><span data-stu-id="9691f-155">Text</span></span>|[<span data-ttu-id="9691f-156">Procedura: Disegnare testo in un Windows Form</span><span class="sxs-lookup"><span data-stu-id="9691f-156">How to: Draw Text on a Windows Form</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-on-a-windows-form.md)|  
    |<span data-ttu-id="9691f-157">Immagini</span><span class="sxs-lookup"><span data-stu-id="9691f-157">Images</span></span>|[<span data-ttu-id="9691f-158">Procedura: Eseguire il rendering delle immagini con GDI+</span><span class="sxs-lookup"><span data-stu-id="9691f-158">How to: Render Images with GDI+</span></span>](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a><span data-ttu-id="9691f-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9691f-159">See Also</span></span>  
 [<span data-ttu-id="9691f-160">Introduzione alla programmazione grafica</span><span class="sxs-lookup"><span data-stu-id="9691f-160">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [<span data-ttu-id="9691f-161">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="9691f-161">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="9691f-162">Linee, curve e forme</span><span class="sxs-lookup"><span data-stu-id="9691f-162">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="9691f-163">Procedura: Eseguire il rendering delle immagini con GDI+</span><span class="sxs-lookup"><span data-stu-id="9691f-163">How to: Render Images with GDI+</span></span>](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)
