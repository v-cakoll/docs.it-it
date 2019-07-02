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
ms.openlocfilehash: 81c0ddf5b937d604559a9eb1a8b598885546c97f
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504958"
---
# <a name="using-transformations-to-scale-colors"></a><span data-ttu-id="efbe4-102">Utilizzo delle trasformazioni per scalare i colori</span><span class="sxs-lookup"><span data-stu-id="efbe4-102">Using Transformations to Scale Colors</span></span>
<span data-ttu-id="efbe4-103">Una trasformazione di ridimensionamento Moltiplica uno o più di quattro componenti di colore da un numero.</span><span class="sxs-lookup"><span data-stu-id="efbe4-103">A scaling transformation multiplies one or more of the four color components by a number.</span></span> <span data-ttu-id="efbe4-104">Le voci di matrice di colore che rappresentano la scalabilità sono indicate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="efbe4-104">The color matrix entries that represent scaling are given in the following table.</span></span>  
  
|<span data-ttu-id="efbe4-105">Componente di scalabilità</span><span class="sxs-lookup"><span data-stu-id="efbe4-105">Component to be scaled</span></span>|<span data-ttu-id="efbe4-106">Voce della matrice</span><span class="sxs-lookup"><span data-stu-id="efbe4-106">Matrix entry</span></span>|  
|----------------------------|------------------|  
|<span data-ttu-id="efbe4-107">Rosso</span><span class="sxs-lookup"><span data-stu-id="efbe4-107">Red</span></span>|<span data-ttu-id="efbe4-108">[0][0]</span><span class="sxs-lookup"><span data-stu-id="efbe4-108">[0][0]</span></span>|  
|<span data-ttu-id="efbe4-109">Verde</span><span class="sxs-lookup"><span data-stu-id="efbe4-109">Green</span></span>|<span data-ttu-id="efbe4-110">[1][1]</span><span class="sxs-lookup"><span data-stu-id="efbe4-110">[1][1]</span></span>|  
|<span data-ttu-id="efbe4-111">Blu</span><span class="sxs-lookup"><span data-stu-id="efbe4-111">Blue</span></span>|<span data-ttu-id="efbe4-112">[2][2]</span><span class="sxs-lookup"><span data-stu-id="efbe4-112">[2][2]</span></span>|  
|<span data-ttu-id="efbe4-113">Alfa</span><span class="sxs-lookup"><span data-stu-id="efbe4-113">Alpha</span></span>|<span data-ttu-id="efbe4-114">[3][3]</span><span class="sxs-lookup"><span data-stu-id="efbe4-114">[3][3]</span></span>|  
  
## <a name="scaling-one-color"></a><span data-ttu-id="efbe4-115">Adattamento di un colore</span><span class="sxs-lookup"><span data-stu-id="efbe4-115">Scaling One Color</span></span>  
 <span data-ttu-id="efbe4-116">Nell'esempio seguente si costruisce un <xref:System.Drawing.Image> oggetto Colorbars2 nel file.</span><span class="sxs-lookup"><span data-stu-id="efbe4-116">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars2.bmp.</span></span> <span data-ttu-id="efbe4-117">Il codice quindi ridimensiona il componente blu di ciascun pixel nell'immagine di un fattore pari a 2.</span><span class="sxs-lookup"><span data-stu-id="efbe4-117">Then the code scales the blue component of each pixel in the image by a factor of 2.</span></span> <span data-ttu-id="efbe4-118">Accanto all'immagine trasformata viene disegnata l'immagine originale.</span><span class="sxs-lookup"><span data-stu-id="efbe4-118">The original image is drawn alongside the transformed image.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.RecoloringImages#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#41)]  
  
 <span data-ttu-id="efbe4-119">Nella figura seguente mostra l'immagine originale a sinistra e l'immagine adattata a destra:</span><span class="sxs-lookup"><span data-stu-id="efbe4-119">The following illustration shows the original image on the left and the scaled image on the right:</span></span>  
  
 ![Screenshot che confronta i colori originali e in scala.](./media/using-transformations-to-scale-colors/four-bar-scale-one-color.png)  
  
 <span data-ttu-id="efbe4-121">La tabella seguente elenca i vettori di colore per le quattro barre prima e dopo il ridimensionamento blu.</span><span class="sxs-lookup"><span data-stu-id="efbe4-121">The following table lists the color vectors for the four bars before and after the blue scaling.</span></span> <span data-ttu-id="efbe4-122">Si noti che il componente blu nella barra dei colori quarto passato da 0,8 a 0,6.</span><span class="sxs-lookup"><span data-stu-id="efbe4-122">Note that the blue component in the fourth color bar went from 0.8 to 0.6.</span></span> <span data-ttu-id="efbe4-123">Ciò avviene perché GDI+ mantiene solo la parte frazionaria del risultato.</span><span class="sxs-lookup"><span data-stu-id="efbe4-123">That is because GDI+ retains only the fractional part of the result.</span></span> <span data-ttu-id="efbe4-124">Ad esempio, (2)(0.8) Version=1.6, e la parte frazionaria di 1.6 è 0,6.</span><span class="sxs-lookup"><span data-stu-id="efbe4-124">For example, (2)(0.8) = 1.6, and the fractional part of 1.6 is 0.6.</span></span> <span data-ttu-id="efbe4-125">Mantenendo solo la parte frazionaria garantisce che il risultato è sempre nell'intervallo [0, 1].</span><span class="sxs-lookup"><span data-stu-id="efbe4-125">Retaining only the fractional part ensures that the result is always in the interval [0, 1].</span></span>  
  
