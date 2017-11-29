---
title: Ritaglio e ridimensionamento di immagini in GDI+
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
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 63e1e55e57d586cbbca87361b95c18f0f53b8c75
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="cropping-and-scaling-images-in-gdi"></a><span data-ttu-id="2be21-102">Ritaglio e ridimensionamento di immagini in GDI+</span><span class="sxs-lookup"><span data-stu-id="2be21-102">Cropping and Scaling Images in GDI+</span></span>
<span data-ttu-id="2be21-103">È possibile utilizzare il <xref:System.Drawing.Graphics.DrawImage%2A> metodo la <xref:System.Drawing.Graphics> classe per creare e posizionare immagini vettoriali e raster immagini.</span><span class="sxs-lookup"><span data-stu-id="2be21-103">You can use the <xref:System.Drawing.Graphics.DrawImage%2A> method of the <xref:System.Drawing.Graphics> class to draw and position vector images and raster images.</span></span> <span data-ttu-id="2be21-104"><xref:System.Drawing.Graphics.DrawImage%2A>è un metodo di overload, pertanto vi sono diversi modi, è possibile fornire argomenti.</span><span class="sxs-lookup"><span data-stu-id="2be21-104"><xref:System.Drawing.Graphics.DrawImage%2A> is an overloaded method, so there are several ways you can supply it with arguments.</span></span>  
  
## <a name="drawimage-variations"></a><span data-ttu-id="2be21-105">DrawImage varianti</span><span class="sxs-lookup"><span data-stu-id="2be21-105">DrawImage Variations</span></span>  
 <span data-ttu-id="2be21-106">Una variazione del <xref:System.Drawing.Graphics.DrawImage%2A> metodo riceve un <xref:System.Drawing.Bitmap> e <xref:System.Drawing.Rectangle>.</span><span class="sxs-lookup"><span data-stu-id="2be21-106">One variation of the <xref:System.Drawing.Graphics.DrawImage%2A> method receives a <xref:System.Drawing.Bitmap> and a <xref:System.Drawing.Rectangle>.</span></span> <span data-ttu-id="2be21-107">Il rettangolo specifica la destinazione per l'operazione di disegno. specifica, ovvero il rettangolo in cui disegnare l'immagine.</span><span class="sxs-lookup"><span data-stu-id="2be21-107">The rectangle specifies the destination for the drawing operation; that is, it specifies the rectangle in which to draw the image.</span></span> <span data-ttu-id="2be21-108">Se le dimensioni del rettangolo di destinazione sono diversa dalla dimensione dell'immagine originale, l'immagine viene adattata al rettangolo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2be21-108">If the size of the destination rectangle is different from the size of the original image, the image is scaled to fit the destination rectangle.</span></span> <span data-ttu-id="2be21-109">Esempio di codice seguente viene illustrato come disegnare l'immagine stessa tre volte: una volta senza ridimensionamento, una volta con un'espansione e una volta con compressione:</span><span class="sxs-lookup"><span data-stu-id="2be21-109">The following code example shows how to draw the same image three times: once with no scaling, once with an expansion, and once with a compression:</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#31)]  
  
 <span data-ttu-id="2be21-110">Nella figura seguente mostra le tre immagini.</span><span class="sxs-lookup"><span data-stu-id="2be21-110">The following illustration shows the three pictures.</span></span>  
  
 <span data-ttu-id="2be21-111">![Scalabilità](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art06.gif "AboutGdip03_Art06")</span><span class="sxs-lookup"><span data-stu-id="2be21-111">![Scaling](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art06.gif "AboutGdip03_Art06")</span></span>  
  
 <span data-ttu-id="2be21-112">Alcune varianti del <xref:System.Drawing.Graphics.DrawImage%2A> metodo dispone di un parametro del rettangolo di origine, nonché un parametro del rettangolo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2be21-112">Some variations of the <xref:System.Drawing.Graphics.DrawImage%2A> method have a source-rectangle parameter as well as a destination-rectangle parameter.</span></span> <span data-ttu-id="2be21-113">Il parametro del rettangolo di origine specifica la parte dell'immagine originale da disegnare.</span><span class="sxs-lookup"><span data-stu-id="2be21-113">The source-rectangle parameter specifies the portion of the original image to draw.</span></span> <span data-ttu-id="2be21-114">Il rettangolo di destinazione specifica il rettangolo in cui disegnare la parte dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="2be21-114">The destination rectangle specifies the rectangle in which to draw that portion of the image.</span></span> <span data-ttu-id="2be21-115">Se le dimensioni del rettangolo di destinazione sono diversa dalla dimensione del rettangolo di origine, l'immagine viene adattata al rettangolo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2be21-115">If the size of the destination rectangle is different from the size of the source rectangle, the picture is scaled to fit the destination rectangle.</span></span>  
  
 <span data-ttu-id="2be21-116">Esempio di codice seguente viene illustrato come costruire un <xref:System.Drawing.Bitmap> dal file Runner.</span><span class="sxs-lookup"><span data-stu-id="2be21-116">The following code example shows how to construct a <xref:System.Drawing.Bitmap> from the file Runner.jpg.</span></span> <span data-ttu-id="2be21-117">Senza ridimensionamento in cui viene disegnata l'immagine intera (0, 0).</span><span class="sxs-lookup"><span data-stu-id="2be21-117">The entire image is drawn with no scaling at (0, 0).</span></span> <span data-ttu-id="2be21-118">Una piccola parte dell'immagine viene disegnato due volte: una volta con una compressione e una volta con un'espansione.</span><span class="sxs-lookup"><span data-stu-id="2be21-118">Then a small portion of the image is drawn twice: once with a compression and once with an expansion.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#32)]  
  
 <span data-ttu-id="2be21-119">Nella figura seguente mostra l'immagine non in scala e le parti di immagine espanso e compresso.</span><span class="sxs-lookup"><span data-stu-id="2be21-119">The following illustration shows the unscaled image, and the compressed and expanded image portions.</span></span>  
  
 <span data-ttu-id="2be21-120">![Ritaglio e ridimensionamento](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art07.gif "AboutGdip03_Art07")</span><span class="sxs-lookup"><span data-stu-id="2be21-120">![Cropping and Scaling](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art07.gif "AboutGdip03_Art07")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2be21-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2be21-121">See Also</span></span>  
 [<span data-ttu-id="2be21-122">Immagini, bitmap e metafile</span><span class="sxs-lookup"><span data-stu-id="2be21-122">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [<span data-ttu-id="2be21-123">Utilizzo di immagini, bitmap, icone e metafile</span><span class="sxs-lookup"><span data-stu-id="2be21-123">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
