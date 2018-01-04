---
title: Disegno, posizionamento e clonazione delle immagini in GDI+
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bbff4023a51687539472ac3e040b125f2f92fc28
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="drawing-positioning-and-cloning-images-in-gdi"></a><span data-ttu-id="472a9-102">Disegno, posizionamento e clonazione delle immagini in GDI+</span><span class="sxs-lookup"><span data-stu-id="472a9-102">Drawing, Positioning, and Cloning Images in GDI+</span></span>
<span data-ttu-id="472a9-103">È possibile utilizzare il <xref:System.Drawing.Bitmap> classe per caricare e visualizzare le immagini raster e si può utilizzare il <xref:System.Drawing.Imaging.Metafile> classe per caricare e visualizzare immagini vettoriali.</span><span class="sxs-lookup"><span data-stu-id="472a9-103">You can use the <xref:System.Drawing.Bitmap> class to load and display raster images, and you can use the <xref:System.Drawing.Imaging.Metafile> class to load and display vector images.</span></span> <span data-ttu-id="472a9-104">Il <xref:System.Drawing.Bitmap> e <xref:System.Drawing.Imaging.Metafile> le classi ereditano dalla <xref:System.Drawing.Image> classe.</span><span class="sxs-lookup"><span data-stu-id="472a9-104">The <xref:System.Drawing.Bitmap> and <xref:System.Drawing.Imaging.Metafile> classes inherit from the <xref:System.Drawing.Image> class.</span></span> <span data-ttu-id="472a9-105">Per visualizzare un'immagine vettoriale, sono necessari un'istanza di <xref:System.Drawing.Graphics> classe e un <xref:System.Drawing.Imaging.Metafile>.</span><span class="sxs-lookup"><span data-stu-id="472a9-105">To display a vector image, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Imaging.Metafile>.</span></span> <span data-ttu-id="472a9-106">Per visualizzare un'immagine raster, sono necessari un'istanza di <xref:System.Drawing.Graphics> classe e un <xref:System.Drawing.Bitmap>.</span><span class="sxs-lookup"><span data-stu-id="472a9-106">To display a raster image, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Bitmap>.</span></span> <span data-ttu-id="472a9-107">L'istanza del <xref:System.Drawing.Graphics> classe fornisce il <xref:System.Drawing.Graphics.DrawImage%2A> metodo che riceve il <xref:System.Drawing.Imaging.Metafile> o <xref:System.Drawing.Bitmap> come argomento.</span><span class="sxs-lookup"><span data-stu-id="472a9-107">The instance of the <xref:System.Drawing.Graphics> class provides the <xref:System.Drawing.Graphics.DrawImage%2A> method, which receives the <xref:System.Drawing.Imaging.Metafile> or <xref:System.Drawing.Bitmap> as an argument.</span></span>  
  
