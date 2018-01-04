---
title: Utilizzo di immagini, bitmap, icone e metafile
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- metafiles [Windows Forms], working with
- examples [Windows Forms], bitmaps
- examples [Windows Forms], images
- bitmaps [Windows Forms], working with
- images [Windows Forms], working with
- examples [Windows Forms], metafiles
ms.assetid: a626d701-bd99-4fd8-b92f-7b8f794e042b
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 29c8a4ef0a495d63c0263262857002f09d8c885a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="working-with-images-bitmaps-icons-and-metafiles"></a><span data-ttu-id="fa724-102">Utilizzo di immagini, bitmap, icone e metafile</span><span class="sxs-lookup"><span data-stu-id="fa724-102">Working with Images, Bitmaps, Icons, and Metafiles</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="fa724-103"> fornisce la classe `Bitmap` per usare immagini raster e la classe `Metafile` per usare immagini vettoriali.</span><span class="sxs-lookup"><span data-stu-id="fa724-103"> provides the `Bitmap` class for working with raster images and the `Metafile` class for working with vector images.</span></span> <span data-ttu-id="fa724-104">Le classi `Bitmap` e `Metafile` ereditano entrambe dalla classe `Image`.</span><span class="sxs-lookup"><span data-stu-id="fa724-104">The `Bitmap` and the `Metafile` classes both inherit from the `Image` class.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fa724-105">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="fa724-105">In This Section</span></span>  
 [<span data-ttu-id="fa724-106">Procedura: Disegnare una bitmap esistente sullo schermo</span><span class="sxs-lookup"><span data-stu-id="fa724-106">How to: Draw an Existing Bitmap to the Screen</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-an-existing-bitmap-to-the-screen.md)  
 <span data-ttu-id="fa724-107">Descrive come caricare e disegnare bitmap.</span><span class="sxs-lookup"><span data-stu-id="fa724-107">Describes how to load and draw bitmaps.</span></span>  
  
 [<span data-ttu-id="fa724-108">Procedura: Caricare e visualizzare metafile</span><span class="sxs-lookup"><span data-stu-id="fa724-108">How to: Load and Display Metafiles</span></span>](../../../../docs/framework/winforms/advanced/how-to-load-and-display-metafiles.md)  
 <span data-ttu-id="fa724-109">Mostra come caricare e disegnare metafile.</span><span class="sxs-lookup"><span data-stu-id="fa724-109">Shows how to load and draw metafiles.</span></span>  
  
 [<span data-ttu-id="fa724-110">Ritaglio e ridimensionamento di immagini in GDI+</span><span class="sxs-lookup"><span data-stu-id="fa724-110">Cropping and Scaling Images in GDI+</span></span>](../../../../docs/framework/winforms/advanced/cropping-and-scaling-images-in-gdi.md)  
 <span data-ttu-id="fa724-111">Illustra come ritagliare e ridimensionare immagini raster e vettoriali.</span><span class="sxs-lookup"><span data-stu-id="fa724-111">Explains how to crop and scale vector and raster images.</span></span>  
  
 [<span data-ttu-id="fa724-112">Procedura: Ruotare, riflettere e inclinare immagini</span><span class="sxs-lookup"><span data-stu-id="fa724-112">How to: Rotate, Reflect, and Skew Images</span></span>](../../../../docs/framework/winforms/advanced/how-to-rotate-reflect-and-skew-images.md)  
 <span data-ttu-id="fa724-113">Descrive come disegnare immagini ruotate, riflesse e inclinate.</span><span class="sxs-lookup"><span data-stu-id="fa724-113">Describes how to draw rotated, reflected and skewed images.</span></span>  
  
 [<span data-ttu-id="fa724-114">Procedura: Usare la modalità di interpolazione per controllare la qualità dell'immagine durante l'adattamento</span><span class="sxs-lookup"><span data-stu-id="fa724-114">How to: Use Interpolation Mode to Control Image Quality During Scaling</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-interpolation-mode-to-control-image-quality-during-scaling.md)  
 <span data-ttu-id="fa724-115">Mostra come usare l'enumerazione <xref:System.Drawing.Drawing2D.InterpolationMode> per modificare la qualità dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="fa724-115">Shows how to use the <xref:System.Drawing.Drawing2D.InterpolationMode> enumeration to change image quality.</span></span>  
  
 [<span data-ttu-id="fa724-116">Procedura: Creare miniature</span><span class="sxs-lookup"><span data-stu-id="fa724-116">How to: Create Thumbnail Images</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-thumbnail-images.md)  
 <span data-ttu-id="fa724-117">Descrive come creare miniature.</span><span class="sxs-lookup"><span data-stu-id="fa724-117">Describes how to create thumbnail images.</span></span>  
  
 [<span data-ttu-id="fa724-118">Procedura: Migliorare le prestazioni evitando il ridimensionamento automatico</span><span class="sxs-lookup"><span data-stu-id="fa724-118">How to: Improve Performance by Avoiding Automatic Scaling</span></span>](../../../../docs/framework/winforms/advanced/how-to-improve-performance-by-avoiding-automatic-scaling.md)  
 <span data-ttu-id="fa724-119">Illustra come disegnare un'immagine senza ridimensionamento automatico.</span><span class="sxs-lookup"><span data-stu-id="fa724-119">Explains how to draw an image without automatic scaling.</span></span>  
  
 [<span data-ttu-id="fa724-120">Procedura: Leggere i metadati delle immagini</span><span class="sxs-lookup"><span data-stu-id="fa724-120">How to: Read Image Metadata</span></span>](../../../../docs/framework/winforms/advanced/how-to-read-image-metadata.md)  
 <span data-ttu-id="fa724-121">Descrive come leggere i metadati da un'immagine.</span><span class="sxs-lookup"><span data-stu-id="fa724-121">Describes how to read metadata from an image.</span></span>  
  
 [<span data-ttu-id="fa724-122">Procedura: Creare un oggetto Bitmap in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="fa724-122">How to: Create a Bitmap at Run Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-bitmap-at-run-time.md)  
 <span data-ttu-id="fa724-123">Mostra come disegnare una bitmap in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fa724-123">Shows how to draw a bitmap at runtime.</span></span>  
  
 [<span data-ttu-id="fa724-124">Procedura: Estrarre l'icona associata a un file in Windows Form</span><span class="sxs-lookup"><span data-stu-id="fa724-124">How to: Extract the Icon Associated with a File in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-extract-the-icon-associated-with-a-file-in-windows-forms.md)  
 <span data-ttu-id="fa724-125">Descrive come estrarre un'icona che è una risorsa incorporata di un file.</span><span class="sxs-lookup"><span data-stu-id="fa724-125">Describes how to extract an icon that is an embedded resource of a file.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="fa724-126">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="fa724-126">Reference</span></span>  
 <xref:System.Drawing.Image>  
 <span data-ttu-id="fa724-127">Descrive la classe e include collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="fa724-127">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Imaging.Metafile>  
 <span data-ttu-id="fa724-128">Descrive la classe e include collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="fa724-128">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Bitmap>  
 <span data-ttu-id="fa724-129">Descrive la classe e include collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="fa724-129">Describes this class and has links to all of its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="fa724-130">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="fa724-130">Related Sections</span></span>  
 [<span data-ttu-id="fa724-131">Immagini, bitmap e metafile</span><span class="sxs-lookup"><span data-stu-id="fa724-131">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 <span data-ttu-id="fa724-132">Contiene collegamenti ad argomenti che illustrano diversi tipi di bitmap e come modificarli nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="fa724-132">Contains links to topics that discuss different types of bitmaps and manipulating them in your applications.</span></span>
