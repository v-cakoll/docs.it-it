---
title: 'Procedura: Appiattire un percorso curvo in una linea'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], flattening curves into lines
- curves [Windows Forms], flattening
- GraphicsPath object
- paths [Windows Forms], flattening
- drawing [Windows Forms], flattening curves
ms.assetid: e654b8de-25f4-4735-9208-42e4514a589c
ms.openlocfilehash: a151b4244e14d3704fd5fa1c55de92211981232f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59215157"
---
# <a name="how-to-flatten-a-curved-path-into-a-line"></a><span data-ttu-id="07e42-102">Procedura: Appiattire un percorso curvo in una linea</span><span class="sxs-lookup"><span data-stu-id="07e42-102">How to: Flatten a Curved Path into a Line</span></span>
<span data-ttu-id="07e42-103">Oggetto <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto archivia una sequenza di spline di Bézier e righe.</span><span class="sxs-lookup"><span data-stu-id="07e42-103">A <xref:System.Drawing.Drawing2D.GraphicsPath> object stores a sequence of lines and Bézier splines.</span></span> <span data-ttu-id="07e42-104">È possibile aggiungere diversi tipi di curve (puntini di sospensione, archi e spline cardinali) in un percorso, ma ogni curva viene convertito in una spline di Bézier prima di essere archiviato nel percorso.</span><span class="sxs-lookup"><span data-stu-id="07e42-104">You can add several types of curves (ellipses, arcs, cardinal splines) to a path, but each curve is converted to a Bézier spline before it is stored in the path.</span></span> <span data-ttu-id="07e42-105">Rendere flat un percorso è costituito ogni spline di Bézier nel percorso di conversione in una sequenza di linee rette.</span><span class="sxs-lookup"><span data-stu-id="07e42-105">Flattening a path consists of converting each Bézier spline in the path to a sequence of straight lines.</span></span> <span data-ttu-id="07e42-106">Nella figura seguente mostra un percorso di prima e dopo l'appiattimento.</span><span class="sxs-lookup"><span data-stu-id="07e42-106">The following illustration shows a path before and after flattening.</span></span>  
  
 <span data-ttu-id="07e42-107">![Linee rette e curve](./media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span><span class="sxs-lookup"><span data-stu-id="07e42-107">![Straight Lines and Curves](./media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span></span>  
  
### <a name="to-flatten-a-path"></a><span data-ttu-id="07e42-108">Per trasformare un percorso</span><span class="sxs-lookup"><span data-stu-id="07e42-108">To Flatten a Path</span></span>  
  
-   <span data-ttu-id="07e42-109">chiamare il <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> metodo di un <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto.</span><span class="sxs-lookup"><span data-stu-id="07e42-109">call the <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method of a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="07e42-110">Il <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> metodo riceve un argomento di appiattimento che specifica la distanza massima tra il percorso appiattito e il percorso originale.</span><span class="sxs-lookup"><span data-stu-id="07e42-110">The <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method receives a flatness argument that specifies the maximum distance between the flattened path and the original path.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07e42-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07e42-111">See also</span></span>

- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- [<span data-ttu-id="07e42-112">Linee, curve e forme</span><span class="sxs-lookup"><span data-stu-id="07e42-112">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="07e42-113">Costruzione e creazione di percorsi</span><span class="sxs-lookup"><span data-stu-id="07e42-113">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
