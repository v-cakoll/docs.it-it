---
title: Gestione dello stato di un oggetto Graphics
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], managing state
- graphics [Windows Forms], clipping
ms.assetid: 6207cad1-7a34-4bd6-bfc1-db823ca7a73e
ms.openlocfilehash: b81c3c8b25f13ac5791b5d2116b8536575f9ebcf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525119"
---
# <a name="managing-the-state-of-a-graphics-object"></a><span data-ttu-id="e5aed-102">Gestione dello stato di un oggetto Graphics</span><span class="sxs-lookup"><span data-stu-id="e5aed-102">Managing the State of a Graphics Object</span></span>
<span data-ttu-id="e5aed-103">Il <xref:System.Drawing.Graphics> classe è il fulcro di [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5aed-103">The <xref:System.Drawing.Graphics> class is at the heart of [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span> <span data-ttu-id="e5aed-104">Per creare qualsiasi oggetto, per ottenere un <xref:System.Drawing.Graphics> dell'oggetto, impostarne le proprietà e chiamarne i metodi <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, <xref:System.Drawing.Graphics.DrawString%2A>e così via).</span><span class="sxs-lookup"><span data-stu-id="e5aed-104">To draw anything, you obtain a <xref:System.Drawing.Graphics> object, set its properties, and call its methods <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, <xref:System.Drawing.Graphics.DrawString%2A>, and the like).</span></span>  
  
 <span data-ttu-id="e5aed-105">L'esempio seguente chiama il <xref:System.Drawing.Graphics.DrawRectangle%2A> metodo di un <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="e5aed-105">The following example calls the <xref:System.Drawing.Graphics.DrawRectangle%2A> method of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="e5aed-106">Il primo argomento passato per il <xref:System.Drawing.Graphics.DrawRectangle%2A> metodo è un <xref:System.Drawing.Pen> oggetto.</span><span class="sxs-lookup"><span data-stu-id="e5aed-106">The first argument passed to the <xref:System.Drawing.Graphics.DrawRectangle%2A> method is a <xref:System.Drawing.Pen> object.</span></span>  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Blue) ' Opaque blue  
graphics.DrawRectangle(pen, 10, 10, 200, 100)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Blue);  // Opaque blue  
graphics.DrawRectangle(pen, 10, 10, 200, 100);  
```  
  
## <a name="graphics-state"></a><span data-ttu-id="e5aed-107">Stato grafica</span><span class="sxs-lookup"><span data-stu-id="e5aed-107">Graphics State</span></span>  
 <span data-ttu-id="e5aed-108">Oggetto <xref:System.Drawing.Graphics> oggetto forniscono più metodi di disegno, ad esempio <xref:System.Drawing.Graphics.DrawLine%2A> e <xref:System.Drawing.Graphics.DrawRectangle%2A>.</span><span class="sxs-lookup"><span data-stu-id="e5aed-108">A <xref:System.Drawing.Graphics> object does more than provide drawing methods, such as <xref:System.Drawing.Graphics.DrawLine%2A> and <xref:System.Drawing.Graphics.DrawRectangle%2A>.</span></span> <span data-ttu-id="e5aed-109">Oggetto <xref:System.Drawing.Graphics> viene conservato anche lo stato di grafica, che può essere suddivisi nelle categorie seguenti:</span><span class="sxs-lookup"><span data-stu-id="e5aed-109">A <xref:System.Drawing.Graphics> object also maintains graphics state, which can be divided into the following categories:</span></span>  
  
-   <span data-ttu-id="e5aed-110">Impostazioni di qualità</span><span class="sxs-lookup"><span data-stu-id="e5aed-110">Quality settings</span></span>  
  
-   <span data-ttu-id="e5aed-111">Trasformazioni</span><span class="sxs-lookup"><span data-stu-id="e5aed-111">Transformations</span></span>  
  
-   <span data-ttu-id="e5aed-112">Area di visualizzazione</span><span class="sxs-lookup"><span data-stu-id="e5aed-112">Clipping region</span></span>  
  
### <a name="quality-settings"></a><span data-ttu-id="e5aed-113">Impostazioni di qualità</span><span class="sxs-lookup"><span data-stu-id="e5aed-113">Quality Settings</span></span>  
 <span data-ttu-id="e5aed-114">Oggetto <xref:System.Drawing.Graphics> oggetto ha diverse proprietà che determinano la qualità degli elementi da cui vengono disegnate.</span><span class="sxs-lookup"><span data-stu-id="e5aed-114">A <xref:System.Drawing.Graphics> object has several properties that influence the quality of the items that are drawn.</span></span> <span data-ttu-id="e5aed-115">Ad esempio, è possibile impostare il <xref:System.Drawing.Graphics.TextRenderingHint%2A> proprietà per specificare il tipo di anti-aliasing (se presente) applicato al testo.</span><span class="sxs-lookup"><span data-stu-id="e5aed-115">For example, you can set the <xref:System.Drawing.Graphics.TextRenderingHint%2A> property to specify the type of antialiasing (if any) applied to text.</span></span> <span data-ttu-id="e5aed-116">Le altre proprietà che influiscono sulla qualità sono <xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.CompositingMode%2A>, <xref:System.Drawing.Graphics.CompositingQuality%2A>, e <xref:System.Drawing.Graphics.InterpolationMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="e5aed-116">Other properties that influence quality are <xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.CompositingMode%2A>, <xref:System.Drawing.Graphics.CompositingQuality%2A>, and <xref:System.Drawing.Graphics.InterpolationMode%2A>.</span></span>  
  
 <span data-ttu-id="e5aed-117">Nell'esempio seguente disegna due ellissi, una con la stessa modalità impostata su <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> e uno con la stessa modalità impostata su <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>:</span><span class="sxs-lookup"><span data-stu-id="e5aed-117">The following example draws two ellipses, one with the smoothing mode set to <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> and one with the smoothing mode set to <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>:</span></span>  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Blue)  
  
graphics.SmoothingMode = SmoothingMode.AntiAlias  
graphics.DrawEllipse(pen, 0, 0, 200, 100)  
graphics.SmoothingMode = SmoothingMode.HighSpeed  
graphics.DrawEllipse(pen, 0, 150, 200, 100)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Blue);  
  
graphics.SmoothingMode = SmoothingMode.AntiAlias;  
graphics.DrawEllipse(pen, 0, 0, 200, 100);  
graphics.SmoothingMode = SmoothingMode.HighSpeed;  
graphics.DrawEllipse(pen, 0, 150, 200, 100);  
```  
  
