---
title: Anti-aliasing con linee e curve
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- antialiasing
- antialiasing [Windows Forms], smoothing modes
- GDI+, antialiasing
ms.assetid: 810da1a4-c136-4abf-88df-68e49efdd8d4
ms.openlocfilehash: 6ea49c591b43d3f70bfd39058fd5ee256c537ec2
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57725012"
---
# <a name="antialiasing-with-lines-and-curves"></a><span data-ttu-id="37a3f-102">Anti-aliasing con linee e curve</span><span class="sxs-lookup"><span data-stu-id="37a3f-102">Antialiasing with Lines and Curves</span></span>
<span data-ttu-id="37a3f-103">Quando si usa [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] per disegnare una linea, si forniscono i punti iniziale e finale della linea, ma non è necessario fornire informazioni sui singoli pixel nella riga.</span><span class="sxs-lookup"><span data-stu-id="37a3f-103">When you use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] to draw a line, you provide the starting point and ending point of the line, but you do not have to provide any information about the individual pixels on the line.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="37a3f-104">funziona in combinazione con il software dei driver di visualizzazione per determinare i pixel che verranno attivati per visualizzare la linea in un dispositivo di visualizzazione particolare.</span><span class="sxs-lookup"><span data-stu-id="37a3f-104">works in conjunction with the display driver software to determine which pixels will be turned on to show the line on a particular display device.</span></span>  
  
## <a name="aliasing"></a><span data-ttu-id="37a3f-105">Aliasing</span><span class="sxs-lookup"><span data-stu-id="37a3f-105">Aliasing</span></span>  
 <span data-ttu-id="37a3f-106">Prendere in considerazione la linea rossa direttamente che va da punti (4, 2) per il punto (16, 10).</span><span class="sxs-lookup"><span data-stu-id="37a3f-106">Consider the straight red line that goes from the point (4, 2) to the point (16, 10).</span></span> <span data-ttu-id="37a3f-107">Si supponga il sistema di coordinate è la sua origine nell'angolo superiore sinistro e che l'unità di misura è il pixel.</span><span class="sxs-lookup"><span data-stu-id="37a3f-107">Assume the coordinate system has its origin in the upper-left corner and that the unit of measure is the pixel.</span></span> <span data-ttu-id="37a3f-108">Si supponga anche che l'asse x punta a destra e i punti di asse y verso il basso.</span><span class="sxs-lookup"><span data-stu-id="37a3f-108">Also assume that the x-axis points to the right and the y-axis points down.</span></span> <span data-ttu-id="37a3f-109">Nella figura seguente mostra una visualizzazione ingrandita della riga di colore rosso disegnata su uno sfondo.</span><span class="sxs-lookup"><span data-stu-id="37a3f-109">The following illustration shows an enlarged view of the red line drawn on a multicolored background.</span></span>  
  
 <span data-ttu-id="37a3f-110">![Linea, senza antialiasing](./media/aboutgdip02-art33.gif "AboutGdip02_Art33")</span><span class="sxs-lookup"><span data-stu-id="37a3f-110">![Line, no antialiasing](./media/aboutgdip02-art33.gif "AboutGdip02_Art33")</span></span>  
  
 <span data-ttu-id="37a3f-111">I pixel rosso usati per il rendering della linea sono opachi.</span><span class="sxs-lookup"><span data-stu-id="37a3f-111">The red pixels used to render the line are opaque.</span></span> <span data-ttu-id="37a3f-112">Non esistono Nessun pixel parzialmente trasparente nella riga.</span><span class="sxs-lookup"><span data-stu-id="37a3f-112">There are no partially transparent pixels in the line.</span></span> <span data-ttu-id="37a3f-113">Questo tipo di rendering fornisce la riga di un aspetto frastagliato, mentre la linea assomiglia scale.</span><span class="sxs-lookup"><span data-stu-id="37a3f-113">This type of line rendering gives the line a jagged appearance, and the line looks somewhat like a staircase.</span></span> <span data-ttu-id="37a3f-114">Questa tecnica di che rappresenta una riga con una scala è chiamata alias; la scala è un alias di linea teorica.</span><span class="sxs-lookup"><span data-stu-id="37a3f-114">This technique of representing a line with a staircase is called aliasing; the staircase is an alias for the theoretical line.</span></span>  
  
