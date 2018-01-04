---
title: Costruzione e creazione di curve
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drawing [Windows Forms], curves
- examples [Windows Forms], drawing curves
- curves [Windows Forms], drawing
ms.assetid: 76e92623-4130-4644-b867-faca58bdb3a2
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 62e9b9e0e1aa432578b7173cd58f88dd44957f84
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="constructing-and-drawing-curves"></a><span data-ttu-id="8648f-102">Costruzione e creazione di curve</span><span class="sxs-lookup"><span data-stu-id="8648f-102">Constructing and Drawing Curves</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="8648f-103">supporta diversi tipi di curve: ellissi, archi, spline di tipo cardinal e spline di Bézier.</span><span class="sxs-lookup"><span data-stu-id="8648f-103"> supports several types of curves: ellipses, arcs, cardinal splines, and Bézier splines.</span></span> <span data-ttu-id="8648f-104">Un'ellisse è definita dal rettangolo di delimitazione; un arco è una parte di un'ellisse definita da un angolo iniziale e un angolo di apertura.</span><span class="sxs-lookup"><span data-stu-id="8648f-104">An ellipse is defined by its bounding rectangle; an arc is a portion of an ellipse defined by a starting angle and a sweep angle.</span></span> <span data-ttu-id="8648f-105">Spline di tipo cardinal è definita da una matrice di punti e un parametro di tensione, ovvero la curva passa per ogni punto della matrice e il parametro di tensione influenza il modo di curvatura.</span><span class="sxs-lookup"><span data-stu-id="8648f-105">A cardinal spline is defined by an array of points and a tension parameter — the curve passes smoothly through each point in the array, and the tension parameter influences the way the curve bends.</span></span> <span data-ttu-id="8648f-106">Una spline di Bézier è definita da due endpoint e due punti di controllo che della curva non passano attraverso i punti di controllo, ma i punti di controllo influenzano la direzione e piegatura come la curva passa da un endpoint a altro.</span><span class="sxs-lookup"><span data-stu-id="8648f-106">A Bézier spline is defined by two endpoints and two control points  the curve does not pass through the control points, but the control points influence the direction and bend as the curve goes from one endpoint to the other.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8648f-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="8648f-107">In This Section</span></span>  
 [<span data-ttu-id="8648f-108">Procedura: Disegnare spline di tipo Cardinal</span><span class="sxs-lookup"><span data-stu-id="8648f-108">How to: Draw Cardinal Splines</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-cardinal-splines.md)  
 <span data-ttu-id="8648f-109">Viene descritto come disegnare li e spline cardinali.</span><span class="sxs-lookup"><span data-stu-id="8648f-109">Describes cardinal splines and how to draw them.</span></span>  
  
 [<span data-ttu-id="8648f-110">Procedura: Disegnare una singola spline di Bézier</span><span class="sxs-lookup"><span data-stu-id="8648f-110">How to: Draw a Single Bézier Spline</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-single-bezier-spline.md)  
 <span data-ttu-id="8648f-111">Viene descritto come creare uno di una spline di Bézier.</span><span class="sxs-lookup"><span data-stu-id="8648f-111">Describes a Bézier spline and how to draw one.</span></span>  
  
 [<span data-ttu-id="8648f-112">Procedura: Disegnare una sequenza di spline di Bézier</span><span class="sxs-lookup"><span data-stu-id="8648f-112">How to: Draw a Sequence of Bézier Splines</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-sequence-of-bezier-splines.md)  
 <span data-ttu-id="8648f-113">Illustra come disegnare spline di Bézier diversi nella sequenza.</span><span class="sxs-lookup"><span data-stu-id="8648f-113">Explains how to draw several Bézier splines in sequence.</span></span>
