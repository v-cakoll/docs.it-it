---
title: 'Procedura: utilizzare un oggetto Pen per disegnare linee'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
ms.assetid: 0828c331-a438-4bdd-a4d6-3ef1e59e8795
ms.openlocfilehash: 6a728bcaf9946b2b92ce0ee97599f4c4fd0fea69
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522985"
---
# <a name="how-to-use-a-pen-to-draw-lines"></a>Procedura: utilizzare un oggetto Pen per disegnare linee
Per tracciare linee, è necessario un <xref:System.Drawing.Graphics> oggetto e un <xref:System.Drawing.Pen> oggetto. Il <xref:System.Drawing.Graphics> oggetto fornisce il <xref:System.Drawing.Graphics.DrawLine%2A> (metodo) e <xref:System.Drawing.Pen> oggetto archivia le funzionalità della riga, ad esempio colore e spessore.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente disegna una linea da (20, 10) a (300, 100). La prima istruzione utilizza il <xref:System.Drawing.Pen.%23ctor%2A> costruttore della classe per creare una penna colore nero. L'argomento passato al <xref:System.Drawing.Pen.%23ctor%2A> costruttore è un <xref:System.Drawing.Color> oggetto creato con il <xref:System.Drawing.Color.FromArgb%2A> metodo. I valori utilizzati per creare il <xref:System.Drawing.Color> oggetto: (255, 0, 0, 0), ovvero corrispondono ai componenti alfa, rossi, verde e blu del colore. Questi valori indicano la penna di colore nera opaca.  
  
 [!code-csharp[System.Drawing.UsingAPen#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Drawing.Pen>  
 [Uso di un oggetto Pen per creare linee e forme](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [Penne, linee e rettangoli in GDI+](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)
