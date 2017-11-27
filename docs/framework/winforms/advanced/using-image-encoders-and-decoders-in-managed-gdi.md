---
title: Utilizzo di codificatori e decodificatori di immagini nel codice gestito GDI+
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- image encoders [Windows Forms], using
- image decoders [Windows Forms], using
ms.assetid: 0e838ea1-4e7e-4334-b882-ab25df607b8b
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 64384e3c283b6596e36d5b2bd583a304faf080b4
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="using-image-encoders-and-decoders-in-managed-gdi"></a><span data-ttu-id="8a720-102">Utilizzo di codificatori e decodificatori di immagini nel codice gestito GDI+</span><span class="sxs-lookup"><span data-stu-id="8a720-102">Using Image Encoders and Decoders in Managed GDI+</span></span>
<span data-ttu-id="8a720-103">Il <xref:System.Drawing> spazio dei nomi fornisce il <xref:System.Drawing.Image> e <xref:System.Drawing.Bitmap> classi per l'archiviazione e la modifica di immagini.</span><span class="sxs-lookup"><span data-stu-id="8a720-103">The <xref:System.Drawing> namespace provides the <xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> classes for storing and manipulating images.</span></span> <span data-ttu-id="8a720-104">Utilizzando i codificatori in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], è possibile scrivere le immagini dalla memoria su disco.</span><span class="sxs-lookup"><span data-stu-id="8a720-104">By using image encoders in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you can write images from memory to disk.</span></span> <span data-ttu-id="8a720-105">Utilizzando i decodificatori di immagini in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], è possibile caricare immagini dal disco nella memoria.</span><span class="sxs-lookup"><span data-stu-id="8a720-105">By using image decoders in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you can load images from disk into memory.</span></span> <span data-ttu-id="8a720-106">Un decodificatore converte i dati in un <xref:System.Drawing.Image> o <xref:System.Drawing.Bitmap> oggetto in un formato di file di disco designato.</span><span class="sxs-lookup"><span data-stu-id="8a720-106">An encoder translates the data in an <xref:System.Drawing.Image> or <xref:System.Drawing.Bitmap> object into a designated disk file format.</span></span> <span data-ttu-id="8a720-107">Un decodificatore converte i dati in un file su disco per il formato richiesto dal <xref:System.Drawing.Image> e <xref:System.Drawing.Bitmap> oggetti.</span><span class="sxs-lookup"><span data-stu-id="8a720-107">A decoder translates the data in a disk file to the format required by the <xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> objects.</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="8a720-108">dispone di codificatori e decodificatori che supportano i seguenti tipi di file incorporati:</span><span class="sxs-lookup"><span data-stu-id="8a720-108"> has built-in encoders and decoders that support the following file types:</span></span>  
  
-   <span data-ttu-id="8a720-109">BMP</span><span class="sxs-lookup"><span data-stu-id="8a720-109">BMP</span></span>  
  
-   <span data-ttu-id="8a720-110">GIF</span><span class="sxs-lookup"><span data-stu-id="8a720-110">GIF</span></span>  
  
-   <span data-ttu-id="8a720-111">JPEG</span><span class="sxs-lookup"><span data-stu-id="8a720-111">JPEG</span></span>  
  
-   <span data-ttu-id="8a720-112">PNG</span><span class="sxs-lookup"><span data-stu-id="8a720-112">PNG</span></span>  
  
-   <span data-ttu-id="8a720-113">TIFF</span><span class="sxs-lookup"><span data-stu-id="8a720-113">TIFF</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="8a720-114">dispone di decodificatori incorporati che supportano i tipi di file seguenti:</span><span class="sxs-lookup"><span data-stu-id="8a720-114"> also has built-in decoders that support the following file types:</span></span>  
  
-   <span data-ttu-id="8a720-115">WMF</span><span class="sxs-lookup"><span data-stu-id="8a720-115">WMF</span></span>  
  
-   <span data-ttu-id="8a720-116">EMF</span><span class="sxs-lookup"><span data-stu-id="8a720-116">EMF</span></span>  
  
