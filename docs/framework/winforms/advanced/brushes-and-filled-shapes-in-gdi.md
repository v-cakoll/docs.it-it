---
title: Pennelli e forme con riempimento in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [Windows Forms], GDI+
- filled shapes [Windows Forms], GDI+
- shapes [Windows Forms], GDI+
- GDI+, brushes
- GDI+, filled shapes
- gradient brushes
- brushes [Windows Forms], gradient
ms.assetid: e863e2a7-0294-4130-99b6-f1ea3201e7cd
ms.openlocfilehash: 9475518a5f0422e0eac1ec521088071bb4d1c885
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="brushes-and-filled-shapes-in-gdi"></a>Pennelli e forme con riempimento in GDI+
Una forma chiusa, ad esempio un rettangolo o un'ellisse, è costituito da una struttura e una parte interna. La struttura viene disegnata con una penna e l'interno viene riempito con un pennello. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] fornisce diverse classi di pennelli per il riempimento di forme chiuse: <xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, e <xref:System.Drawing.Drawing2D.PathGradientBrush>. Tutte queste classi di ereditare il <xref:System.Drawing.Brush> classe. Nella figura seguente viene illustrato un rettangolo riempito con un pennello tinta unita e un'ellisse riempita con un pennello di tratteggio.  
  
 ![Forme piene](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art17.gif "Aboutgdip02_art17")  
  
## <a name="solid-brushes"></a>Pennelli tinta unite  
 Per riempire una forma chiusa, sono necessari un'istanza di <xref:System.Drawing.Graphics> classe e un <xref:System.Drawing.Brush>. L'istanza del <xref:System.Drawing.Graphics> classe fornisce i metodi, ad esempio <xref:System.Drawing.Graphics.FillRectangle%2A> e <xref:System.Drawing.Graphics.FillEllipse%2A>e <xref:System.Drawing.Brush> archivia gli attributi del riempimento, ad esempio colore e il motivo. Il <xref:System.Drawing.Brush> viene passato come uno degli argomenti al metodo di riempimento. Esempio di codice seguente viene illustrato come compilare un'ellisse con un colore rosso.  
  
 [!code-csharp[LinesCurvesAndShapes#121](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#121)]
 [!code-vb[LinesCurvesAndShapes#121](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#121)]  
  
> [!NOTE]
>  Nell'esempio precedente, il pennello è di tipo <xref:System.Drawing.SolidBrush>, che eredita da <xref:System.Drawing.Brush>.  
  
## <a name="hatch-brushes"></a>Pennelli per il tratteggio  
 Quando si riempie una forma con un pennello tratteggiato, specificare un colore di primo piano, un colore di sfondo e uno stile di tratteggio. Il colore primo piano è il colore del tratteggio.  
  
 [!code-csharp[LinesCurvesAndShapes#122](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#122)]
 [!code-vb[LinesCurvesAndShapes#122](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#122)]  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] sono disponibili più di 50 stili di tratteggio. i tre stili mostrati nella figura seguente vengono <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>, <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>, e <xref:System.Drawing.Drawing2D.HatchStyle.Cross>.  
  
 ![Forme piene](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art18.gif "Aboutgdip02_art18")  
  
## <a name="texture-brushes"></a>Pennelli della struttura  
 Con un pennello di trama, è possibile riempire una forma con un modello archiviato in una bitmap. Ad esempio, si supponga che l'immagine seguente è memorizzata in un file di disco denominato `MyTexture.bmp`.  
  
 ![Riempito forma](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art19.gif "Aboutgdip02_Art19")  
  
 Esempio di codice seguente viene illustrato come compilare un'ellisse ripetendo l'immagine memorizzata in `MyTexture.bmp`.  
  
 [!code-csharp[LinesCurvesAndShapes#123](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#123)]
 [!code-vb[LinesCurvesAndShapes#123](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#123)]  
  
 Nella figura seguente mostra l'ellisse piena.  
  
 ![Riempito forma](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art20.gif "AboutGdip02_Art20")  
  
## <a name="gradient-brushes"></a>Pennelli per sfumature  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] sono disponibili due tipi di pennelli per sfumature: lineare e il percorso. È possibile utilizzare un pennello sfumato lineare per riempire una forma con colore che cambia gradualmente mentre si sposta lungo la forma orizzontalmente, verticalmente o in diagonale. Esempio di codice seguente viene illustrato come compilare un'ellisse con un pennello sfumato orizzontale che passa da blu a verde si sposta dal bordo sinistro dell'ellisse al bordo destro.  
  
 [!code-csharp[LinesCurvesAndShapes#124](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#124)]
 [!code-vb[LinesCurvesAndShapes#124](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#124)]  
  
 Nella figura seguente mostra l'ellisse piena.  
  
 ![Riempito forma](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art21.gif "AboutGdip02_Art21")  
  
 Pennello sfumatura percorso può essere configurato per cambiare colore quando si sposta dal centro della forma verso il bordo.  
  
 ![Riempito forma](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art22.gif "AboutGdip02_Art22")  
  
 Pennelli per sfumature di percorso sono molto flessibile. Il pennello sfumato usato per riempire il triangolo le seguenti modifiche di illustrazione gradualmente dal colore rosso del centro per ognuno dei tre colori diversi per i vertici.  
  
 ![Riempito forma](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art23.gif "AboutGdip02_Art23")  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Drawing.SolidBrush?displayProperty=nameWithType>  
 <xref:System.Drawing.Drawing2D.HatchBrush?displayProperty=nameWithType>  
 <xref:System.Drawing.TextureBrush?displayProperty=nameWithType>  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>  
 [Linee, curve e forme](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Procedura: Disegnare un rettangolo con riempimento in un Windows Form](../../../../docs/framework/winforms/advanced/how-to-draw-a-filled-rectangle-on-a-windows-form.md)  
 [Procedura: Disegnare un'ellisse con riempimento in un Windows Form](../../../../docs/framework/winforms/advanced/how-to-draw-a-filled-ellipse-on-a-windows-form.md)
