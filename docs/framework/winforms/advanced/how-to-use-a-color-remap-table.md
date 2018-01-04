---
title: 'Procedura: utilizzare una tabella di riassociazione cromatica'
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
- color tables [Windows Forms], remapping colors with
- custom colors [Windows Forms], creating with color remap table
- color remap tables [Windows Forms], using
ms.assetid: 977df1ce-8665-42d4-9fb1-ef7f0ff63419
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6e208aa9c98c1ca19baee83760cfd0f75972ecfa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-color-remap-table"></a><span data-ttu-id="54aa4-102">Procedura: utilizzare una tabella di riassociazione cromatica</span><span class="sxs-lookup"><span data-stu-id="54aa4-102">How to: Use a Color Remap Table</span></span>
<span data-ttu-id="54aa4-103">Modifica del mapping è il processo di conversione dei colori in un'immagine in base a una tabella di modifica del mapping dei colori.</span><span class="sxs-lookup"><span data-stu-id="54aa4-103">Remapping is the process of converting the colors in an image according to a color remap table.</span></span> <span data-ttu-id="54aa4-104">La tabella è una matrice di <xref:System.Drawing.Imaging.ColorMap> oggetti.</span><span class="sxs-lookup"><span data-stu-id="54aa4-104">The color remap table is an array of <xref:System.Drawing.Imaging.ColorMap> objects.</span></span> <span data-ttu-id="54aa4-105">Ogni <xref:System.Drawing.Imaging.ColorMap> oggetto nella matrice è un <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> proprietà e un <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="54aa4-105">Each <xref:System.Drawing.Imaging.ColorMap> object in the array has an <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> property and a <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> property.</span></span>  
  
 <span data-ttu-id="54aa4-106">Quando [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] disegna un'immagine, ogni pixel dell'immagine viene confrontato con la matrice di colori precedente.</span><span class="sxs-lookup"><span data-stu-id="54aa4-106">When [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] draws an image, each pixel of the image is compared to the array of old colors.</span></span> <span data-ttu-id="54aa4-107">Se il colore del pixel corrisponde a un colore precedente, viene modificato il colore per il nuovo colore corrispondente.</span><span class="sxs-lookup"><span data-stu-id="54aa4-107">If a pixel's color matches an old color, its color is changed to the corresponding new color.</span></span> <span data-ttu-id="54aa4-108">I colori vengono modificati solo per il rendering, i valori di colore dell'immagine (archiviati in un <xref:System.Drawing.Image> o <xref:System.Drawing.Bitmap> oggetto) non vengono modificati.</span><span class="sxs-lookup"><span data-stu-id="54aa4-108">The colors are changed only for rendering — the color values of the image itself (stored in an <xref:System.Drawing.Image> or <xref:System.Drawing.Bitmap> object) are not changed.</span></span>  
  
 <span data-ttu-id="54aa4-109">Per disegnare un'immagine riassociata, inizializzare una matrice di <xref:System.Drawing.Imaging.ColorMap> oggetti.</span><span class="sxs-lookup"><span data-stu-id="54aa4-109">To draw a remapped image, initialize an array of <xref:System.Drawing.Imaging.ColorMap> objects.</span></span> <span data-ttu-id="54aa4-110">Passare la matrice di <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> metodo di un <xref:System.Drawing.Imaging.ImageAttributes> dell'oggetto e quindi passare il <xref:System.Drawing.Imaging.ImageAttributes> dell'oggetto per il <xref:System.Drawing.Graphics.DrawImage%2A> metodo di un <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="54aa4-110">Pass that array to the <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> method of an <xref:System.Drawing.Imaging.ImageAttributes> object, and then pass the <xref:System.Drawing.Imaging.ImageAttributes> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54aa4-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="54aa4-111">Example</span></span>  
 <span data-ttu-id="54aa4-112">Nell'esempio seguente viene creato un <xref:System.Drawing.Image> oggetto dal file RemapInput.</span><span class="sxs-lookup"><span data-stu-id="54aa4-112">The following example creates an <xref:System.Drawing.Image> object from the file RemapInput.bmp.</span></span> <span data-ttu-id="54aa4-113">Il codice crea una tabella di riassociazione cromatica costituita da una singola <xref:System.Drawing.Imaging.ColorMap> oggetto.</span><span class="sxs-lookup"><span data-stu-id="54aa4-113">The code creates a color remap table that consists of a single <xref:System.Drawing.Imaging.ColorMap> object.</span></span> <span data-ttu-id="54aa4-114">Il <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> proprietà del `ColorRemap` è rosso, oggetto e <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> proprietà è di colore blu.</span><span class="sxs-lookup"><span data-stu-id="54aa4-114">The <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> property of the `ColorRemap` object is red, and the <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> property is blue.</span></span> <span data-ttu-id="54aa4-115">L'immagine viene disegnata una sola volta senza mapping e una volta con mapping.</span><span class="sxs-lookup"><span data-stu-id="54aa4-115">The image is drawn once without remapping and once with remapping.</span></span> <span data-ttu-id="54aa4-116">Il processo di modifica del mapping modifica tutti i pixel rossi blu.</span><span class="sxs-lookup"><span data-stu-id="54aa4-116">The remapping process changes all the red pixels to blue.</span></span>  
  
 <span data-ttu-id="54aa4-117">Nella figura seguente mostra l'immagine originale a sinistra e l'immagine rimappato a destra.</span><span class="sxs-lookup"><span data-stu-id="54aa4-117">The following illustration shows the original image on the left and the remapped image on the right.</span></span>  
  
 <span data-ttu-id="54aa4-118">![Modifica del mapping dei colori](../../../../docs/framework/winforms/advanced/media/colortrans7.png "colortrans7")</span><span class="sxs-lookup"><span data-stu-id="54aa4-118">![Color ReMap](../../../../docs/framework/winforms/advanced/media/colortrans7.png "colortrans7")</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.RecoloringImages#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="54aa4-119">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="54aa4-119">Compiling the Code</span></span>  
 <span data-ttu-id="54aa4-120">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="54aa4-120">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54aa4-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54aa4-121">See Also</span></span>  
 [<span data-ttu-id="54aa4-122">Ricolorazione di immagini</span><span class="sxs-lookup"><span data-stu-id="54aa4-122">Recoloring Images</span></span>](../../../../docs/framework/winforms/advanced/recoloring-images.md)  
 [<span data-ttu-id="54aa4-123">Immagini, bitmap e metafile</span><span class="sxs-lookup"><span data-stu-id="54aa4-123">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
