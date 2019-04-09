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
ms.openlocfilehash: 31a8c68f382f81da2acac363bba6c8822e535770
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186095"
---
# <a name="how-to-create-a-path-gradient"></a>Procedura: Creare una sfumatura percorso
Il <xref:System.Drawing.Drawing2D.PathGradientBrush> classe consente di personalizzare il modo in cui riempire una forma con gradualmente la modifica dei colori. Ad esempio, è possibile specificare un colore per il centro di un percorso e un altro per il limite di un percorso. È anche possibile specificare colori separati per ognuno dei vari punti lungo il bordo di un percorso.  
  
> [!NOTE]
>  Nelle [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], un percorso è una sequenza di linee e curve gestita da un <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto. Per altre informazioni sulle [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] percorsi, vedere [percorsi di oggetti Graphics in GDI+](graphics-paths-in-gdi.md) e [costruzione e creazione di percorsi](constructing-and-drawing-paths.md).  
  
### <a name="to-fill-an-ellipse-with-a-path-gradient"></a>Per compilare un'ellisse con una sfumatura percorso  
  
-   Nell'esempio seguente viene compilato un'ellisse con un pennello a sfumatura. Colore centrale è impostato su blu e il colore del limite è impostato su azzurro. La figura seguente mostra l'ellisse piena.  
  
     ![Percorso sfumatura riempimento di un'ellisse.](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse.png)  
  
     Per impostazione predefinita, un pennello a sfumatura non si estende all'esterno dei limiti del percorso. Se si usa il pennello a sfumatura per riempire una figura di seguito che si estende oltre il limite del percorso, l'area dello schermo all'esterno del percorso non essere compilato.  
  
     La figura seguente mostra cosa accade se si modifica il <xref:System.Drawing.Graphics.FillEllipse%2A> chiamare il codice seguente a `e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)`:  
  
     ![Percorso sfumatura estesa oltre i limiti del percorso.](./media/how-to-create-a-path-gradient/gradient-path-extended-beyond-boundary.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#11)]
     [!code-vb[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#11)]  
  
     Esempio di codice precedente è progettato per l'uso con Windows Form e richiede la <xref:System.Windows.Forms.PaintEventArgs> e, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.  
  
### <a name="to-specify-points-on-the-boundary"></a>Per specificare i punti in corrispondenza del limite  
  
-   Nell'esempio seguente crea un pennello a sfumatura da un percorso a forma di stella. Il codice imposta il <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A> proprietà, che imposta il colore al centro della stella e impostato su rosso. Il codice imposta quindi il <xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A> proprietà per specificare diversi colori (archiviati nel `colors` matrice) a singoli punti nel `points` matrice. L'istruzione di codice finale riempie il percorso a forma di stella con pennello a sfumatura.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#12)]
     [!code-vb[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#12)]  
  
-   L'esempio seguente disegna una sfumatura percorso senza un <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto nel codice. Il particolare <xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A> costruttore nell'esempio riceve una matrice di punti, ma non richiede un <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto. Si noti inoltre che il <xref:System.Drawing.Drawing2D.PathGradientBrush> utilizzato per riempire un rettangolo, non un percorso. Il rettangolo è maggiore di tracciato chiuso usata per definire il pennello, in modo da parte del rettangolo non viene disegnato dal pennello. La figura seguente mostra il rettangolo (linea tratteggiata) e la parte del rettangolo disegnato dal pennello a sfumatura: 
  
     ![Sfumatura parte disegnato dal pennello a sfumatura.](./media/how-to-create-a-path-gradient/gradient-painted-path-gradient-brush.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#13)]
     [!code-vb[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#13)]  
  
### <a name="to-customize-a-path-gradient"></a>Per personalizzare una sfumatura percorso  
  
-   Un modo per personalizzare un pennello a sfumatura consiste nell'impostare relativo <xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A> proprietà. Le proporzioni del fuoco specificano un percorso interno che si trova all'interno del percorso principale. Colore centrale viene visualizzato ovunque all'interno di tale percorso interno e non solo al punto centrale.  
  
     L'esempio seguente crea un pennello a sfumatura in base a un percorso ellittico. Il codice imposta il colore di contorno impostandolo sul blu, imposta il colore centrale azzurro per e quindi Usa il pennello a sfumatura per riempire il percorso ellittico.  
  
     Successivamente, il codice imposta le proporzioni del fuoco di pennello a sfumatura. La scala di messa a fuoco x è impostata su 0.3 e la dimensione y è impostata su 0,8. Il codice chiama il <xref:System.Drawing.Graphics.TranslateTransform%2A> metodo di un <xref:System.Drawing.Graphics> oggetto in modo che la chiamata successiva al <xref:System.Drawing.Graphics.FillPath%2A> riempie un'ellisse che si trova a destra della prima ellisse.  
  
     Per visualizzare l'effetto delle scale lo stato attivo, si immagini una piccola ellisse che condivide al proprio centro con i puntini di sospensione principale. Piccola puntini di sospensione (interno) è l'ellisse principale scalata orizzontalmente (intorno al relativo centro) di un fattore di 0.3 e in verticale di un fattore pari a 0,8. Quando si sposta dai limiti dell'ellisse esterno ai limiti dell'ellisse interna, il colore passa gradualmente da blu a verde acqua. Quando si spostano dal limite dell'ellisse interna al centro condiviso, resta il colore azzurro.  
  
     L'immagine seguente illustra l'output del codice riportato di seguito. Puntini di sospensione a sinistra è aqua solo al punto centrale. Puntini di sospensione a destra è aqua ovunque all'interno del tracciato interno.  
  
 ![Effetto sfumatura delle scale messa a fuoco](./media/how-to-create-a-path-gradient/focus-scales-aqua-inner-outer-ellipse.png)  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#14)]  
  
### <a name="to-customize-with-interpolation"></a>Personalizzare con interpolazione  
  
-   Un altro modo per personalizzare un pennello a sfumatura consiste nello specificare una matrice di colori interpolazione e una matrice di posizioni di interpolazione.  
  
     L'esempio seguente crea un pennello a sfumatura basato su un triangolo. Il codice imposta il <xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A> proprietà del pennello a sfumatura path per specificare una matrice di colori di interpolazione (azzurro verde scuro, blu) e una matrice di posizioni di interpolazione (0, 0.25, 1). Quando si sposta dai limiti del triangolo per il punto centrale, il colore cambia gradualmente da verde a aqua e quindi da aqua impostandolo sul blu. La modifica da verde a aqua avviene in 25 percento della distanza da verde a blu.  
  
     La figura seguente mostra il triangolo riempito con il pennello a sfumatura percorso personalizzato.  
  
     ![Triangolo riempita con pennello sfumato percorso personalizzato.](./media/how-to-create-a-path-gradient/gradient-brush-filled-triangle.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#15)]
     [!code-vb[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#15)]  
  
### <a name="to-set-the-center-point"></a>Per impostare il punto centrale  
  
-   Per impostazione predefinita, il punto centrale di un pennello a sfumatura è al centro del percorso usato per costruire il pennello. È possibile modificare la posizione del punto centrale impostando il <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> proprietà del <xref:System.Drawing.Drawing2D.PathGradientBrush> classe.  
  
     L'esempio seguente crea un pennello a sfumatura basato su un'ellisse. È il centro dell'ellisse (70, 35), ma il punto centrale di pennello a sfumatura è impostato su (120, 40).  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#16)]
     [!code-vb[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#16)]  
  
     La figura seguente mostra l'ellisse con riempimento e il punto centrale di pennello a sfumatura:  
  
     ![Percorso sfumatura con colorato puntini di sospensione e il punto centrale.](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse-center-point.png)  
  
-   È possibile impostare il punto centrale di un pennello a sfumatura in una posizione all'esterno del percorso che è stato usato per costruire il pennello. Nell'esempio seguente sostituisce la chiamata per impostare il <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> proprietà nel codice precedente.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#17)]
     [!code-vb[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#17)]  
  
     Nella figura seguente mostra l'output con questa modifica:  
  
     ![Percorso sfumatura con punto centrale all'esterno del percorso.](./media/how-to-create-a-path-gradient/gradient-path-center-point-outside.png)  
  
     Nella figura precedente, i punti all'estrema destra dell'ellisse non sono perfettamente blu (anche se sono molto simili). I colori nella sfumatura vengono posizionati come se il riempimento raggiunto il punto (145, 35) in cui il colore sarebbe pure blu (0, 0, 255). Ma non raggiunga mai il riempimento (145, 35) perché consente di disegnare un pennello a sfumatura solo all'interno di relativo percorso.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Negli esempi precedenti sono progettati per l'uso con Windows Form, e richiedono <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.  
  
## <a name="see-also"></a>Vedere anche

- [Utilizzo di un pennello a sfumatura per il riempimento di forme](using-a-gradient-brush-to-fill-shapes.md)
