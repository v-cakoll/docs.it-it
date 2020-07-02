---
title: 'Procedura: disegnare una linea in un Windows Form'
description: Informazioni su come disegnare una linea in un Form gestendo l'evento Paint, quindi eseguire il disegno usando la proprietà graphics di PaintEventArgs.
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
ms.openlocfilehash: c8e92dc265c63413275561d0e2e3aa820eaec724
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621626"
---
# <a name="how-to-draw-a-line-on-a-windows-form"></a>Procedura: disegnare una linea in un Windows Form
In questo esempio viene disegnata una riga in un form. In genere, quando si disegna in un form, si gestisce l'evento del form <xref:System.Windows.Forms.Control.Paint> e si esegue il disegno usando la <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> proprietà di <xref:System.Windows.Forms.PaintEventArgs> , come illustrato in questo esempio.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Drawing.UsingAPen#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs>`e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 È sempre necessario chiamare <xref:System.IDisposable.Dispose%2A> sugli oggetti che utilizzano risorse di sistema, ad esempio <xref:System.Drawing.Pen> gli oggetti.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Graphics.DrawLine%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [Introduzione alla programmazione grafica](getting-started-with-graphics-programming.md)
- [Uso di una penna per disegnare linee e forme](using-a-pen-to-draw-lines-and-shapes.md)
- [Grafica e disegno in Windows Form](graphics-and-drawing-in-windows-forms.md)
