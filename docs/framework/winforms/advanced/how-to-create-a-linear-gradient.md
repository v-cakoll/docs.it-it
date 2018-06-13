---
title: 'Procedura: creare una sfumatura lineare'
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
ms.openlocfilehash: 9eeedf1ef92bdf6e5e2724eeca5060765b0778f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522460"
---
# <a name="how-to-create-a-linear-gradient"></a><span data-ttu-id="b49da-102">Procedura: creare una sfumatura lineare</span><span class="sxs-lookup"><span data-stu-id="b49da-102">How to: Create a Linear Gradient</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="b49da-103"> fornisce orizzontali, verticali e diagonali gradienti lineari.</span><span class="sxs-lookup"><span data-stu-id="b49da-103"> provides horizontal, vertical, and diagonal linear gradients.</span></span> <span data-ttu-id="b49da-104">Per impostazione predefinita, il colore in una sfumatura lineare cambia in modo uniforme.</span><span class="sxs-lookup"><span data-stu-id="b49da-104">By default, the color in a linear gradient changes uniformly.</span></span> <span data-ttu-id="b49da-105">Tuttavia, è possibile personalizzare una sfumatura lineare in modo che il colore cambia in modo non uniformi.</span><span class="sxs-lookup"><span data-stu-id="b49da-105">However, you can customize a linear gradient so that the color changes in a non-uniform fashion.</span></span>  
  
 <span data-ttu-id="b49da-106">Nell'esempio seguente inserisce una riga di un'ellisse e un rettangolo con un pennello sfumato lineare orizzontale.</span><span class="sxs-lookup"><span data-stu-id="b49da-106">The following example fills a line, an ellipse, and a rectangle with a horizontal linear gradient brush.</span></span>  
  
 <span data-ttu-id="b49da-107">Il <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> costruttore riceve quattro argomenti: due punti e due colori.</span><span class="sxs-lookup"><span data-stu-id="b49da-107">The <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> constructor receives four arguments: two points and two colors.</span></span> <span data-ttu-id="b49da-108">Il primo punto (0, 10) è associato al primo colore (rosso) e il secondo punto (200, 10) è associato il secondo colore (blu).</span><span class="sxs-lookup"><span data-stu-id="b49da-108">The first point (0, 10) is associated with the first color (red), and the second point (200, 10) is associated with the second color (blue).</span></span> <span data-ttu-id="b49da-109">Come prevedibile, la riga disegnata da (0, 10) a (200, 10) cambia gradualmente da rosso a blu.</span><span class="sxs-lookup"><span data-stu-id="b49da-109">As you would expect, the line drawn from (0, 10) to (200, 10) changes gradually from red to blue.</span></span>  
  
 <span data-ttu-id="b49da-110">Il numero 10 punti (50, 10) e (200, 10) non sono importanti.</span><span class="sxs-lookup"><span data-stu-id="b49da-110">The 10s in the points (50, 10) and (200, 10) are not important.</span></span> <span data-ttu-id="b49da-111">L'aspetto importante è che i due punti hanno stessa coordinata secondo, ovvero la riga che li connettono è orizzontale.</span><span class="sxs-lookup"><span data-stu-id="b49da-111">What is important is that the two points have the same second coordinate — the line connecting them is horizontal.</span></span> <span data-ttu-id="b49da-112">I puntini di sospensione e il rettangolo inoltre modificare gradualmente da rosso a blu come coordinata orizzontale va da 0 a 200.</span><span class="sxs-lookup"><span data-stu-id="b49da-112">The ellipse and the rectangle also change gradually from red to blue as the horizontal coordinate goes from 0 to 200.</span></span>  
  
 <span data-ttu-id="b49da-113">Nella figura seguente mostra la riga, i puntini di sospensione e il rettangolo.</span><span class="sxs-lookup"><span data-stu-id="b49da-113">The following illustration shows the line, the ellipse, and the rectangle.</span></span> <span data-ttu-id="b49da-114">Si noti che la sfumatura di colore si ripete per la coordinata orizzontale aumenta oltre 200.</span><span class="sxs-lookup"><span data-stu-id="b49da-114">Note that the color gradient repeats itself as the horizontal coordinate increases beyond 200.</span></span>  
  
 <span data-ttu-id="b49da-115">![Sfumatura lineare](../../../../docs/framework/winforms/advanced/media/cslineargradient1.png "cslineargradient1")</span><span class="sxs-lookup"><span data-stu-id="b49da-115">![Linear Gradient](../../../../docs/framework/winforms/advanced/media/cslineargradient1.png "cslineargradient1")</span></span>  
  
