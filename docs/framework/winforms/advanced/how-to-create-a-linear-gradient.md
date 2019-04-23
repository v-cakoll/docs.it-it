---
title: 'Procedura: Creare una sfumatura lineare'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- linear gradients [Windows Forms], creating
- gradients [Windows Forms], creating linear
- colors [Windows Forms], creating linear gradients
- gradients
ms.assetid: 6c88e1cc-1217-4399-ac12-cb37592b9f01
ms.openlocfilehash: b836659821b54698b675d48acd4e46466001d654
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2019
ms.locfileid: "59977275"
---
# <a name="how-to-create-a-linear-gradient"></a><span data-ttu-id="0c24c-102">Procedura: Creare una sfumatura lineare</span><span class="sxs-lookup"><span data-stu-id="0c24c-102">How to: Create a Linear Gradient</span></span>
<span data-ttu-id="0c24c-103">GDI+ fornisce orizzontali, verticali e diagonali sfumature lineari.</span><span class="sxs-lookup"><span data-stu-id="0c24c-103">GDI+ provides horizontal, vertical, and diagonal linear gradients.</span></span> <span data-ttu-id="0c24c-104">Per impostazione predefinita, il colore in una sfumatura lineare viene modificato in modo uniforme.</span><span class="sxs-lookup"><span data-stu-id="0c24c-104">By default, the color in a linear gradient changes uniformly.</span></span> <span data-ttu-id="0c24c-105">Tuttavia, è possibile personalizzare una sfumatura lineare in modo che il colore viene modificato in modo non uniforme.</span><span class="sxs-lookup"><span data-stu-id="0c24c-105">However, you can customize a linear gradient so that the color changes in a non-uniform fashion.</span></span>  

> [!NOTE]
> <span data-ttu-id="0c24c-106">Gli esempi in questo articolo sono i metodi chiamati da un controllo <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="0c24c-106">The examples in this article are methods that are called from a control's <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  

<span data-ttu-id="0c24c-107">Nell'esempio seguente inserisce una riga, un'ellisse e un rettangolo con un pennello sfumatura lineare orizzontale.</span><span class="sxs-lookup"><span data-stu-id="0c24c-107">The following example fills a line, an ellipse, and a rectangle with a horizontal linear gradient brush.</span></span>  
  
<span data-ttu-id="0c24c-108">Il <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> costruttore riceve quattro argomenti: due punti e due colori.</span><span class="sxs-lookup"><span data-stu-id="0c24c-108">The <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> constructor receives four arguments: two points and two colors.</span></span> <span data-ttu-id="0c24c-109">Il primo punto (0, 10) è associato il primo colore (rosso) e il secondo punto (200, 10) è associato il secondo colore (blu).</span><span class="sxs-lookup"><span data-stu-id="0c24c-109">The first point (0, 10) is associated with the first color (red), and the second point (200, 10) is associated with the second color (blue).</span></span> <span data-ttu-id="0c24c-110">Come si può immaginare, la riga disegnata dal punto (0, 10) a (200, 10) cambia gradualmente da rosso a blu.</span><span class="sxs-lookup"><span data-stu-id="0c24c-110">As you would expect, the line drawn from (0, 10) to (200, 10) changes gradually from red to blue.</span></span>  
  
 <span data-ttu-id="0c24c-111">Il numero 10 in quanto (0, 10) e (200, 10) non sono importanti.</span><span class="sxs-lookup"><span data-stu-id="0c24c-111">The 10s in the points (0, 10) and (200, 10) are not important.</span></span> <span data-ttu-id="0c24c-112">È importante che i due punti abbiano la stessa coordinata secondo, ovvero la linea di connessione è orizzontale.</span><span class="sxs-lookup"><span data-stu-id="0c24c-112">What is important is that the two points have the same second coordinate — the line connecting them is horizontal.</span></span> <span data-ttu-id="0c24c-113">I puntini di sospensione e il rettangolo inoltre modificare gradualmente da rosso a blu come la coordinata orizzontale va da 0 a 200.</span><span class="sxs-lookup"><span data-stu-id="0c24c-113">The ellipse and the rectangle also change gradually from red to blue as the horizontal coordinate goes from 0 to 200.</span></span>  
  
 <span data-ttu-id="0c24c-114">La figura seguente mostra la riga, i puntini di sospensione e il rettangolo.</span><span class="sxs-lookup"><span data-stu-id="0c24c-114">The following illustration shows the line, the ellipse, and the rectangle.</span></span> <span data-ttu-id="0c24c-115">Si noti che la sfumatura di colore viene ripetuto man mano che aumenta la coordinata orizzontale a oltre 200.</span><span class="sxs-lookup"><span data-stu-id="0c24c-115">Note that the color gradient repeats itself as the horizontal coordinate increases beyond 200.</span></span>  
  
 <span data-ttu-id="0c24c-116">![Sfumatura lineare](./media/cslineargradient1.png "cslineargradient1")</span><span class="sxs-lookup"><span data-stu-id="0c24c-116">![Linear Gradient](./media/cslineargradient1.png "cslineargradient1")</span></span>  
  
