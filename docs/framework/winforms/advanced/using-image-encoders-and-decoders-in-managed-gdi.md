---
title: Utilizzo di codificatori e decodificatori di immagini nel codice gestito GDI+
ms.date: 03/30/2017
helpviewer_keywords:
- image encoders [Windows Forms], using
- image decoders [Windows Forms], using
ms.assetid: 0e838ea1-4e7e-4334-b882-ab25df607b8b
ms.openlocfilehash: bf0d3a64ce8860d67f0dcfd37c780f03fbd7471a
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57713262"
---
# <a name="using-image-encoders-and-decoders-in-managed-gdi"></a><span data-ttu-id="3c81b-102">Utilizzo di codificatori e decodificatori di immagini nel codice gestito GDI+</span><span class="sxs-lookup"><span data-stu-id="3c81b-102">Using Image Encoders and Decoders in Managed GDI+</span></span>
<span data-ttu-id="3c81b-103">Il <xref:System.Drawing> spazio dei nomi fornisce le <xref:System.Drawing.Image> e <xref:System.Drawing.Bitmap> classi per l'archiviazione e la modifica delle immagini.</span><span class="sxs-lookup"><span data-stu-id="3c81b-103">The <xref:System.Drawing> namespace provides the <xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> classes for storing and manipulating images.</span></span> <span data-ttu-id="3c81b-104">Usando codificatori di immagini in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], è possibile scrivere le immagini dalla memoria su disco.</span><span class="sxs-lookup"><span data-stu-id="3c81b-104">By using image encoders in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you can write images from memory to disk.</span></span> <span data-ttu-id="3c81b-105">Utilizzando i decodificatori di immagine in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], è possibile caricare immagini dal disco in memoria.</span><span class="sxs-lookup"><span data-stu-id="3c81b-105">By using image decoders in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you can load images from disk into memory.</span></span> <span data-ttu-id="3c81b-106">Un codificatore converte i dati in un' <xref:System.Drawing.Image> o <xref:System.Drawing.Bitmap> oggetto in un formato di file di disco designato.</span><span class="sxs-lookup"><span data-stu-id="3c81b-106">An encoder translates the data in an <xref:System.Drawing.Image> or <xref:System.Drawing.Bitmap> object into a designated disk file format.</span></span> <span data-ttu-id="3c81b-107">Un decodificatore converte i dati in un file di disco per il formato richiesto per il <xref:System.Drawing.Image> e <xref:System.Drawing.Bitmap> oggetti.</span><span class="sxs-lookup"><span data-stu-id="3c81b-107">A decoder translates the data in a disk file to the format required by the <xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> objects.</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="3c81b-108">ha incorporati codificatori e decodificatori di immagini che supportano i tipi di file seguenti:</span><span class="sxs-lookup"><span data-stu-id="3c81b-108">has built-in encoders and decoders that support the following file types:</span></span>  
  
-   <span data-ttu-id="3c81b-109">BMP</span><span class="sxs-lookup"><span data-stu-id="3c81b-109">BMP</span></span>  
  
-   <span data-ttu-id="3c81b-110">GIF</span><span class="sxs-lookup"><span data-stu-id="3c81b-110">GIF</span></span>  
  
-   <span data-ttu-id="3c81b-111">JPEG</span><span class="sxs-lookup"><span data-stu-id="3c81b-111">JPEG</span></span>  
  
-   <span data-ttu-id="3c81b-112">PNG</span><span class="sxs-lookup"><span data-stu-id="3c81b-112">PNG</span></span>  
  
-   <span data-ttu-id="3c81b-113">TIFF</span><span class="sxs-lookup"><span data-stu-id="3c81b-113">TIFF</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="3c81b-114">sono disponibili anche decodificatori di immagini predefinite che supportano i tipi di file seguenti:</span><span class="sxs-lookup"><span data-stu-id="3c81b-114">also has built-in decoders that support the following file types:</span></span>  
  
-   <span data-ttu-id="3c81b-115">WMF</span><span class="sxs-lookup"><span data-stu-id="3c81b-115">WMF</span></span>  
  
-   <span data-ttu-id="3c81b-116">EMF</span><span class="sxs-lookup"><span data-stu-id="3c81b-116">EMF</span></span>  
  
