---
title: 'Procedura: creare una sfumatura percorso'
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
- path gradients [Windows Forms], creating
- gradients [Windows Forms], creating path
- graphics paths [Windows Forms], creating gradient
ms.assetid: 1948e834-e104-481c-b71d-d8aa9e4d106e
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6222b22ea0bb38ea95304d43a6dab0deee0d2d05
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-create-a-path-gradient"></a>Procedura: creare una sfumatura percorso
La <xref:System.Drawing.Drawing2D.PathGradientBrush> classe consente di personalizzare il modo in cui si riempie una forma con gradualmente la modifica dei colori. Ad esempio, è possibile specificare un colore per il centro di un percorso e un altro colore per il limite di un percorso. È anche possibile specificare i colori separati per ognuno dei vari punti lungo il bordo di un percorso.  
  
> [!NOTE]
>  In [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], un percorso è una sequenza di linee e curve gestita da un <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto. Per ulteriori informazioni su [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] percorsi, vedere [percorsi di oggetti Graphics in GDI+](../../../../docs/framework/winforms/advanced/graphics-paths-in-gdi.md) e [costruzione e creazione di percorsi](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md).  
  
### <a name="to-fill-an-ellipse-with-a-path-gradient"></a>Per compilare un'ellisse con una sfumatura percorso  
  
