---
title: 'Procedura: Disegnare una linea in un Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- Graphics.DrawLine
helpviewer_keywords:
- examples [Windows Forms], drawing lines on forms
- drawing [Windows Forms], lines
- lines [Windows Forms], drawing
- drawing lines
ms.assetid: 55c1dbeb-75d0-430c-9814-a24b8971ad8c
ms.openlocfilehash: 4274072b55c79cfe88e906d1401d275b414ebe97
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54586748"
---
# <a name="how-to-draw-a-line-on-a-windows-form"></a>Procedura: Disegnare una linea in un Windows Form
In questo esempio disegna una linea in un form. In genere, quando si disegna in un form, la gestione del modulo <xref:System.Windows.Forms.Control.Paint> eventi ed eseguire il disegno utilizzando i <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> proprietà del <xref:System.Windows.Forms.PaintEventArgs>, come illustrato in questo esempio  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Drawing.UsingAPen#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 È sempre necessario chiamare <xref:System.IDisposable.Dispose%2A> tutti gli oggetti che utilizzano le risorse di sistema, ad esempio <xref:System.Drawing.Pen> oggetti.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Drawing.Graphics.DrawLine%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [Introduzione alla programmazione grafica](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)
- [Uso di un oggetto Pen per creare linee e forme](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
- [Grafica e disegno in Windows Form](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
