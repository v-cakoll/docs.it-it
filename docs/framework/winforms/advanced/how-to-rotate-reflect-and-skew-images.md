---
title: 'Procedura: ruotare, riflettere e inclinare immagini'
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
- images [Windows Forms], reflecting
- images [Windows Forms], rotating
- images [Windows Forms], skewing
ms.assetid: a3bf97eb-63ed-425a-ba07-dcc65efb567c
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: eaa6286731d196dad387e1648644ca3e8103da03
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-rotate-reflect-and-skew-images"></a><span data-ttu-id="f477e-102">Procedura: ruotare, riflettere e inclinare immagini</span><span class="sxs-lookup"><span data-stu-id="f477e-102">How to: Rotate, Reflect, and Skew Images</span></span>
<span data-ttu-id="f477e-103">È possibile ruotare, riflettere e inclinare un'immagine, specificando i punti di destinazione per gli angoli superiore sinistro, superiore destro e inferiore sinistro dell'immagine originale.</span><span class="sxs-lookup"><span data-stu-id="f477e-103">You can rotate, reflect, and skew an image by specifying destination points for the upper-left, upper-right, and lower-left corners of the original image.</span></span> <span data-ttu-id="f477e-104">I punti di tre destinazione determinano una trasformazione affine che esegue il mapping dell'immagine rettangolare originale in un parallelogramma.</span><span class="sxs-lookup"><span data-stu-id="f477e-104">The three destination points determine an affine transformation that maps the original rectangular image to a parallelogram.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f477e-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="f477e-105">Example</span></span>  
 <span data-ttu-id="f477e-106">Ad esempio, si supponga che l'immagine originale è un rettangolo con angoli superiore sinistro (0, 0), nell'angolo superiore destro in (100, 0) e nell'angolo inferiore sinistro a (0, 50).</span><span class="sxs-lookup"><span data-stu-id="f477e-106">For example, suppose the original image is a rectangle with upper-left corner at (0, 0), upper-right corner at (100, 0), and lower-left corner at (0, 50).</span></span> <span data-ttu-id="f477e-107">Ora si supponga che si esegue il mapping di quelli di tre punti ai punti di destinazione come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="f477e-107">Now suppose you map those three points to destination points as follows.</span></span>  
  
|<span data-ttu-id="f477e-108">Punto originale</span><span class="sxs-lookup"><span data-stu-id="f477e-108">Original point</span></span>|<span data-ttu-id="f477e-109">Punto di destinazione</span><span class="sxs-lookup"><span data-stu-id="f477e-109">Destination point</span></span>|  
|--------------------|-----------------------|  
|<span data-ttu-id="f477e-110">Alto-sinistra (0, 0)</span><span class="sxs-lookup"><span data-stu-id="f477e-110">Upper-left (0, 0)</span></span>|<span data-ttu-id="f477e-111">(200, 20)</span><span class="sxs-lookup"><span data-stu-id="f477e-111">(200, 20)</span></span>|  
|<span data-ttu-id="f477e-112">Alto-destra (100, 0)</span><span class="sxs-lookup"><span data-stu-id="f477e-112">Upper-right (100, 0)</span></span>|<span data-ttu-id="f477e-113">(110, 100)</span><span class="sxs-lookup"><span data-stu-id="f477e-113">(110, 100)</span></span>|  
|<span data-ttu-id="f477e-114">Basso-sinistra (0, 50)</span><span class="sxs-lookup"><span data-stu-id="f477e-114">Lower-left (0, 50)</span></span>|<span data-ttu-id="f477e-115">(250, 30)</span><span class="sxs-lookup"><span data-stu-id="f477e-115">(250, 30)</span></span>|  
  
 <span data-ttu-id="f477e-116">Nella figura seguente mostra l'immagine originale e l'immagine associata al parallelogramma.</span><span class="sxs-lookup"><span data-stu-id="f477e-116">The following illustration shows the original image and the image mapped to the parallelogram.</span></span> <span data-ttu-id="f477e-117">L'immagine originale è stata inclinata, riflessa, ruotata e convertito.</span><span class="sxs-lookup"><span data-stu-id="f477e-117">The original image has been skewed, reflected, rotated, and translated.</span></span> <span data-ttu-id="f477e-118">L'asse x lungo il bordo superiore dell'immagine originale viene eseguito il mapping alla riga in cui viene eseguito tramite (200, 20) e (110, 100).</span><span class="sxs-lookup"><span data-stu-id="f477e-118">The x-axis along the top edge of the original image is mapped to the line that runs through (200, 20) and (110, 100).</span></span> <span data-ttu-id="f477e-119">L'asse y lungo il bordo sinistro dell'immagine originale viene eseguito il mapping alla riga in cui viene eseguito tramite (200, 20) e (250, 30).</span><span class="sxs-lookup"><span data-stu-id="f477e-119">The y-axis along the left edge of the original image is mapped to the line that runs through (200, 20) and (250, 30).</span></span>  
  
 <span data-ttu-id="f477e-120">![Strisce](../../../../docs/framework/winforms/advanced/media/stripes1.gif "Stripes1")</span><span class="sxs-lookup"><span data-stu-id="f477e-120">![Stripes](../../../../docs/framework/winforms/advanced/media/stripes1.gif "Stripes1")</span></span>  
  
 <span data-ttu-id="f477e-121">Nella figura seguente mostra una trasformazione analoga applicata a un'immagine fotografica.</span><span class="sxs-lookup"><span data-stu-id="f477e-121">The following illustration shows a similar transformation applied to a photographic image.</span></span>  
  
 <span data-ttu-id="f477e-122">![Aumento trasformato](../../../../docs/framework/winforms/advanced/media/transformedclimber.png "TransformedClimber")</span><span class="sxs-lookup"><span data-stu-id="f477e-122">![Transformed Climber](../../../../docs/framework/winforms/advanced/media/transformedclimber.png "TransformedClimber")</span></span>  
  
 <span data-ttu-id="f477e-123">Nella figura seguente mostra una trasformazione analoga applicata a un metafile.</span><span class="sxs-lookup"><span data-stu-id="f477e-123">The following illustration shows a similar transformation applied to a metafile.</span></span>  
  
 <span data-ttu-id="f477e-124">![Trasformato Metafile](../../../../docs/framework/winforms/advanced/media/transformedmetafile.png "TransformedMetafile")</span><span class="sxs-lookup"><span data-stu-id="f477e-124">![Transformed Metafile](../../../../docs/framework/winforms/advanced/media/transformedmetafile.png "TransformedMetafile")</span></span>  
  
 <span data-ttu-id="f477e-125">Nell'esempio seguente genera le immagini mostrate nella prima figura.</span><span class="sxs-lookup"><span data-stu-id="f477e-125">The following example produces the images shown in the first illustration.</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.WorkingWithImages#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f477e-126">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="f477e-126">Compiling the Code</span></span>  
 <span data-ttu-id="f477e-127">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs>`e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="f477e-127">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="f477e-128">Assicurarsi di sostituire `Stripes.bmp` con il percorso di un'immagine che è valido per il sistema.</span><span class="sxs-lookup"><span data-stu-id="f477e-128">Make sure to replace `Stripes.bmp` with the path to an image that is valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f477e-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f477e-129">See Also</span></span>  
 [<span data-ttu-id="f477e-130">Utilizzo di immagini, bitmap, icone e metafile</span><span class="sxs-lookup"><span data-stu-id="f477e-130">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
