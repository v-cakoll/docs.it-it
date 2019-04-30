---
title: Regioni in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, regions
- drawing [Windows Forms], regions
- regions
ms.assetid: 52184f9b-16dd-4bbd-85be-029112644ceb
ms.openlocfilehash: 33d4f4ecca7b9d777fa4eab5b6d031de10f03ccc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61956812"
---
# <a name="regions-in-gdi"></a><span data-ttu-id="93791-102">Regioni in GDI+</span><span class="sxs-lookup"><span data-stu-id="93791-102">Regions in GDI+</span></span>
<span data-ttu-id="93791-103">Un'area è una parte dell'area di visualizzazione di un dispositivo di output.</span><span class="sxs-lookup"><span data-stu-id="93791-103">A region is a portion of the display area of an output device.</span></span> <span data-ttu-id="93791-104">Aree possono essere complesso (una combinazione di Polygon e curve chiuse) o semplice (un rettangolo singolo).</span><span class="sxs-lookup"><span data-stu-id="93791-104">Regions can be simple (a single rectangle) or complex (a combination of polygons and closed curves).</span></span> <span data-ttu-id="93791-105">La figura seguente mostra due aree: uno creato da un rettangolo, e l'altro creato da un percorso.</span><span class="sxs-lookup"><span data-stu-id="93791-105">The following illustration shows two regions: one constructed from a rectangle, and the other constructed from a path.</span></span>  
  
 <span data-ttu-id="93791-106">![Regions](./media/aboutgdip02-art27.gif "AboutGdip02_Art27")</span><span class="sxs-lookup"><span data-stu-id="93791-106">![Regions](./media/aboutgdip02-art27.gif "AboutGdip02_Art27")</span></span>  
  
