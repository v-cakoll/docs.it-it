---
title: Costruzione e creazione di curve
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [Windows Forms], curves
- examples [Windows Forms], drawing curves
- curves [Windows Forms], drawing
ms.assetid: 76e92623-4130-4644-b867-faca58bdb3a2
ms.openlocfilehash: 92e7b1e8b4ce37db633b5dafe212a252b854d1af
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57702711"
---
# <a name="constructing-and-drawing-curves"></a><span data-ttu-id="aefd5-102">Costruzione e creazione di curve</span><span class="sxs-lookup"><span data-stu-id="aefd5-102">Constructing and Drawing Curves</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="aefd5-103">supporta diversi tipi di curve: puntini di sospensione, archi, cardinali e spline di Bézier.</span><span class="sxs-lookup"><span data-stu-id="aefd5-103">supports several types of curves: ellipses, arcs, cardinal splines, and Bézier splines.</span></span> <span data-ttu-id="aefd5-104">Un'ellisse viene definita dal rettangolo di delimitazione; un arco è una parte di un'ellisse definita da un angolo iniziale e un angolo di apertura.</span><span class="sxs-lookup"><span data-stu-id="aefd5-104">An ellipse is defined by its bounding rectangle; an arc is a portion of an ellipse defined by a starting angle and a sweep angle.</span></span> <span data-ttu-id="aefd5-105">Spline di tipo cardinal è definito da una matrice di punti e un parametro di tensione, ovvero la curva passa per ogni punto della matrice e il parametro tensione influenza il modo curvatura.</span><span class="sxs-lookup"><span data-stu-id="aefd5-105">A cardinal spline is defined by an array of points and a tension parameter — the curve passes smoothly through each point in the array, and the tension parameter influences the way the curve bends.</span></span> <span data-ttu-id="aefd5-106">Una spline di Bézier è definita da due endpoint e due punti di controllo che della curva non passa attraverso i punti di controllo, ma i punti di controllo influenzano la direzione e piegare perché la curva passa da un endpoint a altro.</span><span class="sxs-lookup"><span data-stu-id="aefd5-106">A Bézier spline is defined by two endpoints and two control points  the curve does not pass through the control points, but the control points influence the direction and bend as the curve goes from one endpoint to the other.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="aefd5-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="aefd5-107">In This Section</span></span>  
 [<span data-ttu-id="aefd5-108">Procedura: Disegnare spline di tipo Cardinal</span><span class="sxs-lookup"><span data-stu-id="aefd5-108">How to: Draw Cardinal Splines</span></span>](how-to-draw-cardinal-splines.md)  
 <span data-ttu-id="aefd5-109">Viene descritto come disegnare li e spline cardinale.</span><span class="sxs-lookup"><span data-stu-id="aefd5-109">Describes cardinal splines and how to draw them.</span></span>  
  
 [<span data-ttu-id="aefd5-110">Procedura: Draw a Single Bézier Spline</span><span class="sxs-lookup"><span data-stu-id="aefd5-110">How to: Draw a Single Bézier Spline</span></span>](how-to-draw-a-single-bezier-spline.md)  
 <span data-ttu-id="aefd5-111">Viene descritto come disegnare uno e una spline di Bézier.</span><span class="sxs-lookup"><span data-stu-id="aefd5-111">Describes a Bézier spline and how to draw one.</span></span>  
  
 [<span data-ttu-id="aefd5-112">Procedura: Disegnare una sequenza di spline di Bézier</span><span class="sxs-lookup"><span data-stu-id="aefd5-112">How to: Draw a Sequence of Bézier Splines</span></span>](how-to-draw-a-sequence-of-bezier-splines.md)  
 <span data-ttu-id="aefd5-113">Illustra come disegnare spline di Bézier diversi nella sequenza.</span><span class="sxs-lookup"><span data-stu-id="aefd5-113">Explains how to draw several Bézier splines in sequence.</span></span>
