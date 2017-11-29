---
title: 'Procedura: riempire figure aperte'
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
- open figures [Windows Forms], filling
- figures [Windows Forms], filling
ms.assetid: 5a36b0e4-f1f4-46c0-a85a-22ae98491950
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7a8a2d5a13cac97063bf2a04969928c859a5954d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-fill-open-figures"></a>Procedura: riempire figure aperte
È possibile inserire un percorso passando un <xref:System.Drawing.Drawing2D.GraphicsPath> dell'oggetto per il <xref:System.Drawing.Graphics.FillPath%2A> metodo. Il <xref:System.Drawing.Graphics.FillPath%2A> metodo compila il percorso secondo la modalità di riempimento (alternativo o culling) attualmente impostato per il percorso. Se il percorso contiene figure aperte, il percorso viene inserito come se fossero chiuse. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]chiude una figura tracciando una linea retta tra il punto finale e il punto iniziale.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea un percorso che abbia una figura aperta (un arco) e una figura chiusa (un'ellisse). Il <xref:System.Drawing.Graphics.FillPath%2A> metodo compila il percorso in base alla modalità di riempimento predefinito, ovvero <xref:System.Drawing.Drawing2D.FillMode.Alternate>.  
  
 Nella figura seguente mostra l'output del codice di esempio. Si noti che il percorso viene riempito (in base a <xref:System.Drawing.Drawing2D.FillMode.Alternate>) come se figura aperta sono stati chiusi da una linea retta tra il punto finale e il punto iniziale.  
  
 ![Percorso di apertura](../../../../docs/framework/winforms/advanced/media/fillopenpath.png "FillOpenPath")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Drawing.Drawing2D.GraphicsPath>  
 [Percorsi di oggetti Graphics in GDI+](../../../../docs/framework/winforms/advanced/graphics-paths-in-gdi.md)
