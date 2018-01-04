---
title: Regioni in GDI+
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
- GDI+, regions
- drawing [Windows Forms], regions
- regions
ms.assetid: 52184f9b-16dd-4bbd-85be-029112644ceb
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2d3805c2d67f5241425ef72d3802aba996d33cfb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="regions-in-gdi"></a><span data-ttu-id="8594d-102">Regioni in GDI+</span><span class="sxs-lookup"><span data-stu-id="8594d-102">Regions in GDI+</span></span>
<span data-ttu-id="8594d-103">Un'area è una parte dell'area di visualizzazione di un dispositivo di output.</span><span class="sxs-lookup"><span data-stu-id="8594d-103">A region is a portion of the display area of an output device.</span></span> <span data-ttu-id="8594d-104">Aree possono essere semplice (un rettangolo singolo) o complesso (una combinazione di poligoni e curve chiuse).</span><span class="sxs-lookup"><span data-stu-id="8594d-104">Regions can be simple (a single rectangle) or complex (a combination of polygons and closed curves).</span></span> <span data-ttu-id="8594d-105">La figura seguente mostra due aree: una creata da un rettangolo e l'altro costruito da un percorso.</span><span class="sxs-lookup"><span data-stu-id="8594d-105">The following illustration shows two regions: one constructed from a rectangle, and the other constructed from a path.</span></span>  
  
 <span data-ttu-id="8594d-106">![Aree](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art27.gif "AboutGdip02_Art27")</span><span class="sxs-lookup"><span data-stu-id="8594d-106">![Regions](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art27.gif "AboutGdip02_Art27")</span></span>  
  
