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
# <a name="constructing-and-drawing-curves"></a>Costruzione e creazione di curve
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] supporta diversi tipi di curve: puntini di sospensione, archi, spline cardinali e spline di Bézier. Un'ellisse è definita dal rettangolo di delimitazione; un arco è una parte di un'ellisse definita da un angolo iniziale e un angolo di apertura. Spline di tipo cardinal è definita da una matrice di punti e un parametro di tensione, ovvero la curva passa per ogni punto della matrice e il parametro di tensione influenza il modo di curvatura. Una spline di Bézier è definita da due endpoint e due punti di controllo che della curva non passano attraverso i punti di controllo, ma i punti di controllo influenzano la direzione e piegatura come la curva passa da un endpoint a altro.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura: Disegnare spline di tipo Cardinal](../../../../docs/framework/winforms/advanced/how-to-draw-cardinal-splines.md)  
 Viene descritto come disegnare li e spline cardinali.  
  
 [Procedura: Disegnare una singola spline di Bézier](../../../../docs/framework/winforms/advanced/how-to-draw-a-single-bezier-spline.md)  
 Viene descritto come creare uno di una spline di Bézier.  
  
 [Procedura: Disegnare una sequenza di spline di Bézier](../../../../docs/framework/winforms/advanced/how-to-draw-a-sequence-of-bezier-splines.md)  
 Illustra come disegnare spline di Bézier diversi nella sequenza.
