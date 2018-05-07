---
title: 'Procedura: riempire figure aperte'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- open figures [Windows Forms], filling
- figures [Windows Forms], filling
ms.assetid: 5a36b0e4-f1f4-46c0-a85a-22ae98491950
ms.openlocfilehash: b7422ae2a4dc4d59fd337ab2294caa0d65057bae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-fill-open-figures"></a>Procedura: riempire figure aperte
È possibile inserire un percorso passando un <xref:System.Drawing.Drawing2D.GraphicsPath> dell'oggetto per il <xref:System.Drawing.Graphics.FillPath%2A> metodo. Il <xref:System.Drawing.Graphics.FillPath%2A> metodo compila il percorso secondo la modalità di riempimento (alternativo o culling) attualmente impostato per il percorso. Se il percorso contiene figure aperte, il percorso viene inserito come se fossero chiuse. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] chiude una figura tracciando una linea retta tra il punto finale e il punto iniziale.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea un percorso che abbia una figura aperta (un arco) e una figura chiusa (un'ellisse). Il <xref:System.Drawing.Graphics.FillPath%2A> metodo compila il percorso in base alla modalità di riempimento predefinito, ovvero <xref:System.Drawing.Drawing2D.FillMode.Alternate>.  
  
 Nella figura seguente mostra l'output del codice di esempio. Si noti che il percorso viene riempito (in base a <xref:System.Drawing.Drawing2D.FillMode.Alternate>) come se figura aperta sono stati chiusi da una linea retta tra il punto finale e il punto iniziale.  
  
 ![Percorso di apertura file](../../../../docs/framework/winforms/advanced/media/fillopenpath.png "FillOpenPath")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Drawing.Drawing2D.GraphicsPath>  
 [Percorsi di oggetti Graphics in GDI+](../../../../docs/framework/winforms/advanced/graphics-paths-in-gdi.md)
