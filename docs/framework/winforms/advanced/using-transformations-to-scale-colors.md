---
title: Utilizzo delle trasformazioni per scalare i colori
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
- transformations [Windows Forms], for scaling colors
- colors [Windows Forms], scaling
ms.assetid: df23c887-7fd6-4b15-ad94-e30b5bd4b849
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7515f34858ef6f4b0495ac6fc545ae498d45c7f9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="using-transformations-to-scale-colors"></a><span data-ttu-id="264e8-102">Utilizzo delle trasformazioni per scalare i colori</span><span class="sxs-lookup"><span data-stu-id="264e8-102">Using Transformations to Scale Colors</span></span>
<span data-ttu-id="264e8-103">Una trasformazione di ridimensionamento Moltiplica uno o più di quattro componenti di colore da un numero.</span><span class="sxs-lookup"><span data-stu-id="264e8-103">A scaling transformation multiplies one or more of the four color components by a number.</span></span> <span data-ttu-id="264e8-104">Le voci della matrice di colori che rappresentano l'adattamento sono indicate nella tabella riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="264e8-104">The color matrix entries that represent scaling are given in the following table.</span></span>  
  
|<span data-ttu-id="264e8-105">Componente scalabilità</span><span class="sxs-lookup"><span data-stu-id="264e8-105">Component to be scaled</span></span>|<span data-ttu-id="264e8-106">Voce della matrice</span><span class="sxs-lookup"><span data-stu-id="264e8-106">Matrix entry</span></span>|  
|----------------------------|------------------|  
|<span data-ttu-id="264e8-107">Rosso</span><span class="sxs-lookup"><span data-stu-id="264e8-107">Red</span></span>|<span data-ttu-id="264e8-108">[0][0]</span><span class="sxs-lookup"><span data-stu-id="264e8-108">[0][0]</span></span>|  
|<span data-ttu-id="264e8-109">Verde</span><span class="sxs-lookup"><span data-stu-id="264e8-109">Green</span></span>|<span data-ttu-id="264e8-110">[1][1]</span><span class="sxs-lookup"><span data-stu-id="264e8-110">[1][1]</span></span>|  
|<span data-ttu-id="264e8-111">Blu</span><span class="sxs-lookup"><span data-stu-id="264e8-111">Blue</span></span>|<span data-ttu-id="264e8-112">[2][2]</span><span class="sxs-lookup"><span data-stu-id="264e8-112">[2][2]</span></span>|  
|<span data-ttu-id="264e8-113">Alfa</span><span class="sxs-lookup"><span data-stu-id="264e8-113">Alpha</span></span>|<span data-ttu-id="264e8-114">[3][3]</span><span class="sxs-lookup"><span data-stu-id="264e8-114">[3][3]</span></span>|  
  
