---
title: 'Procedura: disegnare un rettangolo con riempimento in un Windows Form'
description: Informazioni su come creare un rettangolo pieno in un Windows Form a livello di codice. Altre informazioni sulla compilazione del codice.
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
ms.openlocfilehash: 0ad8ec97000e29b2194a9eda713aa43d5557b44c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621639"
---
# <a name="how-to-draw-a-filled-rectangle-on-a-windows-form"></a>Procedura: disegnare un rettangolo con riempimento in un Windows Form
Questo esempio disegna un rettangolo pieno in un form.  
  
## <a name="example"></a>Esempio  
 [!code-cpp[System.Drawing.ConceptualHowTos#2](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#2)]
 [!code-csharp[System.Drawing.ConceptualHowTos#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#2)]
 [!code-vb[System.Drawing.ConceptualHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#2)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Non è possibile chiamare questo metodo nel <xref:System.Windows.Forms.Form.Load> gestore eventi. Il contenuto disegnato non verrà ridisegnato se il form viene ridimensionato o nascosto da un altro form. Per ridisegnare automaticamente il contenuto, è necessario eseguire l'override del <xref:System.Windows.Forms.Control.OnPaint%2A> metodo.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 È sempre necessario chiamare <xref:System.IDisposable.Dispose%2A> sugli oggetti che utilizzano le risorse di sistema, ad <xref:System.Drawing.Brush> esempio <xref:System.Drawing.Graphics> gli oggetti e.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Graphics.FillRectangle%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [Introduzione alla programmazione grafica](getting-started-with-graphics-programming.md)
- [Grafica e disegno in Windows Form](graphics-and-drawing-in-windows-forms.md)
- [Uso di una penna per disegnare linee e forme](using-a-pen-to-draw-lines-and-shapes.md)
- [Pennelli e forme con riempimento in GDI+](brushes-and-filled-shapes-in-gdi.md)
