---
title: Cenni preliminari sulla grafica vettoriale
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inclusive-inclusive endpoints
- coordinate systems
- graphics [Windows Forms], vector graphics
ms.assetid: 0195df81-66be-452d-bb53-5a582ebfdc09
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 603b76c999933f177a9e48ddb819562b8e4dd8f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="vector-graphics-overview"></a>Cenni preliminari sulla grafica vettoriale
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]Consente di disegnare linee, rettangoli e altre forme in un sistema di coordinate. È possibile scegliere tra un'ampia gamma di sistemi di coordinate, ma il sistema di coordinate è l'origine nell'angolo superiore sinistro con l'asse x a destra e l'asse y rivolta verso il basso. L'unità di misura nel sistema di coordinate predefinito è il pixel.  
  
## <a name="the-building-blocks-of-gdi"></a>I blocchi predefiniti di GDI+  
 ![Grafica vettoriale](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art01.gif "AboutGdip02_Art01")  
  
 Un monitor del computer crea la visualizzazione in una matrice rettangolare di punti definiti elementi immagine o pixel. Il numero di pixel che vengono visualizzati sullo schermo varia da un monitor alla successiva e il numero di pixel che vengono visualizzati su un monitor specifico può essere configurato in una certa misura in genere dall'utente.  
  
 ![Grafica vettoriale](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art02.gif "AboutGdip02_Art02")  
  
 Quando si utilizza [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] per disegnare una riga, un rettangolo o una curva, si forniscono determinate informazioni sull'elemento da disegnare. Ad esempio, è possibile specificare una riga, fornendo due punti ed è possibile specificare un rettangolo fornendo un punto, un'altezza e larghezza. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]funziona in combinazione con il software dei driver di visualizzazione per determinare i pixel che devono essere accesi per mostrare la riga, nel rettangolo o curva. Nella figura seguente mostra i pixel che vengono attivati per visualizzare una linea tra il punto (4, 2) per il punto (12, 8).  
  
 ![Grafica vettoriale](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art03.gif "AboutGdip02_Art03")  
  
 Nel corso del tempo, determinati blocchi predefiniti sono rivelati utili per la creazione di immagini bidimensionali. Questi blocchi predefiniti, tutti supportati da [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], figurano nell'elenco seguente:  
  
-   Linee  
  
-   Rettangoli  
  
-   Puntini di sospensione  
  
-   Archi  
  
-   Poligoni  
  
-   Spline cardinali  
  
-   spline di Bézier  
  
## <a name="methods-for-drawing-with-a-graphics-object"></a>Metodi per disegnare con un oggetto Graphics  
 Il <xref:System.Drawing.Graphics> classe [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] fornisce i seguenti metodi di disegno degli elementi nell'elenco precedente: <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawRectangle%2A>, <xref:System.Drawing.Graphics.DrawEllipse%2A>, <xref:System.Drawing.Graphics.DrawPolygon%2A>, <xref:System.Drawing.Graphics.DrawArc%2A>, <xref:System.Drawing.Graphics.DrawCurve%2A> (per spline cardinali), e <xref:System.Drawing.Graphics.DrawBezier%2A>. Ognuno di questi metodi è in overload; ovvero, ogni metodo supporta diversi elenchi di parametri diversi. Ad esempio, una variazione del <xref:System.Drawing.Graphics.DrawLine%2A> metodo riceve un <xref:System.Drawing.Pen> oggetto e quattro valori integer, mentre un'altra variazione del <xref:System.Drawing.Graphics.DrawLine%2A> metodo riceve un <xref:System.Drawing.Pen> oggetto e due <xref:System.Drawing.Point> oggetti.  
  
 I metodi per tracciare linee, rettangoli e spline di Bézier sono associati più metodi che consentono di disegnare diversi elementi in una singola chiamata: <xref:System.Drawing.Graphics.DrawLines%2A>, <xref:System.Drawing.Graphics.DrawRectangles%2A>, e <xref:System.Drawing.Graphics.DrawBeziers%2A>. Inoltre, il <xref:System.Drawing.Graphics.DrawCurve%2A> metodo ha un metodo correlato <xref:System.Drawing.Graphics.DrawClosedCurve%2A>, che si chiude una curva connettendo il punto finale della curva a partire dalla punto.  
  
 Tutti i metodi di disegno di <xref:System.Drawing.Graphics> classe funzionare in combinazione con un <xref:System.Drawing.Pen> oggetto. Per creare qualsiasi oggetto, è necessario creare almeno due oggetti: un <xref:System.Drawing.Graphics> oggetto e un <xref:System.Drawing.Pen> oggetto. Il <xref:System.Drawing.Pen> oggetto archivia gli attributi, ad esempio spessore e colore, dell'elemento da disegnare. Il <xref:System.Drawing.Pen> oggetto viene passato come uno degli argomenti del metodo di disegno. Ad esempio, una variazione del <xref:System.Drawing.Graphics.DrawLine%2A> metodo riceve un <xref:System.Drawing.Pen> oggetto e quattro valori integer, come illustrato nell'esempio seguente, che disegna un rettangolo con una larghezza pari a 100 e un'altezza pari a 50 e un angolo superiore sinistro di (20, 10):  
  
 [!code-csharp[LinesCurvesAndShapes#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#11)]
 [!code-vb[LinesCurvesAndShapes#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#11)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [Linee, curve e forme](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Procedura: Creare oggetti Graphics per disegnare](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)