## <a name="scaling-one-color"></a><span data-ttu-id="264e8-115">Adattamento di un colore</span><span class="sxs-lookup"><span data-stu-id="264e8-115">Scaling One Color</span></span>  
 <span data-ttu-id="264e8-116">Nell'esempio seguente viene costruito un <xref:System.Drawing.Image> oggetto dal file Colorbars2.</span><span class="sxs-lookup"><span data-stu-id="264e8-116">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars2.bmp.</span></span> <span data-ttu-id="264e8-117">Il codice quindi ridimensiona il componente blu di ciascun pixel nell'immagine di un fattore pari a 2.</span><span class="sxs-lookup"><span data-stu-id="264e8-117">Then the code scales the blue component of each pixel in the image by a factor of 2.</span></span> <span data-ttu-id="264e8-118">L'immagine originale viene disegnato accanto all'immagine trasformata.</span><span class="sxs-lookup"><span data-stu-id="264e8-118">The original image is drawn alongside the transformed image.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.RecoloringImages#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#41)]  
  
 <span data-ttu-id="264e8-119">Nella figura seguente mostra l'immagine originale a sinistra e l'immagine adattata a destra.</span><span class="sxs-lookup"><span data-stu-id="264e8-119">The following illustration shows the original image on the left and the scaled image on the right.</span></span>  
  
 <span data-ttu-id="264e8-120">![Scalare i colori](../../../../docs/framework/winforms/advanced/media/colortrans3.png "colortrans3")</span><span class="sxs-lookup"><span data-stu-id="264e8-120">![Scale Colors](../../../../docs/framework/winforms/advanced/media/colortrans3.png "colortrans3")</span></span>  
  
 <span data-ttu-id="264e8-121">Nella tabella seguente sono elencati i vettori di colore per le quattro barre prima e dopo il ridimensionamento blu.</span><span class="sxs-lookup"><span data-stu-id="264e8-121">The following table lists the color vectors for the four bars before and after the blue scaling.</span></span> <span data-ttu-id="264e8-122">Si noti che il componente blu nella quarta barra di colore è passato da 0,8 a 0,6.</span><span class="sxs-lookup"><span data-stu-id="264e8-122">Note that the blue component in the fourth color bar went from 0.8 to 0.6.</span></span> <span data-ttu-id="264e8-123">Ciò accade perché [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] mantiene solo la parte frazionaria del risultato.</span><span class="sxs-lookup"><span data-stu-id="264e8-123">That is because [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] retains only the fractional part of the result.</span></span> <span data-ttu-id="264e8-124">Ad esempio, (2)(0.8) = 1.6, e la parte frazionaria 1.6 è 0,6.</span><span class="sxs-lookup"><span data-stu-id="264e8-124">For example, (2)(0.8) = 1.6, and the fractional part of 1.6 is 0.6.</span></span> <span data-ttu-id="264e8-125">Mantenendo solo la parte frazionaria assicura che il risultato è sempre nell'intervallo [0, 1].</span><span class="sxs-lookup"><span data-stu-id="264e8-125">Retaining only the fractional part ensures that the result is always in the interval [0, 1].</span></span>  
  
