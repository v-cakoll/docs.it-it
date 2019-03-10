---
title: Ritaglio e ridimensionamento di immagini in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, scaling images
- GDI+, cropping images
- images [Windows Forms], cropping
- compressing data [Windows Forms], images
- images [Windows Forms], expansion
- images [Windows Forms], scaling
- rectangles [Windows Forms], source
- rectangles [Windows Forms], destination
- images [Windows Forms], compression
ms.assetid: ad5daf26-005f-45bc-a2af-e0e97777a21a
ms.openlocfilehash: 311673c30283cdf3e0206d143daab8c01adc2bce
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718792"
---
# <a name="cropping-and-scaling-images-in-gdi"></a><span data-ttu-id="3be35-102">Ritaglio e ridimensionamento di immagini in GDI+</span><span class="sxs-lookup"><span data-stu-id="3be35-102">Cropping and Scaling Images in GDI+</span></span>
<span data-ttu-id="3be35-103">È possibile usare il <xref:System.Drawing.Graphics.DrawImage%2A> metodo di <xref:System.Drawing.Graphics> classe per creare e posizionare immagini vettoriali e raster.</span><span class="sxs-lookup"><span data-stu-id="3be35-103">You can use the <xref:System.Drawing.Graphics.DrawImage%2A> method of the <xref:System.Drawing.Graphics> class to draw and position vector images and raster images.</span></span> <span data-ttu-id="3be35-104"><xref:System.Drawing.Graphics.DrawImage%2A> è un metodo di overload, quindi esistono diversi modi, è possibile fornire argomenti.</span><span class="sxs-lookup"><span data-stu-id="3be35-104"><xref:System.Drawing.Graphics.DrawImage%2A> is an overloaded method, so there are several ways you can supply it with arguments.</span></span>  
  
## <a name="drawimage-variations"></a><span data-ttu-id="3be35-105">DrawImage varianti</span><span class="sxs-lookup"><span data-stu-id="3be35-105">DrawImage Variations</span></span>  
 <span data-ttu-id="3be35-106">Una variazione del <xref:System.Drawing.Graphics.DrawImage%2A> metodo riceve un <xref:System.Drawing.Bitmap> e un <xref:System.Drawing.Rectangle>.</span><span class="sxs-lookup"><span data-stu-id="3be35-106">One variation of the <xref:System.Drawing.Graphics.DrawImage%2A> method receives a <xref:System.Drawing.Bitmap> and a <xref:System.Drawing.Rectangle>.</span></span> <span data-ttu-id="3be35-107">Il rettangolo specifica la destinazione per l'operazione di disegno. vale a dire, specifica il rettangolo in cui disegnare l'immagine.</span><span class="sxs-lookup"><span data-stu-id="3be35-107">The rectangle specifies the destination for the drawing operation; that is, it specifies the rectangle in which to draw the image.</span></span> <span data-ttu-id="3be35-108">Se le dimensioni del rettangolo di destinazione sono diversa dalla dimensione dell'immagine originale, l'immagine viene adattata al rettangolo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3be35-108">If the size of the destination rectangle is different from the size of the original image, the image is scaled to fit the destination rectangle.</span></span> <span data-ttu-id="3be35-109">Esempio di codice seguente illustra come disegnare l'immagine stessa tre volte: una volta senza ridimensionamento, una volta con un'espansione e una volta con la compressione:</span><span class="sxs-lookup"><span data-stu-id="3be35-109">The following code example shows how to draw the same image three times: once with no scaling, once with an expansion, and once with a compression:</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#31)]  
  
 <span data-ttu-id="3be35-110">La figura seguente illustra le tre immagini.</span><span class="sxs-lookup"><span data-stu-id="3be35-110">The following illustration shows the three pictures.</span></span>  
  
 <span data-ttu-id="3be35-111">![Scaling](./media/aboutgdip03-art06.gif "AboutGdip03_Art06")</span><span class="sxs-lookup"><span data-stu-id="3be35-111">![Scaling](./media/aboutgdip03-art06.gif "AboutGdip03_Art06")</span></span>  
  
 <span data-ttu-id="3be35-112">Alcune variazioni del <xref:System.Drawing.Graphics.DrawImage%2A> metodo hanno un parametro del rettangolo di origine, nonché un parametro del rettangolo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3be35-112">Some variations of the <xref:System.Drawing.Graphics.DrawImage%2A> method have a source-rectangle parameter as well as a destination-rectangle parameter.</span></span> <span data-ttu-id="3be35-113">Il parametro del rettangolo di origine specifica la parte dell'immagine originale da disegnare.</span><span class="sxs-lookup"><span data-stu-id="3be35-113">The source-rectangle parameter specifies the portion of the original image to draw.</span></span> <span data-ttu-id="3be35-114">Il rettangolo di destinazione specifica il rettangolo in cui disegnare la parte dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="3be35-114">The destination rectangle specifies the rectangle in which to draw that portion of the image.</span></span> <span data-ttu-id="3be35-115">Se le dimensioni del rettangolo di destinazione sono diversa dalla dimensione del rettangolo di origine, l'immagine viene adattata al rettangolo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3be35-115">If the size of the destination rectangle is different from the size of the source rectangle, the picture is scaled to fit the destination rectangle.</span></span>  
  
 <span data-ttu-id="3be35-116">Esempio di codice seguente viene illustrato come costruire un <xref:System.Drawing.Bitmap> Runner nel file.</span><span class="sxs-lookup"><span data-stu-id="3be35-116">The following code example shows how to construct a <xref:System.Drawing.Bitmap> from the file Runner.jpg.</span></span> <span data-ttu-id="3be35-117">L'intera immagine viene disegnata con alcuna implementazione della scalabilità a (0, 0).</span><span class="sxs-lookup"><span data-stu-id="3be35-117">The entire image is drawn with no scaling at (0, 0).</span></span> <span data-ttu-id="3be35-118">Quindi una piccola parte dell'immagine viene disegnata due volte: una volta con la compressione e la seconda con un'espansione.</span><span class="sxs-lookup"><span data-stu-id="3be35-118">Then a small portion of the image is drawn twice: once with a compression and once with an expansion.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#32)]  
  
 <span data-ttu-id="3be35-119">La figura seguente mostra l'immagine non in scala e le parti immagine compresso ed espanso.</span><span class="sxs-lookup"><span data-stu-id="3be35-119">The following illustration shows the unscaled image, and the compressed and expanded image portions.</span></span>  
  
 <span data-ttu-id="3be35-120">![Ritaglio e ridimensionamento](./media/aboutgdip03-art07.gif "AboutGdip03_Art07")</span><span class="sxs-lookup"><span data-stu-id="3be35-120">![Cropping and Scaling](./media/aboutgdip03-art07.gif "AboutGdip03_Art07")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3be35-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3be35-121">See also</span></span>
- [<span data-ttu-id="3be35-122">Immagini, bitmap e metafile</span><span class="sxs-lookup"><span data-stu-id="3be35-122">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="3be35-123">Utilizzo di immagini, bitmap, icone e metafile</span><span class="sxs-lookup"><span data-stu-id="3be35-123">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