-   Nell'esempio seguente inserisce un'ellisse con un pennello a sfumatura. Colore centrale è impostato su blu e il colore del limite è impostato su verde acqua. Nella figura seguente mostra l'ellisse piena.  
  
     ![Percorso sfumatura](../../../../docs/framework/winforms/advanced/media/pathgradient1.png "pathgradient1")  
  
     Per impostazione predefinita, un pennello a sfumatura non estende oltre i limiti del percorso. Se si utilizza il pennello a sfumatura per riempire una figura che si estende oltre il limite del percorso, l'area dello schermo all'esterno del tracciato non essere compilato.  
  
     La figura seguente mostra cosa accade se si modifica il <xref:System.Drawing.Graphics.FillEllipse%2A> nel codice seguente per chiamare `e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)`.  
  
     ![Percorso sfumatura](../../../../docs/framework/winforms/advanced/media/pathgradient2.png "pathgradient2")  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#11)]
     [!code-vb[System.Drawing.UsingaGradientBrush#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#11)]  
  
     L'esempio di codice precedente è progettato per l'uso con Windows Form e richiede la <xref:System.Windows.Forms.PaintEventArgs> e, un parametro di <xref:System.Windows.Forms.PaintEventHandler>.  
  
### <a name="to-specify-points-on-the-boundary"></a>Per specificare i punti in corrispondenza del limite  
  
-   L'esempio seguente crea un pennello a sfumatura percorso da un percorso a forma di stella. Il codice imposta la <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A> proprietà, che imposta il colore al centro della stella in rosso. Il codice imposta quindi la <xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A> proprietà per specificare colori diversi (archiviati nel `colors` matrice) in corrispondenza di singoli punti nel `points` matrice. L'istruzione finale di codice viene compilato il percorso a forma di stella con pennello a sfumatura.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#12)]
     [!code-vb[System.Drawing.UsingaGradientBrush#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#12)]  
  
-   Nell'esempio seguente disegna una sfumatura percorso senza un <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto nel codice. Il particolare <xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A> costruttore nell'esempio riceve una matrice di punti ma non richiede un <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto. Si noti inoltre che il <xref:System.Drawing.Drawing2D.PathGradientBrush> viene utilizzato per riempire un rettangolo, non un percorso. Il rettangolo è maggiore del percorso chiuso utilizzato per definire il pennello, pertanto alcuni del rettangolo non viene disegnato dal pennello. Nella figura seguente viene illustrato il rettangolo (linea tratteggiata) e la parte del rettangolo disegnato usando pennello a sfumatura.  
  
     ![Sfumatura](../../../../docs/framework/winforms/advanced/media/gradient4.png "gradient4")  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#13)]
     [!code-vb[System.Drawing.UsingaGradientBrush#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#13)]  
  
### <a name="to-customize-a-path-gradient"></a>Per personalizzare una sfumatura percorso  
  
-   È possibile personalizzare un pennello sfumatura percorso consiste nell'impostare il relativo <xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A> proprietà. Le scale lo stato attivo per specificano un percorso interno che si trova all'interno del percorso principale. Colore centrale viene visualizzato ovunque all'interno di tale percorso interno anziché solo nel punto centrale.  
  
     Nell'esempio seguente viene creato un pennello a sfumatura percorso in base a un percorso ellittico. Il codice imposta il colore di contorno impostandolo sul blu, imposta il colore centrale azzurro e quindi utilizza il pennello a sfumatura per riempire il percorso ellittico.  
  
     Successivamente, il codice imposta le scale lo stato attivo del pennello a sfumatura percorso. La scala di x lo stato attivo è impostata su 0,3, e la dimensione y è impostata su 0,8. Il codice chiama il <xref:System.Drawing.Graphics.TranslateTransform%2A> metodo di un <xref:System.Drawing.Graphics> oggetto in modo che la successiva chiamata a <xref:System.Drawing.Graphics.FillPath%2A> riempie un'ellisse che si trova a destra della prima ellisse.  
  
     Per visualizzare l'effetto delle scale lo stato attivo, si immagini una piccola ellisse che condivide il centro con i puntini di sospensione principale. Piccola ellisse (interna) è l'ellisse principale scalata orizzontalmente (rispetto al centro) di un fattore di 0,3 e in verticale di un fattore pari a 0,8. Quando si sposta dal limite dell'ellisse esterno ai limiti dell'ellisse interna, il colore cambia gradualmente da blu ad azzurro. Quando si sposta dal limite dell'ellisse interna al centro condiviso, il colore rimane azzurro.  
  
     L'immagine seguente illustra l'output del codice riportato di seguito. I puntini di sospensione a sinistra è azzurra solo nel punto centrale. I puntini di sospensione a destra è azzurra ovunque all'interno del percorso interno.  
  
 ![Sfumatura](../../../../docs/framework/winforms/advanced/media/focusscales1nogamma.png "focusscales1NoGamma")  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#14](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.UsingaGradientBrush#14](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#14)]  
  
### <a name="to-customize-with-interpolation"></a>Per personalizzare mediante interpolazione  
  
-   È inoltre possibile personalizzare un pennello a sfumatura percorso consiste nello specificare una matrice di colori di interpolazione e una matrice di posizioni di interpolazione.  
  
     Nell'esempio seguente viene creato un pennello a sfumatura percorso basato su un triangolo. Il codice imposta la <xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A> proprietà del pennello a sfumatura percorso per specificare una matrice di colori di interpolazione (azzurro verde scuro, blu) e una matrice di posizioni di interpolazione (0, 0.25, 1). Quando si sposta dal limite del triangolo verso il centro, il colore cambia gradualmente da verde a azzurro e quindi da azzurro a blu. La modifica da verde a azzurro avviene al 25% della distanza tra verde e blu.  
  
     Nella figura seguente viene illustrato il triangolo riempito con pennello a sfumatura percorso personalizzato.  
  
     ![Percorso sfumatura](../../../../docs/framework/winforms/advanced/media/pathgradient4.png "pathgradient4")  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#15](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#15)]
     [!code-vb[System.Drawing.UsingaGradientBrush#15](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#15)]  
  
### <a name="to-set-the-center-point"></a>Per impostare il punto centrale  
  
-   Per impostazione predefinita, il punto centrale di un pennello a sfumatura è al centro del percorso utilizzato per costruire il pennello. È possibile modificare il percorso del punto centrale mediante l'impostazione di <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> proprietà la <xref:System.Drawing.Drawing2D.PathGradientBrush> classe.  
  
     Nell'esempio seguente viene creato un pennello a sfumatura percorso basato su un'ellisse. Trova il centro dell'ellisse (70, 35), ma il punto centrale di pennello a sfumatura è impostato su (120, 40).  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#16](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#16)]
     [!code-vb[System.Drawing.UsingaGradientBrush#16](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#16)]  
  
     Nella figura seguente mostra l'ellisse piena e il punto centrale di pennello a sfumatura.  
  
     ![Percorso sfumatura](../../../../docs/framework/winforms/advanced/media/pathgradient5.png "pathgradient5")  
  
-   È possibile impostare il punto centrale di un pennello a sfumatura in una posizione all'esterno del percorso utilizzato per costruire il pennello. Nell'esempio seguente sostituisce la chiamata per impostare il <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> proprietà nel codice precedente.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#17](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#17)]
     [!code-vb[System.Drawing.UsingaGradientBrush#17](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#17)]  
  
     Nella figura seguente mostra l'output con questa modifica.  
  
     ![Percorso sfumatura](../../../../docs/framework/winforms/advanced/media/pathgradient6.png "pathgradient6")  
  
     Nell'illustrazione precedente, i punti all'estrema destra dell'ellisse non sono perfettamente blu (anche se sono molto simili). I colori della sfumatura vengono posizionati come se il riempimento raggiunto il punto (145, 35) in cui il colore sarebbe perfettamente blu (0, 0, 255). Ma non raggiunge mai il riempimento (145, 35) perché un pennello a sfumatura percorso consente di disegnare solo all'interno di percorso.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Negli esempi precedenti sono progettati per l'uso con Windows Form e richiedono <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.  
  
## <a name="see-also"></a>Vedere anche  
 [Uso di un pennello a sfumatura per il riempimento di forme](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)