|<span data-ttu-id="264e8-126">Originale</span><span class="sxs-lookup"><span data-stu-id="264e8-126">Original</span></span>|<span data-ttu-id="264e8-127">Scala</span><span class="sxs-lookup"><span data-stu-id="264e8-127">Scaled</span></span>|  
|--------------|------------|  
|<span data-ttu-id="264e8-128">(0.4, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="264e8-128">(0.4, 0.4, 0.4, 1)</span></span>|<span data-ttu-id="264e8-129">(0.4, 0.4, 0.8, 1)</span><span class="sxs-lookup"><span data-stu-id="264e8-129">(0.4, 0.4, 0.8, 1)</span></span>|  
|<span data-ttu-id="264e8-130">(0.4, 0.2, 0.2, 1)</span><span class="sxs-lookup"><span data-stu-id="264e8-130">(0.4, 0.2, 0.2, 1)</span></span>|<span data-ttu-id="264e8-131">(0.4, 0.2, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="264e8-131">(0.4, 0.2, 0.4, 1)</span></span>|  
|<span data-ttu-id="264e8-132">(0.2, 0.4, 0.2, 1)</span><span class="sxs-lookup"><span data-stu-id="264e8-132">(0.2, 0.4, 0.2, 1)</span></span>|<span data-ttu-id="264e8-133">(0.2, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="264e8-133">(0.2, 0.4, 0.4, 1)</span></span>|  
|<span data-ttu-id="264e8-134">(0.4, 0.4, 0.8, 1)</span><span class="sxs-lookup"><span data-stu-id="264e8-134">(0.4, 0.4, 0.8, 1)</span></span>|<span data-ttu-id="264e8-135">(0.4, 0.4, 0.6, 1)</span><span class="sxs-lookup"><span data-stu-id="264e8-135">(0.4, 0.4, 0.6, 1)</span></span>|  
  
## <a name="scaling-multiple-colors"></a><span data-ttu-id="264e8-136">Adattamento dei colori più</span><span class="sxs-lookup"><span data-stu-id="264e8-136">Scaling Multiple Colors</span></span>  
 <span data-ttu-id="264e8-137">Nell'esempio seguente viene costruito un <xref:System.Drawing.Image> oggetto dal file Colorbars2.</span><span class="sxs-lookup"><span data-stu-id="264e8-137">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars2.bmp.</span></span> <span data-ttu-id="264e8-138">Il codice quindi ridimensiona i componenti rossi, verde e blu di ciascun pixel dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="264e8-138">Then the code scales the red, green, and blue components of each pixel in the image.</span></span> <span data-ttu-id="264e8-139">I componenti rossi sono ridotte del 25% e vengono ridimensionati i componenti di colore verde del 35% vengono ridimensionati i componenti di colore blu del 50%.</span><span class="sxs-lookup"><span data-stu-id="264e8-139">The red components are scaled down 25 percent, the green components are scaled down 35 percent, and the blue components are scaled down 50 percent.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.RecoloringImages#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#42)]  
  
 <span data-ttu-id="264e8-140">Nella figura seguente mostra l'immagine originale a sinistra e l'immagine adattata a destra.</span><span class="sxs-lookup"><span data-stu-id="264e8-140">The following illustration shows the original image on the left and the scaled image on the right.</span></span>  
  
 <span data-ttu-id="264e8-141">![Scalare i colori](../../../../docs/framework/winforms/advanced/media/colortrans4.png "colortrans4")</span><span class="sxs-lookup"><span data-stu-id="264e8-141">![Scale Colors](../../../../docs/framework/winforms/advanced/media/colortrans4.png "colortrans4")</span></span>  
  
 <span data-ttu-id="264e8-142">Nella tabella seguente sono elencati i vettori di colore per le quattro barre prima e dopo il ridimensionamento rosso, verde e blu.</span><span class="sxs-lookup"><span data-stu-id="264e8-142">The following table lists the color vectors for the four bars before and after the red, green and blue scaling.</span></span>  
  
|<span data-ttu-id="264e8-143">Originale</span><span class="sxs-lookup"><span data-stu-id="264e8-143">Original</span></span>|<span data-ttu-id="264e8-144">Scala</span><span class="sxs-lookup"><span data-stu-id="264e8-144">Scaled</span></span>|  
|--------------|------------|  
|<span data-ttu-id="264e8-145">(0.6, 0.6, 0.6, 1)</span><span class="sxs-lookup"><span data-stu-id="264e8-145">(0.6, 0.6, 0.6, 1)</span></span>|<span data-ttu-id="264e8-146">(0.45, 0.39, 0.3, 1)</span><span class="sxs-lookup"><span data-stu-id="264e8-146">(0.45, 0.39, 0.3, 1)</span></span>|  
|<span data-ttu-id="264e8-147">(0, 1, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="264e8-147">(0, 1, 1, 1)</span></span>|<span data-ttu-id="264e8-148">(0, 0.65, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="264e8-148">(0, 0.65, 0.5, 1)</span></span>|  
|<span data-ttu-id="264e8-149">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="264e8-149">(1, 1, 0, 1)</span></span>|<span data-ttu-id="264e8-150">(0.75, 0.65, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="264e8-150">(0.75, 0.65, 0, 1)</span></span>|  
|<span data-ttu-id="264e8-151">(1, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="264e8-151">(1, 0, 1, 1)</span></span>|<span data-ttu-id="264e8-152">(0.75, 0, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="264e8-152">(0.75, 0, 0.5, 1)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="264e8-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="264e8-153">See Also</span></span>  
 <xref:System.Drawing.Imaging.ColorMatrix>  
 <xref:System.Drawing.Imaging.ImageAttributes>  
 [<span data-ttu-id="264e8-154">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="264e8-154">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="264e8-155">Ricolorazione di immagini</span><span class="sxs-lookup"><span data-stu-id="264e8-155">Recoloring Images</span></span>](../../../../docs/framework/winforms/advanced/recoloring-images.md)
