---
title: Costruzione e creazione di curve
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [Windows Forms], curves
- examples [Windows Forms], drawing curves
- curves [Windows Forms], drawing
ms.assetid: 76e92623-4130-4644-b867-faca58bdb3a2
ms.openlocfilehash: 4c1b0cc6c6f878569fcf0c392f1b6f9683ec8afc
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "67506108"
---
# <a name="constructing-and-drawing-curves"></a>Costruzione e creazione di curve
GDI + supporta diversi tipi di curve: puntini di sospensione, archi, cardinali e spline di Bézier. Un'ellisse viene definita dal rettangolo di delimitazione; un arco è una parte di un'ellisse definita da un angolo iniziale e un angolo di apertura. Spline di tipo cardinal è definito da una matrice di punti e un parametro di tensione, ovvero la curva passa per ogni punto della matrice e il parametro tensione influenza il modo curvatura. Una spline di Bézier è definita da due endpoint e due punti di controllo che della curva non passa attraverso i punti di controllo, ma i punti di controllo influenzano la direzione e piegare perché la curva passa da un endpoint a altro.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura: Disegnare spline di tipo Cardinal](how-to-draw-cardinal-splines.md)  
 Viene descritto come disegnare li e spline cardinale.  
  
 [Procedura: Draw a Single Bézier Spline](how-to-draw-a-single-bezier-spline.md)  
 Viene descritto come disegnare uno e una spline di Bézier.  
  
 [Procedura: Disegnare una sequenza di spline di Bézier](how-to-draw-a-sequence-of-bezier-splines.md)  
 Illustra come disegnare spline di Bézier diversi nella sequenza.
