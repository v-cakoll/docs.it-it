---
title: 'Procedura: Variare le componenti cromatiche'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], transforming with color matrices
- colors [Windows Forms], shearing
ms.assetid: 0a424171-5b8b-45c4-afef-e9720a6c3e22
ms.openlocfilehash: bb5f9043ea5bdd25e984d73d3640c80f599714e6
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826392"
---
# <a name="how-to-shear-colors"></a><span data-ttu-id="4a34b-102">Procedura: Variare le componenti cromatiche</span><span class="sxs-lookup"><span data-stu-id="4a34b-102">How to: Shear Colors</span></span>
<span data-ttu-id="4a34b-103">Inclinazione aumenta o diminuisce di un componente di colore in modo proporzionale a un altro componente di colore.</span><span class="sxs-lookup"><span data-stu-id="4a34b-103">Shearing increases or decreases a color component by an amount proportional to another color component.</span></span> <span data-ttu-id="4a34b-104">Si consideri ad esempio la trasformazione in cui il componente rossa viene incrementato della metà di quella del valore del componente blu.</span><span class="sxs-lookup"><span data-stu-id="4a34b-104">For example, consider the transformation where the red component is increased by one half the value of the blue component.</span></span> <span data-ttu-id="4a34b-105">In una trasformazione di questo tipo, il colore (0,2, 0.5, 1) diventerebbe (0,7, 0.5, 1).</span><span class="sxs-lookup"><span data-stu-id="4a34b-105">Under such a transformation, the color (0.2, 0.5, 1) would become (0.7, 0.5, 1).</span></span> <span data-ttu-id="4a34b-106">Il nuovo componente rossa è la 0.2 + (1/2)(1) = 0,7.</span><span class="sxs-lookup"><span data-stu-id="4a34b-106">The new red component is 0.2 + (1/2)(1) = 0.7.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a34b-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="4a34b-107">Example</span></span>  
 <span data-ttu-id="4a34b-108">Nell'esempio seguente si costruisce un <xref:System.Drawing.Image> oggetto Colorbars4 nel file.</span><span class="sxs-lookup"><span data-stu-id="4a34b-108">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars4.bmp.</span></span> <span data-ttu-id="4a34b-109">Il codice applica quindi la trasformazione di inclinazione descritta nel paragrafo precedente per ogni pixel nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="4a34b-109">Then the code applies the shearing transformation described in the preceding paragraph to each pixel in the image.</span></span>  
  
 <span data-ttu-id="4a34b-110">Nella figura seguente mostra l'immagine originale a sinistra e l'immagine tagliata a destra:</span><span class="sxs-lookup"><span data-stu-id="4a34b-110">The following illustration shows the original image on the left and the sheared image on the right:</span></span> 
  
 ![Due dei quadrati con strisce colorato side-by-side che illustra l'immagine originale e l'immagine tagliata.](./media/how-to-shear-colors/original-image-sheared-image.png)  
  
 <span data-ttu-id="4a34b-112">La tabella seguente elenca i vettori di colore per le quattro barre prima e dopo la trasformazione di inclinazione.</span><span class="sxs-lookup"><span data-stu-id="4a34b-112">The following table lists the color vectors for the four bars before and after the shearing transformation.</span></span>  
  
|<span data-ttu-id="4a34b-113">Originale</span><span class="sxs-lookup"><span data-stu-id="4a34b-113">Original</span></span>|<span data-ttu-id="4a34b-114">Inclinato</span><span class="sxs-lookup"><span data-stu-id="4a34b-114">Sheared</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="4a34b-115">(0, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="4a34b-115">(0, 0, 1, 1)</span></span>|<span data-ttu-id="4a34b-116">(0.5, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="4a34b-116">(0.5, 0, 1, 1)</span></span>|  
|<span data-ttu-id="4a34b-117">(0.5, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="4a34b-117">(0.5, 1, 0.5, 1)</span></span>|<span data-ttu-id="4a34b-118">(0.75, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="4a34b-118">(0.75, 1, 0.5, 1)</span></span>|  
|<span data-ttu-id="4a34b-119">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="4a34b-119">(1, 1, 0, 1)</span></span>|<span data-ttu-id="4a34b-120">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="4a34b-120">(1, 1, 0, 1)</span></span>|  
|<span data-ttu-id="4a34b-121">(0.4, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="4a34b-121">(0.4, 0.4, 0.4, 1)</span></span>|<span data-ttu-id="4a34b-122">(0.6, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="4a34b-122">(0.6, 0.4, 0.4, 1)</span></span>|  
  
 [!code-csharp[System.Drawing.Misc3#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4a34b-123">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="4a34b-123">Compiling the Code</span></span>  
 <span data-ttu-id="4a34b-124">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs>`e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="4a34b-124">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="4a34b-125">Sostituire `ColorBars.bmp` con un nome di immagine e un percorso valido nel sistema.</span><span class="sxs-lookup"><span data-stu-id="4a34b-125">Replace `ColorBars.bmp` with an image name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a34b-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a34b-126">See also</span></span>
- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="4a34b-127">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="4a34b-127">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="4a34b-128">Ricolorazione di immagini</span><span class="sxs-lookup"><span data-stu-id="4a34b-128">Recoloring Images</span></span>](recoloring-images.md)
