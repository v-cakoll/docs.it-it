---
title: 'Procedura: trasformare un percorso curvo in una linea'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [Windows Forms], flattening curves into lines
- curves [Windows Forms], flattening
- GraphicsPath object
- paths [Windows Forms], flattening
- drawing [Windows Forms], flattening curves
ms.assetid: e654b8de-25f4-4735-9208-42e4514a589c
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 334fc0fee7166f8f8c5c1db61d3b9e370da72f87
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-flatten-a-curved-path-into-a-line"></a><span data-ttu-id="3081c-102">Procedura: trasformare un percorso curvo in una linea</span><span class="sxs-lookup"><span data-stu-id="3081c-102">How to: Flatten a Curved Path into a Line</span></span>
<span data-ttu-id="3081c-103">Oggetto <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto archivia una sequenza di righe e di spline di Bézier.</span><span class="sxs-lookup"><span data-stu-id="3081c-103">A <xref:System.Drawing.Drawing2D.GraphicsPath> object stores a sequence of lines and Bézier splines.</span></span> <span data-ttu-id="3081c-104">È possibile aggiungere diversi tipi di curve (puntini di sospensione, archi, spline di tipo cardinal) a un percorso, ma ogni curva viene convertito in una spline di Bézier prima che venga archiviata nel percorso.</span><span class="sxs-lookup"><span data-stu-id="3081c-104">You can add several types of curves (ellipses, arcs, cardinal splines) to a path, but each curve is converted to a Bézier spline before it is stored in the path.</span></span> <span data-ttu-id="3081c-105">Appiattimento di un percorso costituito dalla conversione ogni spline di Bézier nel percorso in una sequenza di linee rette.</span><span class="sxs-lookup"><span data-stu-id="3081c-105">Flattening a path consists of converting each Bézier spline in the path to a sequence of straight lines.</span></span> <span data-ttu-id="3081c-106">Nella figura seguente viene mostrato un percorso prima e dopo la conversione.</span><span class="sxs-lookup"><span data-stu-id="3081c-106">The following illustration shows a path before and after flattening.</span></span>  
  
 <span data-ttu-id="3081c-107">![Linee rette e curve](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span><span class="sxs-lookup"><span data-stu-id="3081c-107">![Straight Lines and Curves](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span></span>  
  
### <a name="to-flatten-a-path"></a><span data-ttu-id="3081c-108">Per trasformare un percorso</span><span class="sxs-lookup"><span data-stu-id="3081c-108">To Flatten a Path</span></span>  
  
-   <span data-ttu-id="3081c-109">chiamare il <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> metodo di un <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto.</span><span class="sxs-lookup"><span data-stu-id="3081c-109">call the <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method of a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="3081c-110">Il <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> metodo riceve un argomento di appiattimento che specifica la distanza massima tra il percorso bidimensionale e il percorso originale.</span><span class="sxs-lookup"><span data-stu-id="3081c-110">The <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method receives a flatness argument that specifies the maximum distance between the flattened path and the original path.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3081c-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3081c-111">See Also</span></span>  
 <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>  
 [<span data-ttu-id="3081c-112">Linee, curve e forme</span><span class="sxs-lookup"><span data-stu-id="3081c-112">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="3081c-113">Costruzione e creazione di percorsi</span><span class="sxs-lookup"><span data-stu-id="3081c-113">Constructing and Drawing Paths</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)
