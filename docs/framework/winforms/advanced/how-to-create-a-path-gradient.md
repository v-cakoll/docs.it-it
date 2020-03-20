---
title: 'Procedura: creare una sfumatura percorso'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- path gradients [Windows Forms], creating
- gradients [Windows Forms], creating path
- graphics paths [Windows Forms], creating gradient
ms.assetid: 1948e834-e104-481c-b71d-d8aa9e4d106e
ms.openlocfilehash: cf4dc558c008fb8adfc327a6a894a428e985df03
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182637"
---
# <a name="how-to-create-a-path-gradient"></a>Procedura: creare una sfumatura percorso
La <xref:System.Drawing.Drawing2D.PathGradientBrush> classe consente di personalizzare il modo in cui si riempie una forma con colori che cambiano gradualmente. Ad esempio, è possibile specificare un colore per il centro di un tracciato e un altro colore per il contorno di un tracciato. È inoltre possibile specificare colori separati per ciascuno dei diversi punti lungo il contorno di un tracciato.  
  
> [!NOTE]
> In GDI, un tracciato è una sequenza <xref:System.Drawing.Drawing2D.GraphicsPath> di linee e curve gestite da un oggetto. Per ulteriori informazioni sui percorsi GDI, vedere [Percorsi grafici in GDI](graphics-paths-in-gdi.md) e [Costruzione di percorsi di disegno e di disegno](constructing-and-drawing-paths.md).  

Gli esempi in questo articolo sono metodi chiamati <xref:System.Windows.Forms.Control.Paint> dal gestore eventi di un controllo.  

### <a name="to-fill-an-ellipse-with-a-path-gradient"></a>Per riempire un'ellisse con una sfumatura del tracciato  
  
