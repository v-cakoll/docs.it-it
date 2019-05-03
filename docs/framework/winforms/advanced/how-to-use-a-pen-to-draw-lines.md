---
title: 'Procedura: Usare un oggetto Pen per disegnare linee'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
ms.assetid: 0828c331-a438-4bdd-a4d6-3ef1e59e8795
ms.openlocfilehash: 8b4eb7684e15ffd5b0b528771490ba66f3b7bb45
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61954440"
---
# <a name="how-to-use-a-pen-to-draw-lines"></a>Procedura: Usare un oggetto Pen per disegnare linee
Per tracciare linee, è necessario un <xref:System.Drawing.Graphics> oggetto e un <xref:System.Drawing.Pen> oggetto. Il <xref:System.Drawing.Graphics> oggetto fornisce le <xref:System.Drawing.Graphics.DrawLine%2A> metodo e il <xref:System.Drawing.Pen> oggetto archivia le funzionalità della riga, ad esempio colore e spessore.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente disegna una linea da (20, 10) a (300, 100). La prima istruzione Usa la <xref:System.Drawing.Pen.%23ctor%2A> costruttore della classe per creare una penna colore nero. L'unico argomento passato per il <xref:System.Drawing.Pen.%23ctor%2A> costruttore è una <xref:System.Drawing.Color> oggetto creato con il <xref:System.Drawing.Color.FromArgb%2A> (metodo). I valori utilizzati per creare il <xref:System.Drawing.Color> oggetto, ovvero (255, 0, 0, 0), corrispondono ai componenti alfa, rossi, verdi e blu del colore. Questi valori definiscono una penna nera opaca.  
  
 [!code-csharp[System.Drawing.UsingAPen#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs>`e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Pen>
- [Uso di un oggetto Pen per creare linee e forme](using-a-pen-to-draw-lines-and-shapes.md)
- [Penne, linee e rettangoli in GDI+](pens-lines-and-rectangles-in-gdi.md)
