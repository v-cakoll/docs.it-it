---
title: Cenni preliminari sulla grafica vettoriale
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inclusive-inclusive endpoints
- coordinate systems
- graphics [Windows Forms], vector graphics
ms.assetid: 0195df81-66be-452d-bb53-5a582ebfdc09
ms.openlocfilehash: 9c854d8742e50a7136455da72a239623fb0c0d91
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64639751"
---
# <a name="vector-graphics-overview"></a>Cenni preliminari sulla grafica vettoriale
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Consente di disegnare linee, rettangoli e le altre forme in un sistema di coordinate. È possibile scegliere tra un'ampia gamma di sistemi di coordinate, ma il sistema di coordinate predefinito è l'origine nell'angolo superiore sinistro con l'asse x che punta a destra e l'asse y rivolta verso il basso. L'unità di misura nel sistema di coordinate predefinito è il pixel.  
  
## <a name="the-building-blocks-of-gdi"></a>I blocchi predefiniti di GDI+  
 ![Grafica vettoriale](./media/aboutgdip02-art01.gif "AboutGdip02_Art01")  
  
 Un monitor del computer consente di creare una visualizzazione personalizzata in una matrice rettangolare di punti definiti elementi immagine o pixel. Il numero di pixel visualizzati sullo schermo varia da un monitor alla successiva e il numero di pixel visualizzati su un monitor specifico può essere configurato in una certa misura in genere dall'utente.  
  
 ![Grafica vettoriale](./media/aboutgdip02-art02.gif "AboutGdip02_Art02")  
  
 Quando si usa [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] per disegnare una riga, nel rettangolo o curve, si forniscono alcune informazioni essenziali sull'elemento da disegnare. Ad esempio, è possibile specificare una riga, fornendo due punti ed è possibile specificare un rettangolo, fornendo un punto, un'altezza e una larghezza. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] funziona in combinazione con il software dei driver di visualizzazione per determinare i pixel che devono essere attivati per mostrare la riga, nel rettangolo o curva. La figura seguente mostra i pixel che vengano impostati su on per visualizzare una linea dal punto (4, 2) per il punto (12, 8).  
  
 ![Grafica vettoriale](./media/aboutgdip02-art03.gif "AboutGdip02_Art03")  
  
 Nel corso del tempo, determinati componenti di base sono rivelati a essere più utili per la creazione di immagini bidimensionale. Questi blocchi predefiniti, che sono tutti supportati da [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], vengono forniti nell'elenco seguente:  
  
- Linee  
  
- Rettangoli  
  
- Puntini di sospensione  
  
- Archi  
  
- Poligoni  
  
- Spline cardinali  
  
- spline di Bézier  
  
## <a name="methods-for-drawing-with-a-graphics-object"></a>Metodi per il disegno con un oggetto Graphics  
 Il <xref:System.Drawing.Graphics> classe [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] fornisce i seguenti metodi di disegno degli elementi nell'elenco precedente: <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawRectangle%2A>, <xref:System.Drawing.Graphics.DrawEllipse%2A>, <xref:System.Drawing.Graphics.DrawPolygon%2A>, <xref:System.Drawing.Graphics.DrawArc%2A>, <xref:System.Drawing.Graphics.DrawCurve%2A> (per cardinali), e <xref:System.Drawing.Graphics.DrawBezier%2A>. Ognuno di questi metodi è in overload; ogni metodo, ovvero supporta diversi elenchi di parametri diversi. Ad esempio, una variazione del <xref:System.Drawing.Graphics.DrawLine%2A> metodo riceve un <xref:System.Drawing.Pen> oggetto e quattro interi, mentre un'altra variazione del <xref:System.Drawing.Graphics.DrawLine%2A> metodo riceve un <xref:System.Drawing.Pen> oggetto e due <xref:System.Drawing.Point> oggetti.  
  
 I metodi per disegnare linee, rettangoli e spline di Bézier sono associati più metodi che consentono di disegnare vari elementi in una singola chiamata: <xref:System.Drawing.Graphics.DrawLines%2A>, <xref:System.Drawing.Graphics.DrawRectangles%2A>, e <xref:System.Drawing.Graphics.DrawBeziers%2A>. Inoltre, il <xref:System.Drawing.Graphics.DrawCurve%2A> metodo ha un metodo correlato <xref:System.Drawing.Graphics.DrawClosedCurve%2A>, che si chiude una curva connettendo il punto finale della curva per l'avvio di un punto.  
  
 Tutti i metodi di disegno di <xref:System.Drawing.Graphics> classe funzionare in combinazione con un <xref:System.Drawing.Pen> oggetto. Per disegnare qualsiasi elemento, è necessario creare almeno due oggetti: una <xref:System.Drawing.Graphics> oggetto e un <xref:System.Drawing.Pen> oggetto. Il <xref:System.Drawing.Pen> oggetto archivia gli attributi, ad esempio larghezza di riga e il colore dell'elemento da disegnare. Il <xref:System.Drawing.Pen> oggetto viene passato come uno degli argomenti del metodo di disegno. Ad esempio, una variazione del <xref:System.Drawing.Graphics.DrawLine%2A> metodo riceve un <xref:System.Drawing.Pen> oggetto e quattro interi come illustrato nell'esempio seguente, che consente di disegnare un rettangolo con una larghezza pari a 100, con un'altezza pari a 50 e un angolo superiore sinistro del (20, 10):  
  
 [!code-csharp[LinesCurvesAndShapes#11](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#11)]
 [!code-vb[LinesCurvesAndShapes#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#11)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [Linee, curve e forme](lines-curves-and-shapes.md)
- [Procedura: Creare oggetti Graphics per disegnare](how-to-create-graphics-objects-for-drawing.md)
