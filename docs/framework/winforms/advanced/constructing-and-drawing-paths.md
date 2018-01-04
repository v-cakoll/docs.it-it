---
title: Costruzione e creazione di percorsi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- paths [Windows Forms], drawing
- drawing paths [Windows Forms]
- graphics paths [Windows Forms], creating
- graphics paths [Windows Forms], drawing
- examples [Windows Forms], drawing paths
ms.assetid: f16ec921-56cf-46d1-9741-d7316ad06b23
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e6cec2356159b59e58ac6785a2988df7b2fac0e4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="constructing-and-drawing-paths"></a><span data-ttu-id="4d2db-102">Costruzione e creazione di percorsi</span><span class="sxs-lookup"><span data-stu-id="4d2db-102">Constructing and Drawing Paths</span></span>
<span data-ttu-id="4d2db-103">Un percorso è una sequenza di primitive grafiche (linee, rettangoli, curve, testo e così via) che può essere modificato e visualizzato come una singola unità.</span><span class="sxs-lookup"><span data-stu-id="4d2db-103">A path is a sequence of graphics primitives (lines, rectangles, curves, text, and the like) that can be manipulated and drawn as a single unit.</span></span> <span data-ttu-id="4d2db-104">Un percorso può essere suddiviso in *figure* che sono aperti o chiusi.</span><span class="sxs-lookup"><span data-stu-id="4d2db-104">A path can be divided into *figures* that are either open or closed.</span></span> <span data-ttu-id="4d2db-105">Una figura può contenere diverse primitive.</span><span class="sxs-lookup"><span data-stu-id="4d2db-105">A figure can contain several primitives.</span></span>  
  
 <span data-ttu-id="4d2db-106">È possibile disegnare un tracciato chiamando il <xref:System.Drawing.Graphics.DrawPath%2A> metodo il <xref:System.Drawing.Graphics> classe ed è possibile compilare un percorso chiamando il <xref:System.Drawing.Graphics.FillPath%2A> metodo il <xref:System.Drawing.Graphics> classe.</span><span class="sxs-lookup"><span data-stu-id="4d2db-106">You can draw a path by calling the <xref:System.Drawing.Graphics.DrawPath%2A> method of the <xref:System.Drawing.Graphics> class, and you can fill a path by calling the <xref:System.Drawing.Graphics.FillPath%2A> method of the <xref:System.Drawing.Graphics> class.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4d2db-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="4d2db-107">In This Section</span></span>  
 [<span data-ttu-id="4d2db-108">Procedura: Creare figure da linee, curve e forme</span><span class="sxs-lookup"><span data-stu-id="4d2db-108">How to: Create Figures from Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-figures-from-lines-curves-and-shapes.md)  
 <span data-ttu-id="4d2db-109">Viene illustrato come utilizzare un <xref:System.Drawing.Drawing2D.GraphicsPath> per creare figure.</span><span class="sxs-lookup"><span data-stu-id="4d2db-109">Shows how to use a <xref:System.Drawing.Drawing2D.GraphicsPath> to create figures.</span></span>  
  
 [<span data-ttu-id="4d2db-110">Procedura: Riempire figure aperte</span><span class="sxs-lookup"><span data-stu-id="4d2db-110">How to: Fill Open Figures</span></span>](../../../../docs/framework/winforms/advanced/how-to-fill-open-figures.md)  
 <span data-ttu-id="4d2db-111">Viene illustrato come compilare un <xref:System.Drawing.Drawing2D.GraphicsPath>.</span><span class="sxs-lookup"><span data-stu-id="4d2db-111">Explains how to fill a <xref:System.Drawing.Drawing2D.GraphicsPath>.</span></span>  
  
 [<span data-ttu-id="4d2db-112">Procedura: Trasformare un percorso curvo in una linea</span><span class="sxs-lookup"><span data-stu-id="4d2db-112">How to: Flatten a Curved Path into a Line</span></span>](../../../../docs/framework/winforms/advanced/how-to-flatten-a-curved-path-into-a-line.md)  
 <span data-ttu-id="4d2db-113">Viene illustrato come convertire un <xref:System.Drawing.Drawing2D.GraphicsPath>.</span><span class="sxs-lookup"><span data-stu-id="4d2db-113">Shows how to flatten a <xref:System.Drawing.Drawing2D.GraphicsPath>.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4d2db-114">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="4d2db-114">Reference</span></span>  
 <xref:System.Drawing.Drawing2D.GraphicsPath>  
 <span data-ttu-id="4d2db-115">Descrive la classe e contiene collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="4d2db-115">Describes this class and contains links to all of its members.</span></span>
