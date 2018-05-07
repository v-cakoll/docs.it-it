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
ms.openlocfilehash: b457e94acb334dc012f017090c63189de372592d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="restricting-the-drawing-surface-in-gdi"></a>Limitazione della superficie di disegno in GDI+
Il ritaglio implica la restrizione di disegno per un determinato rettangolo o un'area. Nella figura seguente mostra la stringa "Hello" troncato a un'area a forma di cuore.  
  
 ![Superficie di disegno limitata](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art30.gif "AboutGdip02_Art30")  
  
## <a name="clipping-with-regions"></a>Le aree di visualizzazione  
 Aree possono essere costruite da percorsi e i percorsi possono contenere le strutture delle stringhe, pertanto è possibile utilizzare testo strutturato per il ritaglio. Nella figura seguente viene illustrato un set di ellissi concentriche troncato all'interno di una stringa di testo.  
  
 ![Superficie di disegno limitata](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art31.gif "AboutGdip02_Art31")  
  
 Per disegnare con il ritaglio, creare un <xref:System.Drawing.Graphics> dell'oggetto, impostare il relativo <xref:System.Drawing.Graphics.Clip%2A> proprietà e quindi chiamare metodi di disegno che stesso <xref:System.Drawing.Graphics> oggetto:  
  
 [!code-csharp[LinesCurvesAndShapes#91](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#91)]
 [!code-vb[LinesCurvesAndShapes#91](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#91)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Region?displayProperty=nameWithType>  
 [Linee, curve e forme](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Uso delle regioni](../../../../docs/framework/winforms/advanced/using-regions.md)