## <a name="using-regions"></a><span data-ttu-id="93791-107">Utilizzo delle regioni</span><span class="sxs-lookup"><span data-stu-id="93791-107">Using Regions</span></span>  
 <span data-ttu-id="93791-108">Le aree vengono spesso usate per il ritaglio e l'hit testing.</span><span class="sxs-lookup"><span data-stu-id="93791-108">Regions are often used for clipping and hit testing.</span></span> <span data-ttu-id="93791-109">Ritaglio comporta la limitazione di disegno per una determinata area dell'area di visualizzazione, in genere la parte che deve essere aggiornato.</span><span class="sxs-lookup"><span data-stu-id="93791-109">Clipping involves restricting drawing to a certain region of the display area, usually the portion that needs to be updated.</span></span> <span data-ttu-id="93791-110">Hit test prevedono la verifica per determinare se il cursore si trova in una determinata area dello schermo quando viene premuto un pulsante del mouse.</span><span class="sxs-lookup"><span data-stu-id="93791-110">Hit testing involves checking to determine whether the cursor is in a certain region of the screen when a mouse button is pressed.</span></span>  
  
 <span data-ttu-id="93791-111">È possibile creare un'area da un rettangolo o un percorso.</span><span class="sxs-lookup"><span data-stu-id="93791-111">You can construct a region from a rectangle or a path.</span></span> <span data-ttu-id="93791-112">È anche possibile creare aree complesse combinando aree esistenti.</span><span class="sxs-lookup"><span data-stu-id="93791-112">You can also create complex regions by combining existing regions.</span></span> <span data-ttu-id="93791-113">Il <xref:System.Drawing.Region> classe fornisce metodi per la combinazione delle aree seguenti: <xref:System.Drawing.Region.Intersect%2A>, <xref:System.Drawing.Region.Union%2A>, <xref:System.Drawing.Region.Xor%2A>, <xref:System.Drawing.Region.Exclude%2A>, e <xref:System.Drawing.Region.Complement%2A>.</span><span class="sxs-lookup"><span data-stu-id="93791-113">The <xref:System.Drawing.Region> class provides the following methods for combining regions: <xref:System.Drawing.Region.Intersect%2A>, <xref:System.Drawing.Region.Union%2A>, <xref:System.Drawing.Region.Xor%2A>, <xref:System.Drawing.Region.Exclude%2A>, and <xref:System.Drawing.Region.Complement%2A>.</span></span>  
  
 <span data-ttu-id="93791-114">L'intersezione di due aree geografiche è il set di tutti i punti che appartengono a entrambe le aree.</span><span class="sxs-lookup"><span data-stu-id="93791-114">The intersection of two regions is the set of all points belonging to both regions.</span></span> <span data-ttu-id="93791-115">L'unione è il set di tutti i punti che appartengono a uno o l'altro o entrambe le aree.</span><span class="sxs-lookup"><span data-stu-id="93791-115">The union is the set of all points belonging to one or the other or both regions.</span></span> <span data-ttu-id="93791-116">Il complemento di un'area è il set di tutti i punti che non sono presenti nell'area.</span><span class="sxs-lookup"><span data-stu-id="93791-116">The complement of a region is the set of all points that are not in the region.</span></span> <span data-ttu-id="93791-117">La figura seguente mostra l'intersezione e l'unione delle due aree illustrato nella figura precedente.</span><span class="sxs-lookup"><span data-stu-id="93791-117">The following illustration shows the intersection and union of the two regions shown in the preceding illustration.</span></span>  
  
 <span data-ttu-id="93791-118">![Regions](./media/aboutgdip02-art28.gif "AboutGdip02_Art28")</span><span class="sxs-lookup"><span data-stu-id="93791-118">![Regions](./media/aboutgdip02-art28.gif "AboutGdip02_Art28")</span></span>  
  
 <span data-ttu-id="93791-119">Il <xref:System.Drawing.Region.Xor%2A> metodo, applicato a una coppia di aree, produce un'area che contiene tutti i punti che appartengono a un'area o l'altro, ma non entrambi.</span><span class="sxs-lookup"><span data-stu-id="93791-119">The <xref:System.Drawing.Region.Xor%2A> method, applied to a pair of regions, produces a region that contains all points that belong to one region or the other, but not both.</span></span> <span data-ttu-id="93791-120">Il <xref:System.Drawing.Region.Exclude%2A> metodo, applicato a una coppia di aree, produce un'area che contiene tutti i punti della prima area che non sono presenti nella seconda area.</span><span class="sxs-lookup"><span data-stu-id="93791-120">The <xref:System.Drawing.Region.Exclude%2A> method, applied to a pair of regions, produces a region that contains all points in the first region that are not in the second region.</span></span> <span data-ttu-id="93791-121">La figura seguente mostra le aree ottenuto dall'applicazione il <xref:System.Drawing.Region.Xor%2A> e <xref:System.Drawing.Region.Exclude%2A> metodi alle due aree mostrate all'inizio di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="93791-121">The following illustration shows the regions that result from applying the <xref:System.Drawing.Region.Xor%2A> and <xref:System.Drawing.Region.Exclude%2A> methods to the two regions shown at the beginning of this topic.</span></span>  
  
 <span data-ttu-id="93791-122">![Regions](./media/aboutgdip02-art29.gif "AboutGdip02_Art29")</span><span class="sxs-lookup"><span data-stu-id="93791-122">![Regions](./media/aboutgdip02-art29.gif "AboutGdip02_Art29")</span></span>  
  
 <span data-ttu-id="93791-123">Per riempire un'area, è necessario un <xref:System.Drawing.Graphics> oggetti, una <xref:System.Drawing.Brush> oggetti e un <xref:System.Drawing.Region> oggetto.</span><span class="sxs-lookup"><span data-stu-id="93791-123">To fill a region, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Brush> object, and a <xref:System.Drawing.Region> object.</span></span> <span data-ttu-id="93791-124">Il <xref:System.Drawing.Graphics> oggetto fornisce le <xref:System.Drawing.Graphics.FillRegion%2A> metodo e il <xref:System.Drawing.Brush> oggetto archivia gli attributi del riempimento, ad esempio colori o modello.</span><span class="sxs-lookup"><span data-stu-id="93791-124">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.FillRegion%2A> method, and the <xref:System.Drawing.Brush> object stores attributes of the fill, such as color or pattern.</span></span> <span data-ttu-id="93791-125">Nell'esempio seguente riempie un'area con colori a tinta unita.</span><span class="sxs-lookup"><span data-stu-id="93791-125">The following example fills a region with a solid color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#61](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#61)]
 [!code-vb[LinesCurvesAndShapes#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#61)]  
  
## <a name="see-also"></a><span data-ttu-id="93791-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93791-126">See also</span></span>

- <xref:System.Drawing.Region?displayProperty=nameWithType>
- [<span data-ttu-id="93791-127">Linee, curve e forme</span><span class="sxs-lookup"><span data-stu-id="93791-127">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="93791-128">Uso delle regioni</span><span class="sxs-lookup"><span data-stu-id="93791-128">Using Regions</span></span>](using-regions.md)
