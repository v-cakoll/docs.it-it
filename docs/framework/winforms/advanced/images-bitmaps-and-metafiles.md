---
title: Immagini, bitmap e metafile
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- metafiles [Windows Forms], about metafiles
- bitmaps [Windows Forms], about bitmaps
- images [Windows Forms], about images
- Windows Forms, images
ms.assetid: 7152b45b-a55c-49bc-8c78-ae002a844f71
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3f48027e413f9573158cfa2c3748fc93408b3f83
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="images-bitmaps-and-metafiles"></a><span data-ttu-id="f16d3-102">Immagini, bitmap e metafile</span><span class="sxs-lookup"><span data-stu-id="f16d3-102">Images, Bitmaps, and Metafiles</span></span>
<span data-ttu-id="f16d3-103">La classe `Image` è una classe base astratta che fornisce i metodi per eseguire operazioni con immagini raster (bitmap) e immagini vettoriali (metafile).</span><span class="sxs-lookup"><span data-stu-id="f16d3-103">The `Image` class is an abstract base class that provides methods for working with raster images (bitmaps) and vector images (metafiles).</span></span> <span data-ttu-id="f16d3-104">La classe `Bitmap` e la classe <xref:System.Drawing.Imaging.Metafile> ereditano entrambe dalla classe `Image`.</span><span class="sxs-lookup"><span data-stu-id="f16d3-104">The `Bitmap` class and the <xref:System.Drawing.Imaging.Metafile> class both inherit from the `Image` class.</span></span> <span data-ttu-id="f16d3-105">La classe `Bitmap` espande le funzionalità della classe `Image` grazie a metodi aggiuntivi per il caricamento, il salvataggio e la modifica di immagini raster.</span><span class="sxs-lookup"><span data-stu-id="f16d3-105">The `Bitmap` class expands on the capabilities of the `Image` class by providing additional methods for loading, saving, and manipulating raster images.</span></span> <span data-ttu-id="f16d3-106">La classe <xref:System.Drawing.Imaging.Metafile> espande le funzionalità della classe `Image` grazie a metodi aggiuntivi per la registrazione e l'esame di immagini vettoriali.</span><span class="sxs-lookup"><span data-stu-id="f16d3-106">The <xref:System.Drawing.Imaging.Metafile> class expands on the capabilities of the `Image` class by providing additional methods for recording and examining vector images.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f16d3-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="f16d3-107">In This Section</span></span>  
 [<span data-ttu-id="f16d3-108">Tipi di bitmap</span><span class="sxs-lookup"><span data-stu-id="f16d3-108">Types of Bitmaps</span></span>](../../../../docs/framework/winforms/advanced/types-of-bitmaps.md)  
 <span data-ttu-id="f16d3-109">Illustra i vari formati immagini.</span><span class="sxs-lookup"><span data-stu-id="f16d3-109">Discusses the various image formats.</span></span>  
  
 [<span data-ttu-id="f16d3-110">Metafile in GDI+</span><span class="sxs-lookup"><span data-stu-id="f16d3-110">Metafiles in GDI+</span></span>](../../../../docs/framework/winforms/advanced/metafiles-in-gdi.md)  
 <span data-ttu-id="f16d3-111">Descrive il supporto [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] per i metafile.</span><span class="sxs-lookup"><span data-stu-id="f16d3-111">Discusses [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] support for metafiles.</span></span>  
  
 [<span data-ttu-id="f16d3-112">Disegno, posizionamento e clonazione delle immagini in GDI+</span><span class="sxs-lookup"><span data-stu-id="f16d3-112">Drawing, Positioning, and Cloning Images in GDI+</span></span>](../../../../docs/framework/winforms/advanced/drawing-positioning-and-cloning-images-in-gdi.md)  
 <span data-ttu-id="f16d3-113">Illustra i metodi per il disegno di immagini vettoriali e raster con codice gestito.</span><span class="sxs-lookup"><span data-stu-id="f16d3-113">Discusses methods for drawing vector and raster images with managed code.</span></span>  
  
 [<span data-ttu-id="f16d3-114">Ritaglio e ridimensionamento di immagini in GDI+</span><span class="sxs-lookup"><span data-stu-id="f16d3-114">Cropping and Scaling Images in GDI+</span></span>](../../../../docs/framework/winforms/advanced/cropping-and-scaling-images-in-gdi.md)  
 <span data-ttu-id="f16d3-115">Illustra i metodi per il ritaglio e il ridimensionamento di immagini vettoriali e raster con codice gestito.</span><span class="sxs-lookup"><span data-stu-id="f16d3-115">Discusses methods for cropping and scaling vector and raster images with managed code</span></span>  
  
## <a name="reference"></a><span data-ttu-id="f16d3-116">Riferimento</span><span class="sxs-lookup"><span data-stu-id="f16d3-116">Reference</span></span>  
 <xref:System.Drawing.Image>  
 <span data-ttu-id="f16d3-117">Descrive la classe e include collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="f16d3-117">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Bitmap>  
 <span data-ttu-id="f16d3-118">Descrive la classe e include collegamenti a tutti i membri correlati.</span><span class="sxs-lookup"><span data-stu-id="f16d3-118">Describes this class and has links to all of its members</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f16d3-119">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="f16d3-119">Related Sections</span></span>  
 [<span data-ttu-id="f16d3-120">Utilizzo di immagini, bitmap, icone e metafile</span><span class="sxs-lookup"><span data-stu-id="f16d3-120">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)  
 <span data-ttu-id="f16d3-121">Fornisce collegamenti ad argomenti in cui è illustrato l'uso di immagini in un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f16d3-121">Contains links to topics that demonstrate how to use images in your application.</span></span>