- L'esempio seguente riempie un'ellisse con un pennello a sfumatura del tracciato. Il colore centrale è impostato su blu e il colore del contorno è impostato su aqua. La figura seguente mostra l'ellisse riempita.  
  
     ![Percorso sfumato riempie un'ellisse.](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse.png)  
  
     Per impostazione predefinita, un pennello sfumatura percorso non si estende oltre il contorno del tracciato. Se si utilizza il pennello sfumato percorso per riempire una figura che si estende oltre il contorno del tracciato, l'area dello schermo all'esterno del tracciato non verrà riempita.  
  
     Nella figura seguente viene illustrato <xref:System.Drawing.Graphics.FillEllipse%2A?displayProperty=nameWithType> cosa accade se `e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)`si modifica la chiamata nel codice seguente in :  
  
     ![Percorso sfumatura esteso oltre il contorno del tracciato.](./media/how-to-create-a-path-gradient/gradient-path-extended-beyond-boundary.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#11)]
     [!code-vb[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#11)]  
  
     L'esempio di codice precedente è progettato per <xref:System.Windows.Forms.PaintEventArgs> l'utilizzo con Windows <xref:System.Windows.Forms.PaintEventHandler>Form e richiede e , che è un parametro di .  
  
### <a name="to-specify-points-on-the-boundary"></a>Per specificare i punti sul contorno  
  
- L'esempio seguente costruisce un pennello a sfumatura di percorso da un percorso a forma di stella. Il codice <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A> imposta la proprietà , che imposta il colore in corrispondenza del centroide della stella su rosso. Quindi il codice <xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A> imposta la proprietà per `colors` specificare vari colori (memorizzati nella matrice) in corrispondenza dei singoli punti della `points` matrice. L'istruzione di codice finale riempie il percorso a forma di stella con il pennello a sfumatura del percorso.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#12)]
     [!code-vb[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#12)]  
  
- L'esempio seguente disegna <xref:System.Drawing.Drawing2D.GraphicsPath> una sfumatura di percorso senza un oggetto nel codice. Il <xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A> costruttore particolare nell'esempio riceve una matrice <xref:System.Drawing.Drawing2D.GraphicsPath> di punti ma non richiede un oggetto. Si noti <xref:System.Drawing.Drawing2D.PathGradientBrush> inoltre che l'oggetto viene utilizzato per riempire un rettangolo, non un percorso. Il rettangolo è più grande del tracciato chiuso utilizzato per definire il pennello, pertanto parte del rettangolo non viene disegnato dal pennello. La figura seguente mostra il rettangolo (linea tratteggiata) e la parte del rettangolo disegnata dal pennello sfumatura percorso:
  
     ![Porzione sfumata disegnata dal pennello sfumatura percorso.](./media/how-to-create-a-path-gradient/gradient-painted-path-gradient-brush.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#13)]
     [!code-vb[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#13)]  
  
### <a name="to-customize-a-path-gradient"></a>Per personalizzare una sfumatura del tracciato  
  
- Un modo per personalizzare un pennello <xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A> a sfumatura percorso consiste nell'impostarne la proprietà. Le scale di messa a fuoco specificano un percorso interno che si trova all'interno del percorso principale. Il colore centrale viene visualizzato ovunque all'interno di tale percorso interno anziché solo nel punto centrale.  
  
     L'esempio seguente crea un pennello a sfumatura di percorso basato su un percorso ellittico. Il codice imposta il colore del contorno su blu, imposta il colore centrale su aqua, quindi utilizza il pennello sfumato percorso per riempire il percorso ellittico.  
  
     Successivamente, il codice imposta le scale di messa a fuoco del pennello sfumatura percorso. La scala di messa a fuoco x è impostata su 0,3 e la scala di messa a fuoco y è impostata su 0,8.The x focus scale is set to 0.3, and the y focus scale is set to 0.8. Il codice <xref:System.Drawing.Graphics.TranslateTransform%2A> chiama il <xref:System.Drawing.Graphics> metodo di un <xref:System.Drawing.Graphics.FillPath%2A> oggetto in modo che la chiamata successiva a riempia un'ellisse che si trova a destra della prima ellisse.  
  
     Per vedere l'effetto delle scale di messa a fuoco, immaginate una piccola ellisse che condivide il suo centro con l'ellisse principale. L'ellisse piccola (interna) è l'ellisse principale ridimensionata (circa il suo centro) orizzontalmente di un fattore di 0,3 e verticalmente di un fattore di 0,8. Quando ci si sposta dal contorno dell'ellisse esterna al contorno dell'ellisse interna, il colore cambia gradualmente da blu ad acqua. Quando ci si sposta dal contorno dell'ellisse interna al centro condiviso, il colore rimane acqua.  
  
     L'immagine seguente illustra l'output del codice riportato di seguito. L'ellisse a sinistra è acqua solo al punto centrale. L'ellisse a destra è acqua ovunque all'interno del percorso interno.  
  
 ![Effetto sfumatura delle scale di messa a fuoco](./media/how-to-create-a-path-gradient/focus-scales-aqua-inner-outer-ellipse.png)  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#14)]  
  
### <a name="to-customize-with-interpolation"></a>Per personalizzare con l'interpolazione  
  
- Un altro modo per personalizzare un pennello a sfumatura percorso consiste nel specificare una matrice di colori di interpolazione e una matrice di posizioni di interpolazione.  
  
     L'esempio seguente crea un pennello a sfumatura percorso basato su un triangolo. Il codice <xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A> imposta la proprietà del pennello sfumatura percorso per specificare una matrice di colori di interpolazione (verde scuro, acqua, blu) e una matrice di posizioni di interpolazione (0, 0,25, 1). Quando ci si sposta dal contorno del triangolo al punto centrale, il colore cambia gradualmente dal verde scuro all'acqua e quindi dall'acqua al blu. Il passaggio dal verde scuro all'acqua avviene nel 25% della distanza dal verde scuro al blu.  
  
     La figura seguente mostra il triangolo riempito con il pennello sfumato percorso personalizzato.  
  
     ![Triangolo riempito con pennello sfumatura percorso personalizzato.](./media/how-to-create-a-path-gradient/gradient-brush-filled-triangle.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#15)]
     [!code-vb[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#15)]  
  
### <a name="to-set-the-center-point"></a>Per impostare il punto centrale  
  
- Per impostazione predefinita, il punto centrale di un pennello a sfumatura percorso si trova in corrispondenza del centroide del percorso utilizzato per costruire il pennello. È possibile modificare la posizione del <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> punto centrale <xref:System.Drawing.Drawing2D.PathGradientBrush> impostando la proprietà della classe.  
  
     L'esempio seguente crea un pennello a sfumatura percorso basato su un'ellisse. Il centro dell'ellisse è al (70, 35), ma il punto centrale del pennello sfumato percorso è impostato su (120, 40).  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#16)]
     [!code-vb[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#16)]  
  
     La figura seguente mostra l'ellisse riempita e il punto centrale del pennello a sfumatura percorso:  
  
     ![Tracciato sfumato con ellisse e punto centrale riempito.](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse-center-point.png)  
  
- È possibile impostare il punto centrale di un pennello sfumatura percorso su una posizione esterna al percorso utilizzato per costruire il pennello. Nell'esempio seguente viene sostituita <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> la chiamata per impostare la proprietà nel codice precedente.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#17)]
     [!code-vb[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#17)]  
  
     La figura seguente mostra l'output con questa modifica:The following illustration shows the output with this change:  
  
     ![Tracciato sfumato con il punto centrale all'esterno del tracciato.](./media/how-to-create-a-path-gradient/gradient-path-center-point-outside.png)  
  
     Nell'illustrazione precedente, i punti all'estrema destra dell'ellisse non sono blu puro (anche se sono molto vicini). I colori nella sfumatura vengono posizionati come se il riempimento raggiungesse il punto (145, 35) dove il colore sarebbe blu puro (0, 0, 255). Ma il riempimento non raggiunge mai (145, 35) perché un pennello sfumato percorso disegna solo all'interno del suo percorso.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Gli esempi precedenti sono progettati per l'utilizzo <xref:System.Windows.Forms.PaintEventArgs> `e`con Windows Form <xref:System.Windows.Forms.Control.Paint> e richiedono , che è un parametro del gestore eventi.  
  
## <a name="see-also"></a>Vedere anche

- [Utilizzo di un pennello a sfumatura per il riempimento di forme](using-a-gradient-brush-to-fill-shapes.md)
