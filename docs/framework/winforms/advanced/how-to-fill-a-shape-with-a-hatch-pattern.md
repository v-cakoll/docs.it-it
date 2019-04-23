---
title: 'Procedura: Riempire una forma con un motivo di tratteggio'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- patterns [Windows Forms], adding to shapes
- shapes [Windows Forms], filling with patterns
- brushes [Windows Forms], using hatch brushes
ms.assetid: 9c8300ff-187b-404f-af1f-ebd499f5b16f
ms.openlocfilehash: f5399c4151b335090f4b93be041375b8c2781afa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59118118"
---
# <a name="how-to-fill-a-shape-with-a-hatch-pattern"></a>Procedura: Riempire una forma con un motivo di tratteggio
Un motivo a tratteggio è composto da due colori: uno per lo sfondo e uno per le linee che costituiscono il modello sullo sfondo. Per riempire una forma chiusa con un motivo a tratteggio, utilizzare un <xref:System.Drawing.Drawing2D.HatchBrush> oggetto. Nell'esempio seguente viene illustrato come compilare un'ellisse con un motivo a tratteggio:  
  
## <a name="example"></a>Esempio  
 Il <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> costruttore accetta tre argomenti: il colore di sfondo, il colore della linea di tratteggio e lo stile di tratteggio. L'argomento dello stile di tratteggio può essere qualsiasi valore compreso il <xref:System.Drawing.Drawing2D.HatchStyle> enumerazione. Sono presenti più di 50 elementi nel <xref:System.Drawing.Drawing2D.HatchStyle> enumerazione; alcuni di questi elementi sono visualizzati nell'elenco seguente:  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Vertical>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.BackwardDiagonal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Cross>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.DiagonalCross>  
  
 La figura seguente mostra l'ellisse piena.  
  
 ![Motivo di tratteggio](./media/hatch1.png "hatch1")  
  
 [!code-csharp[System.Drawing.UsingABrush#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.UsingABrush#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs>`e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vedere anche

- [Uso di un oggetto Brush per il riempimento di forme](using-a-brush-to-fill-shapes.md)
