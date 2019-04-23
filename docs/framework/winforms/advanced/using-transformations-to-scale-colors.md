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
ms.openlocfilehash: 9c8f2392137d04f56096120cec64b60c42c47419
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59107984"
---
# <a name="using-transformations-to-scale-colors"></a><span data-ttu-id="b2e84-102">Utilizzo delle trasformazioni per scalare i colori</span><span class="sxs-lookup"><span data-stu-id="b2e84-102">Using Transformations to Scale Colors</span></span>
<span data-ttu-id="b2e84-103">Una trasformazione di ridimensionamento Moltiplica uno o più di quattro componenti di colore da un numero.</span><span class="sxs-lookup"><span data-stu-id="b2e84-103">A scaling transformation multiplies one or more of the four color components by a number.</span></span> <span data-ttu-id="b2e84-104">Le voci di matrice di colore che rappresentano la scalabilità sono indicate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="b2e84-104">The color matrix entries that represent scaling are given in the following table.</span></span>  
  
|<span data-ttu-id="b2e84-105">Componente di scalabilità</span><span class="sxs-lookup"><span data-stu-id="b2e84-105">Component to be scaled</span></span>|<span data-ttu-id="b2e84-106">Voce della matrice</span><span class="sxs-lookup"><span data-stu-id="b2e84-106">Matrix entry</span></span>|  
|----------------------------|------------------|  
|<span data-ttu-id="b2e84-107">Rosso</span><span class="sxs-lookup"><span data-stu-id="b2e84-107">Red</span></span>|<span data-ttu-id="b2e84-108">[0][0]</span><span class="sxs-lookup"><span data-stu-id="b2e84-108">[0][0]</span></span>|  
|<span data-ttu-id="b2e84-109">Verde</span><span class="sxs-lookup"><span data-stu-id="b2e84-109">Green</span></span>|<span data-ttu-id="b2e84-110">[1][1]</span><span class="sxs-lookup"><span data-stu-id="b2e84-110">[1][1]</span></span>|  
|<span data-ttu-id="b2e84-111">Blu</span><span class="sxs-lookup"><span data-stu-id="b2e84-111">Blue</span></span>|<span data-ttu-id="b2e84-112">[2][2]</span><span class="sxs-lookup"><span data-stu-id="b2e84-112">[2][2]</span></span>|  
|<span data-ttu-id="b2e84-113">Alfa</span><span class="sxs-lookup"><span data-stu-id="b2e84-113">Alpha</span></span>|<span data-ttu-id="b2e84-114">[3][3]</span><span class="sxs-lookup"><span data-stu-id="b2e84-114">[3][3]</span></span>|  
  
## <a name="scaling-one-color"></a><span data-ttu-id="b2e84-115">Adattamento di un colore</span><span class="sxs-lookup"><span data-stu-id="b2e84-115">Scaling One Color</span></span>  
 <span data-ttu-id="b2e84-116">Nell'esempio seguente si costruisce un <xref:System.Drawing.Image> oggetto Colorbars2 nel file.</span><span class="sxs-lookup"><span data-stu-id="b2e84-116">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars2.bmp.</span></span> <span data-ttu-id="b2e84-117">Il codice quindi ridimensiona il componente blu di ciascun pixel nell'immagine di un fattore pari a 2.</span><span class="sxs-lookup"><span data-stu-id="b2e84-117">Then the code scales the blue component of each pixel in the image by a factor of 2.</span></span> <span data-ttu-id="b2e84-118">Accanto all'immagine trasformata viene disegnata l'immagine originale.</span><span class="sxs-lookup"><span data-stu-id="b2e84-118">The original image is drawn alongside the transformed image.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.RecoloringImages#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#41)]  
  
 <span data-ttu-id="b2e84-119">Nella figura seguente mostra l'immagine originale a sinistra e l'immagine adattata a destra:</span><span class="sxs-lookup"><span data-stu-id="b2e84-119">The following illustration shows the original image on the left and the scaled image on the right:</span></span>  
  
 ![Screenshot che confronta i colori originali e in scala.](./media/using-transformations-to-scale-colors/four-bar-scale-one-color.png)  
  
 <span data-ttu-id="b2e84-121">La tabella seguente elenca i vettori di colore per le quattro barre prima e dopo il ridimensionamento blu.</span><span class="sxs-lookup"><span data-stu-id="b2e84-121">The following table lists the color vectors for the four bars before and after the blue scaling.</span></span> <span data-ttu-id="b2e84-122">Si noti che il componente blu nella barra dei colori quarto passato da 0,8 a 0,6.</span><span class="sxs-lookup"><span data-stu-id="b2e84-122">Note that the blue component in the fourth color bar went from 0.8 to 0.6.</span></span> <span data-ttu-id="b2e84-123">Infatti, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] mantiene solo la parte frazionaria del risultato.</span><span class="sxs-lookup"><span data-stu-id="b2e84-123">That is because [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] retains only the fractional part of the result.</span></span> <span data-ttu-id="b2e84-124">Ad esempio, (2)(0.8) Version=1.6, e la parte frazionaria di 1.6 è 0,6.</span><span class="sxs-lookup"><span data-stu-id="b2e84-124">For example, (2)(0.8) = 1.6, and the fractional part of 1.6 is 0.6.</span></span> <span data-ttu-id="b2e84-125">Mantenendo solo la parte frazionaria garantisce che il risultato è sempre nell'intervallo [0, 1].</span><span class="sxs-lookup"><span data-stu-id="b2e84-125">Retaining only the fractional part ensures that the result is always in the interval [0, 1].</span></span>  
  
