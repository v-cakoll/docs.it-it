---
title: 'Procedura: Creare una sfumatura percorso'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- path gradients [Windows Forms], creating
- gradients [Windows Forms], creating path
- graphics paths [Windows Forms], creating gradient
ms.assetid: 1948e834-e104-481c-b71d-d8aa9e4d106e
ms.openlocfilehash: 8399a56fca87704e10456a4cf8109d7c80d4db45
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964409"
---
# <a name="how-to-create-a-path-gradient"></a>Procedura: Creare una sfumatura percorso
La <xref:System.Drawing.Drawing2D.PathGradientBrush> classe consente di personalizzare la modalità di riempimento di una forma con colori gradualmente modificati. Ad esempio, è possibile specificare un colore per il centro di un tracciato e un altro colore per il limite di un percorso. È anche possibile specificare colori distinti per ognuno dei diversi punti lungo il limite di un percorso.  
  
> [!NOTE]
> In GDI+ un percorso è una sequenza di linee e curve gestite da un <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto. Per ulteriori informazioni sui percorsi GDI+, vedere [percorsi grafici in GDI+](graphics-paths-in-gdi.md) , [creazione e](constructing-and-drawing-paths.md)creazione di percorsi.  

Gli esempi in questo articolo sono metodi che vengono chiamati dal gestore <xref:System.Windows.Forms.Control.Paint> eventi di un controllo.  

### <a name="to-fill-an-ellipse-with-a-path-gradient"></a>Per riempire un'ellisse con una sfumatura del tracciato  
  