## <a name="file-types-and-cloning"></a><span data-ttu-id="472a9-108">Tipi di file e la clonazione</span><span class="sxs-lookup"><span data-stu-id="472a9-108">File Types and Cloning</span></span>  
 <span data-ttu-id="472a9-109">Esempio di codice seguente viene illustrato come costruire un <xref:System.Drawing.Bitmap> dal file Climber. jpg e visualizzare la bitmap.</span><span class="sxs-lookup"><span data-stu-id="472a9-109">The following code example shows how to construct a <xref:System.Drawing.Bitmap> from the file Climber.jpg and displays the bitmap.</span></span> <span data-ttu-id="472a9-110">Il punto di destinazione per l'angolo superiore sinistro dell'immagine, (10, 10), specificato nel secondo e il terzo parametro.</span><span class="sxs-lookup"><span data-stu-id="472a9-110">The destination point for the upper-left corner of the image, (10, 10), is specified in the second and third parameters.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#11)]  
  
 <span data-ttu-id="472a9-111">Nella figura seguente mostra l'immagine.</span><span class="sxs-lookup"><span data-stu-id="472a9-111">The following illustration shows the image.</span></span>  
  
 <span data-ttu-id="472a9-112">![Immagine di esempio](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art04.gif "AboutGdip03_Art04")</span><span class="sxs-lookup"><span data-stu-id="472a9-112">![Image Sample](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art04.gif "AboutGdip03_Art04")</span></span>  
  
 <span data-ttu-id="472a9-113">È possibile costruire <xref:System.Drawing.Bitmap> formati di file di oggetti da una varietà di grafica: BMP, GIF, JPEG, EXIF, PNG, TIFF e ICONA.</span><span class="sxs-lookup"><span data-stu-id="472a9-113">You can construct <xref:System.Drawing.Bitmap> objects from a variety of graphics file formats: BMP, GIF, JPEG, EXIF, PNG, TIFF, and ICON.</span></span>  
  
 <span data-ttu-id="472a9-114">Esempio di codice seguente viene illustrato come costruire <xref:System.Drawing.Bitmap> degli oggetti da una varietà di tipi di file e quindi visualizzare le bitmap.</span><span class="sxs-lookup"><span data-stu-id="472a9-114">The following code example shows how to construct <xref:System.Drawing.Bitmap> objects from a variety of file types and then displays the bitmaps.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#12)]  
  
 <span data-ttu-id="472a9-115">Il <xref:System.Drawing.Bitmap> classe fornisce un <xref:System.Drawing.Bitmap.Clone%2A> metodo che è possibile utilizzare per creare una copia di un oggetto esistente <xref:System.Drawing.Bitmap>.</span><span class="sxs-lookup"><span data-stu-id="472a9-115">The <xref:System.Drawing.Bitmap> class provides a <xref:System.Drawing.Bitmap.Clone%2A> method that you can use to make a copy of an existing <xref:System.Drawing.Bitmap>.</span></span> <span data-ttu-id="472a9-116">Il <xref:System.Drawing.Bitmap.Clone%2A> metodo ha un parametro rettangolo di origine che è possibile utilizzare per specificare la parte della bitmap originale che si desidera copiare.</span><span class="sxs-lookup"><span data-stu-id="472a9-116">The <xref:System.Drawing.Bitmap.Clone%2A> method has a source rectangle parameter that you can use to specify the portion of the original bitmap that you want to copy.</span></span> <span data-ttu-id="472a9-117">Esempio di codice seguente viene illustrato come creare un <xref:System.Drawing.Bitmap> clonando la metà superiore di un oggetto esistente <xref:System.Drawing.Bitmap>.</span><span class="sxs-lookup"><span data-stu-id="472a9-117">The following code example shows how to create a <xref:System.Drawing.Bitmap> by cloning the top half of an existing <xref:System.Drawing.Bitmap>.</span></span> <span data-ttu-id="472a9-118">Quindi vengono disegnate entrambe le immagini.</span><span class="sxs-lookup"><span data-stu-id="472a9-118">Then both images are drawn.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#13)]  
  
 <span data-ttu-id="472a9-119">Nella figura seguente mostra le due immagini.</span><span class="sxs-lookup"><span data-stu-id="472a9-119">The following illustration shows the two images.</span></span>  
  
 <span data-ttu-id="472a9-120">![Ritaglio](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art05.gif "AboutGdip03_Art05")</span><span class="sxs-lookup"><span data-stu-id="472a9-120">![Cropping](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art05.gif "AboutGdip03_Art05")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="472a9-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="472a9-121">See Also</span></span>  
 [<span data-ttu-id="472a9-122">Immagini, bitmap e metafile</span><span class="sxs-lookup"><span data-stu-id="472a9-122">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [<span data-ttu-id="472a9-123">Procedura: Creare oggetti Graphics per disegnare</span><span class="sxs-lookup"><span data-stu-id="472a9-123">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [<span data-ttu-id="472a9-124">Utilizzo di immagini, bitmap, icone e metafile</span><span class="sxs-lookup"><span data-stu-id="472a9-124">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
