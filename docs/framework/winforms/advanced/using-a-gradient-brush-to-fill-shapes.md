---
title: Utilizzo di un pennello a sfumatura per il riempimento di forme
ms.date: 03/30/2017
helpviewer_keywords:
- brushes [Windows Forms], gradient brushes
- gradient brushes
- examples [Windows Forms], gradient brushes
ms.assetid: 2c6037b9-05bd-44c0-a22a-19584b722524
ms.openlocfilehash: 7ff555ba4fd81e9123e5f9e9feed38a0ec9d0a08
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063605"
---
# <a name="using-a-gradient-brush-to-fill-shapes"></a><span data-ttu-id="cbe81-102">Utilizzo di un pennello a sfumatura per il riempimento di forme</span><span class="sxs-lookup"><span data-stu-id="cbe81-102">Using a Gradient Brush to Fill Shapes</span></span>
<span data-ttu-id="cbe81-103">È possibile usare un pennello a sfumatura per riempire una forma con un colore gradualmente.</span><span class="sxs-lookup"><span data-stu-id="cbe81-103">You can use a gradient brush to fill a shape with a gradually changing color.</span></span> <span data-ttu-id="cbe81-104">Ad esempio, è possibile utilizzare una sfumatura orizzontale per riempire una forma con il colore che cambia gradualmente quando si spostano tra il bordo sinistro della forma per il bordo destro.</span><span class="sxs-lookup"><span data-stu-id="cbe81-104">For example, you can use a horizontal gradient to fill a shape with color that changes gradually as you move from the left edge of the shape to the right edge.</span></span> <span data-ttu-id="cbe81-105">Si immagini un rettangolo con un bordo nero (rappresentato da componenti rosso, verde e blu 0, 0, 0) e un diritto ovvero bordo rosso (rappresentato da 255, 0, 0).</span><span class="sxs-lookup"><span data-stu-id="cbe81-105">Imagine a rectangle with a left edge that is black (represented by red, green, and blue components 0, 0, 0) and a right edge that is red (represented by 255, 0, 0).</span></span> <span data-ttu-id="cbe81-106">Se il rettangolo è 256 pixel in larghezza, il componente rosso di un pixel specifico sarà una maggiore del componente rosso del pixel alla sua sinistra.</span><span class="sxs-lookup"><span data-stu-id="cbe81-106">If the rectangle is 256 pixels wide, the red component of a given pixel will be one greater than the red component of the pixel to its left.</span></span> <span data-ttu-id="cbe81-107">Il pixel più a sinistra in una riga ha componenti di colore (0, 0, 0), il secondo pixel ha (1, 0, 0), il terzo pixel (2, 0, 0) e così via, fino ad arrivare al pixel più a destra, che include componenti di colore (255, 0, 0).</span><span class="sxs-lookup"><span data-stu-id="cbe81-107">The leftmost pixel in a row has color components (0, 0, 0), the second pixel has (1, 0, 0), the third pixel has (2, 0, 0), and so on, until you get to the rightmost pixel, which has color components (255, 0, 0).</span></span> <span data-ttu-id="cbe81-108">Questi valori di colore interpolata costituiscono la sfumatura di colore.</span><span class="sxs-lookup"><span data-stu-id="cbe81-108">These interpolated color values make up the color gradient.</span></span>  
  
 <span data-ttu-id="cbe81-109">Una sfumatura lineare cambia colore quando si sposta orizzontalmente, verticalmente o in parallelo per una riga obliqua specificata.</span><span class="sxs-lookup"><span data-stu-id="cbe81-109">A linear gradient changes color as you move horizontally, vertically, or parallel to a specified slanted line.</span></span> <span data-ttu-id="cbe81-110">Una sfumatura percorso cambia colore quando si sposta sulla parte interna e limiti di un percorso.</span><span class="sxs-lookup"><span data-stu-id="cbe81-110">A path gradient changes color as you move about the interior and boundary of a path.</span></span> <span data-ttu-id="cbe81-111">È possibile personalizzare le sfumature di percorso per ottenere un'ampia gamma di effetti.</span><span class="sxs-lookup"><span data-stu-id="cbe81-111">You can customize path gradients to achieve a wide variety of effects.</span></span>  
  
 <span data-ttu-id="cbe81-112">La figura seguente mostra un rettangolo riempito con un pennello sfumato lineare e un'ellisse riempito con un pennello a sfumatura:</span><span class="sxs-lookup"><span data-stu-id="cbe81-112">The following illustration shows a rectangle filled with a linear gradient brush and an ellipse filled with a path gradient brush:</span></span>  
  
 ![Un rettangolo riempito con un pennello sfumato con un'ellisse.](./media/using-a-gradient-brush-to-fill-shapes/rectangle-ellipse-gradient-brush.png)  
  
## <a name="in-this-section"></a><span data-ttu-id="cbe81-114">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="cbe81-114">In This Section</span></span>  
 [<span data-ttu-id="cbe81-115">Procedura: Creare una sfumatura lineare</span><span class="sxs-lookup"><span data-stu-id="cbe81-115">How to: Create a Linear Gradient</span></span>](how-to-create-a-linear-gradient.md)  
 <span data-ttu-id="cbe81-116">Viene illustrato come creare una sfumatura lineare utilizzando il <xref:System.Drawing.Drawing2D.LinearGradientBrush> classe.</span><span class="sxs-lookup"><span data-stu-id="cbe81-116">Shows how to create a linear gradient using the <xref:System.Drawing.Drawing2D.LinearGradientBrush> class.</span></span>  
  
 [<span data-ttu-id="cbe81-117">Procedura: Creare una sfumatura percorso</span><span class="sxs-lookup"><span data-stu-id="cbe81-117">How to: Create a Path Gradient</span></span>](how-to-create-a-path-gradient.md)  
 <span data-ttu-id="cbe81-118">Viene descritto come creare una sfumatura di percorso utilizzando il <xref:System.Drawing.Drawing2D.PathGradientBrush> classe.</span><span class="sxs-lookup"><span data-stu-id="cbe81-118">Describes how to create a path gradient using the <xref:System.Drawing.Drawing2D.PathGradientBrush> class.</span></span>  
  
 [<span data-ttu-id="cbe81-119">Procedura: Applicare la correzione Gamma a una sfumatura</span><span class="sxs-lookup"><span data-stu-id="cbe81-119">How to: Apply Gamma Correction to a Gradient</span></span>](how-to-apply-gamma-correction-to-a-gradient.md)  
 <span data-ttu-id="cbe81-120">Viene illustrato come utilizzare la correzione gamma con un pennello sfumato.</span><span class="sxs-lookup"><span data-stu-id="cbe81-120">Explains how to use gamma correction with a gradient brush.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="cbe81-121">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="cbe81-121">Reference</span></span>  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>  
 <span data-ttu-id="cbe81-122">Contiene una descrizione di questa classe e include collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="cbe81-122">Contains a description of this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Drawing2D.PathGradientBrush?displayProperty=nameWithType>  
 <span data-ttu-id="cbe81-123">Contiene una descrizione di questa classe e include collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="cbe81-123">Contains a description of this class and has links to all of its members.</span></span>
