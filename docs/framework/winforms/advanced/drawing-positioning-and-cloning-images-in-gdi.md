---
title: Disegno, posizionamento e duplicazione delle immagini in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- raster images [Windows Forms]
- images [Windows Forms], positioning
- drawing [Windows Forms], images
- drawing [Windows Forms], raster images
- images [Windows Forms], cloning
- images [Windows Forms], drawing
- GDI+, drawing images
- GDI+, cloning images
- GDI+, positioning images
ms.assetid: 09f0c07a-19c0-43b4-90a2-862a10545ce8
ms.openlocfilehash: b5f98e7bdef9ff8ed0a4cd0e040cb92a31f30503
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59188448"
---
# <a name="drawing-positioning-and-cloning-images-in-gdi"></a><span data-ttu-id="669ac-102">Disegno, posizionamento e duplicazione delle immagini in GDI+</span><span class="sxs-lookup"><span data-stu-id="669ac-102">Drawing, Positioning, and Cloning Images in GDI+</span></span>
<span data-ttu-id="669ac-103">È possibile usare la <xref:System.Drawing.Bitmap> classe per caricare e visualizzare le immagini raster e si può usare il <xref:System.Drawing.Imaging.Metafile> classe da caricare e visualizzare immagini vettoriali.</span><span class="sxs-lookup"><span data-stu-id="669ac-103">You can use the <xref:System.Drawing.Bitmap> class to load and display raster images, and you can use the <xref:System.Drawing.Imaging.Metafile> class to load and display vector images.</span></span> <span data-ttu-id="669ac-104">Il <xref:System.Drawing.Bitmap> e <xref:System.Drawing.Imaging.Metafile> ereditino dal <xref:System.Drawing.Image> classe.</span><span class="sxs-lookup"><span data-stu-id="669ac-104">The <xref:System.Drawing.Bitmap> and <xref:System.Drawing.Imaging.Metafile> classes inherit from the <xref:System.Drawing.Image> class.</span></span> <span data-ttu-id="669ac-105">Per visualizzare un'immagine del vettore, è necessario un'istanza di <xref:System.Drawing.Graphics> classe e un <xref:System.Drawing.Imaging.Metafile>.</span><span class="sxs-lookup"><span data-stu-id="669ac-105">To display a vector image, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Imaging.Metafile>.</span></span> <span data-ttu-id="669ac-106">Per visualizzare un'immagine raster, è necessario un'istanza di <xref:System.Drawing.Graphics> classe e un <xref:System.Drawing.Bitmap>.</span><span class="sxs-lookup"><span data-stu-id="669ac-106">To display a raster image, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Bitmap>.</span></span> <span data-ttu-id="669ac-107">L'istanza del <xref:System.Drawing.Graphics> classe fornisce il <xref:System.Drawing.Graphics.DrawImage%2A> metodo, che riceve il <xref:System.Drawing.Imaging.Metafile> o <xref:System.Drawing.Bitmap> come argomento.</span><span class="sxs-lookup"><span data-stu-id="669ac-107">The instance of the <xref:System.Drawing.Graphics> class provides the <xref:System.Drawing.Graphics.DrawImage%2A> method, which receives the <xref:System.Drawing.Imaging.Metafile> or <xref:System.Drawing.Bitmap> as an argument.</span></span>  
  
