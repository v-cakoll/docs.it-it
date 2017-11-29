---
title: Utilizzo di un oggetto Pen per creare linee e forme
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pens
- examples [Windows Forms], drawing lines and shapes
- examples [Windows Forms], pens
- drawing
ms.assetid: 8a7542ab-3e9e-443f-8405-2d6053528e20
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0913dc2745e1b244e4b03c0e6b946441a401c5b1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="using-a-pen-to-draw-lines-and-shapes"></a><span data-ttu-id="3ff10-102">Utilizzo di un oggetto Pen per creare linee e forme</span><span class="sxs-lookup"><span data-stu-id="3ff10-102">Using a Pen to Draw Lines and Shapes</span></span>
<span data-ttu-id="3ff10-103">Utilizzare [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] `Pen` oggetti per creare segmenti di linea, curve e le strutture delle forme.</span><span class="sxs-lookup"><span data-stu-id="3ff10-103">Use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] `Pen` objects to draw line segments, curves, and the outlines of shapes.</span></span> <span data-ttu-id="3ff10-104">In questa sezione, *riga* fa riferimento a uno di questi, salvo per indicare solo un segmento di linea.</span><span class="sxs-lookup"><span data-stu-id="3ff10-104">In this section, *line* refers to any of these, unless specified to mean only a line segment.</span></span> <span data-ttu-id="3ff10-105">Impostare le proprietà di un oggetto pen per controllare il colore, larghezza, l'allineamento e stile delle linee disegnate con quella penna.</span><span class="sxs-lookup"><span data-stu-id="3ff10-105">Set the properties of a pen to control the color, width, alignment, and style of lines drawn with that pen.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3ff10-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="3ff10-106">In This Section</span></span>  
 [<span data-ttu-id="3ff10-107">Procedura: Usare un oggetto Pen per disegnare linee</span><span class="sxs-lookup"><span data-stu-id="3ff10-107">How to: Use a Pen to Draw Lines</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-a-pen-to-draw-lines.md)  
 <span data-ttu-id="3ff10-108">Viene descritto come creare linee.</span><span class="sxs-lookup"><span data-stu-id="3ff10-108">Explains how to draw lines.</span></span>  
  
 [<span data-ttu-id="3ff10-109">Procedura: Usare un oggetto Pen per disegnare rettangoli</span><span class="sxs-lookup"><span data-stu-id="3ff10-109">How to: Use a Pen to Draw Rectangles</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-a-pen-to-draw-rectangles.md)  
 <span data-ttu-id="3ff10-110">Viene descritto come disegnare rettangoli.</span><span class="sxs-lookup"><span data-stu-id="3ff10-110">Describes how to draw rectangles.</span></span>  
  
 [<span data-ttu-id="3ff10-111">Procedura: Impostare la larghezza e l'allineamento di un oggetto Pen</span><span class="sxs-lookup"><span data-stu-id="3ff10-111">How to: Set Pen Width and Alignment</span></span>](../../../../docs/framework/winforms/advanced/how-to-set-pen-width-and-alignment.md)  
 <span data-ttu-id="3ff10-112">Viene illustrato come modificare la larghezza e l'allineamento di un `Pen` oggetto.</span><span class="sxs-lookup"><span data-stu-id="3ff10-112">Explains how to change the width and alignment of a `Pen` object.</span></span>  
  
 [<span data-ttu-id="3ff10-113">Procedura: Disegnare una linea con estremità</span><span class="sxs-lookup"><span data-stu-id="3ff10-113">How to: Draw a Line with Line Caps</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-line-with-line-caps.md)  
 <span data-ttu-id="3ff10-114">Viene descritto come aggiungere i delimitatori finali quando si disegna una linea.</span><span class="sxs-lookup"><span data-stu-id="3ff10-114">Describes how to add end caps when drawing a line.</span></span>  
  
 [<span data-ttu-id="3ff10-115">Procedura: Unire linee</span><span class="sxs-lookup"><span data-stu-id="3ff10-115">How to: Join Lines</span></span>](../../../../docs/framework/winforms/advanced/how-to-join-lines.md)  
 <span data-ttu-id="3ff10-116">Viene illustrato come unire due linee.</span><span class="sxs-lookup"><span data-stu-id="3ff10-116">Shows how to join two lines.</span></span>  
  
 [<span data-ttu-id="3ff10-117">Procedura: Disegnare una linea tratteggiata personalizzata</span><span class="sxs-lookup"><span data-stu-id="3ff10-117">How to: Draw a Custom Dashed Line</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-custom-dashed-line.md)  
 <span data-ttu-id="3ff10-118">Viene descritto come disegnare una linea tratteggiata.</span><span class="sxs-lookup"><span data-stu-id="3ff10-118">Describes how to draw a dashed line.</span></span>  
  
 [<span data-ttu-id="3ff10-119">Procedura: Disegnare una linea con riempimento a trama</span><span class="sxs-lookup"><span data-stu-id="3ff10-119">How to: Draw a Line Filled with a Texture</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-line-filled-with-a-texture.md)  
 <span data-ttu-id="3ff10-120">Viene illustrato come disegnare una linea di trama di riempimento.</span><span class="sxs-lookup"><span data-stu-id="3ff10-120">Explains how to draw a texture-filled line.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="3ff10-121">Riferimento</span><span class="sxs-lookup"><span data-stu-id="3ff10-121">Reference</span></span>  
 <xref:System.Drawing.Pen>  
 <span data-ttu-id="3ff10-122">Descrive la classe e fornisce i collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="3ff10-122">Describes this class and has links to all its members.</span></span>
