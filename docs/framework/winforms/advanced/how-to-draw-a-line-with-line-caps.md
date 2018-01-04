---
title: "Procedura: disegnare una linea con estremità"
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
- drawing [Windows Forms], lines
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
- drawing lines [Windows Forms], line caps
ms.assetid: eb68c3e1-c400-4886-8a04-76978a429cb6
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4048757e11724aa1e175d8b18c47f48d22d807e4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-a-line-with-line-caps"></a>Procedura: disegnare una linea con estremità
È possibile disegnare l'inizio o alla fine di una riga in una delle diverse forme dette estremità di linea. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]supporta numerose estremità di linee, ad esempio round, quadrato, rombo e punta di freccia.  
  
## <a name="example"></a>Esempio  
 È possibile specificare i delimitatori di riga per l'avvio di una riga (estremità iniziale), la fine di una riga (estremità) o i trattini di una linea tratteggiata (cap dash).  
  
 Nell'esempio seguente disegna una linea con una freccia a un'estremità e un'estremità a altra estremità arrotondata. La figura mostra la riga risulta:  
  
 ![Penne](../../../../docs/framework/winforms/advanced/media/pens4.gif "pens4")  
  
 [!code-csharp[System.Drawing.UsingAPen#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.UsingAPen#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
  
-   Creare un Windows Form e gestire il modulo <xref:System.Windows.Forms.Control.Paint> evento. Incollare il codice di esempio nel <xref:System.Windows.Forms.Control.Paint> gestore eventi passando `e` come <xref:System.Windows.Forms.PaintEventArgs>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 <xref:System.Drawing.Drawing2D.LineCap?displayProperty=nameWithType>  
 [Grafica e disegno in Windows Form](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Uso di un oggetto Pen per creare linee e forme](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