- Nell'esempio seguente viene riempita un'ellisse con un pennello sfumatura del percorso. Il colore centrale è impostato su blu e il colore limite è impostato su Aqua. Nell'illustrazione seguente viene mostrata l'ellisse piena.  
  
     ![Il percorso sfumatura riempie un'ellisse.](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse.png)  
  
     Per impostazione predefinita, un pennello sfumatura del percorso non si estende al di fuori del limite del percorso. Se si utilizza il pennello sfumatura percorso per riempire una figura che si estende oltre il limite del tracciato, l'area della schermata all'esterno del percorso non verrà compilata.  
  
     La figura seguente mostra cosa accade se si modifica la <xref:System.Drawing.Graphics.FillEllipse%2A?displayProperty=nameWithType> chiamata nel codice seguente in: `e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)`  
  
     ![Tracciato sfumato esteso oltre il limite del percorso.](./media/how-to-create-a-path-gradient/gradient-path-extended-beyond-boundary.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#11)]
     [!code-vb[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#11)]  
  
     L'esempio di codice precedente è progettato per l'uso con Windows Forms e richiede l' <xref:System.Windows.Forms.PaintEventArgs> e, che è un parametro di <xref:System.Windows.Forms.PaintEventHandler>.  
  
### <a name="to-specify-points-on-the-boundary"></a>Per specificare i punti sul limite  
  
- Nell'esempio seguente viene creato un pennello sfumatura tracciato da un percorso a forma di stella. Il codice imposta la <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A> proprietà, che imposta il colore al centro della stella su rosso. Il codice imposta quindi la <xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A> proprietà in modo da specificare vari colori (archiviati `colors` nella matrice) nei singoli punti della `points` matrice. L'istruzione del codice finale riempie il tracciato a forma di stella con il pennello sfumatura del percorso.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#12)]
     [!code-vb[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#12)]  
  
- Nell'esempio seguente viene disegnata una sfumatura <xref:System.Drawing.Drawing2D.GraphicsPath> del percorso senza un oggetto nel codice. Il costruttore <xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A> specifico nell'esempio riceve una matrice di punti ma non richiede un <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto. Si noti inoltre che l' <xref:System.Drawing.Drawing2D.PathGradientBrush> oggetto viene utilizzato per riempire un rettangolo, non un percorso. Il rettangolo è più grande del percorso chiuso usato per definire il pennello, quindi parte del rettangolo non viene disegnata dal pennello. Nella figura seguente viene illustrato il rettangolo (linea tratteggiata) e la parte del rettangolo disegnata dal pennello sfumatura tracciato: 
  
     ![Parte sfumata disegnata dal pennello sfumatura del percorso.](./media/how-to-create-a-path-gradient/gradient-painted-path-gradient-brush.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#13)]
     [!code-vb[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#13)]  
  
### <a name="to-customize-a-path-gradient"></a>Per personalizzare una sfumatura del tracciato  
  
- Un modo per personalizzare un pennello sfumatura del tracciato consiste nell' <xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A> impostarne la proprietà. Le scale dello stato attivo specificano un percorso interno che si trova all'interno del percorso principale. Il colore centrale viene visualizzato ovunque all'interno del percorso interno anziché solo al punto centrale.  
  
     Nell'esempio seguente viene creato un pennello sfumatura del percorso basato su un percorso ellittico. Il codice imposta il colore limite su blu, imposta il colore centrale su Aqua, quindi usa il pennello sfumatura tracciato per riempire il percorso ellittico.  
  
     Il codice imposta quindi le scale dello stato attivo del pennello sfumatura del percorso. La scala dello stato attivo x è impostata su 0,3 e la scala dello stato attivo y è impostata su 0,8. Il codice chiama il <xref:System.Drawing.Graphics.TranslateTransform%2A> metodo di un <xref:System.Drawing.Graphics> oggetto in modo <xref:System.Drawing.Graphics.FillPath%2A> che la chiamata successiva Compili un'ellisse che si trova a destra della prima ellisse.  
  
     Per visualizzare l'effetto delle scale di messa a fuoco, Immaginate una piccola ellisse che condivide il centro con l'ellisse principale. L'ellisse (interna) di piccole dimensioni è l'ellisse principale ridimensionata orizzontalmente (attorno al centro) per un fattore di 0,3 e verticalmente in base a un fattore di 0,8. Quando si passa dal limite dell'ellisse esterna al limite dell'ellisse interna, il colore passa gradualmente da blu a Aqua. Quando si passa dal limite dell'ellisse interna al centro condiviso, il colore rimane Aqua.  
  
     L'immagine seguente illustra l'output del codice riportato di seguito. L'ellisse a sinistra è Aqua solo al punto centrale. L'ellisse a destra è Aqua ovunque all'interno del percorso interno.  
  
 ![Effetto sfumatura delle scale dello stato attivo](./media/how-to-create-a-path-gradient/focus-scales-aqua-inner-outer-ellipse.png)  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#14)]  
  
### <a name="to-customize-with-interpolation"></a>Per personalizzare con l'interpolazione  
  
- Un altro modo per personalizzare un pennello sfumatura del tracciato consiste nel specificare una matrice di colori di interpolazione e una matrice di posizioni di interpolazione.  
  
     Nell'esempio seguente viene creato un pennello sfumatura del percorso basato su un triangolo. Il codice imposta la <xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A> proprietà del pennello sfumatura percorso per specificare una matrice di colori di interpolazione (verde scuro, Aqua, blu) e una matrice di posizioni di interpolazione (0, 0,25, 1). Quando si passa dal limite del triangolo al punto centrale, il colore cambia gradualmente da verde scuro a Aqua e quindi da Aqua a blu. Il passaggio da verde scuro a Aqua avviene nel 25% della distanza dal verde scuro al blu.  
  
     Nella figura seguente viene illustrato il triangolo riempito con il pennello sfumatura percorso personalizzato.  
  
     ![Triangolo riempito con pennello sfumatura percorso personalizzato.](./media/how-to-create-a-path-gradient/gradient-brush-filled-triangle.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#15)]
     [!code-vb[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#15)]  
  
### <a name="to-set-the-center-point"></a>Per impostare il punto centrale  
  
- Per impostazione predefinita, il punto centrale di un pennello sfumatura del tracciato si trova al centro del tracciato usato per costruire il pennello. È possibile modificare la posizione del punto centrale impostando la <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> proprietà <xref:System.Drawing.Drawing2D.PathGradientBrush> della classe.  
  
     Nell'esempio seguente viene creato un pennello sfumatura del percorso basato su un'ellisse. Il centro dell'ellisse si trova in (70, 35), ma il punto centrale del pennello sfumatura del tracciato è impostato su (120, 40).  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#16)]
     [!code-vb[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#16)]  
  
     Nella figura seguente vengono illustrati l'ellisse piena e il punto centrale del pennello sfumatura tracciato:  
  
     ![Percorso sfumato con ellisse riempita e punto centrale.](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse-center-point.png)  
  
- È possibile impostare il punto centrale di un pennello sfumatura tracciato su una posizione esterna al percorso utilizzato per costruire il pennello. Nell'esempio seguente viene sostituita la chiamata per <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> impostare la proprietà nel codice precedente.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#17)]
     [!code-vb[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#17)]  
  
     La figura seguente mostra l'output con questa modifica:  
  
     ![Tracciato sfumato con punto centrale esterno al percorso.](./media/how-to-create-a-path-gradient/gradient-path-center-point-outside.png)  
  
     Nell'illustrazione precedente, i punti all'estrema destra dell'ellisse non sono puri blu (anche se sono molto vicini). I colori della sfumatura sono posizionati come se il riempimento raggiungesse il punto (145, 35) dove il colore sarebbe un blu puro (0, 0, 255). Tuttavia, il riempimento non raggiunge mai (145, 35) perché un pennello sfumatura del percorso disegna solo all'interno del percorso.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Gli esempi precedenti sono progettati per l'uso con Windows Forms e richiedono <xref:System.Windows.Forms.PaintEventArgs> `e`, che <xref:System.Windows.Forms.Control.Paint> è un parametro del gestore eventi.  
  
## <a name="see-also"></a>Vedere anche

- [Uso di un pennello a sfumatura per il riempimento di forme](using-a-gradient-brush-to-fill-shapes.md)