### <a name="transformations"></a><span data-ttu-id="e5aed-118">Trasformazioni</span><span class="sxs-lookup"><span data-stu-id="e5aed-118">Transformations</span></span>  
 <span data-ttu-id="e5aed-119">Oggetto <xref:System.Drawing.Graphics> oggetto gestisce due trasformazioni (globali e pagina) che vengono applicate a tutti gli elementi che disegnati <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="e5aed-119">A <xref:System.Drawing.Graphics> object maintains two transformations (world and page) that are applied to all items drawn by that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="e5aed-120">Qualsiasi trasformazione affine può essere archiviati nella trasformazione globale.</span><span class="sxs-lookup"><span data-stu-id="e5aed-120">Any affine transformation can be stored in the world transformation.</span></span> <span data-ttu-id="e5aed-121">Trasformazioni affini includono la scalabilità, ruotare, riflettere, inclinazione e la conversione.</span><span class="sxs-lookup"><span data-stu-id="e5aed-121">Affine transformations include scaling, rotating, reflecting, skewing, and translating.</span></span> <span data-ttu-id="e5aed-122">La trasformazione della pagina utilizzabile per la scalabilità e per la modifica di unità (ad esempio, in pixel per pollici).</span><span class="sxs-lookup"><span data-stu-id="e5aed-122">The page transformation can be used for scaling and for changing units (for example, pixels to inches).</span></span> <span data-ttu-id="e5aed-123">Per ulteriori informazioni, vedere [sistemi di Coordinate e trasformazioni](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="e5aed-123">For more information, see [Coordinate Systems and Transformations](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md).</span></span>  
  
 <span data-ttu-id="e5aed-124">Nell'esempio seguente imposta le trasformazioni globali e di pagina di un <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="e5aed-124">The following example sets the world and page transformations of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="e5aed-125">La trasformazione globale è impostata su una rotazione di 30 gradi.</span><span class="sxs-lookup"><span data-stu-id="e5aed-125">The world transformation is set to a 30-degree rotation.</span></span> <span data-ttu-id="e5aed-126">La trasformazione di pagina viene impostata in modo che le coordinate passate al secondo <xref:System.Drawing.Graphics.DrawEllipse%2A> verrà considerato come millimetri anziché pixel.</span><span class="sxs-lookup"><span data-stu-id="e5aed-126">The page transformation is set so that the coordinates passed to the second <xref:System.Drawing.Graphics.DrawEllipse%2A> will be treated as millimeters instead of pixels.</span></span> <span data-ttu-id="e5aed-127">Il codice richiama due identici per il <xref:System.Drawing.Graphics.DrawEllipse%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="e5aed-127">The code makes two identical calls to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method.</span></span> <span data-ttu-id="e5aed-128">La trasformazione globale viene applicata al primo <xref:System.Drawing.Graphics.DrawEllipse%2A> chiamata ed entrambe le trasformazioni, world e pagina, vengono applicate al secondo <xref:System.Drawing.Graphics.DrawEllipse%2A> chiamare.</span><span class="sxs-lookup"><span data-stu-id="e5aed-128">The world transformation is applied to the first <xref:System.Drawing.Graphics.DrawEllipse%2A> call, and both transformations (world and page) are applied to the second <xref:System.Drawing.Graphics.DrawEllipse%2A> call.</span></span>  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Red)  
  
graphics.ResetTransform()  
graphics.RotateTransform(30) ' world transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50)  
graphics.PageUnit = GraphicsUnit.Millimeter ' page transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Red);   
  
graphics.ResetTransform();  
graphics.RotateTransform(30);                    // world transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50);  
graphics.PageUnit = GraphicsUnit.Millimeter;     // page transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50);  
```  
  
 <span data-ttu-id="e5aed-129">Nella figura seguente mostra due ellissi.</span><span class="sxs-lookup"><span data-stu-id="e5aed-129">The following illustration shows the two ellipses.</span></span> <span data-ttu-id="e5aed-130">Si noti che il 30 gradi di rotazione intorno all'origine del sistema di coordinate (angolo superiore sinistro dell'area client), non rispetto al centro dei puntini di sospensione.</span><span class="sxs-lookup"><span data-stu-id="e5aed-130">Note that the 30-degree rotation is about the origin of the coordinate system (upper-left corner of the client area), not about the centers of the ellipses.</span></span> <span data-ttu-id="e5aed-131">Si noti inoltre che la larghezza della penna di 1 significa 1 pixel per la prima ellisse e 1 millimetro della seconda ellisse.</span><span class="sxs-lookup"><span data-stu-id="e5aed-131">Also note that the pen width of 1 means 1 pixel for the first ellipse and 1 millimeter for the second ellipse.</span></span>  
  
 <span data-ttu-id="e5aed-132">![Ovali](../../../../docs/framework/winforms/advanced/media/csgraphicsascon1.png "csgraphicsascon1")</span><span class="sxs-lookup"><span data-stu-id="e5aed-132">![Ovals](../../../../docs/framework/winforms/advanced/media/csgraphicsascon1.png "csgraphicsascon1")</span></span>  
  
### <a name="clipping-region"></a><span data-ttu-id="e5aed-133">Area di visualizzazione</span><span class="sxs-lookup"><span data-stu-id="e5aed-133">Clipping Region</span></span>  
 <span data-ttu-id="e5aed-134">Oggetto <xref:System.Drawing.Graphics> oggetto mantiene un'area di visualizzazione che si applica a tutti gli elementi che disegnati <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="e5aed-134">A <xref:System.Drawing.Graphics> object maintains a clipping region that applies to all items drawn by that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="e5aed-135">È possibile impostare l'area di visualizzazione chiamando il <xref:System.Drawing.Graphics.SetClip%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="e5aed-135">You can set the clipping region by calling the <xref:System.Drawing.Graphics.SetClip%2A> method.</span></span>  
  
 <span data-ttu-id="e5aed-136">L'esempio seguente crea un'area a forma di segno più tramite l'unione di due rettangoli.</span><span class="sxs-lookup"><span data-stu-id="e5aed-136">The following example creates a plus-shaped region by forming the union of two rectangles.</span></span> <span data-ttu-id="e5aed-137">Tale area è designata come area di visualizzazione di un <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="e5aed-137">That region is designated as the clipping region of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="e5aed-138">Il codice crea quindi due righe che sono limitate all'interno dell'area di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="e5aed-138">Then the code draws two lines that are restricted to the interior of the clipping region.</span></span>  
  
```vb  
Dim graphics As Graphics = e.Graphics  
  
' Opaque red, width 5  
Dim pen As New Pen(Color.Red, 5)  
  
' Opaque aqua  
Dim brush As New SolidBrush(Color.FromArgb(255, 180, 255, 255))  
  
' Create a plus-shaped region by forming the union of two rectangles.  
Dim [region] As New [Region](New Rectangle(50, 0, 50, 150))  
[region].Union(New Rectangle(0, 50, 150, 50))  
graphics.FillRegion(brush, [region])  
  
' Set the clipping region.  
graphics.SetClip([region], CombineMode.Replace)  
  
' Draw two clipped lines.  
graphics.DrawLine(pen, 0, 30, 150, 160)  
graphics.DrawLine(pen, 40, 20, 190, 150)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
  
// Opaque red, width 5  
Pen pen = new Pen(Color.Red, 5);    
  
// Opaque aqua  
SolidBrush brush = new SolidBrush(Color.FromArgb(255, 180, 255, 255));    
  
// Create a plus-shaped region by forming the union of two rectangles.  
Region region = new Region(new Rectangle(50, 0, 50, 150));  
region.Union(new Rectangle(0, 50, 150, 50));  
graphics.FillRegion(brush, region);  
  
// Set the clipping region.  
graphics.SetClip(region, CombineMode.Replace);  
  
// Draw two clipped lines.  
graphics.DrawLine(pen, 0, 30, 150, 160);  
graphics.DrawLine(pen, 40, 20, 190, 150);  
```  
  
 <span data-ttu-id="e5aed-139">Nella figura seguente mostra le righe ritagliate.</span><span class="sxs-lookup"><span data-stu-id="e5aed-139">The following illustration shows the clipped lines.</span></span>  
  
 <span data-ttu-id="e5aed-140">![Area di ritaglio limitata](../../../../docs/framework/winforms/advanced/media/graphicsascon2.png "graphicsascon2")</span><span class="sxs-lookup"><span data-stu-id="e5aed-140">![Limited Clip Region](../../../../docs/framework/winforms/advanced/media/graphicsascon2.png "graphicsascon2")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5aed-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5aed-141">See Also</span></span>  
 [<span data-ttu-id="e5aed-142">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="e5aed-142">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="e5aed-143">Uso di contenitori di grafica annidati</span><span class="sxs-lookup"><span data-stu-id="e5aed-143">Using Nested Graphics Containers</span></span>](../../../../docs/framework/winforms/advanced/using-nested-graphics-containers.md)