### <a name="to-use-horizontal-linear-gradients"></a><span data-ttu-id="b49da-116">Per utilizzare sfumature lineare orizzontale</span><span class="sxs-lookup"><span data-stu-id="b49da-116">To use horizontal linear gradients</span></span>  
  
-   <span data-ttu-id="b49da-117">Passare l'opaco rosso e blu opaco come terzo e quarto argomento, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="b49da-117">Pass in the opaque red and opaque blue as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#21)]
     [!code-vb[System.Drawing.UsingaGradientBrush#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#21)]  
  
 <span data-ttu-id="b49da-118">Nell'esempio precedente, i componenti di colore modificare in modo lineare si sposta da una coordinata orizzontale pari a 0 per una coordinata orizzontale 200.</span><span class="sxs-lookup"><span data-stu-id="b49da-118">In the preceding example, the color components change linearly as you move from a horizontal coordinate of 0 to a horizontal coordinate of 200.</span></span> <span data-ttu-id="b49da-119">Ad esempio, un punto in cui la coordinata è compreso tra 0 e 200 disporrà di un componente blu che si trova a metà tra 0 e 255.</span><span class="sxs-lookup"><span data-stu-id="b49da-119">For example, a point whose first coordinate is halfway between 0 and 200 will have a blue component that is halfway between 0 and 255.</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="b49da-120"> Consente di regolare il modo in cui che un colore varia da un bordo di una sfumatura a altro.</span><span class="sxs-lookup"><span data-stu-id="b49da-120"> allows you to adjust the way a color varies from one edge of a gradient to the other.</span></span> <span data-ttu-id="b49da-121">Si supponga di che voler creare un pennello sfumato cambia da nero in rosso in base alla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="b49da-121">Suppose you want to create a gradient brush that changes from black to red according to the following table.</span></span>  
  
|<span data-ttu-id="b49da-122">Coordinata orizzontale</span><span class="sxs-lookup"><span data-stu-id="b49da-122">Horizontal coordinate</span></span>|<span data-ttu-id="b49da-123">Componenti RGB</span><span class="sxs-lookup"><span data-stu-id="b49da-123">RGB components</span></span>|  
|---------------------------|--------------------|  
|<span data-ttu-id="b49da-124">0</span><span class="sxs-lookup"><span data-stu-id="b49da-124">0</span></span>|<span data-ttu-id="b49da-125">(0, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="b49da-125">(0, 0, 0)</span></span>|  
|<span data-ttu-id="b49da-126">40</span><span class="sxs-lookup"><span data-stu-id="b49da-126">40</span></span>|<span data-ttu-id="b49da-127">(128, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="b49da-127">(128, 0, 0)</span></span>|  
|<span data-ttu-id="b49da-128">200</span><span class="sxs-lookup"><span data-stu-id="b49da-128">200</span></span>|<span data-ttu-id="b49da-129">(255, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="b49da-129">(255, 0, 0)</span></span>|  
  
 <span data-ttu-id="b49da-130">Si noti che il componente rosso intensità media quando la coordinata orizzontale corrisponde solo il 20% del modo in cui da 0 a 200.</span><span class="sxs-lookup"><span data-stu-id="b49da-130">Note that the red component is at half intensity when the horizontal coordinate is only 20 percent of the way from 0 to 200.</span></span>  
  
 <span data-ttu-id="b49da-131">L'esempio seguente imposta il <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A> proprietà di un <xref:System.Drawing.Drawing2D.LinearGradientBrush> oggetto da associare tre intensità relative a tre posizioni relative.</span><span class="sxs-lookup"><span data-stu-id="b49da-131">The following example sets the <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A> property of a <xref:System.Drawing.Drawing2D.LinearGradientBrush> object to associate three relative intensities with three relative positions.</span></span> <span data-ttu-id="b49da-132">Come indicato nella tabella precedente, un'intensità pari a 0,5 è associata a una posizione relativa di 0,2.</span><span class="sxs-lookup"><span data-stu-id="b49da-132">As in the preceding table, a relative intensity of 0.5 is associated with a relative position of 0.2.</span></span> <span data-ttu-id="b49da-133">Il codice verrà inserito un'ellisse e un rettangolo con pennello sfumato.</span><span class="sxs-lookup"><span data-stu-id="b49da-133">The code fills an ellipse and a rectangle with the gradient brush.</span></span>  
  
 <span data-ttu-id="b49da-134">Nella figura seguente viene illustrato il rettangolo e l'ellisse risultante.</span><span class="sxs-lookup"><span data-stu-id="b49da-134">The following illustration shows the resulting ellipse and rectangle.</span></span>  
  
 <span data-ttu-id="b49da-135">![Sfumatura lineare](../../../../docs/framework/winforms/advanced/media/cslineargradient2.png "cslineargradient2")</span><span class="sxs-lookup"><span data-stu-id="b49da-135">![Linear Gradient](../../../../docs/framework/winforms/advanced/media/cslineargradient2.png "cslineargradient2")</span></span>  
  
### <a name="to-customize-linear-gradients"></a><span data-ttu-id="b49da-136">Per personalizzare i gradienti lineari</span><span class="sxs-lookup"><span data-stu-id="b49da-136">To customize linear gradients</span></span>  
  
-   <span data-ttu-id="b49da-137">Passare l'opaco nero e rosso opaco come terzo e quarto argomento, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="b49da-137">Pass in the opaque black and opaque red as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#22)]
     [!code-vb[System.Drawing.UsingaGradientBrush#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#22)]  
  
 <span data-ttu-id="b49da-138">Le sfumature negli esempi precedenti sono state orizzontale; vale a dire il colore cambia gradualmente mentre si sposta lungo una linea orizzontale.</span><span class="sxs-lookup"><span data-stu-id="b49da-138">The gradients in the preceding examples have been horizontal; that is, the color changes gradually as you move along any horizontal line.</span></span> <span data-ttu-id="b49da-139">È inoltre possibile definire sfumature verticali e diagonali.</span><span class="sxs-lookup"><span data-stu-id="b49da-139">You can also define vertical gradients and diagonal gradients.</span></span>  
  
 <span data-ttu-id="b49da-140">Nell'esempio seguente passa i punti (0, 0) e (200, 100) a un <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> costruttore.</span><span class="sxs-lookup"><span data-stu-id="b49da-140">The following example passes the points (0, 0) and (200, 100) to a <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> constructor.</span></span> <span data-ttu-id="b49da-141">Il colore blu è associato a (0, 0), ed è associato il colore verde (200, 100).</span><span class="sxs-lookup"><span data-stu-id="b49da-141">The color blue is associated with (0, 0), and the color green is associated with (200, 100).</span></span> <span data-ttu-id="b49da-142">Una riga (con la larghezza della penna 10) e un'ellisse vengono riempiti con pennello sfumato lineare.</span><span class="sxs-lookup"><span data-stu-id="b49da-142">A line (with pen width 10) and an ellipse are filled with the linear gradient brush.</span></span>  
  
 <span data-ttu-id="b49da-143">Nella figura seguente mostra la riga e l'ellisse.</span><span class="sxs-lookup"><span data-stu-id="b49da-143">The following illustration shows the line and the ellipse.</span></span> <span data-ttu-id="b49da-144">Si noti che il colore in ellisse cambia gradualmente mentre si sposta lungo una riga che sono parallelo a quella che passa attraverso (0, 0) e (200, 100).</span><span class="sxs-lookup"><span data-stu-id="b49da-144">Note that the color in the ellipse changes gradually as you move along any line that is parallel to the line passing through (0, 0) and (200, 100).</span></span>  
  
 <span data-ttu-id="b49da-145">![Sfumatura lineare](../../../../docs/framework/winforms/advanced/media/cslineargradient3.png "cslineargradient3")</span><span class="sxs-lookup"><span data-stu-id="b49da-145">![Linear Gradient](../../../../docs/framework/winforms/advanced/media/cslineargradient3.png "cslineargradient3")</span></span>  
  
### <a name="to-create-diagonal-linear-gradients"></a><span data-ttu-id="b49da-146">Per creare diagonale gradienti lineari</span><span class="sxs-lookup"><span data-stu-id="b49da-146">To create diagonal linear gradients</span></span>  
  
-   <span data-ttu-id="b49da-147">Passare l'opaco blu e verde opaco come terzo e quarto argomento, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="b49da-147">Pass in the opaque blue and opaque green as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#23)]
     [!code-vb[System.Drawing.UsingaGradientBrush#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="b49da-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b49da-148">See Also</span></span>  
 [<span data-ttu-id="b49da-149">Uso di un pennello a sfumatura per il riempimento di forme</span><span class="sxs-lookup"><span data-stu-id="b49da-149">Using a Gradient Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)  
 [<span data-ttu-id="b49da-150">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="b49da-150">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
