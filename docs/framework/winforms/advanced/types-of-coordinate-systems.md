---
title: Tipi di sistemi di coordinate
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], page
- unit of measure
- world coordinate system
- page coordinate system
- page transformation
- device coordinate system
- world transformation
- coordinate systems
- transformations [Windows Forms], world
ms.assetid: c61ff50a-eb1d-4e6c-83cd-f7e9764cfa9f
ms.openlocfilehash: 23d9374f1f46c4480079eb4ad5269a197a13a5bf
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963882"
---
# <a name="types-of-coordinate-systems"></a><span data-ttu-id="bd599-102">Tipi di sistemi di coordinate</span><span class="sxs-lookup"><span data-stu-id="bd599-102">Types of Coordinate Systems</span></span>
<span data-ttu-id="bd599-103">GDI+ utilizza tre spazi delle coordinate: mondo, pagina e dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bd599-103">GDI+ uses three coordinate spaces: world, page, and device.</span></span> <span data-ttu-id="bd599-104">Le coordinate globali sono le coordinate usate per modellare un particolare ambiente grafico e sono le coordinate passate ai metodi nel .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bd599-104">World coordinates are the coordinates used to model a particular graphic world and are the coordinates you pass to methods in the .NET Framework.</span></span> <span data-ttu-id="bd599-105">Le coordinate della pagina fanno riferimento al sistema di coordinate utilizzato da una superficie di disegno, ad esempio un form o un controllo.</span><span class="sxs-lookup"><span data-stu-id="bd599-105">Page coordinates refer to the coordinate system used by a drawing surface, such as a form or control.</span></span> <span data-ttu-id="bd599-106">Le coordinate del dispositivo sono le coordinate usate dal dispositivo fisico disegnato, ad esempio uno schermo o un foglio di carta.</span><span class="sxs-lookup"><span data-stu-id="bd599-106">Device coordinates are the coordinates used by the physical device being drawn on, such as a screen or sheet of paper.</span></span> <span data-ttu-id="bd599-107">Quando si effettua la chiamata `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, i punti passati <xref:System.Drawing.Graphics.DrawLine%2A> al metodo`(0, 0)` , e `(160, 80)`, si trovano nello spazio delle coordinate internazionali.</span><span class="sxs-lookup"><span data-stu-id="bd599-107">When you make the call `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, the points that you pass to the <xref:System.Drawing.Graphics.DrawLine%2A> method—`(0, 0)` and `(160, 80)`—are in the world coordinate space.</span></span> <span data-ttu-id="bd599-108">Prima che GDI+ possa creare la riga sullo schermo, le coordinate passano attraverso una sequenza di trasformazioni.</span><span class="sxs-lookup"><span data-stu-id="bd599-108">Before GDI+ can draw the line on the screen, the coordinates pass through a sequence of transformations.</span></span> <span data-ttu-id="bd599-109">Una trasformazione, denominata trasformazione globale, converte le coordinate internazionali in coordinate di pagina e un'altra trasformazione, denominata trasformazione pagina, converte le coordinate della pagina in coordinate del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bd599-109">One transformation, called the world transformation, converts world coordinates to page coordinates, and another transformation, called the page transformation, converts page coordinates to device coordinates.</span></span>  
  
## <a name="transforms-and-coordinate-systems"></a><span data-ttu-id="bd599-110">Trasformazioni e sistemi di coordinate</span><span class="sxs-lookup"><span data-stu-id="bd599-110">Transforms and Coordinate Systems</span></span>  
 <span data-ttu-id="bd599-111">Si supponga di voler usare un sistema di coordinate con la relativa origine nel corpo dell'area client anziché nell'angolo superiore sinistro.</span><span class="sxs-lookup"><span data-stu-id="bd599-111">Suppose you want to work with a coordinate system that has its origin in the body of the client area rather than the upper-left corner.</span></span> <span data-ttu-id="bd599-112">Supponiamo, ad esempio, che si desideri che l'origine sia 100 pixel dal bordo sinistro dell'area client e 50 pixel dalla parte superiore dell'area client.</span><span class="sxs-lookup"><span data-stu-id="bd599-112">Say, for example, that you want the origin to be 100 pixels from the left edge of the client area and 50 pixels from the top of the client area.</span></span> <span data-ttu-id="bd599-113">Nella figura seguente viene illustrato un sistema di coordinate di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="bd599-113">The following illustration shows such a coordinate system.</span></span>  
  
 <span data-ttu-id="bd599-114">![Sistema di coordinate](./media/aboutgdip05-art01.gif "AboutGdip05_art01")</span><span class="sxs-lookup"><span data-stu-id="bd599-114">![Coordinate System](./media/aboutgdip05-art01.gif "AboutGdip05_art01")</span></span>  
  
 <span data-ttu-id="bd599-115">Quando si effettua la chiamata `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, si ottiene la riga illustrata nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="bd599-115">When you make the call `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, you get the line shown in the following illustration.</span></span>  
  
 <span data-ttu-id="bd599-116">![Sistema di coordinate](./media/aboutgdip05-art02.gif "AboutGdip05_art02")</span><span class="sxs-lookup"><span data-stu-id="bd599-116">![Coordinate System](./media/aboutgdip05-art02.gif "AboutGdip05_art02")</span></span>  
  
 <span data-ttu-id="bd599-117">Le coordinate degli endpoint della linea nei tre spazi delle coordinate sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="bd599-117">The coordinates of the endpoints of your line in the three coordinate spaces are as follows:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bd599-118">Mondo</span><span class="sxs-lookup"><span data-stu-id="bd599-118">World</span></span>|<span data-ttu-id="bd599-119">(0, 0) a (160, 80)</span><span class="sxs-lookup"><span data-stu-id="bd599-119">(0, 0) to (160, 80)</span></span>|  