|<span data-ttu-id="b2e84-126">Originale</span><span class="sxs-lookup"><span data-stu-id="b2e84-126">Original</span></span>|<span data-ttu-id="b2e84-127">Scalabilità</span><span class="sxs-lookup"><span data-stu-id="b2e84-127">Scaled</span></span>|  
|--------------|------------|  
|<span data-ttu-id="b2e84-128">(0.4, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="b2e84-128">(0.4, 0.4, 0.4, 1)</span></span>|<span data-ttu-id="b2e84-129">(0.4, 0.4, 0.8, 1)</span><span class="sxs-lookup"><span data-stu-id="b2e84-129">(0.4, 0.4, 0.8, 1)</span></span>|  
|<span data-ttu-id="b2e84-130">(0.4, 0.2, 0.2, 1)</span><span class="sxs-lookup"><span data-stu-id="b2e84-130">(0.4, 0.2, 0.2, 1)</span></span>|<span data-ttu-id="b2e84-131">(0.4, 0.2, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="b2e84-131">(0.4, 0.2, 0.4, 1)</span></span>|  
|<span data-ttu-id="b2e84-132">(0.2, 0.4, 0.2, 1)</span><span class="sxs-lookup"><span data-stu-id="b2e84-132">(0.2, 0.4, 0.2, 1)</span></span>|<span data-ttu-id="b2e84-133">(0.2, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="b2e84-133">(0.2, 0.4, 0.4, 1)</span></span>|  
|<span data-ttu-id="b2e84-134">(0.4, 0.4, 0.8, 1)</span><span class="sxs-lookup"><span data-stu-id="b2e84-134">(0.4, 0.4, 0.8, 1)</span></span>|<span data-ttu-id="b2e84-135">(0.4, 0.4, 0.6, 1)</span><span class="sxs-lookup"><span data-stu-id="b2e84-135">(0.4, 0.4, 0.6, 1)</span></span>|  
  
## <a name="scaling-multiple-colors"></a><span data-ttu-id="b2e84-136">Adattamento dei colori più</span><span class="sxs-lookup"><span data-stu-id="b2e84-136">Scaling Multiple Colors</span></span>  
 <span data-ttu-id="b2e84-137">Nell'esempio seguente si costruisce un <xref:System.Drawing.Image> oggetto Colorbars2 nel file.</span><span class="sxs-lookup"><span data-stu-id="b2e84-137">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars2.bmp.</span></span> <span data-ttu-id="b2e84-138">Il codice quindi ridimensiona i componenti rossi, verdi e blu di ogni pixel nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="b2e84-138">Then the code scales the red, green, and blue components of each pixel in the image.</span></span> <span data-ttu-id="b2e84-139">I componenti rosso sono stati ridotti del 25%, i componenti verdi sono stati ridotti del 35% e i componenti blu sono stati ridotti al 50%.</span><span class="sxs-lookup"><span data-stu-id="b2e84-139">The red components are scaled down 25 percent, the green components are scaled down 35 percent, and the blue components are scaled down 50 percent.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.RecoloringImages#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#42)]  
  
 <span data-ttu-id="b2e84-140">Nella figura seguente mostra l'immagine originale a sinistra e l'immagine adattata a destra:</span><span class="sxs-lookup"><span data-stu-id="b2e84-140">The following illustration shows the original image on the left and the scaled image on the right:</span></span>  
  
 ![Screenshot che confronta i colori originali e in scala.](./media/using-transformations-to-scale-colors/four-bar-scale-multiple-colors.png)  
  
 <span data-ttu-id="b2e84-142">La tabella seguente elenca i vettori di colore per le quattro barre prima e dopo il ridimensionamento rosso, verde e blu.</span><span class="sxs-lookup"><span data-stu-id="b2e84-142">The following table lists the color vectors for the four bars before and after the red, green and blue scaling.</span></span>  
  
|<span data-ttu-id="b2e84-143">Originale</span><span class="sxs-lookup"><span data-stu-id="b2e84-143">Original</span></span>|<span data-ttu-id="b2e84-144">Scalabilità</span><span class="sxs-lookup"><span data-stu-id="b2e84-144">Scaled</span></span>|  
|--------------|------------|  
|<span data-ttu-id="b2e84-145">(0.6, 0.6, 0.6, 1)</span><span class="sxs-lookup"><span data-stu-id="b2e84-145">(0.6, 0.6, 0.6, 1)</span></span>|<span data-ttu-id="b2e84-146">(0.45, 0.39, 0.3, 1)</span><span class="sxs-lookup"><span data-stu-id="b2e84-146">(0.45, 0.39, 0.3, 1)</span></span>|  
|<span data-ttu-id="b2e84-147">(0, 1, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="b2e84-147">(0, 1, 1, 1)</span></span>|<span data-ttu-id="b2e84-148">(0, 0.65, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="b2e84-148">(0, 0.65, 0.5, 1)</span></span>|  
|<span data-ttu-id="b2e84-149">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="b2e84-149">(1, 1, 0, 1)</span></span>|<span data-ttu-id="b2e84-150">(0.75, 0.65, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="b2e84-150">(0.75, 0.65, 0, 1)</span></span>|  
|<span data-ttu-id="b2e84-151">(1, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="b2e84-151">(1, 0, 1, 1)</span></span>|<span data-ttu-id="b2e84-152">(0.75, 0, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="b2e84-152">(0.75, 0, 0.5, 1)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b2e84-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2e84-153">See also</span></span>

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="b2e84-154">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="b2e84-154">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="b2e84-155">Ricolorazione di immagini</span><span class="sxs-lookup"><span data-stu-id="b2e84-155">Recoloring Images</span></span>](recoloring-images.md)
