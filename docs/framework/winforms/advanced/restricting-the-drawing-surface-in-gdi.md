---
title: Limitazione della superficie di disegno in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, clipping
- clipping [Windows Forms], using GDI+
- GDI+, restricting drawing surface
ms.assetid: 8b5f71d9-d2f0-4540-9c41-740f90fd4c26
ms.openlocfilehash: da12ece815d8ae9d1f974b02198498b250885843
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57717116"
---
# <a name="restricting-the-drawing-surface-in-gdi"></a>Limitazione della superficie di disegno in GDI+
Ritaglio comporta la limitazione di disegno per una determinata rettangolo o area geografica. La figura seguente mostra la stringa "Hello" ritagliata a un'area a forma di cuore.  
  
 ![Nell'area di disegno limitata](./media/aboutgdip02-art30.gif "AboutGdip02_Art30")  
  
## <a name="clipping-with-regions"></a>Le aree di visualizzazione  
 Aree possono essere costruite da percorsi e i percorsi possono contenere i contorni di stringhe, pertanto è possibile utilizzare testo con contorni di ritaglio. La figura seguente mostra un set di puntini di sospensione concentrici ritagliati all'interno di una stringa di testo.  
  
 ![Nell'area di disegno limitata](./media/aboutgdip02-art31.gif "AboutGdip02_Art31")  
  
 Per disegnare con ridimensionamento, creare un <xref:System.Drawing.Graphics> dell'oggetto, impostare relativi <xref:System.Drawing.Graphics.Clip%2A> proprietà, quindi chiamare i metodi di disegno di tale stesso <xref:System.Drawing.Graphics> oggetto:  
  
 [!code-csharp[LinesCurvesAndShapes#91](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#91)]
 [!code-vb[LinesCurvesAndShapes#91](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#91)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Region?displayProperty=nameWithType>
- [Linee, curve e forme](lines-curves-and-shapes.md)
- [Uso delle regioni](using-regions.md)