|<span data-ttu-id="bd599-120">Pagina</span><span class="sxs-lookup"><span data-stu-id="bd599-120">Page</span></span>|<span data-ttu-id="bd599-121">(100, 50) a (260, 130)</span><span class="sxs-lookup"><span data-stu-id="bd599-121">(100, 50) to (260, 130)</span></span>|  
|<span data-ttu-id="bd599-122">Dispositivo</span><span class="sxs-lookup"><span data-stu-id="bd599-122">Device</span></span>|<span data-ttu-id="bd599-123">(100, 50) a (260, 130)</span><span class="sxs-lookup"><span data-stu-id="bd599-123">(100, 50) to (260, 130)</span></span>|  
  
 <span data-ttu-id="bd599-124">Si noti che lo spazio delle coordinate della pagina ha origine nell'angolo superiore sinistro dell'area client. Questo sarà sempre il caso.</span><span class="sxs-lookup"><span data-stu-id="bd599-124">Note that the page coordinate space has its origin at the upper-left corner of the client area; this will always be the case.</span></span> <span data-ttu-id="bd599-125">Si noti inoltre che, poiché l'unità di misura è il pixel, le coordinate del dispositivo corrispondono alle coordinate della pagina.</span><span class="sxs-lookup"><span data-stu-id="bd599-125">Also note that because the unit of measure is the pixel, the device coordinates are the same as the page coordinates.</span></span> <span data-ttu-id="bd599-126">Se si imposta l'unità di misura su un valore diverso da pixel (ad esempio, pollici), le coordinate del dispositivo saranno diverse dalle coordinate della pagina.</span><span class="sxs-lookup"><span data-stu-id="bd599-126">If you set the unit of measure to something other than pixels (for example, inches), then the device coordinates will be different from the page coordinates.</span></span>  
  
 <span data-ttu-id="bd599-127">La trasformazione globale, che esegue il mapping delle coordinate internazionali alle coordinate di pagina, <xref:System.Drawing.Graphics.Transform%2A> viene mantenuta <xref:System.Drawing.Graphics> nella proprietà della classe.</span><span class="sxs-lookup"><span data-stu-id="bd599-127">The world transformation, which maps world coordinates to page coordinates, is held in the <xref:System.Drawing.Graphics.Transform%2A> property of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="bd599-128">Nell'esempio precedente la trasformazione globale è una conversione di unità 100 nella direzione x e 50 unità nella direzione y.</span><span class="sxs-lookup"><span data-stu-id="bd599-128">In the preceding example, the world transformation is a translation 100 units in the x direction and 50 units in the y direction.</span></span> <span data-ttu-id="bd599-129">Nell'esempio seguente viene impostata la trasformazione globale di <xref:System.Drawing.Graphics> un oggetto e quindi viene <xref:System.Drawing.Graphics> utilizzato tale oggetto per creare la riga illustrata nella figura precedente:</span><span class="sxs-lookup"><span data-stu-id="bd599-129">The following example sets the world transformation of a <xref:System.Drawing.Graphics> object and then uses that <xref:System.Drawing.Graphics> object to draw the line shown in the preceding figure:</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.CoordinateSystems#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#31)]  
  
 <span data-ttu-id="bd599-130">La trasformazione pagina mappa le coordinate della pagina alle coordinate del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bd599-130">The page transformation maps page coordinates to device coordinates.</span></span> <span data-ttu-id="bd599-131">La <xref:System.Drawing.Graphics> classe fornisce le <xref:System.Drawing.Graphics.PageUnit%2A> proprietà <xref:System.Drawing.Graphics.PageScale%2A> e per la modifica della trasformazione pagina.</span><span class="sxs-lookup"><span data-stu-id="bd599-131">The <xref:System.Drawing.Graphics> class provides the <xref:System.Drawing.Graphics.PageUnit%2A> and <xref:System.Drawing.Graphics.PageScale%2A> properties for manipulating the page transformation.</span></span> <span data-ttu-id="bd599-132">La <xref:System.Drawing.Graphics> classe fornisce inoltre due <xref:System.Drawing.Graphics.DpiX%2A> proprietà di sola lettura e <xref:System.Drawing.Graphics.DpiY%2A>, per esaminare i punti orizzontali e verticali per pollice del dispositivo di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="bd599-132">The <xref:System.Drawing.Graphics> class also provides two read-only properties, <xref:System.Drawing.Graphics.DpiX%2A> and <xref:System.Drawing.Graphics.DpiY%2A>, for examining the horizontal and vertical dots per inch of the display device.</span></span>  
  
 <span data-ttu-id="bd599-133">È possibile utilizzare la <xref:System.Drawing.Graphics.PageUnit%2A> proprietà <xref:System.Drawing.Graphics> della classe per specificare un'unità di misura diversa dal pixel.</span><span class="sxs-lookup"><span data-stu-id="bd599-133">You can use the <xref:System.Drawing.Graphics.PageUnit%2A> property of the <xref:System.Drawing.Graphics> class to specify a unit of measure other than the pixel.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bd599-134">Non è possibile impostare <xref:System.Drawing.Graphics.PageUnit%2A> la proprietà <xref:System.Drawing.GraphicsUnit.World>su, perché non si tratta di un'unità fisica e genererà un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="bd599-134">You cannot set the <xref:System.Drawing.Graphics.PageUnit%2A> property to <xref:System.Drawing.GraphicsUnit.World>, as this is not a physical unit and will cause an exception.</span></span>  
  
 <span data-ttu-id="bd599-135">Nell'esempio seguente viene disegnata una riga da (0,0) a (2, 1), in cui il punto (2, 1) è di 2 centimetri a destra e 1 pollice verso il basso dal punto (0,0):</span><span class="sxs-lookup"><span data-stu-id="bd599-135">The following example draws a line from (0, 0) to (2, 1), where the point (2, 1) is 2 inches to the right and 1 inch down from the point (0, 0):</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.CoordinateSystems#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#32)]  
  
