---
title: Costruzione e creazione di curve
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [Windows Forms], curves
- examples [Windows Forms], drawing curves
- curves [Windows Forms], drawing
ms.assetid: 76e92623-4130-4644-b867-faca58bdb3a2
ms.openlocfilehash: d9a790060fdf0f0c2a739d99aba1b36cf0323f8b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33520617"
---
# <a name="constructing-and-drawing-curves"></a><span data-ttu-id="64760-102">Costruzione e creazione di curve</span><span class="sxs-lookup"><span data-stu-id="64760-102">Constructing and Drawing Curves</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="64760-103"> supporta diversi tipi di curve: puntini di sospensione, archi, spline cardinali e spline di Bézier.</span><span class="sxs-lookup"><span data-stu-id="64760-103"> supports several types of curves: ellipses, arcs, cardinal splines, and Bézier splines.</span></span> <span data-ttu-id="64760-104">Un'ellisse è definita dal rettangolo di delimitazione; un arco è una parte di un'ellisse definita da un angolo iniziale e un angolo di apertura.</span><span class="sxs-lookup"><span data-stu-id="64760-104">An ellipse is defined by its bounding rectangle; an arc is a portion of an ellipse defined by a starting angle and a sweep angle.</span></span> <span data-ttu-id="64760-105">Spline di tipo cardinal è definita da una matrice di punti e un parametro di tensione, ovvero la curva passa per ogni punto della matrice e il parametro di tensione influenza il modo di curvatura.</span><span class="sxs-lookup"><span data-stu-id="64760-105">A cardinal spline is defined by an array of points and a tension parameter — the curve passes smoothly through each point in the array, and the tension parameter influences the way the curve bends.</span></span> <span data-ttu-id="64760-106">Una spline di Bézier è definita da due endpoint e due punti di controllo che della curva non passano attraverso i punti di controllo, ma i punti di controllo influenzano la direzione e piegatura come la curva passa da un endpoint a altro.</span><span class="sxs-lookup"><span data-stu-id="64760-106">A Bézier spline is defined by two endpoints and two control points  the curve does not pass through the control points, but the control points influence the direction and bend as the curve goes from one endpoint to the other.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="64760-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="64760-107">In This Section</span></span>  
 [<span data-ttu-id="64760-108">Procedura: Disegnare spline di tipo Cardinal</span><span class="sxs-lookup"><span data-stu-id="64760-108">How to: Draw Cardinal Splines</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-cardinal-splines.md)  
 <span data-ttu-id="64760-109">Viene descritto come disegnare li e spline cardinali.</span><span class="sxs-lookup"><span data-stu-id="64760-109">Describes cardinal splines and how to draw them.</span></span>  
  
 [<span data-ttu-id="64760-110">Procedura: Disegnare una singola spline di Bézier</span><span class="sxs-lookup"><span data-stu-id="64760-110">How to: Draw a Single Bézier Spline</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-single-bezier-spline.md)  
 <span data-ttu-id="64760-111">Viene descritto come creare uno di una spline di Bézier.</span><span class="sxs-lookup"><span data-stu-id="64760-111">Describes a Bézier spline and how to draw one.</span></span>  
  
 [<span data-ttu-id="64760-112">Procedura: Disegnare una sequenza di spline di Bézier</span><span class="sxs-lookup"><span data-stu-id="64760-112">How to: Draw a Sequence of Bézier Splines</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-sequence-of-bezier-splines.md)  
 <span data-ttu-id="64760-113">Illustra come disegnare spline di Bézier diversi nella sequenza.</span><span class="sxs-lookup"><span data-stu-id="64760-113">Explains how to draw several Bézier splines in sequence.</span></span>
