---
title: 'Procedura: Disegnare una linea con riempimento a trama'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- lines [Windows Forms], texture
- drawing lines [Windows Forms], texture
ms.assetid: dc9118cc-f3c2-42e5-8173-f46d41d18fd5
ms.openlocfilehash: c0f90c298f48aeb96893bb09241faddc08d8a49d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004291"
---
# <a name="how-to-draw-a-line-filled-with-a-texture"></a><span data-ttu-id="8bc80-102">Procedura: Disegnare una linea con riempimento a trama</span><span class="sxs-lookup"><span data-stu-id="8bc80-102">How to: Draw a Line Filled with a Texture</span></span>
<span data-ttu-id="8bc80-103">Invece di tracciare una linea con un colore a tinta unita, è possibile disegnare una linea con una trama.</span><span class="sxs-lookup"><span data-stu-id="8bc80-103">Instead of drawing a line with a solid color, you can draw a line with a texture.</span></span> <span data-ttu-id="8bc80-104">Per tracciare linee e curve con una trama, creare un <xref:System.Drawing.TextureBrush> dell'oggetto e passarlo <xref:System.Drawing.TextureBrush> dell'oggetto a un <xref:System.Drawing.Pen.%23ctor%2A> costruttore.</span><span class="sxs-lookup"><span data-stu-id="8bc80-104">To draw lines and curves with a texture, create a <xref:System.Drawing.TextureBrush> object, and pass that <xref:System.Drawing.TextureBrush> object to a <xref:System.Drawing.Pen.%23ctor%2A> constructor.</span></span> <span data-ttu-id="8bc80-105">La bitmap associata al pennello trama viene utilizzata per affiancare il piano (in modo invisibile) e quando la penna Disegna una linea o una curva, il tratto di penna permette di ottenere determinate pixel della trama affiancata.</span><span class="sxs-lookup"><span data-stu-id="8bc80-105">The bitmap associated with the texture brush is used to tile the plane (invisibly), and when the pen draws a line or curve, the stroke of the pen uncovers certain pixels of the tiled texture.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8bc80-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="8bc80-106">Example</span></span>  
 <span data-ttu-id="8bc80-107">L'esempio seguente crea una <xref:System.Drawing.Bitmap> oggetto dal file `Texture1.jpg`.</span><span class="sxs-lookup"><span data-stu-id="8bc80-107">The following example creates a <xref:System.Drawing.Bitmap> object from the file `Texture1.jpg`.</span></span> <span data-ttu-id="8bc80-108">La bitmap viene usato per costruire una <xref:System.Drawing.TextureBrush> oggetti e il <xref:System.Drawing.TextureBrush> oggetto viene usato per costruire un <xref:System.Drawing.Pen> oggetto.</span><span class="sxs-lookup"><span data-stu-id="8bc80-108">That bitmap is used to construct a <xref:System.Drawing.TextureBrush> object, and the <xref:System.Drawing.TextureBrush> object is used to construct a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="8bc80-109">La chiamata a <xref:System.Drawing.Graphics.DrawImage%2A> consente di disegnare la bitmap con relativo angolo superiore sinistro a (0, 0).</span><span class="sxs-lookup"><span data-stu-id="8bc80-109">The call to <xref:System.Drawing.Graphics.DrawImage%2A> draws the bitmap with its upper-left corner at (0, 0).</span></span> <span data-ttu-id="8bc80-110">La chiamata a <xref:System.Drawing.Graphics.DrawEllipse%2A> utilizza il <xref:System.Drawing.Pen> oggetto su cui disegnare un'ellisse con trama.</span><span class="sxs-lookup"><span data-stu-id="8bc80-110">The call to <xref:System.Drawing.Graphics.DrawEllipse%2A> uses the <xref:System.Drawing.Pen> object to draw a textured ellipse.</span></span>  
  
 <span data-ttu-id="8bc80-111">La figura seguente mostra la bitmap e la trama ellisse:</span><span class="sxs-lookup"><span data-stu-id="8bc80-111">The following illustration shows the bitmap and the textured ellipse:</span></span>  
  
 ![Screenshot che mostra la bitmap e la trama ellisse.](./media/how-to-draw-a-line-filled-with-a-texture/bitmap-textured-ellipse.png)  
  
 [!code-csharp[System.Drawing.UsingAPen#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.UsingAPen#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8bc80-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="8bc80-113">Compiling the Code</span></span>  
 <span data-ttu-id="8bc80-114">Creare un modulo di Windows e la gestione del modulo <xref:System.Windows.Forms.Control.Paint> evento.</span><span class="sxs-lookup"><span data-stu-id="8bc80-114">Create a Windows Form and handle the form's <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="8bc80-115">Incollare il codice precedente nel <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="8bc80-115">Paste the preceding code into the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="8bc80-116">Sostituire `Texture.jpg` con un'immagine valida nel sistema.</span><span class="sxs-lookup"><span data-stu-id="8bc80-116">Replace `Texture.jpg` with an image valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bc80-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8bc80-117">See also</span></span>

- [<span data-ttu-id="8bc80-118">Uso di un oggetto Pen per creare linee e forme</span><span class="sxs-lookup"><span data-stu-id="8bc80-118">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="8bc80-119">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="8bc80-119">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
