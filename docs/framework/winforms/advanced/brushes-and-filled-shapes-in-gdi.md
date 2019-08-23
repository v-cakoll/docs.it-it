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
ms.openlocfilehash: 45ef0b5920e43300e047d363149ea10a7833477b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912225"
---
# <a name="brushes-and-filled-shapes-in-gdi"></a>Pennelli e forme con riempimento in GDI+
Una forma chiusa, ad esempio un rettangolo o un'ellisse, è costituita da un contorno e da una parte interna. Il contorno viene disegnato con una penna e l'interno è riempito da un pennello. In GDI+ sono disponibili diverse classi di pennelli per riempire le parti <xref:System.Drawing.SolidBrush>interne <xref:System.Drawing.Drawing2D.HatchBrush>delle <xref:System.Drawing.TextureBrush>forme <xref:System.Drawing.Drawing2D.LinearGradientBrush>chiuse, <xref:System.Drawing.Drawing2D.PathGradientBrush>ovvero,,, e. Tutte le classi ereditano dalla <xref:System.Drawing.Brush> classe. Nella figura seguente viene illustrato un rettangolo riempito con un pennello a tinta unita e un'ellisse riempita con un pennello di tratteggio.  
  
 ![Forme piene](./media/aboutgdip02-art17.gif "Aboutgdip02_art17")  
  
## <a name="solid-brushes"></a>Pennelli a tinta unita  
 Per riempire una forma chiusa, è necessario disporre di un'istanza <xref:System.Drawing.Graphics> della classe e <xref:System.Drawing.Brush>di un oggetto. L'istanza della <xref:System.Drawing.Graphics> classe fornisce metodi, <xref:System.Drawing.Graphics.FillRectangle%2A> ad esempio e <xref:System.Drawing.Graphics.FillEllipse%2A>, e archivia gli <xref:System.Drawing.Brush> attributi del riempimento, ad esempio il colore e il motivo. <xref:System.Drawing.Brush> Viene passato come uno degli argomenti del metodo Fill. Nell'esempio di codice seguente viene illustrato come riempire un'ellisse con un colore rosso a tinta unita.  
  
 [!code-csharp[LinesCurvesAndShapes#121](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#121)]
 [!code-vb[LinesCurvesAndShapes#121](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#121)]  
  
> [!NOTE]
> Nell'esempio precedente, il pennello è di tipo <xref:System.Drawing.SolidBrush>, che eredita da. <xref:System.Drawing.Brush>  
  
## <a name="hatch-brushes"></a>Pennelli tratteggiati  
 Quando si riempie una forma con un pennello tratteggiato, è necessario specificare un colore di primo piano, un colore di sfondo e uno stile di tratteggio. Il colore di primo piano è il colore del tratteggio.  
  
 [!code-csharp[LinesCurvesAndShapes#122](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#122)]
 [!code-vb[LinesCurvesAndShapes#122](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#122)]  
  
 GDI+ fornisce più di 50 stili di tratteggio; i tre stili illustrati nella figura seguente sono <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>, <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>e <xref:System.Drawing.Drawing2D.HatchStyle.Cross>.  
  
 ![Forme piene](./media/aboutgdip02-art18.gif "Aboutgdip02_art18")  
  
## <a name="texture-brushes"></a>Pennelli trama  
 Con un pennello trama è possibile riempire una forma con un modello archiviato in una bitmap. Si supponga, ad esempio, che l'immagine seguente venga archiviata in `MyTexture.bmp`un file su disco denominato.  
  
 ![Forma riempita](./media/aboutgdip02-art19.gif "Aboutgdip02_Art19")  
  
 Nell'esempio di codice seguente viene illustrato come riempire un'ellisse ripetendo l' `MyTexture.bmp`immagine archiviata in.  
  
 [!code-csharp[LinesCurvesAndShapes#123](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#123)]
 [!code-vb[LinesCurvesAndShapes#123](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#123)]  
  
 Nell'illustrazione seguente viene mostrata l'ellisse piena.  
  
 ![Forma riempita](./media/aboutgdip02-art20.gif "AboutGdip02_Art20")  
  
## <a name="gradient-brushes"></a>Pennelli sfumatura  
 GDI+ fornisce due tipi di pennelli sfumatura: lineare e percorso. È possibile utilizzare un pennello sfumato lineare per riempire una forma con un colore che cambia gradualmente man mano che si sposta la forma orizzontalmente, verticalmente o in diagonale. Nell'esempio di codice seguente viene illustrato come riempire un'ellisse con un pennello sfumato orizzontale che passa da blu a verde mentre si sposta dal bordo sinistro dell'ellisse al bordo destro.  
  
 [!code-csharp[LinesCurvesAndShapes#124](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#124)]
 [!code-vb[LinesCurvesAndShapes#124](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#124)]  
  
 Nell'illustrazione seguente viene mostrata l'ellisse piena.  
  
 ![Forma riempita](./media/aboutgdip02-art21.gif "AboutGdip02_Art21")  
  
 Un pennello sfumatura percorso può essere configurato per modificare il colore mentre si sposta dal centro di una forma verso il bordo.  
  
 ![Forma riempita](./media/aboutgdip02-art22.gif "AboutGdip02_Art22")  
  
 I pennelli sfumatura del percorso sono piuttosto flessibili. Il pennello sfumatura utilizzato per riempire il triangolo nell'illustrazione seguente passa gradualmente da rosso al centro a ognuno dei tre colori diversi nei vertici.  
  
 ![Forma riempita](./media/aboutgdip02-art23.gif "AboutGdip02_Art23")  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.SolidBrush?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.HatchBrush?displayProperty=nameWithType>
- <xref:System.Drawing.TextureBrush?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>
- [Linee, curve e forme](lines-curves-and-shapes.md)
- [Procedura: Creare un rettangolo pieno in un Windows Form](how-to-draw-a-filled-rectangle-on-a-windows-form.md)
- [Procedura: Creare un'ellisse piena in un Windows Form](how-to-draw-a-filled-ellipse-on-a-windows-form.md)