-   <span data-ttu-id="8a720-117">ICONA</span><span class="sxs-lookup"><span data-stu-id="8a720-117">ICON</span></span>  
  
 <span data-ttu-id="8a720-118">Gli argomenti seguenti descrivono i codificatori e decodificatori in modo più dettagliato:</span><span class="sxs-lookup"><span data-stu-id="8a720-118">The following topics discuss encoders and decoders in more detail:</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8a720-119">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="8a720-119">In This Section</span></span>  
 [<span data-ttu-id="8a720-120">Procedura: Elencare i codificatori installati</span><span class="sxs-lookup"><span data-stu-id="8a720-120">How to: List Installed Encoders</span></span>](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)  
 <span data-ttu-id="8a720-121">Viene descritto come elencare i codificatori disponibili in un computer.</span><span class="sxs-lookup"><span data-stu-id="8a720-121">Describes how to list the encoders available on a computer.</span></span>  
  
 [<span data-ttu-id="8a720-122">Procedura: Elencare i decodificatori installati</span><span class="sxs-lookup"><span data-stu-id="8a720-122">How to: List Installed Decoders</span></span>](../../../../docs/framework/winforms/advanced/how-to-list-installed-decoders.md)  
 <span data-ttu-id="8a720-123">Viene descritto come elencare i decodificatori disponibili in un computer.</span><span class="sxs-lookup"><span data-stu-id="8a720-123">Describes how to list the decoders available on a computer.</span></span>  
  
 [<span data-ttu-id="8a720-124">Procedura: Determinare i parametri supportati da un codificatore</span><span class="sxs-lookup"><span data-stu-id="8a720-124">How to: Determine the Parameters Supported by an Encoder</span></span>](../../../../docs/framework/winforms/advanced/how-to-determine-the-parameters-supported-by-an-encoder.md)  
 <span data-ttu-id="8a720-125">Viene illustrato come elencare le <xref:System.Drawing.Imaging.EncoderParameters> supportati da un codificatore.</span><span class="sxs-lookup"><span data-stu-id="8a720-125">Describes how to list the <xref:System.Drawing.Imaging.EncoderParameters> supported by an encoder.</span></span>  
  
 [<span data-ttu-id="8a720-126">Procedura: Convertire un'immagine BMP in un'immagine PNG</span><span class="sxs-lookup"><span data-stu-id="8a720-126">How to: Convert a BMP image to a PNG image</span></span>](../../../../docs/framework/winforms/advanced/how-to-convert-a-bmp-image-to-a-png-image.md)  
 <span data-ttu-id="8a720-127">Viene descritto come salvare un'immagine in un formato di immagine diverso.</span><span class="sxs-lookup"><span data-stu-id="8a720-127">Describes how to save a image in a different image format.</span></span>  
  
 [<span data-ttu-id="8a720-128">Procedura: Impostare il livello di compressione JPEG</span><span class="sxs-lookup"><span data-stu-id="8a720-128">How to: Set JPEG Compression Level</span></span>](../../../../docs/framework/winforms/advanced/how-to-set-jpeg-compression-level.md)  
 <span data-ttu-id="8a720-129">Viene descritto come modificare il livello di qualità di un'immagine.</span><span class="sxs-lookup"><span data-stu-id="8a720-129">Describes how to change the quality level of an image.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="8a720-130">Riferimento</span><span class="sxs-lookup"><span data-stu-id="8a720-130">Reference</span></span>  
 <xref:System.Drawing.Image>  
  
 <xref:System.Drawing.Bitmap>  
  
 <xref:System.Drawing.Imaging.ImageCodecInfo>  
  
 <xref:System.Drawing.Imaging.EncoderParameter>  
  
 <xref:System.Drawing.Imaging.Encoder>  
  
## <a name="related-sections"></a><span data-ttu-id="8a720-131">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="8a720-131">Related Sections</span></span>  
 [<span data-ttu-id="8a720-132">Informazioni sul codice gestito GDI+</span><span class="sxs-lookup"><span data-stu-id="8a720-132">About GDI+ Managed Code</span></span>](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)  
  
 [<span data-ttu-id="8a720-133">Immagini, bitmap e metafile</span><span class="sxs-lookup"><span data-stu-id="8a720-133">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
