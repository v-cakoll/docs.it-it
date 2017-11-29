---
title: 'Procedura: variare le componenti cromatiche'
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
- colors [Windows Forms], transforming with color matrices
- colors [Windows Forms], shearing
ms.assetid: 0a424171-5b8b-45c4-afef-e9720a6c3e22
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 35f89bb5d87ef58c5ecda7be4cb9fb41da08e8a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-shear-colors"></a><span data-ttu-id="94a2b-102">Procedura: variare le componenti cromatiche</span><span class="sxs-lookup"><span data-stu-id="94a2b-102">How to: Shear Colors</span></span>
<span data-ttu-id="94a2b-103">Inclinazione aumenta o diminuisce di un componente di colore in modo proporzionale a un altro componente di colore.</span><span class="sxs-lookup"><span data-stu-id="94a2b-103">Shearing increases or decreases a color component by an amount proportional to another color component.</span></span> <span data-ttu-id="94a2b-104">Si consideri ad esempio la trasformazione in cui il componente rosso viene aumentato la metà il valore del componente blu.</span><span class="sxs-lookup"><span data-stu-id="94a2b-104">For example, consider the transformation where the red component is increased by one half the value of the blue component.</span></span> <span data-ttu-id="94a2b-105">In una trasformazione, il colore (0,2, 0,5, 1) diventa (0,7, 0,5, 1).</span><span class="sxs-lookup"><span data-stu-id="94a2b-105">Under such a transformation, the color (0.2, 0.5, 1) would become (0.7, 0.5, 1).</span></span> <span data-ttu-id="94a2b-106">Il nuovo componente rosso è 0,2 + (1/2)(1) = 0,7.</span><span class="sxs-lookup"><span data-stu-id="94a2b-106">The new red component is 0.2 + (1/2)(1) = 0.7.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94a2b-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="94a2b-107">Example</span></span>  
 <span data-ttu-id="94a2b-108">Nell'esempio seguente viene costruito un <xref:System.Drawing.Image> oggetto dal file Colorbars4.</span><span class="sxs-lookup"><span data-stu-id="94a2b-108">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars4.bmp.</span></span> <span data-ttu-id="94a2b-109">Quindi il codice si applica la trasformazione di inclinazione descritta nel paragrafo precedente per ogni pixel dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="94a2b-109">Then the code applies the shearing transformation described in the preceding paragraph to each pixel in the image.</span></span>  
  
 <span data-ttu-id="94a2b-110">Nella figura seguente mostra l'immagine originale a sinistra e l'immagine tagliata a destra.</span><span class="sxs-lookup"><span data-stu-id="94a2b-110">The following illustration shows the original image on the left and the sheared image on the right.</span></span>  
  
 <span data-ttu-id="94a2b-111">![Cromatiche](../../../../docs/framework/winforms/advanced/media/colortrans6.png "colortrans6")</span><span class="sxs-lookup"><span data-stu-id="94a2b-111">![Shear Colors](../../../../docs/framework/winforms/advanced/media/colortrans6.png "colortrans6")</span></span>  
  
 <span data-ttu-id="94a2b-112">Nella tabella seguente sono elencati i vettori di colore per le quattro barre prima e dopo la trasformazione di inclinazione.</span><span class="sxs-lookup"><span data-stu-id="94a2b-112">The following table lists the color vectors for the four bars before and after the shearing transformation.</span></span>  
  
|<span data-ttu-id="94a2b-113">Originale</span><span class="sxs-lookup"><span data-stu-id="94a2b-113">Original</span></span>|<span data-ttu-id="94a2b-114">Inclinato</span><span class="sxs-lookup"><span data-stu-id="94a2b-114">Sheared</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="94a2b-115">(0, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="94a2b-115">(0, 0, 1, 1)</span></span>|<span data-ttu-id="94a2b-116">(0.5, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="94a2b-116">(0.5, 0, 1, 1)</span></span>|  
|<span data-ttu-id="94a2b-117">(0.5, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="94a2b-117">(0.5, 1, 0.5, 1)</span></span>|<span data-ttu-id="94a2b-118">(0.75, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="94a2b-118">(0.75, 1, 0.5, 1)</span></span>|  
|<span data-ttu-id="94a2b-119">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="94a2b-119">(1, 1, 0, 1)</span></span>|<span data-ttu-id="94a2b-120">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="94a2b-120">(1, 1, 0, 1)</span></span>|  
|<span data-ttu-id="94a2b-121">(0.4, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="94a2b-121">(0.4, 0.4, 0.4, 1)</span></span>|<span data-ttu-id="94a2b-122">(0.6, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="94a2b-122">(0.6, 0.4, 0.4, 1)</span></span>|  
  
 [!code-csharp[System.Drawing.Misc3#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="94a2b-123">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="94a2b-123">Compiling the Code</span></span>  
 <span data-ttu-id="94a2b-124">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs>`e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="94a2b-124">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="94a2b-125">Sostituire `ColorBars.bmp` con un nome dell'immagine e un percorso valido per il sistema.</span><span class="sxs-lookup"><span data-stu-id="94a2b-125">Replace `ColorBars.bmp` with an image name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94a2b-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94a2b-126">See Also</span></span>  
 <xref:System.Drawing.Imaging.ColorMatrix>  
 <xref:System.Drawing.Imaging.ImageAttributes>  
 [<span data-ttu-id="94a2b-127">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="94a2b-127">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="94a2b-128">Ricolorazione di immagini</span><span class="sxs-lookup"><span data-stu-id="94a2b-128">Recoloring Images</span></span>](../../../../docs/framework/winforms/advanced/recoloring-images.md)
