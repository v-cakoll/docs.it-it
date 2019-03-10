---
title: Limitazione della superficie di disegno in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, clipping
- clipping [Windows Forms], using GDI+
- GDI+, restricting drawing surface
ms.assetid: 8b5f71d9-d2f0-4540-9c41-740f90fd4c26
ms.openlocfilehash: da12ece815d8ae9d1f974b02198498b250885843
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57717116"
---
# <a name="restricting-the-drawing-surface-in-gdi"></a><span data-ttu-id="f1031-102">Limitazione della superficie di disegno in GDI+</span><span class="sxs-lookup"><span data-stu-id="f1031-102">Restricting the Drawing Surface in GDI+</span></span>
<span data-ttu-id="f1031-103">Ritaglio comporta la limitazione di disegno per una determinata rettangolo o area geografica.</span><span class="sxs-lookup"><span data-stu-id="f1031-103">Clipping involves restricting drawing to a certain rectangle or region.</span></span> <span data-ttu-id="f1031-104">La figura seguente mostra la stringa "Hello" ritagliata a un'area a forma di cuore.</span><span class="sxs-lookup"><span data-stu-id="f1031-104">The following illustration shows the string "Hello" clipped to a heart-shaped region.</span></span>  
  
 <span data-ttu-id="f1031-105">![Nell'area di disegno limitata](./media/aboutgdip02-art30.gif "AboutGdip02_Art30")</span><span class="sxs-lookup"><span data-stu-id="f1031-105">![Restricted Drawing Surface](./media/aboutgdip02-art30.gif "AboutGdip02_Art30")</span></span>  
  
## <a name="clipping-with-regions"></a><span data-ttu-id="f1031-106">Le aree di visualizzazione</span><span class="sxs-lookup"><span data-stu-id="f1031-106">Clipping with Regions</span></span>  
 <span data-ttu-id="f1031-107">Aree possono essere costruite da percorsi e i percorsi possono contenere i contorni di stringhe, pertanto è possibile utilizzare testo con contorni di ritaglio.</span><span class="sxs-lookup"><span data-stu-id="f1031-107">Regions can be constructed from paths, and paths can contain the outlines of strings, so you can use outlined text for clipping.</span></span> <span data-ttu-id="f1031-108">La figura seguente mostra un set di puntini di sospensione concentrici ritagliati all'interno di una stringa di testo.</span><span class="sxs-lookup"><span data-stu-id="f1031-108">The following illustration shows a set of concentric ellipses clipped to the interior of a string of text.</span></span>  
  
 <span data-ttu-id="f1031-109">![Nell'area di disegno limitata](./media/aboutgdip02-art31.gif "AboutGdip02_Art31")</span><span class="sxs-lookup"><span data-stu-id="f1031-109">![Restricted Drawing Surface](./media/aboutgdip02-art31.gif "AboutGdip02_Art31")</span></span>  
  
 <span data-ttu-id="f1031-110">Per disegnare con ridimensionamento, creare un <xref:System.Drawing.Graphics> dell'oggetto, impostare relativi <xref:System.Drawing.Graphics.Clip%2A> proprietà, quindi chiamare i metodi di disegno di tale stesso <xref:System.Drawing.Graphics> oggetto:</span><span class="sxs-lookup"><span data-stu-id="f1031-110">To draw with clipping, create a <xref:System.Drawing.Graphics> object, set its <xref:System.Drawing.Graphics.Clip%2A> property, and then call the drawing methods of that same <xref:System.Drawing.Graphics> object:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#91](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#91)]
 [!code-vb[LinesCurvesAndShapes#91](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#91)]  
  
## <a name="see-also"></a><span data-ttu-id="f1031-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1031-111">See also</span></span>
- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Region?displayProperty=nameWithType>
- [<span data-ttu-id="f1031-112">Linee, curve e forme</span><span class="sxs-lookup"><span data-stu-id="f1031-112">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="f1031-113">Uso delle regioni</span><span class="sxs-lookup"><span data-stu-id="f1031-113">Using Regions</span></span>](using-regions.md)
