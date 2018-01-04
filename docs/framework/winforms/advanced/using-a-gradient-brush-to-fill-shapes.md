---
title: Utilizzo di un pennello a sfumatura per il riempimento di forme
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- brushes [Windows Forms], gradient brushes
- gradient brushes
- examples [Windows Forms], gradient brushes
ms.assetid: 2c6037b9-05bd-44c0-a22a-19584b722524
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6a84a68f9082d00559938c2710b6574690fa6ab4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="using-a-gradient-brush-to-fill-shapes"></a><span data-ttu-id="d5cfb-102">Utilizzo di un pennello a sfumatura per il riempimento di forme</span><span class="sxs-lookup"><span data-stu-id="d5cfb-102">Using a Gradient Brush to Fill Shapes</span></span>
<span data-ttu-id="d5cfb-103">È possibile utilizzare un pennello a sfumatura per riempire una forma con un colore gradualmente.</span><span class="sxs-lookup"><span data-stu-id="d5cfb-103">You can use a gradient brush to fill a shape with a gradually changing color.</span></span> <span data-ttu-id="d5cfb-104">Ad esempio, è possibile utilizzare una sfumatura orizzontale per riempire una forma con colore che cambia gradualmente man mano che si sposta dal bordo sinistro della forma al bordo destro.</span><span class="sxs-lookup"><span data-stu-id="d5cfb-104">For example, you can use a horizontal gradient to fill a shape with color that changes gradually as you move from the left edge of the shape to the right edge.</span></span> <span data-ttu-id="d5cfb-105">Si supponga di un rettangolo con un bordo sinistro di colore nero (rappresentato da componenti rosso, verde e blu 0, 0, 0) e un diritto margine (rappresentato da 255, 0, 0).</span><span class="sxs-lookup"><span data-stu-id="d5cfb-105">Imagine a rectangle with a left edge that is black (represented by red, green, and blue components 0, 0, 0) and a right edge that is red (represented by 255, 0, 0).</span></span> <span data-ttu-id="d5cfb-106">Se il rettangolo è 256 pixel in larghezza, il componente rosso di un determinato pixel sarà una maggiore il componente rosso di pixel alla sua sinistra.</span><span class="sxs-lookup"><span data-stu-id="d5cfb-106">If the rectangle is 256 pixels wide, the red component of a given pixel will be one greater than the red component of the pixel to its left.</span></span> <span data-ttu-id="d5cfb-107">Il pixel più a sinistra in una riga ha componenti di colore (0, 0, 0), il secondo pixel è (1, 0, 0), il terzo pixel (2, 0, 0) e così via, fino a ottenere il pixel più a destra, che include componenti di colore (255, 0, 0).</span><span class="sxs-lookup"><span data-stu-id="d5cfb-107">The leftmost pixel in a row has color components (0, 0, 0), the second pixel has (1, 0, 0), the third pixel has (2, 0, 0), and so on, until you get to the rightmost pixel, which has color components (255, 0, 0).</span></span> <span data-ttu-id="d5cfb-108">Questi valori di colore interpolata è costituiscono la sfumatura di colore.</span><span class="sxs-lookup"><span data-stu-id="d5cfb-108">These interpolated color values make up the color gradient.</span></span>  
  
 <span data-ttu-id="d5cfb-109">Sfumatura lineare cambia colore quando si sposta orizzontalmente, verticalmente o parallela a una determinata riga inclinata.</span><span class="sxs-lookup"><span data-stu-id="d5cfb-109">A linear gradient changes color as you move horizontally, vertically, or parallel to a specified slanted line.</span></span> <span data-ttu-id="d5cfb-110">Quando si sposta sulla parte interna e limiti di un percorso, una sfumatura percorso cambia colore.</span><span class="sxs-lookup"><span data-stu-id="d5cfb-110">A path gradient changes color as you move about the interior and boundary of a path.</span></span> <span data-ttu-id="d5cfb-111">È possibile personalizzare i gradienti del percorso per raggiungere una vasta gamma di effetti.</span><span class="sxs-lookup"><span data-stu-id="d5cfb-111">You can customize path gradients to achieve a wide variety of effects.</span></span>  
  
 <span data-ttu-id="d5cfb-112">Nella figura seguente viene illustrato un rettangolo riempito con pennello sfumato lineare e un'ellisse riempita con un pennello a sfumatura.</span><span class="sxs-lookup"><span data-stu-id="d5cfb-112">The following illustration shows a rectangle filled with a linear gradient brush and an ellipse filled with a path gradient brush.</span></span>  
  
 <span data-ttu-id="d5cfb-113">![Sfumatura](../../../../docs/framework/winforms/advanced/media/gradient2.png "gradient2")</span><span class="sxs-lookup"><span data-stu-id="d5cfb-113">![Gradient](../../../../docs/framework/winforms/advanced/media/gradient2.png "gradient2")</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d5cfb-114">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="d5cfb-114">In This Section</span></span>  
 [<span data-ttu-id="d5cfb-115">Procedura: Creare una sfumatura lineare</span><span class="sxs-lookup"><span data-stu-id="d5cfb-115">How to: Create a Linear Gradient</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-linear-gradient.md)  
 <span data-ttu-id="d5cfb-116">Viene illustrato come creare una sfumatura lineare utilizzando la <xref:System.Drawing.Drawing2D.LinearGradientBrush> classe.</span><span class="sxs-lookup"><span data-stu-id="d5cfb-116">Shows how to create a linear gradient using the <xref:System.Drawing.Drawing2D.LinearGradientBrush> class.</span></span>  
  
 [<span data-ttu-id="d5cfb-117">Procedura: Creare una sfumatura percorso</span><span class="sxs-lookup"><span data-stu-id="d5cfb-117">How to: Create a Path Gradient</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-path-gradient.md)  
 <span data-ttu-id="d5cfb-118">Viene descritto come creare una sfumatura di percorso utilizzando il <xref:System.Drawing.Drawing2D.PathGradientBrush> classe.</span><span class="sxs-lookup"><span data-stu-id="d5cfb-118">Describes how to create a path gradient using the <xref:System.Drawing.Drawing2D.PathGradientBrush> class.</span></span>  
  
 [<span data-ttu-id="d5cfb-119">Procedura: Applicare la correzione gamma a una sfumatura</span><span class="sxs-lookup"><span data-stu-id="d5cfb-119">How to: Apply Gamma Correction to a Gradient</span></span>](../../../../docs/framework/winforms/advanced/how-to-apply-gamma-correction-to-a-gradient.md)  
 <span data-ttu-id="d5cfb-120">Viene illustrato come utilizzare la correzione gamma con un pennello sfumato.</span><span class="sxs-lookup"><span data-stu-id="d5cfb-120">Explains how to use gamma correction with a gradient brush.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d5cfb-121">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="d5cfb-121">Reference</span></span>  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>  
 <span data-ttu-id="d5cfb-122">Contiene una descrizione di questa classe e include collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="d5cfb-122">Contains a description of this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Drawing2D.PathGradientBrush?displayProperty=nameWithType>  
 <span data-ttu-id="d5cfb-123">Contiene una descrizione di questa classe e include collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="d5cfb-123">Contains a description of this class and has links to all of its members.</span></span>
