---
title: Spline di tipo Cardinal in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- splines [Windows Forms], cardinal
- GDI+, cardinal splines
- cardinal splines
ms.assetid: 09b3797a-6294-422d-9adf-a5a0a7695c0c
ms.openlocfilehash: 93ae09c72415fa489e62f753e51e5a3ffcfb2425
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="cardinal-splines-in-gdi"></a>Spline di tipo Cardinal in GDI+
Spline di tipo cardinal è una sequenza di curve individuali unite per formare una curva più grande. Spline è specificata da una matrice di punti e un parametro di tensione. Spline di tipo cardinal passa per ogni punto della matrice. Esistono alcun angoli acuti e apportare alcuna modifica improvviso la tensione della curva. Nella figura seguente viene illustrato un set di punti e di una spline di tipo cardinal che attraversa ogni punto nel set.  
  
 ![Spline di tipo Cardinal](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art09.gif "Aboutgdip02_art09")  
  
## <a name="physical-and-mathematical-splines"></a>Spline fisiche e matematiche  
 Una spline di tipo fisico è un componente thin legno o altro materiale flessibile. Prima dell'avvento di spline matematiche, finestre di progettazione utilizzato fisiche spline per disegnare curve. Posizionare la spline in un foglio di carta e ancorare l'annotazione a un determinato set di punti di una finestra di progettazione. La finestra di progettazione può quindi creare una curva lungo la spline con una penna o una matita. Un set di punti specificato perché potrebbe generare un'ampia gamma di curve, a seconda delle proprietà della spline fisica. Ad esempio, una spline di tipo con un'elevata resistenza consentiva produrrebbe una curva diversa rispetto a spline estremamente flessibile.  
  
 Le formule per spline matematiche sono basate sulle proprietà di aste flessibile, pertanto la curva delle curve prodotte da spline matematiche è simili alle curve prodotte da spline fisiche. Come spline fisiche della tensione diversi produrranno curve diverse tramite un determinato set di punti, spline matematiche con valori diversi per il parametro di tensione produrranno curve diverse tramite un determinato set di punti. Nella figura seguente mostra quattro spline cardinali passano attraverso lo stesso set di punti. Viene mostrata la tensione per ogni spline. Una tensione pari a 0 corrisponde a tensione fisica infinita, forzando la curva per rendere il modo più veloce (linee rette) tra i punti. Una tensione 1 corrisponde a nessun tensione fisica, consentendo la spline rendere il percorso di minima curvatura totale. Con valori di tensione maggiori di 1, la curva si comporta come una molla compressa, inserito un percorso più lungo.  
  
 ![Spline di tipo Cardinal](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art10.gif "Aboutgdip02_art10")  
  
 Le quattro spline mostrate nell'illustrazione precedente condividono la stessa tangente in corrispondenza del punto inizia. La tangente è la riga disegnata dal punto di partenza al successivo punto della curva. Analogamente, la tangente condivisa al punto finale è la riga disegnata dal punto di fine al punto precedente della curva.  
  
 Per tracciare una spline di tipo cardinal, sono necessari un'istanza del <xref:System.Drawing.Graphics> (classe), un <xref:System.Drawing.Pen>e una matrice di <xref:System.Drawing.Point> l'istanza di oggetti il <xref:System.Drawing.Graphics> classe fornisce il <xref:System.Drawing.Graphics.DrawCurve%2A> metodo, che consente di disegnare spline, e <xref:System.Drawing.Pen> Archivia gli attributi di spline di tipo, ad esempio spessore e colore. Matrice di <xref:System.Drawing.Point> oggetti archivia i punti che verrà passati la curva. Esempio di codice seguente mostra come disegnare spline di tipo cardinal che passano attraverso i punti in `myPointArray`. Il terzo parametro è la tensione.  
  
 [!code-csharp[LinesCurvesAndShapes#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#31)]
 [!code-vb[LinesCurvesAndShapes#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#31)]  
  
## <a name="see-also"></a>Vedere anche  
 [Linee, curve e forme](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Costruzione e creazione di curve](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)
