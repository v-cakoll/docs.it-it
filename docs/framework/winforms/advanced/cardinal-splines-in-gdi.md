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
ms.openlocfilehash: 4588f6f606f0f479aeae1d143f23175ec4be32a5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59200415"
---
# <a name="cardinal-splines-in-gdi"></a>Spline di tipo Cardinal in GDI+
Spline di tipo cardinal è una sequenza di curve singole raggruppate per formare una curva di dimensioni maggiori. La spline di tipo è specificato da una matrice di punti e un parametro di tensione. Spline di tipo cardinal passa per ogni punto della matrice; Esistono Nessun angoli acuti e apportare alcuna modifica improvviso la tensione della curva. Nella figura seguente mostra un set di punti e di una spline di tipo cardinal che passa attraverso ogni punto nel set.  
  
 ![Spline cardinale](./media/aboutgdip02-art09.gif "Aboutgdip02_art09")  
  
## <a name="physical-and-mathematical-splines"></a>Spline di tipo fisiche e matematiche  
 Una spline di tipo fisico è un componente thin wood o altro materiale flessibile. Prima dell'avvento di spline di matematiche, finestre di progettazione utilizzato spline fisiche per disegnare curve. Una finestra di progettazione potrebbe inserire la spline di tipo in un foglio di carta e ancorare l'annotazione a un determinato set di punti. La finestra di progettazione è stato possibile creare quindi una curva da lungo la spline con una penna o una matita. Un set specificato di punti perché potrebbe generare un'ampia gamma di curve, a seconda delle proprietà della spline fisica. Ad esempio, una spline di tipo con un'elevata resistenza a curvatura produrrebbe una curva diversa rispetto a spline estremamente flessibile.  
  
 Le formule per la spline di matematiche sono basate sulle proprietà delle aste di perforazione flessibile, in modo che le curve prodotte da spline matematiche sono simili per le curve che sono stati prodotti una volta da spline fisiche. Esattamente come spline fisiche della tensione diversi produrrà curve diverse tramite un set specificato di punti, spline matematiche con valori diversi per il parametro tensione produrrà curve diverse tramite un set specificato di punti. La figura seguente mostra quattro cardinali passando attraverso lo stesso set di punti. Viene mostrata la tensione per ogni spline. Una tensione pari a 0 corrisponde a una tensione fisica infinita, forzando la curva per rendere il modo più breve (linee rette) tra i punti. Una tensione 1 corrisponde a nessun tensione fisica, consentendo la spline di adottare il percorso di curvatura minima totale. Con valori di tensione maggiori di 1, la curva si comporta come una molla compressa, il push per richiedere un percorso più lungo.  
  
 ![Di tipo Cardinal](./media/aboutgdip02-art10.gif "Aboutgdip02_art10")  
  
 La spline di quattro nell'illustrazione precedente condividono la stessa tangente in corrispondenza del punto di partenza. La tangente è la riga disegnata dal punto di partenza al successivo punto lungo la curva. Analogamente, la tangente a condivisa in corrispondenza del punto finale è la riga disegnata dal punto finale al precedente punto sulla curva.  
  
 Per disegnare spline di tipo cardinal, necessaria un'istanza del <xref:System.Drawing.Graphics> (classe), una <xref:System.Drawing.Pen>e una matrice di <xref:System.Drawing.Point> oggetti istanza del <xref:System.Drawing.Graphics> classe fornisce il <xref:System.Drawing.Graphics.DrawCurve%2A> metodo, che consente di disegnare spline, e il <xref:System.Drawing.Pen> Archivia gli attributi di spline di tipo, ad esempio spessore e colore. Matrice di <xref:System.Drawing.Point> gli oggetti vengono archiviati i punti della curva verrà pass-through. Esempio di codice seguente illustra come disegnare spline di tipo cardinal che passa attraverso i punti in `myPointArray`. Il terzo parametro è la tensione.  
  
 [!code-csharp[LinesCurvesAndShapes#31](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#31)]
 [!code-vb[LinesCurvesAndShapes#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#31)]  
  
## <a name="see-also"></a>Vedere anche

- [Linee, curve e forme](lines-curves-and-shapes.md)
- [Costruzione e creazione di curve](constructing-and-drawing-curves.md)