## <a name="antialiasing"></a><span data-ttu-id="37a3f-115">anti-aliasing</span><span class="sxs-lookup"><span data-stu-id="37a3f-115">Antialiasing</span></span>  
 <span data-ttu-id="37a3f-116">Una tecnica più sofisticata per il rendering di una riga comporta l'utilizzo di pixel parzialmente trasparente insieme ai pixel opaco.</span><span class="sxs-lookup"><span data-stu-id="37a3f-116">A more sophisticated technique for rendering a line involves using partially transparent pixels along with opaque pixels.</span></span> <span data-ttu-id="37a3f-117">Pixel sono impostati su rosso puro, o a una fusione del red team e il colore di sfondo, a seconda di quanto si avvicina sono per la riga.</span><span class="sxs-lookup"><span data-stu-id="37a3f-117">Pixels are set to pure red, or to some blend of red and the background color, depending on how close they are to the line.</span></span> <span data-ttu-id="37a3f-118">Questo tipo di rendering viene chiamato anti-aliasing e risultati in una riga che viene percepita come più uniforme.</span><span class="sxs-lookup"><span data-stu-id="37a3f-118">This type of rendering is called antialiasing and results in a line that the human eye perceives as more smooth.</span></span> <span data-ttu-id="37a3f-119">La figura seguente mostra come fusione di alcuni pixel con sfondo per produrre una linea con anti-aliasing.</span><span class="sxs-lookup"><span data-stu-id="37a3f-119">The following illustration shows how certain pixels are blended with the background to produce an antialiased line.</span></span>  
  
 <span data-ttu-id="37a3f-120">![Antialiasing di una linea](./media/aboutgdip02-art34.gif "AboutGdip02_Art34")</span><span class="sxs-lookup"><span data-stu-id="37a3f-120">![Antialiasing a Line](./media/aboutgdip02-art34.gif "AboutGdip02_Art34")</span></span>  
  
 <span data-ttu-id="37a3f-121">Anti-aliasing, detto anche anti-aliasing, può essere applicato anche alle curve.</span><span class="sxs-lookup"><span data-stu-id="37a3f-121">Antialiasing, also called smoothing, can also be applied to curves.</span></span> <span data-ttu-id="37a3f-122">Nella figura seguente mostra una visualizzazione ingrandita di un'ellisse equalizzata.</span><span class="sxs-lookup"><span data-stu-id="37a3f-122">The following illustration shows an enlarged view of a smoothed ellipse.</span></span>  
  
 <span data-ttu-id="37a3f-123">![Antialiasing di curve](./media/aboutgdip02-art35.gif "AboutGdip02_Art35")</span><span class="sxs-lookup"><span data-stu-id="37a3f-123">![Antialiasing Curves](./media/aboutgdip02-art35.gif "AboutGdip02_Art35")</span></span>  
  
 <span data-ttu-id="37a3f-124">Nella figura seguente viene mostrata la stessa ellisse dimensioni effettive, una volta senza anti-aliasing e una volta con anti-aliasing.</span><span class="sxs-lookup"><span data-stu-id="37a3f-124">The following illustration shows the same ellipse in its actual size, once without antialiasing and once with antialiasing.</span></span>  
  
 <span data-ttu-id="37a3f-125">![Esempio di antialiasing](./media/aboutgdip02-art36.gif "AboutGdip02_Art36")</span><span class="sxs-lookup"><span data-stu-id="37a3f-125">![Antialiasing example](./media/aboutgdip02-art36.gif "AboutGdip02_Art36")</span></span>  
  
 <span data-ttu-id="37a3f-126">Per tracciare linee e curve che utilizzano l'anti-aliasing, creare un'istanza del <xref:System.Drawing.Graphics> classe e impostare relativi <xref:System.Drawing.Graphics.SmoothingMode%2A> proprietà <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> o <xref:System.Drawing.Drawing2D.SmoothingMode.HighQuality>.</span><span class="sxs-lookup"><span data-stu-id="37a3f-126">To draw lines and curves that use antialiasing, create an instance of the <xref:System.Drawing.Graphics> class and set its <xref:System.Drawing.Graphics.SmoothingMode%2A> property to <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> or <xref:System.Drawing.Drawing2D.SmoothingMode.HighQuality>.</span></span> <span data-ttu-id="37a3f-127">Quindi chiamare uno dei metodi di disegno che stesso <xref:System.Drawing.Graphics> classe.</span><span class="sxs-lookup"><span data-stu-id="37a3f-127">Then call one of the drawing methods of that same <xref:System.Drawing.Graphics> class.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#81](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#81)]
 [!code-vb[LinesCurvesAndShapes#81](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#81)]  
  
## <a name="see-also"></a><span data-ttu-id="37a3f-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="37a3f-128">See also</span></span>
- <xref:System.Drawing.Drawing2D.SmoothingMode?displayProperty=nameWithType>
- [<span data-ttu-id="37a3f-129">Linee, curve e forme</span><span class="sxs-lookup"><span data-stu-id="37a3f-129">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="37a3f-130">Procedura: Usare l'antialiasing nel testo</span><span class="sxs-lookup"><span data-stu-id="37a3f-130">How to: Use Antialiasing with Text</span></span>](how-to-use-antialiasing-with-text.md)