|<span data-ttu-id="efbe4-126">Originale</span><span class="sxs-lookup"><span data-stu-id="efbe4-126">Original</span></span>|<span data-ttu-id="efbe4-127">Scalabilità</span><span class="sxs-lookup"><span data-stu-id="efbe4-127">Scaled</span></span>|  
|--------------|------------|  
|<span data-ttu-id="efbe4-128">(0.4, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="efbe4-128">(0.4, 0.4, 0.4, 1)</span></span>|<span data-ttu-id="efbe4-129">(0.4, 0.4, 0.8, 1)</span><span class="sxs-lookup"><span data-stu-id="efbe4-129">(0.4, 0.4, 0.8, 1)</span></span>|  
|<span data-ttu-id="efbe4-130">(0.4, 0.2, 0.2, 1)</span><span class="sxs-lookup"><span data-stu-id="efbe4-130">(0.4, 0.2, 0.2, 1)</span></span>|<span data-ttu-id="efbe4-131">(0.4, 0.2, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="efbe4-131">(0.4, 0.2, 0.4, 1)</span></span>|  
|<span data-ttu-id="efbe4-132">(0.2, 0.4, 0.2, 1)</span><span class="sxs-lookup"><span data-stu-id="efbe4-132">(0.2, 0.4, 0.2, 1)</span></span>|<span data-ttu-id="efbe4-133">(0.2, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="efbe4-133">(0.2, 0.4, 0.4, 1)</span></span>|  
|<span data-ttu-id="efbe4-134">(0.4, 0.4, 0.8, 1)</span><span class="sxs-lookup"><span data-stu-id="efbe4-134">(0.4, 0.4, 0.8, 1)</span></span>|<span data-ttu-id="efbe4-135">(0.4, 0.4, 0.6, 1)</span><span class="sxs-lookup"><span data-stu-id="efbe4-135">(0.4, 0.4, 0.6, 1)</span></span>|  
  
## <a name="scaling-multiple-colors"></a><span data-ttu-id="efbe4-136">Adattamento dei colori più</span><span class="sxs-lookup"><span data-stu-id="efbe4-136">Scaling Multiple Colors</span></span>  
 <span data-ttu-id="efbe4-137">Nell'esempio seguente si costruisce un <xref:System.Drawing.Image> oggetto Colorbars2 nel file.</span><span class="sxs-lookup"><span data-stu-id="efbe4-137">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars2.bmp.</span></span> <span data-ttu-id="efbe4-138">Il codice quindi ridimensiona i componenti rossi, verdi e blu di ogni pixel nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="efbe4-138">Then the code scales the red, green, and blue components of each pixel in the image.</span></span> <span data-ttu-id="efbe4-139">I componenti rosso sono stati ridotti del 25%, i componenti verdi sono stati ridotti del 35% e i componenti blu sono stati ridotti al 50%.</span><span class="sxs-lookup"><span data-stu-id="efbe4-139">The red components are scaled down 25 percent, the green components are scaled down 35 percent, and the blue components are scaled down 50 percent.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.RecoloringImages#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#42)]  
  
 <span data-ttu-id="efbe4-140">Nella figura seguente mostra l'immagine originale a sinistra e l'immagine adattata a destra:</span><span class="sxs-lookup"><span data-stu-id="efbe4-140">The following illustration shows the original image on the left and the scaled image on the right:</span></span>  
  
 ![Screenshot che confronta i colori originali e in scala.](./media/using-transformations-to-scale-colors/four-bar-scale-multiple-colors.png)  
  
 <span data-ttu-id="efbe4-142">La tabella seguente elenca i vettori di colore per le quattro barre prima e dopo il ridimensionamento rosso, verde e blu.</span><span class="sxs-lookup"><span data-stu-id="efbe4-142">The following table lists the color vectors for the four bars before and after the red, green and blue scaling.</span></span>  
  
|<span data-ttu-id="efbe4-143">Originale</span><span class="sxs-lookup"><span data-stu-id="efbe4-143">Original</span></span>|<span data-ttu-id="efbe4-144">Scalabilità</span><span class="sxs-lookup"><span data-stu-id="efbe4-144">Scaled</span></span>|  
|--------------|------------|  
|<span data-ttu-id="efbe4-145">(0.6, 0.6, 0.6, 1)</span><span class="sxs-lookup"><span data-stu-id="efbe4-145">(0.6, 0.6, 0.6, 1)</span></span>|<span data-ttu-id="efbe4-146">(0.45, 0.39, 0.3, 1)</span><span class="sxs-lookup"><span data-stu-id="efbe4-146">(0.45, 0.39, 0.3, 1)</span></span>|  
|<span data-ttu-id="efbe4-147">(0, 1, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="efbe4-147">(0, 1, 1, 1)</span></span>|<span data-ttu-id="efbe4-148">(0, 0.65, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="efbe4-148">(0, 0.65, 0.5, 1)</span></span>|  
|<span data-ttu-id="efbe4-149">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="efbe4-149">(1, 1, 0, 1)</span></span>|<span data-ttu-id="efbe4-150">(0.75, 0.65, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="efbe4-150">(0.75, 0.65, 0, 1)</span></span>|  
|<span data-ttu-id="efbe4-151">(1, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="efbe4-151">(1, 0, 1, 1)</span></span>|<span data-ttu-id="efbe4-152">(0.75, 0, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="efbe4-152">(0.75, 0, 0.5, 1)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="efbe4-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="efbe4-153">See also</span></span>

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="efbe4-154">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="efbe4-154">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="efbe4-155">Ricolorazione di immagini</span><span class="sxs-lookup"><span data-stu-id="efbe4-155">Recoloring Images</span></span>](recoloring-images.md)
