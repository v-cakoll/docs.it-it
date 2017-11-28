---
title: 'Procedura: utilizzare un oggetto Pen per disegnare linee'
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
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
ms.assetid: 0828c331-a438-4bdd-a4d6-3ef1e59e8795
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 481200d1383fd6cc5e95379823af651c78275cb5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-a-pen-to-draw-lines"></a>Procedura: utilizzare un oggetto Pen per disegnare linee
Per tracciare linee, è necessario un <xref:System.Drawing.Graphics> oggetto e un <xref:System.Drawing.Pen> oggetto. Il <xref:System.Drawing.Graphics> oggetto fornisce il <xref:System.Drawing.Graphics.DrawLine%2A> (metodo) e <xref:System.Drawing.Pen> oggetto archivia le funzionalità della riga, ad esempio colore e spessore.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente disegna una linea da (20, 10) a (300, 100). La prima istruzione utilizza il <xref:System.Drawing.Pen.%23ctor%2A> costruttore della classe per creare una penna colore nero. L'argomento passato al <xref:System.Drawing.Pen.%23ctor%2A> costruttore è un <xref:System.Drawing.Color> oggetto creato con il <xref:System.Drawing.Color.FromArgb%2A> metodo. I valori utilizzati per creare il <xref:System.Drawing.Color> oggetto: (255, 0, 0, 0), ovvero corrispondono ai componenti alfa, rossi, verde e blu del colore. Questi valori indicano la penna di colore nera opaca.  
  
 [!code-csharp[System.Drawing.UsingAPen#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs>`e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Drawing.Pen>  
 [Uso di un oggetto Pen per creare linee e forme](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [Penne, linee e rettangoli in GDI+](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)
