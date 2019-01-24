---
title: 'Procedura: Trasformare un percorso curvo in una riga'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], flattening curves into lines
- curves [Windows Forms], flattening
- GraphicsPath object
- paths [Windows Forms], flattening
- drawing [Windows Forms], flattening curves
ms.assetid: e654b8de-25f4-4735-9208-42e4514a589c
ms.openlocfilehash: aa47a655417cdf82d79fb222dc6ff6f6d8c3a947
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54601818"
---
# <a name="how-to-flatten-a-curved-path-into-a-line"></a><span data-ttu-id="dfa90-102">Procedura: Trasformare un percorso curvo in una riga</span><span class="sxs-lookup"><span data-stu-id="dfa90-102">How to: Flatten a Curved Path into a Line</span></span>
<span data-ttu-id="dfa90-103">Oggetto <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto archivia una sequenza di spline di Bézier e righe.</span><span class="sxs-lookup"><span data-stu-id="dfa90-103">A <xref:System.Drawing.Drawing2D.GraphicsPath> object stores a sequence of lines and Bézier splines.</span></span> <span data-ttu-id="dfa90-104">È possibile aggiungere diversi tipi di curve (puntini di sospensione, archi e spline cardinali) in un percorso, ma ogni curva viene convertito in una spline di Bézier prima di essere archiviato nel percorso.</span><span class="sxs-lookup"><span data-stu-id="dfa90-104">You can add several types of curves (ellipses, arcs, cardinal splines) to a path, but each curve is converted to a Bézier spline before it is stored in the path.</span></span> <span data-ttu-id="dfa90-105">Rendere flat un percorso è costituito ogni spline di Bézier nel percorso di conversione in una sequenza di linee rette.</span><span class="sxs-lookup"><span data-stu-id="dfa90-105">Flattening a path consists of converting each Bézier spline in the path to a sequence of straight lines.</span></span> <span data-ttu-id="dfa90-106">Nella figura seguente mostra un percorso di prima e dopo l'appiattimento.</span><span class="sxs-lookup"><span data-stu-id="dfa90-106">The following illustration shows a path before and after flattening.</span></span>  
  
 <span data-ttu-id="dfa90-107">![Linee rette e curve](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span><span class="sxs-lookup"><span data-stu-id="dfa90-107">![Straight Lines and Curves](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span></span>  
  
### <a name="to-flatten-a-path"></a><span data-ttu-id="dfa90-108">Per trasformare un percorso</span><span class="sxs-lookup"><span data-stu-id="dfa90-108">To Flatten a Path</span></span>  
  
-   <span data-ttu-id="dfa90-109">chiamare il <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> metodo di un <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto.</span><span class="sxs-lookup"><span data-stu-id="dfa90-109">call the <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method of a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="dfa90-110">Il <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> metodo riceve un argomento di appiattimento che specifica la distanza massima tra il percorso appiattito e il percorso originale.</span><span class="sxs-lookup"><span data-stu-id="dfa90-110">The <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method receives a flatness argument that specifies the maximum distance between the flattened path and the original path.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfa90-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dfa90-111">See also</span></span>
- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- [<span data-ttu-id="dfa90-112">Linee, curve e forme</span><span class="sxs-lookup"><span data-stu-id="dfa90-112">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)
- [<span data-ttu-id="dfa90-113">Costruzione e creazione di percorsi</span><span class="sxs-lookup"><span data-stu-id="dfa90-113">Constructing and Drawing Paths</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)
