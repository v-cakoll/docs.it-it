---
title: Anti-aliasing con linee e curve
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
- antialiasing
- antialiasing [Windows Forms], smoothing modes
- GDI+, antialiasing
ms.assetid: 810da1a4-c136-4abf-88df-68e49efdd8d4
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d69d635fbdd8720937cd189826c1496b8126ddef
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="antialiasing-with-lines-and-curves"></a><span data-ttu-id="ac3ea-102">Anti-aliasing con linee e curve</span><span class="sxs-lookup"><span data-stu-id="ac3ea-102">Antialiasing with Lines and Curves</span></span>
<span data-ttu-id="ac3ea-103">Quando si utilizza [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] per disegnare una linea, si forniscono i punti iniziale e finale della riga, ma non è necessario fornire le informazioni sui singoli pixel della riga.</span><span class="sxs-lookup"><span data-stu-id="ac3ea-103">When you use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] to draw a line, you provide the starting point and ending point of the line, but you do not have to provide any information about the individual pixels on the line.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="ac3ea-104">funziona in combinazione con il software dei driver di visualizzazione per determinare i pixel verranno attivati per visualizzare la riga in un particolare dispositivo di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="ac3ea-104"> works in conjunction with the display driver software to determine which pixels will be turned on to show the line on a particular display device.</span></span>  
  
## <a name="aliasing"></a><span data-ttu-id="ac3ea-105">Alias</span><span class="sxs-lookup"><span data-stu-id="ac3ea-105">Aliasing</span></span>  
 <span data-ttu-id="ac3ea-106">Prendere in considerazione la linea rossa direttamente che unisce il punto (4, 2) per il punto (16, 10).</span><span class="sxs-lookup"><span data-stu-id="ac3ea-106">Consider the straight red line that goes from the point (4, 2) to the point (16, 10).</span></span> <span data-ttu-id="ac3ea-107">Si supponga che il sistema di coordinate ha origine nell'angolo superiore sinistro e che l'unità di misura è il pixel.</span><span class="sxs-lookup"><span data-stu-id="ac3ea-107">Assume the coordinate system has its origin in the upper-left corner and that the unit of measure is the pixel.</span></span> <span data-ttu-id="ac3ea-108">Si supponga inoltre che l'asse x punta a destra e i punti di asse y verso il basso.</span><span class="sxs-lookup"><span data-stu-id="ac3ea-108">Also assume that the x-axis points to the right and the y-axis points down.</span></span> <span data-ttu-id="ac3ea-109">Nella figura seguente mostra una linea rossa tracciata su uno sfondo ingrandita.</span><span class="sxs-lookup"><span data-stu-id="ac3ea-109">The following illustration shows an enlarged view of the red line drawn on a multicolored background.</span></span>  
  
 <span data-ttu-id="ac3ea-110">![Linea, senza antialiasing](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art33.gif "AboutGdip02_Art33")</span><span class="sxs-lookup"><span data-stu-id="ac3ea-110">![Line, no antialiasing](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art33.gif "AboutGdip02_Art33")</span></span>  
  
 <span data-ttu-id="ac3ea-111">Il pixel rossi utilizzati per il rendering della linea sono opachi.</span><span class="sxs-lookup"><span data-stu-id="ac3ea-111">The red pixels used to render the line are opaque.</span></span> <span data-ttu-id="ac3ea-112">Nella riga sono non presenti Nessun pixel semitrasparente.</span><span class="sxs-lookup"><span data-stu-id="ac3ea-112">There are no partially transparent pixels in the line.</span></span> <span data-ttu-id="ac3ea-113">Questo tipo di rendering fornisce la riga di un aspetto irregolare, mentre la linea assomiglia scale.</span><span class="sxs-lookup"><span data-stu-id="ac3ea-113">This type of line rendering gives the line a jagged appearance, and the line looks somewhat like a staircase.</span></span> <span data-ttu-id="ac3ea-114">Questa tecnica di che rappresenta una riga con una scala è chiamata alias; la scala è un alias per la linea teorica.</span><span class="sxs-lookup"><span data-stu-id="ac3ea-114">This technique of representing a line with a staircase is called aliasing; the staircase is an alias for the theoretical line.</span></span>  
  
