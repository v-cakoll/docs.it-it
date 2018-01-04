---
title: Limitazione della superficie di disegno in GDI+
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
- GDI+, clipping
- clipping [Windows Forms], using GDI+
- GDI+, restricting drawing surface
ms.assetid: 8b5f71d9-d2f0-4540-9c41-740f90fd4c26
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b7834c95959972e7264e1caa2cfc21b190341b21
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
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
