---
title: 'Procedura: Disegna un rettangolo pieno in un Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Graphics.FillRectangle
helpviewer_keywords:
- drawing [Windows Forms], rectangles
- rectangles [Windows Forms], drawing
- drawing rectangles
ms.assetid: d656a93c-987d-4809-aafd-493fe17450f0
ms.openlocfilehash: a9722b2939e77282453743a4dea165a340412a21
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587034"
---
# <a name="how-to-draw-a-filled-rectangle-on-a-windows-form"></a>Procedura: Disegna un rettangolo pieno in un Windows Form
In questo esempio disegna un rettangolo pieno in un form.  
  
## <a name="example"></a>Esempio  
 [!code-cpp[System.Drawing.ConceptualHowTos#2](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#2)]
 [!code-csharp[System.Drawing.ConceptualHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#2)]
 [!code-vb[System.Drawing.ConceptualHowTos#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#2)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 È possibile chiamare questo metodo nel <xref:System.Windows.Forms.Form.Load> gestore dell'evento. Il contenuto creato non verrà ridisegnato se il form viene ridimensionato o nascosto da un altro form. Per rendere il contenuto viene ridisegnata automaticamente, è necessario eseguire l'override di <xref:System.Windows.Forms.Control.OnPaint%2A> (metodo).  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 È sempre necessario chiamare <xref:System.IDisposable.Dispose%2A> tutti gli oggetti che utilizzano le risorse di sistema, ad esempio <xref:System.Drawing.Brush> e <xref:System.Drawing.Graphics> oggetti.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Drawing.Graphics.FillRectangle%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [Introduzione alla programmazione grafica](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)
- [Grafica e disegno in Windows Form](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
- [Uso di un oggetto Pen per creare linee e forme](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
- [Pennelli e forme con riempimento in GDI+](../../../../docs/framework/winforms/advanced/brushes-and-filled-shapes-in-gdi.md)