> [!NOTE]
> <span data-ttu-id="bd599-136">Se non si specifica una larghezza della penna quando si costruisce la penna, nell'esempio precedente verrà disegnato un valore di una linea di un pollice.</span><span class="sxs-lookup"><span data-stu-id="bd599-136">If you don't specify a pen width when you construct your pen, the preceding example will draw a line that is one inch wide.</span></span> <span data-ttu-id="bd599-137">È possibile specificare la larghezza della penna nel secondo argomento per il <xref:System.Drawing.Pen> Costruttore:</span><span class="sxs-lookup"><span data-stu-id="bd599-137">You can specify the pen width in the second argument to the <xref:System.Drawing.Pen> constructor:</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#33](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#33)]
 [!code-vb[System.Drawing.CoordinateSystems#33](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#33)]  
  
 <span data-ttu-id="bd599-138">Se si presuppone che il dispositivo di visualizzazione includa 96 punti per pollice nella direzione orizzontale e 96 punti per pollice nella direzione verticale, gli endpoint della riga nell'esempio precedente hanno le coordinate seguenti nei tre spazi delle coordinate:</span><span class="sxs-lookup"><span data-stu-id="bd599-138">If we assume that the display device has 96 dots per inch in the horizontal direction and 96 dots per inch in the vertical direction, the endpoints of the line in the preceding example have the following coordinates in the three coordinate spaces:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bd599-139">Mondo</span><span class="sxs-lookup"><span data-stu-id="bd599-139">World</span></span>|<span data-ttu-id="bd599-140">(0, 0) in (2, 1)</span><span class="sxs-lookup"><span data-stu-id="bd599-140">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="bd599-141">Pagina</span><span class="sxs-lookup"><span data-stu-id="bd599-141">Page</span></span>|<span data-ttu-id="bd599-142">(0, 0) in (2, 1)</span><span class="sxs-lookup"><span data-stu-id="bd599-142">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="bd599-143">Dispositivo</span><span class="sxs-lookup"><span data-stu-id="bd599-143">Device</span></span>|<span data-ttu-id="bd599-144">(0, 0, a (192, 96)</span><span class="sxs-lookup"><span data-stu-id="bd599-144">(0, 0, to (192, 96)</span></span>|  
  
 <span data-ttu-id="bd599-145">Si noti che poiché l'origine dello spazio delle coordinate globali si trova nell'angolo superiore sinistro dell'area client, le coordinate della pagina sono le stesse delle coordinate internazionali.</span><span class="sxs-lookup"><span data-stu-id="bd599-145">Note that because the origin of the world coordinate space is at the upper-left corner of the client area, the page coordinates are the same as the world coordinates.</span></span>  
  
 <span data-ttu-id="bd599-146">È possibile combinare le trasformazioni del mondo e della pagina per ottenere una varietà di effetti.</span><span class="sxs-lookup"><span data-stu-id="bd599-146">You can combine the world and page transformations to achieve a variety of effects.</span></span> <span data-ttu-id="bd599-147">Si supponga, ad esempio, di voler usare i pollici come unità di misura e che l'origine del sistema di coordinate sia 2 centimetri dal bordo sinistro dell'area client e 1/2 di pollice dalla parte superiore dell'area client.</span><span class="sxs-lookup"><span data-stu-id="bd599-147">For example, suppose you want to use inches as the unit of measure and you want the origin of your coordinate system to be 2 inches from the left edge of the client area and 1/2 inch from the top of the client area.</span></span> <span data-ttu-id="bd599-148">Nell'esempio seguente vengono impostate le trasformazioni globali e di pagina <xref:System.Drawing.Graphics> di un oggetto, quindi viene disegnata una linea da (0,0) a (2, 1):</span><span class="sxs-lookup"><span data-stu-id="bd599-148">The following example sets the world and page transformations of a <xref:System.Drawing.Graphics> object and then draws a line from (0, 0) to (2, 1):</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#34](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.CoordinateSystems#34](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#34)]  
  
 <span data-ttu-id="bd599-149">Nella figura seguente viene illustrato il sistema di coordinate e linee.</span><span class="sxs-lookup"><span data-stu-id="bd599-149">The following illustration shows the line and coordinate system.</span></span>  
  
 <span data-ttu-id="bd599-150">![Sistema di coordinate](./media/aboutgdip05-art03.gif "AboutGdip05_art03")</span><span class="sxs-lookup"><span data-stu-id="bd599-150">![Coordinate System](./media/aboutgdip05-art03.gif "AboutGdip05_art03")</span></span>  
  
 <span data-ttu-id="bd599-151">Se si presuppone che il dispositivo di visualizzazione includa 96 punti per pollice nella direzione orizzontale e 96 punti per pollice nella direzione verticale, gli endpoint della riga nell'esempio precedente hanno le coordinate seguenti nei tre spazi delle coordinate:</span><span class="sxs-lookup"><span data-stu-id="bd599-151">If we assume that the display device has 96 dots per inch in the horizontal direction and 96 dots per inch in the vertical direction, the endpoints of the line in the preceding example have the following coordinates in the three coordinate spaces:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bd599-152">Mondo</span><span class="sxs-lookup"><span data-stu-id="bd599-152">World</span></span>|<span data-ttu-id="bd599-153">(0, 0) in (2, 1)</span><span class="sxs-lookup"><span data-stu-id="bd599-153">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="bd599-154">Pagina</span><span class="sxs-lookup"><span data-stu-id="bd599-154">Page</span></span>|<span data-ttu-id="bd599-155">(da 2 a 0,5) a (4, 1,5)</span><span class="sxs-lookup"><span data-stu-id="bd599-155">(2, 0.5) to (4, 1.5)</span></span>|  
|<span data-ttu-id="bd599-156">Dispositivo</span><span class="sxs-lookup"><span data-stu-id="bd599-156">Device</span></span>|<span data-ttu-id="bd599-157">(192, 48) a (384, 144)</span><span class="sxs-lookup"><span data-stu-id="bd599-157">(192, 48) to (384, 144)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bd599-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd599-158">See also</span></span>

- [<span data-ttu-id="bd599-159">Sistemi di coordinate e trasformazioni</span><span class="sxs-lookup"><span data-stu-id="bd599-159">Coordinate Systems and Transformations</span></span>](coordinate-systems-and-transformations.md)
- [<span data-ttu-id="bd599-160">Rappresentazione tramite matrici delle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="bd599-160">Matrix Representation of Transformations</span></span>](matrix-representation-of-transformations.md)