## <a name="antialiasing"></a><span data-ttu-id="ac3ea-115">Anti-aliasing</span><span class="sxs-lookup"><span data-stu-id="ac3ea-115">Antialiasing</span></span>  
 <span data-ttu-id="ac3ea-116">Una tecnica più sofisticata per il rendering di una riga comporta l'utilizzo di pixel semitrasparente insieme ai pixel opachi.</span><span class="sxs-lookup"><span data-stu-id="ac3ea-116">A more sophisticated technique for rendering a line involves using partially transparent pixels along with opaque pixels.</span></span> <span data-ttu-id="ac3ea-117">Pixel viene impostato su rosso puro, o per alcuni sfumatura di rosso e il colore di sfondo, a seconda di come chiudere siano alla riga.</span><span class="sxs-lookup"><span data-stu-id="ac3ea-117">Pixels are set to pure red, or to some blend of red and the background color, depending on how close they are to the line.</span></span> <span data-ttu-id="ac3ea-118">Questo tipo di rendering viene chiamato l'anti-aliasing e risultati in una riga che viene percepita come più uniforme.</span><span class="sxs-lookup"><span data-stu-id="ac3ea-118">This type of rendering is called antialiasing and results in a line that the human eye perceives as more smooth.</span></span> <span data-ttu-id="ac3ea-119">Nella figura seguente viene illustrato come determinate pixel vengono combinati con lo sfondo per produrre una riga di anti-aliasing.</span><span class="sxs-lookup"><span data-stu-id="ac3ea-119">The following illustration shows how certain pixels are blended with the background to produce an antialiased line.</span></span>  
  
 <span data-ttu-id="ac3ea-120">![Antialiasing di una linea](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art34.gif "AboutGdip02_Art34")</span><span class="sxs-lookup"><span data-stu-id="ac3ea-120">![Antialiasing a Line](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art34.gif "AboutGdip02_Art34")</span></span>  
  
 <span data-ttu-id="ac3ea-121">Anti-aliasing, smussamento, possono inoltre essere applicate alle curve.</span><span class="sxs-lookup"><span data-stu-id="ac3ea-121">Antialiasing, also called smoothing, can also be applied to curves.</span></span> <span data-ttu-id="ac3ea-122">Nella figura seguente mostra una visualizzazione di un'ellisse smussata ingrandita.</span><span class="sxs-lookup"><span data-stu-id="ac3ea-122">The following illustration shows an enlarged view of a smoothed ellipse.</span></span>  
  
 <span data-ttu-id="ac3ea-123">![Antialiasing di curve](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art35.gif "AboutGdip02_Art35")</span><span class="sxs-lookup"><span data-stu-id="ac3ea-123">![Antialiasing Curves](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art35.gif "AboutGdip02_Art35")</span></span>  
  
 <span data-ttu-id="ac3ea-124">Nella figura seguente viene mostrata la stessa ellisse dimensioni effettive, senza e una volta con anti-aliasing.</span><span class="sxs-lookup"><span data-stu-id="ac3ea-124">The following illustration shows the same ellipse in its actual size, once without antialiasing and once with antialiasing.</span></span>  
  
 <span data-ttu-id="ac3ea-125">![Esempio di antialiasing](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art36.gif "AboutGdip02_Art36")</span><span class="sxs-lookup"><span data-stu-id="ac3ea-125">![Antialiasing example](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art36.gif "AboutGdip02_Art36")</span></span>  
  
 <span data-ttu-id="ac3ea-126">Per disegnare linee e curve che utilizzano l'anti-aliasing, creare un'istanza del <xref:System.Drawing.Graphics> e impostare il relativo <xref:System.Drawing.Graphics.SmoothingMode%2A> proprietà <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> o <xref:System.Drawing.Drawing2D.SmoothingMode.HighQuality>.</span><span class="sxs-lookup"><span data-stu-id="ac3ea-126">To draw lines and curves that use antialiasing, create an instance of the <xref:System.Drawing.Graphics> class and set its <xref:System.Drawing.Graphics.SmoothingMode%2A> property to <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> or <xref:System.Drawing.Drawing2D.SmoothingMode.HighQuality>.</span></span> <span data-ttu-id="ac3ea-127">Quindi chiamare uno dei metodi di disegno che stesso <xref:System.Drawing.Graphics> classe.</span><span class="sxs-lookup"><span data-stu-id="ac3ea-127">Then call one of the drawing methods of that same <xref:System.Drawing.Graphics> class.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#81](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#81)]
 [!code-vb[LinesCurvesAndShapes#81](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#81)]  
  
## <a name="see-also"></a><span data-ttu-id="ac3ea-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac3ea-128">See Also</span></span>  
 <xref:System.Drawing.Drawing2D.SmoothingMode?displayProperty=nameWithType>  
 [<span data-ttu-id="ac3ea-129">Linee, curve e forme</span><span class="sxs-lookup"><span data-stu-id="ac3ea-129">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="ac3ea-130">Procedura: Usare l'antialiasing nel testo</span><span class="sxs-lookup"><span data-stu-id="ac3ea-130">How to: Use Antialiasing with Text</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-antialiasing-with-text.md)