## <a name="using-regions"></a><span data-ttu-id="8594d-107">Utilizzo delle regioni</span><span class="sxs-lookup"><span data-stu-id="8594d-107">Using Regions</span></span>  
 <span data-ttu-id="8594d-108">Le aree vengono spesso utilizzate per il ritaglio e l'hit test.</span><span class="sxs-lookup"><span data-stu-id="8594d-108">Regions are often used for clipping and hit testing.</span></span> <span data-ttu-id="8594d-109">Il ritaglio implica la restrizione di disegno per una determinata area geografica dell'area di visualizzazione, in genere la parte che deve essere aggiornato.</span><span class="sxs-lookup"><span data-stu-id="8594d-109">Clipping involves restricting drawing to a certain region of the display area, usually the portion that needs to be updated.</span></span> <span data-ttu-id="8594d-110">Processo di hit testing implica il controllo per determinare se il cursore si trova in una determinata area dello schermo quando viene premuto un pulsante del mouse.</span><span class="sxs-lookup"><span data-stu-id="8594d-110">Hit testing involves checking to determine whether the cursor is in a certain region of the screen when a mouse button is pressed.</span></span>  
  
 <span data-ttu-id="8594d-111">È possibile creare un'area da un rettangolo o un percorso.</span><span class="sxs-lookup"><span data-stu-id="8594d-111">You can construct a region from a rectangle or a path.</span></span> <span data-ttu-id="8594d-112">È anche possibile creare aree complesse combinando regioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="8594d-112">You can also create complex regions by combining existing regions.</span></span> <span data-ttu-id="8594d-113">Il <xref:System.Drawing.Region> classe fornisce i metodi seguenti per la combinazione di regioni: <xref:System.Drawing.Region.Intersect%2A>, <xref:System.Drawing.Region.Union%2A>, <xref:System.Drawing.Region.Xor%2A>, <xref:System.Drawing.Region.Exclude%2A>, e <xref:System.Drawing.Region.Complement%2A>.</span><span class="sxs-lookup"><span data-stu-id="8594d-113">The <xref:System.Drawing.Region> class provides the following methods for combining regions: <xref:System.Drawing.Region.Intersect%2A>, <xref:System.Drawing.Region.Union%2A>, <xref:System.Drawing.Region.Xor%2A>, <xref:System.Drawing.Region.Exclude%2A>, and <xref:System.Drawing.Region.Complement%2A>.</span></span>  
  
 <span data-ttu-id="8594d-114">L'intersezione di due aree è il set di tutti i punti appartenenti a entrambe le aree.</span><span class="sxs-lookup"><span data-stu-id="8594d-114">The intersection of two regions is the set of all points belonging to both regions.</span></span> <span data-ttu-id="8594d-115">L'unione è il set di tutti i punti appartenenti a uno o l'altro o entrambe le aree.</span><span class="sxs-lookup"><span data-stu-id="8594d-115">The union is the set of all points belonging to one or the other or both regions.</span></span> <span data-ttu-id="8594d-116">Il complemento di un'area è il set di tutti i punti che non sono presenti nell'area.</span><span class="sxs-lookup"><span data-stu-id="8594d-116">The complement of a region is the set of all points that are not in the region.</span></span> <span data-ttu-id="8594d-117">Nella figura seguente mostra l'intersezione e l'unione delle due aree illustrato nella figura precedente.</span><span class="sxs-lookup"><span data-stu-id="8594d-117">The following illustration shows the intersection and union of the two regions shown in the preceding illustration.</span></span>  
  
 <span data-ttu-id="8594d-118">![Aree](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art28.gif "AboutGdip02_Art28")</span><span class="sxs-lookup"><span data-stu-id="8594d-118">![Regions](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art28.gif "AboutGdip02_Art28")</span></span>  
  
 <span data-ttu-id="8594d-119">Il <xref:System.Drawing.Region.Xor%2A> metodo, applicato a una coppia di regioni, genera un'area che contiene tutti i punti che appartengono a un'area o l'altro, ma non entrambi.</span><span class="sxs-lookup"><span data-stu-id="8594d-119">The <xref:System.Drawing.Region.Xor%2A> method, applied to a pair of regions, produces a region that contains all points that belong to one region or the other, but not both.</span></span> <span data-ttu-id="8594d-120">Il <xref:System.Drawing.Region.Exclude%2A> metodo, applicato a una coppia di regioni, genera un'area che contiene tutti i punti nella prima area che non si trovano nella seconda area.</span><span class="sxs-lookup"><span data-stu-id="8594d-120">The <xref:System.Drawing.Region.Exclude%2A> method, applied to a pair of regions, produces a region that contains all points in the first region that are not in the second region.</span></span> <span data-ttu-id="8594d-121">La figura seguente mostra le aree risultanti dall'applicazione di <xref:System.Drawing.Region.Xor%2A> e <xref:System.Drawing.Region.Exclude%2A> metodi alle due aree riportate all'inizio di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="8594d-121">The following illustration shows the regions that result from applying the <xref:System.Drawing.Region.Xor%2A> and <xref:System.Drawing.Region.Exclude%2A> methods to the two regions shown at the beginning of this topic.</span></span>  
  
 <span data-ttu-id="8594d-122">![Aree](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art29.gif "AboutGdip02_Art29")</span><span class="sxs-lookup"><span data-stu-id="8594d-122">![Regions](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art29.gif "AboutGdip02_Art29")</span></span>  
  
 <span data-ttu-id="8594d-123">Per riempire un'area, è necessario un <xref:System.Drawing.Graphics> oggetto, un <xref:System.Drawing.Brush> , oggetto e un <xref:System.Drawing.Region> oggetto.</span><span class="sxs-lookup"><span data-stu-id="8594d-123">To fill a region, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Brush> object, and a <xref:System.Drawing.Region> object.</span></span> <span data-ttu-id="8594d-124">Il <xref:System.Drawing.Graphics> oggetto fornisce il <xref:System.Drawing.Graphics.FillRegion%2A> (metodo) e <xref:System.Drawing.Brush> oggetto archivia gli attributi del riempimento, ad esempio colore o il motivo.</span><span class="sxs-lookup"><span data-stu-id="8594d-124">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.FillRegion%2A> method, and the <xref:System.Drawing.Brush> object stores attributes of the fill, such as color or pattern.</span></span> <span data-ttu-id="8594d-125">Nell'esempio seguente inserisce un'area con un colore a tinta unita.</span><span class="sxs-lookup"><span data-stu-id="8594d-125">The following example fills a region with a solid color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#61)]
 [!code-vb[LinesCurvesAndShapes#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#61)]  
  
## <a name="see-also"></a><span data-ttu-id="8594d-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8594d-126">See Also</span></span>  
 <xref:System.Drawing.Region?displayProperty=nameWithType>  
 [<span data-ttu-id="8594d-127">Linee, curve e forme</span><span class="sxs-lookup"><span data-stu-id="8594d-127">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="8594d-128">Uso delle regioni</span><span class="sxs-lookup"><span data-stu-id="8594d-128">Using Regions</span></span>](../../../../docs/framework/winforms/advanced/using-regions.md)
