---
title: Linee e riempimenti con fusione alfa
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- lines [Windows Forms], adding transparency
- examples [Windows Forms], alpha blending
- alpha blending [Windows Forms], using with lines
- alpha blending
- lines [Windows Forms], alpha blending
- fills [Windows Forms], alpha blending
- alpha blending [Windows Forms], using with fills
- shapes [Windows Forms], adding transparency
ms.assetid: 5440f48c-3ac9-44c3-b170-c1c110bdbab8
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5b3c0ee3ec82d4d8447c43b7dc9b275591ebe890
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="alpha-blending-lines-and-fills"></a><span data-ttu-id="a4f96-102">Linee e riempimenti con fusione alfa</span><span class="sxs-lookup"><span data-stu-id="a4f96-102">Alpha Blending Lines and Fills</span></span>
<span data-ttu-id="a4f96-103">In [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], un colore è un valore a 32 bit con 8 bit per ciascun alfa, rosso, verde e blu.</span><span class="sxs-lookup"><span data-stu-id="a4f96-103">In [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], a color is a 32-bit value with 8 bits each for alpha, red, green, and blue.</span></span> <span data-ttu-id="a4f96-104">Il valore alfa indica la trasparenza del colore, ovvero l'entità a cui il colore viene sfumato con il colore di sfondo.</span><span class="sxs-lookup"><span data-stu-id="a4f96-104">The alpha value indicates the transparency of the color — the extent to which the color is blended with the background color.</span></span> <span data-ttu-id="a4f96-105">I valori alfa compresi tra 0 e 255, dove 0 rappresenta un colore completamente trasparente, e 255 rappresenta un colore completamente opaco.</span><span class="sxs-lookup"><span data-stu-id="a4f96-105">Alpha values range from 0 through 255, where 0 represents a fully transparent color, and 255 represents a fully opaque color.</span></span>  
  
 <span data-ttu-id="a4f96-106">Sfumatura alfa è una combinazione di pixel per pixel dei dati di colore di sfondo e di origine.</span><span class="sxs-lookup"><span data-stu-id="a4f96-106">Alpha blending is a pixel-by-pixel blending of source and background color data.</span></span> <span data-ttu-id="a4f96-107">Ognuno dei tre componenti (rosso, verde e blu) di un colore di origine specificato viene sfumato con il componente corrispondente del colore di sfondo in base alla formula seguente:</span><span class="sxs-lookup"><span data-stu-id="a4f96-107">Each of the three components (red, green, blue) of a given source color is blended with the corresponding component of the background color according to the following formula:</span></span>  
  
 <span data-ttu-id="a4f96-108">Colore_di_visualizzazione = Colore_di_origine x alfa / 255 + backgroundColor × (255-alfa) / 255</span><span class="sxs-lookup"><span data-stu-id="a4f96-108">displayColor = sourceColor × alpha / 255 + backgroundColor × (255 – alpha) / 255</span></span>  
  
 <span data-ttu-id="a4f96-109">Si supponga, ad esempio, il componente rosso del colore di origine è 150 e il componente rosso del colore di sfondo è 100.</span><span class="sxs-lookup"><span data-stu-id="a4f96-109">For example, suppose the red component of the source color is 150 and the red component of the background color is 100.</span></span> <span data-ttu-id="a4f96-110">Se il valore alfa è 200, il componente rosso di colore risultante viene calcolato come segue:</span><span class="sxs-lookup"><span data-stu-id="a4f96-110">If the alpha value is 200, the red component of the resultant color is calculated as follows:</span></span>  
  
 <span data-ttu-id="a4f96-111">150 × 200 / 255 + 100 × (255 – 200) / 255 = 139</span><span class="sxs-lookup"><span data-stu-id="a4f96-111">150 × 200 / 255 + 100 × (255 – 200) / 255 = 139</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a4f96-112">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="a4f96-112">In This Section</span></span>  
 [<span data-ttu-id="a4f96-113">Procedura: Disegnare linee opache e semitrasparenti</span><span class="sxs-lookup"><span data-stu-id="a4f96-113">How to: Draw Opaque and Semitransparent Lines</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-opaque-and-semitransparent-lines.md)  
 <span data-ttu-id="a4f96-114">Viene illustrato come disegnare linee con fusione alfa.</span><span class="sxs-lookup"><span data-stu-id="a4f96-114">Shows how to draw alpha-blended lines.</span></span>  
  
 [<span data-ttu-id="a4f96-115">Procedura: Disegnare con pennelli opachi e semitrasparenti</span><span class="sxs-lookup"><span data-stu-id="a4f96-115">How to: Draw with Opaque and Semitransparent Brushes</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-with-opaque-and-semitransparent-brushes.md)  
 <span data-ttu-id="a4f96-116">Viene illustrato come applicare la fusione alfa con pennelli.</span><span class="sxs-lookup"><span data-stu-id="a4f96-116">Explains how to alpha-blend with brushes.</span></span>  
  
 [<span data-ttu-id="a4f96-117">Procedura: Usare la modalità di composizione per controllare la fusione alfa</span><span class="sxs-lookup"><span data-stu-id="a4f96-117">How to: Use Compositing Mode to Control Alpha Blending</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-compositing-mode-to-control-alpha-blending.md)  
 <span data-ttu-id="a4f96-118">Viene descritto come controllare la fusione alfa utilizzando <xref:System.Drawing.Drawing2D.CompositingMode>.</span><span class="sxs-lookup"><span data-stu-id="a4f96-118">Describes how to control alpha blending using <xref:System.Drawing.Drawing2D.CompositingMode>.</span></span>  
  
 [<span data-ttu-id="a4f96-119">Procedura: Usare una matrice di colori per impostare i valori alfa nelle immagini</span><span class="sxs-lookup"><span data-stu-id="a4f96-119">How to: Use a Color Matrix to Set Alpha Values in Images</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-a-color-matrix-to-set-alpha-values-in-images.md)  
 <span data-ttu-id="a4f96-120">Viene illustrato come utilizzare un <xref:System.Drawing.Imaging.ColorMatrix> oggetto da controllare la fusione alfa.</span><span class="sxs-lookup"><span data-stu-id="a4f96-120">Explains how to use a <xref:System.Drawing.Imaging.ColorMatrix> object to control alpha blending.</span></span>
