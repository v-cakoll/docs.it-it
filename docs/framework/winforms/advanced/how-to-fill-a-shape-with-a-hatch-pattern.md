---
title: 'Procedura: riempire una forma con un motivo a tratteggio'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- patterns [Windows Forms], adding to shapes
- shapes [Windows Forms], filling with patterns
- brushes [Windows Forms], using hatch brushes
ms.assetid: 9c8300ff-187b-404f-af1f-ebd499f5b16f
ms.openlocfilehash: b80708f0ce722b1809fe49190639231e7e4c8329
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320063"
---
# <a name="how-to-fill-a-shape-with-a-hatch-pattern"></a>Procedura: riempire una forma con un motivo a tratteggio
Un modello di tratteggio è costituito da due colori: uno per lo sfondo e uno per le linee che formano il modello sullo sfondo. Per riempire una forma chiusa con un motivo di tratteggio, usare un oggetto <xref:System.Drawing.Drawing2D.HatchBrush>. Nell'esempio seguente viene illustrato come riempire un'ellisse con un motivo di tratteggio:  
  
## <a name="example"></a>Esempio  
 Il costruttore <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> accetta tre argomenti: lo stile di tratteggio, il colore della linea di tratteggio e il colore dello sfondo. L'argomento dello stile di tratteggio può essere qualsiasi valore dell'enumerazione <xref:System.Drawing.Drawing2D.HatchStyle>. Sono presenti più di 50 elementi nell'enumerazione <xref:System.Drawing.Drawing2D.HatchStyle>; alcuni di questi elementi sono illustrati nell'elenco seguente:  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Vertical>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.BackwardDiagonal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Cross>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.DiagonalCross>  
  
 Nell'illustrazione seguente viene mostrata l'ellisse piena.  
  
  ![Screenshot dell'aspetto di un'ellisse riempita con un modello di tratteggio.](./media/how-to-fill-a-shape-with-a-hatch-pattern/ellipse-filled-hatch.png "hatch1")
  
 [!code-csharp[System.Drawing.UsingABrush#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.UsingABrush#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs>`e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vedere anche

- [Uso di un oggetto Brush per il riempimento di forme](using-a-brush-to-fill-shapes.md)
