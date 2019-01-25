---
title: Utilizzo delle trasformazioni per scalare i colori
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], for scaling colors
- colors [Windows Forms], scaling
ms.assetid: df23c887-7fd6-4b15-ad94-e30b5bd4b849
ms.openlocfilehash: ff6172d571a7ca449ab21d1f7a7f9a699bf40f8e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737975"
---
# <a name="using-transformations-to-scale-colors"></a><span data-ttu-id="01404-102">Utilizzo delle trasformazioni per scalare i colori</span><span class="sxs-lookup"><span data-stu-id="01404-102">Using Transformations to Scale Colors</span></span>
<span data-ttu-id="01404-103">Una trasformazione di ridimensionamento Moltiplica uno o più di quattro componenti di colore da un numero.</span><span class="sxs-lookup"><span data-stu-id="01404-103">A scaling transformation multiplies one or more of the four color components by a number.</span></span> <span data-ttu-id="01404-104">Le voci di matrice di colore che rappresentano la scalabilità sono indicate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="01404-104">The color matrix entries that represent scaling are given in the following table.</span></span>  
  
|<span data-ttu-id="01404-105">Componente di scalabilità</span><span class="sxs-lookup"><span data-stu-id="01404-105">Component to be scaled</span></span>|<span data-ttu-id="01404-106">Voce della matrice</span><span class="sxs-lookup"><span data-stu-id="01404-106">Matrix entry</span></span>|  
|----------------------------|------------------|  
|<span data-ttu-id="01404-107">Rosso</span><span class="sxs-lookup"><span data-stu-id="01404-107">Red</span></span>|<span data-ttu-id="01404-108">[0][0]</span><span class="sxs-lookup"><span data-stu-id="01404-108">[0][0]</span></span>|  
|<span data-ttu-id="01404-109">Verde</span><span class="sxs-lookup"><span data-stu-id="01404-109">Green</span></span>|<span data-ttu-id="01404-110">[1][1]</span><span class="sxs-lookup"><span data-stu-id="01404-110">[1][1]</span></span>|  
|<span data-ttu-id="01404-111">Blu</span><span class="sxs-lookup"><span data-stu-id="01404-111">Blue</span></span>|<span data-ttu-id="01404-112">[2][2]</span><span class="sxs-lookup"><span data-stu-id="01404-112">[2][2]</span></span>|  
|<span data-ttu-id="01404-113">Alfa</span><span class="sxs-lookup"><span data-stu-id="01404-113">Alpha</span></span>|<span data-ttu-id="01404-114">[3][3]</span><span class="sxs-lookup"><span data-stu-id="01404-114">[3][3]</span></span>|  
  
## <a name="scaling-one-color"></a><span data-ttu-id="01404-115">Adattamento di un colore</span><span class="sxs-lookup"><span data-stu-id="01404-115">Scaling One Color</span></span>  
 <span data-ttu-id="01404-116">Nell'esempio seguente si costruisce un <xref:System.Drawing.Image> oggetto Colorbars2 nel file.</span><span class="sxs-lookup"><span data-stu-id="01404-116">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars2.bmp.</span></span> <span data-ttu-id="01404-117">Il codice quindi ridimensiona il componente blu di ciascun pixel nell'immagine di un fattore pari a 2.</span><span class="sxs-lookup"><span data-stu-id="01404-117">Then the code scales the blue component of each pixel in the image by a factor of 2.</span></span> <span data-ttu-id="01404-118">Accanto all'immagine trasformata viene disegnata l'immagine originale.</span><span class="sxs-lookup"><span data-stu-id="01404-118">The original image is drawn alongside the transformed image.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.RecoloringImages#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#41)]  
  
 <span data-ttu-id="01404-119">Nella figura seguente mostra l'immagine originale a sinistra e l'immagine adattata a destra.</span><span class="sxs-lookup"><span data-stu-id="01404-119">The following illustration shows the original image on the left and the scaled image on the right.</span></span>  
  
 <span data-ttu-id="01404-120">![Scalare i colori](../../../../docs/framework/winforms/advanced/media/colortrans3.png "colortrans3")</span><span class="sxs-lookup"><span data-stu-id="01404-120">![Scale Colors](../../../../docs/framework/winforms/advanced/media/colortrans3.png "colortrans3")</span></span>  
  
 <span data-ttu-id="01404-121">La tabella seguente elenca i vettori di colore per le quattro barre prima e dopo il ridimensionamento blu.</span><span class="sxs-lookup"><span data-stu-id="01404-121">The following table lists the color vectors for the four bars before and after the blue scaling.</span></span> <span data-ttu-id="01404-122">Si noti che il componente blu nella barra dei colori quarto passato da 0,8 a 0,6.</span><span class="sxs-lookup"><span data-stu-id="01404-122">Note that the blue component in the fourth color bar went from 0.8 to 0.6.</span></span> <span data-ttu-id="01404-123">Infatti, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] mantiene solo la parte frazionaria del risultato.</span><span class="sxs-lookup"><span data-stu-id="01404-123">That is because [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] retains only the fractional part of the result.</span></span> <span data-ttu-id="01404-124">Ad esempio, (2)(0.8) Version=1.6, e la parte frazionaria di 1.6 è 0,6.</span><span class="sxs-lookup"><span data-stu-id="01404-124">For example, (2)(0.8) = 1.6, and the fractional part of 1.6 is 0.6.</span></span> <span data-ttu-id="01404-125">Mantenendo solo la parte frazionaria garantisce che il risultato è sempre nell'intervallo [0, 1].</span><span class="sxs-lookup"><span data-stu-id="01404-125">Retaining only the fractional part ensures that the result is always in the interval [0, 1].</span></span>  
  