## <a name="file-types-and-cloning"></a><span data-ttu-id="669ac-108">Tipi di file e clonare</span><span class="sxs-lookup"><span data-stu-id="669ac-108">File Types and Cloning</span></span>  
 <span data-ttu-id="669ac-109">Esempio di codice seguente viene illustrato come costruire un <xref:System.Drawing.Bitmap> dal file Climber. jpg e visualizza l'immagine bitmap.</span><span class="sxs-lookup"><span data-stu-id="669ac-109">The following code example shows how to construct a <xref:System.Drawing.Bitmap> from the file Climber.jpg and displays the bitmap.</span></span> <span data-ttu-id="669ac-110">Il punto di destinazione per l'angolo superiore sinistro dell'immagine, (10, 10), specificato nel secondo e terzo parametro.</span><span class="sxs-lookup"><span data-stu-id="669ac-110">The destination point for the upper-left corner of the image, (10, 10), is specified in the second and third parameters.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#11)]  
  
 <span data-ttu-id="669ac-111">La figura seguente mostra l'immagine.</span><span class="sxs-lookup"><span data-stu-id="669ac-111">The following illustration shows the image.</span></span>  
  
 <span data-ttu-id="669ac-112">![Esempio di immagine](./media/aboutgdip03-art04.gif "AboutGdip03_Art04")</span><span class="sxs-lookup"><span data-stu-id="669ac-112">![Image Sample](./media/aboutgdip03-art04.gif "AboutGdip03_Art04")</span></span>  
  
 <span data-ttu-id="669ac-113">È possibile costruire <xref:System.Drawing.Bitmap> formati di file di oggetti da una varietà di grafici: BMP, GIF, JPEG, EXIF, PNG, TIFF e ICONA.</span><span class="sxs-lookup"><span data-stu-id="669ac-113">You can construct <xref:System.Drawing.Bitmap> objects from a variety of graphics file formats: BMP, GIF, JPEG, EXIF, PNG, TIFF, and ICON.</span></span>  
  
 <span data-ttu-id="669ac-114">Esempio di codice seguente viene illustrato come costruire <xref:System.Drawing.Bitmap> oggetti da un'ampia gamma di tipi di file e quindi Visualizza il bitmap.</span><span class="sxs-lookup"><span data-stu-id="669ac-114">The following code example shows how to construct <xref:System.Drawing.Bitmap> objects from a variety of file types and then displays the bitmaps.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#12)]  
  
 <span data-ttu-id="669ac-115">Il <xref:System.Drawing.Bitmap> classe fornisce un <xref:System.Drawing.Bitmap.Clone%2A> metodo che è possibile usare per creare una copia di un oggetto esistente <xref:System.Drawing.Bitmap>.</span><span class="sxs-lookup"><span data-stu-id="669ac-115">The <xref:System.Drawing.Bitmap> class provides a <xref:System.Drawing.Bitmap.Clone%2A> method that you can use to make a copy of an existing <xref:System.Drawing.Bitmap>.</span></span> <span data-ttu-id="669ac-116">Il <xref:System.Drawing.Bitmap.Clone%2A> metodo ha un parametro di rettangolo di origine che è possibile usare per specificare la parte della bitmap originale che si desidera copiare.</span><span class="sxs-lookup"><span data-stu-id="669ac-116">The <xref:System.Drawing.Bitmap.Clone%2A> method has a source rectangle parameter that you can use to specify the portion of the original bitmap that you want to copy.</span></span> <span data-ttu-id="669ac-117">Esempio di codice seguente viene illustrato come creare un <xref:System.Drawing.Bitmap> clonando la metà superiore di un oggetto esistente <xref:System.Drawing.Bitmap>.</span><span class="sxs-lookup"><span data-stu-id="669ac-117">The following code example shows how to create a <xref:System.Drawing.Bitmap> by cloning the top half of an existing <xref:System.Drawing.Bitmap>.</span></span> <span data-ttu-id="669ac-118">Quindi vengono create entrambe le immagini.</span><span class="sxs-lookup"><span data-stu-id="669ac-118">Then both images are drawn.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#13)]  
  
 <span data-ttu-id="669ac-119">La figura seguente mostra le due immagini.</span><span class="sxs-lookup"><span data-stu-id="669ac-119">The following illustration shows the two images.</span></span>  
  
 <span data-ttu-id="669ac-120">![Cropping](./media/aboutgdip03-art05.gif "AboutGdip03_Art05")</span><span class="sxs-lookup"><span data-stu-id="669ac-120">![Cropping](./media/aboutgdip03-art05.gif "AboutGdip03_Art05")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="669ac-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="669ac-121">See also</span></span>

- [<span data-ttu-id="669ac-122">Immagini, bitmap e metafile</span><span class="sxs-lookup"><span data-stu-id="669ac-122">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="669ac-123">Procedura: Creare oggetti Graphics per disegnare</span><span class="sxs-lookup"><span data-stu-id="669ac-123">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="669ac-124">Utilizzo di immagini, bitmap, icone e metafile</span><span class="sxs-lookup"><span data-stu-id="669ac-124">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