### <a name="to-use-horizontal-linear-gradients"></a><span data-ttu-id="0c24c-117">Per utilizzare sfumature lineari orizzontali</span><span class="sxs-lookup"><span data-stu-id="0c24c-117">To use horizontal linear gradients</span></span>  
  
-   <span data-ttu-id="0c24c-118">Passare blu rosso ed è opaco opaco come il terzo e quarto argomento, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="0c24c-118">Pass in the opaque red and opaque blue as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#21)]
     [!code-vb[System.Drawing.UsingaGradientBrush#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#21)]  
  
 <span data-ttu-id="0c24c-119">Nell'esempio precedente, i componenti di colore modificare in modo lineare come si spostano da una coordinata orizzontale pari a 0 a una coordinata orizzontale pari a 200.</span><span class="sxs-lookup"><span data-stu-id="0c24c-119">In the preceding example, the color components change linearly as you move from a horizontal coordinate of 0 to a horizontal coordinate of 200.</span></span> <span data-ttu-id="0c24c-120">Ad esempio, un punto di cui prima coordinata è compreso tra 0 e 200 avrà un componente blu che è compreso tra 0 e 255.</span><span class="sxs-lookup"><span data-stu-id="0c24c-120">For example, a point whose first coordinate is halfway between 0 and 200 will have a blue component that is halfway between 0 and 255.</span></span>  
  
 <span data-ttu-id="0c24c-121">GDI + consente di regolare la modalità di che un colore varia da un bordo di una sfumatura a altro.</span><span class="sxs-lookup"><span data-stu-id="0c24c-121">GDI+ allows you to adjust the way a color varies from one edge of a gradient to the other.</span></span> <span data-ttu-id="0c24c-122">Si supponga di che voler creare un pennello a sfumatura che le modifiche apportate dal nero al rosso in base alla tabella riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="0c24c-122">Suppose you want to create a gradient brush that changes from black to red according to the following table.</span></span>  
  
|<span data-ttu-id="0c24c-123">Coordinata orizzontale</span><span class="sxs-lookup"><span data-stu-id="0c24c-123">Horizontal coordinate</span></span>|<span data-ttu-id="0c24c-124">Componenti RGB</span><span class="sxs-lookup"><span data-stu-id="0c24c-124">RGB components</span></span>|  
|---------------------------|--------------------|  
|<span data-ttu-id="0c24c-125">0</span><span class="sxs-lookup"><span data-stu-id="0c24c-125">0</span></span>|<span data-ttu-id="0c24c-126">(0, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="0c24c-126">(0, 0, 0)</span></span>|  
|<span data-ttu-id="0c24c-127">40</span><span class="sxs-lookup"><span data-stu-id="0c24c-127">40</span></span>|<span data-ttu-id="0c24c-128">(128, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="0c24c-128">(128, 0, 0)</span></span>|  
|<span data-ttu-id="0c24c-129">200</span><span class="sxs-lookup"><span data-stu-id="0c24c-129">200</span></span>|<span data-ttu-id="0c24c-130">(255, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="0c24c-130">(255, 0, 0)</span></span>|  
  
 <span data-ttu-id="0c24c-131">Si noti che il componente rossa intensità media quando la coordinata orizzontale corrisponde solo il 20% del modo in cui da 0 a 200.</span><span class="sxs-lookup"><span data-stu-id="0c24c-131">Note that the red component is at half intensity when the horizontal coordinate is only 20 percent of the way from 0 to 200.</span></span>  
  
 <span data-ttu-id="0c24c-132">L'esempio seguente imposta il <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A?displayProperty=nameWithType> proprietà da associare tre intensità relative tre posizioni relative.</span><span class="sxs-lookup"><span data-stu-id="0c24c-132">The following example sets the <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A?displayProperty=nameWithType> property to associate three relative intensities with three relative positions.</span></span> <span data-ttu-id="0c24c-133">Come indicato nella tabella precedente, è associata a una posizione relativa di 0.2 un'intensità di 0,5.</span><span class="sxs-lookup"><span data-stu-id="0c24c-133">As in the preceding table, a relative intensity of 0.5 is associated with a relative position of 0.2.</span></span> <span data-ttu-id="0c24c-134">Il codice viene compilato un rettangolo con il pennello a sfumatura e un'ellisse.</span><span class="sxs-lookup"><span data-stu-id="0c24c-134">The code fills an ellipse and a rectangle with the gradient brush.</span></span>  
  
 <span data-ttu-id="0c24c-135">La figura seguente mostra l'ellisse risultante e il rettangolo.</span><span class="sxs-lookup"><span data-stu-id="0c24c-135">The following illustration shows the resulting ellipse and rectangle.</span></span>  
  
 <span data-ttu-id="0c24c-136">![Sfumatura lineare](./media/cslineargradient2.png "cslineargradient2")</span><span class="sxs-lookup"><span data-stu-id="0c24c-136">![Linear Gradient](./media/cslineargradient2.png "cslineargradient2")</span></span>  

### <a name="to-customize-linear-gradients"></a><span data-ttu-id="0c24c-137">Per personalizzare le sfumature lineari</span><span class="sxs-lookup"><span data-stu-id="0c24c-137">To customize linear gradients</span></span>  
  
-   <span data-ttu-id="0c24c-138">Passare il rosso opaco e nero opaco come il terzo e quarto argomento, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="0c24c-138">Pass in the opaque black and opaque red as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#22)]
     [!code-vb[System.Drawing.UsingaGradientBrush#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#22)]  
  
 <span data-ttu-id="0c24c-139">Le sfumature negli esempi precedenti sono state orizzontale; vale a dire il colore cambia gradualmente quando si sposta lungo una linea orizzontale.</span><span class="sxs-lookup"><span data-stu-id="0c24c-139">The gradients in the preceding examples have been horizontal; that is, the color changes gradually as you move along any horizontal line.</span></span> <span data-ttu-id="0c24c-140">È anche possibile definire le sfumature verticali e diagonali.</span><span class="sxs-lookup"><span data-stu-id="0c24c-140">You can also define vertical gradients and diagonal gradients.</span></span>  
  
 <span data-ttu-id="0c24c-141">L'esempio seguente passa i punti (0, 0) e (200, 100) per un <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> costruttore.</span><span class="sxs-lookup"><span data-stu-id="0c24c-141">The following example passes the points (0, 0) and (200, 100) to a <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> constructor.</span></span> <span data-ttu-id="0c24c-142">È associato il colore blu (0, 0), ed è associato il colore verde (200, 100).</span><span class="sxs-lookup"><span data-stu-id="0c24c-142">The color blue is associated with (0, 0), and the color green is associated with (200, 100).</span></span> <span data-ttu-id="0c24c-143">Una riga (con la larghezza della penna 10) e un elemento ellipse vengono riempiti con il pennello sfumato lineare.</span><span class="sxs-lookup"><span data-stu-id="0c24c-143">A line (with pen width 10) and an ellipse are filled with the linear gradient brush.</span></span>  
  
 <span data-ttu-id="0c24c-144">La figura seguente mostra la riga e l'ellisse.</span><span class="sxs-lookup"><span data-stu-id="0c24c-144">The following illustration shows the line and the ellipse.</span></span> <span data-ttu-id="0c24c-145">Si noti che il colore in ellisse cambia gradualmente quando si sposta lungo una riga che sono parallelo a quella che passa attraverso (0, 0) e (200, 100).</span><span class="sxs-lookup"><span data-stu-id="0c24c-145">Note that the color in the ellipse changes gradually as you move along any line that is parallel to the line passing through (0, 0) and (200, 100).</span></span>  
  
 <span data-ttu-id="0c24c-146">![Sfumatura lineare](./media/cslineargradient3.png "cslineargradient3")</span><span class="sxs-lookup"><span data-stu-id="0c24c-146">![Linear Gradient](./media/cslineargradient3.png "cslineargradient3")</span></span>  
  
### <a name="to-create-diagonal-linear-gradients"></a><span data-ttu-id="0c24c-147">Per creare diagonale sfumature lineari</span><span class="sxs-lookup"><span data-stu-id="0c24c-147">To create diagonal linear gradients</span></span>  
  
-   <span data-ttu-id="0c24c-148">Passare l'opaco blu e verde opaco come il terzo e quarto argomento, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="0c24c-148">Pass in the opaque blue and opaque green as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#23)]
     [!code-vb[System.Drawing.UsingaGradientBrush#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="0c24c-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c24c-149">See also</span></span>

- [<span data-ttu-id="0c24c-150">Uso di un pennello a sfumatura per il riempimento di forme</span><span class="sxs-lookup"><span data-stu-id="0c24c-150">Using a Gradient Brush to Fill Shapes</span></span>](using-a-gradient-brush-to-fill-shapes.md)
- [<span data-ttu-id="0c24c-151">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="0c24c-151">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