|<span data-ttu-id="01404-126">Originale</span><span class="sxs-lookup"><span data-stu-id="01404-126">Original</span></span>|<span data-ttu-id="01404-127">Scalabilità</span><span class="sxs-lookup"><span data-stu-id="01404-127">Scaled</span></span>|  
|--------------|------------|  
|<span data-ttu-id="01404-128">(0.4, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="01404-128">(0.4, 0.4, 0.4, 1)</span></span>|<span data-ttu-id="01404-129">(0.4, 0.4, 0.8, 1)</span><span class="sxs-lookup"><span data-stu-id="01404-129">(0.4, 0.4, 0.8, 1)</span></span>|  
|<span data-ttu-id="01404-130">(0.4, 0.2, 0.2, 1)</span><span class="sxs-lookup"><span data-stu-id="01404-130">(0.4, 0.2, 0.2, 1)</span></span>|<span data-ttu-id="01404-131">(0.4, 0.2, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="01404-131">(0.4, 0.2, 0.4, 1)</span></span>|  
|<span data-ttu-id="01404-132">(0.2, 0.4, 0.2, 1)</span><span class="sxs-lookup"><span data-stu-id="01404-132">(0.2, 0.4, 0.2, 1)</span></span>|<span data-ttu-id="01404-133">(0.2, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="01404-133">(0.2, 0.4, 0.4, 1)</span></span>|  
|<span data-ttu-id="01404-134">(0.4, 0.4, 0.8, 1)</span><span class="sxs-lookup"><span data-stu-id="01404-134">(0.4, 0.4, 0.8, 1)</span></span>|<span data-ttu-id="01404-135">(0.4, 0.4, 0.6, 1)</span><span class="sxs-lookup"><span data-stu-id="01404-135">(0.4, 0.4, 0.6, 1)</span></span>|  
  
## <a name="scaling-multiple-colors"></a><span data-ttu-id="01404-136">Adattamento dei colori più</span><span class="sxs-lookup"><span data-stu-id="01404-136">Scaling Multiple Colors</span></span>  
 <span data-ttu-id="01404-137">Nell'esempio seguente si costruisce un <xref:System.Drawing.Image> oggetto Colorbars2 nel file.</span><span class="sxs-lookup"><span data-stu-id="01404-137">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars2.bmp.</span></span> <span data-ttu-id="01404-138">Il codice quindi ridimensiona i componenti rossi, verdi e blu di ogni pixel nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="01404-138">Then the code scales the red, green, and blue components of each pixel in the image.</span></span> <span data-ttu-id="01404-139">I componenti rosso sono stati ridotti del 25%, i componenti verdi sono stati ridotti del 35% e i componenti blu sono stati ridotti al 50%.</span><span class="sxs-lookup"><span data-stu-id="01404-139">The red components are scaled down 25 percent, the green components are scaled down 35 percent, and the blue components are scaled down 50 percent.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.RecoloringImages#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#42)]  
  
 <span data-ttu-id="01404-140">Nella figura seguente mostra l'immagine originale a sinistra e l'immagine adattata a destra.</span><span class="sxs-lookup"><span data-stu-id="01404-140">The following illustration shows the original image on the left and the scaled image on the right.</span></span>  
  
 <span data-ttu-id="01404-141">![Scalare i colori](../../../../docs/framework/winforms/advanced/media/colortrans4.png "colortrans4")</span><span class="sxs-lookup"><span data-stu-id="01404-141">![Scale Colors](../../../../docs/framework/winforms/advanced/media/colortrans4.png "colortrans4")</span></span>  
  
 <span data-ttu-id="01404-142">La tabella seguente elenca i vettori di colore per le quattro barre prima e dopo il ridimensionamento rosso, verde e blu.</span><span class="sxs-lookup"><span data-stu-id="01404-142">The following table lists the color vectors for the four bars before and after the red, green and blue scaling.</span></span>  
  
|<span data-ttu-id="01404-143">Originale</span><span class="sxs-lookup"><span data-stu-id="01404-143">Original</span></span>|<span data-ttu-id="01404-144">Scalabilità</span><span class="sxs-lookup"><span data-stu-id="01404-144">Scaled</span></span>|  
|--------------|------------|  
|<span data-ttu-id="01404-145">(0.6, 0.6, 0.6, 1)</span><span class="sxs-lookup"><span data-stu-id="01404-145">(0.6, 0.6, 0.6, 1)</span></span>|<span data-ttu-id="01404-146">(0.45, 0.39, 0.3, 1)</span><span class="sxs-lookup"><span data-stu-id="01404-146">(0.45, 0.39, 0.3, 1)</span></span>|  
|<span data-ttu-id="01404-147">(0, 1, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="01404-147">(0, 1, 1, 1)</span></span>|<span data-ttu-id="01404-148">(0, 0.65, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="01404-148">(0, 0.65, 0.5, 1)</span></span>|  
|<span data-ttu-id="01404-149">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="01404-149">(1, 1, 0, 1)</span></span>|<span data-ttu-id="01404-150">(0.75, 0.65, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="01404-150">(0.75, 0.65, 0, 1)</span></span>|  
|<span data-ttu-id="01404-151">(1, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="01404-151">(1, 0, 1, 1)</span></span>|<span data-ttu-id="01404-152">(0.75, 0, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="01404-152">(0.75, 0, 0.5, 1)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="01404-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01404-153">See also</span></span>
- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="01404-154">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="01404-154">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="01404-155">Ricolorazione di immagini</span><span class="sxs-lookup"><span data-stu-id="01404-155">Recoloring Images</span></span>](../../../../docs/framework/winforms/advanced/recoloring-images.md)