-   <span data-ttu-id="3c81b-117">ICON</span><span class="sxs-lookup"><span data-stu-id="3c81b-117">ICON</span></span>  
  
 <span data-ttu-id="3c81b-118">Gli argomenti seguenti descrivono i codificatori e decodificatori di immagini in modo più dettagliato:</span><span class="sxs-lookup"><span data-stu-id="3c81b-118">The following topics discuss encoders and decoders in more detail:</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3c81b-119">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="3c81b-119">In This Section</span></span>  
 [<span data-ttu-id="3c81b-120">Procedura: Elencare i codificatori installati</span><span class="sxs-lookup"><span data-stu-id="3c81b-120">How to: List Installed Encoders</span></span>](how-to-list-installed-encoders.md)  
 <span data-ttu-id="3c81b-121">Descrive come elencare i codificatori disponibili in un computer.</span><span class="sxs-lookup"><span data-stu-id="3c81b-121">Describes how to list the encoders available on a computer.</span></span>  
  
 [<span data-ttu-id="3c81b-122">Procedura: Elencare i decodificatori installati</span><span class="sxs-lookup"><span data-stu-id="3c81b-122">How to: List Installed Decoders</span></span>](how-to-list-installed-decoders.md)  
 <span data-ttu-id="3c81b-123">Viene descritto come elencare i decodificatori disponibili in un computer.</span><span class="sxs-lookup"><span data-stu-id="3c81b-123">Describes how to list the decoders available on a computer.</span></span>  
  
 [<span data-ttu-id="3c81b-124">Procedura: Determinare i parametri supportati da un codificatore</span><span class="sxs-lookup"><span data-stu-id="3c81b-124">How to: Determine the Parameters Supported by an Encoder</span></span>](how-to-determine-the-parameters-supported-by-an-encoder.md)  
 <span data-ttu-id="3c81b-125">Viene illustrato come elencare le <xref:System.Drawing.Imaging.EncoderParameters> supportati da un codificatore.</span><span class="sxs-lookup"><span data-stu-id="3c81b-125">Describes how to list the <xref:System.Drawing.Imaging.EncoderParameters> supported by an encoder.</span></span>  
  
 [<span data-ttu-id="3c81b-126">Procedura: Convertire un'immagine BMP in un'immagine PNG</span><span class="sxs-lookup"><span data-stu-id="3c81b-126">How to: Convert a BMP image to a PNG image</span></span>](how-to-convert-a-bmp-image-to-a-png-image.md)  
 <span data-ttu-id="3c81b-127">Viene descritto come salvare un'immagine in un formato di immagine diversi.</span><span class="sxs-lookup"><span data-stu-id="3c81b-127">Describes how to save a image in a different image format.</span></span>  
  
 [<span data-ttu-id="3c81b-128">Procedura: Impostare il livello di compressione JPEG</span><span class="sxs-lookup"><span data-stu-id="3c81b-128">How to: Set JPEG Compression Level</span></span>](how-to-set-jpeg-compression-level.md)  
 <span data-ttu-id="3c81b-129">Viene descritto come modificare il livello di qualità di un'immagine.</span><span class="sxs-lookup"><span data-stu-id="3c81b-129">Describes how to change the quality level of an image.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="3c81b-130">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="3c81b-130">Reference</span></span>  
 <xref:System.Drawing.Image>  
  
 <xref:System.Drawing.Bitmap>  
  
 <xref:System.Drawing.Imaging.ImageCodecInfo>  
  
 <xref:System.Drawing.Imaging.EncoderParameter>  
  
 <xref:System.Drawing.Imaging.Encoder>  
  
## <a name="related-sections"></a><span data-ttu-id="3c81b-131">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="3c81b-131">Related Sections</span></span>  
 [<span data-ttu-id="3c81b-132">Informazioni sul codice gestito GDI+</span><span class="sxs-lookup"><span data-stu-id="3c81b-132">About GDI+ Managed Code</span></span>](about-gdi-managed-code.md)  
  
 [<span data-ttu-id="3c81b-133">Immagini, bitmap e metafile</span><span class="sxs-lookup"><span data-stu-id="3c81b-133">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
