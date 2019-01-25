---
title: Struttura dell'interfaccia grafica
ms.date: 03/30/2017
helpviewer_keywords:
- GDI+, using managed interface
- graphics [Windows Forms], class structure
ms.assetid: 010a1e46-656b-40a1-8d5d-87aa05ee1243
ms.openlocfilehash: 4d000adfa02555a766410833fabe4039dd06c268
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54592046"
---
# <a name="structure-of-the-graphics-interface"></a>Struttura dell'interfaccia grafica
L'interfaccia di classe gestita a [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] contiene le classi di circa 60, 50 enumerazioni e strutture di 8. Il <xref:System.Drawing.Graphics> classe è alla base di [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] funzionalità; si tratta della classe che consente di disegnare effettivamente le linee, curve, figure, immagini e testo.  
  
## <a name="important-classes"></a>Classi importanti  
 Molte classi possono essere utilizzate con il <xref:System.Drawing.Graphics> classe. Ad esempio, il <xref:System.Drawing.Graphics.DrawLine%2A> metodo riceve un <xref:System.Drawing.Pen> oggetto, che contiene gli attributi (color, width, dello stile di tratteggio e simili) della riga da disegnare. Il <xref:System.Drawing.Graphics.FillRectangle%2A> metodo può ricevere un puntatore a un <xref:System.Drawing.Drawing2D.LinearGradientBrush> oggetto, che funziona con il <xref:System.Drawing.Graphics> oggetto per riempire il rettangolo con un colore gradualmente. <xref:System.Drawing.Font> e <xref:System.Drawing.StringFormat> oggetti influenzano il modo in cui un <xref:System.Drawing.Graphics> oggetto disegna testo. Oggetto <xref:System.Drawing.Drawing2D.Matrix> oggetto archivia e gestisce la trasformazione globale di un <xref:System.Drawing.Graphics> oggetto, che consente di ruotare, ridimensionare e capovolgere le immagini.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] sono disponibili varie strutture (ad esempio, <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Point>, e <xref:System.Drawing.Size>) per organizzare i dati di grafica. Inoltre, alcune classi servono strutturati principalmente come tipi di dati. Ad esempio, il <xref:System.Drawing.Imaging.BitmapData> classe è un supporto per il <xref:System.Drawing.Bitmap> (classe) e il <xref:System.Drawing.Drawing2D.PathData> classe è un supporto per il <xref:System.Drawing.Drawing2D.GraphicsPath> classe.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] definisce le enumerazioni diversi, ovvero raccolte di costanti correlate. Ad esempio, il <xref:System.Drawing.Drawing2D.LineJoin> enumerazione contiene gli elementi <xref:System.Drawing.Drawing2D.LineJoin.Bevel>, <xref:System.Drawing.Drawing2D.LineJoin.Miter>, e <xref:System.Drawing.Drawing2D.LineJoin.Round>, che specifica gli stili che possono essere utilizzati per unire due righe.  
  
## <a name="see-also"></a>Vedere anche
- [Cenni preliminari sulla grafica](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)
- [Informazioni sul codice gestito GDI+](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)
- [Uso di classi grafiche gestite](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)
