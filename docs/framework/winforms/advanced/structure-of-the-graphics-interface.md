---
title: Struttura dell'interfaccia grafica
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GDI+, using managed interface
- graphics [Windows Forms], class structure
ms.assetid: 010a1e46-656b-40a1-8d5d-87aa05ee1243
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 43bd899a1dd53dc8cdae4f81e90b1aa74c29cb67
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="structure-of-the-graphics-interface"></a>Struttura dell'interfaccia grafica
L'interfaccia di classe gestita a [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] contiene circa 60 classi, 50 enumerazioni e strutture di 8. Il <xref:System.Drawing.Graphics> classe costituisce la base di [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] funzionalità; si tratta della classe che disegna effettivamente linee, curve, figure, immagini e testo.  
  
## <a name="important-classes"></a>Classi importanti  
 Numerose classi vengono utilizzate in combinazione con la <xref:System.Drawing.Graphics> classe. Ad esempio, il <xref:System.Drawing.Graphics.DrawLine%2A> metodo riceve un <xref:System.Drawing.Pen> oggetto, che contiene gli attributi (colore, larghezza, stile tratteggio e così via) della riga da disegnare. Il <xref:System.Drawing.Graphics.FillRectangle%2A> metodo può ricevere un puntatore a un <xref:System.Drawing.Drawing2D.LinearGradientBrush> oggetto, che funziona con il <xref:System.Drawing.Graphics> oggetto per riempire un rettangolo con un colore gradualmente. <xref:System.Drawing.Font>e <xref:System.Drawing.StringFormat> oggetti influenzano il modo in cui un <xref:System.Drawing.Graphics> Disegna un oggetto testo. Oggetto <xref:System.Drawing.Drawing2D.Matrix> oggetto archivia e gestisce la trasformazione globale di un <xref:System.Drawing.Graphics> oggetto, che è possibile ruotare e ridimensionare, capovolgere immagini.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]vengono fornite diverse strutture (ad esempio, <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Point>, e <xref:System.Drawing.Size>) per organizzare i dati di grafici. Inoltre, alcune classi di servono principalmente è strutturati come tipi di dati. Ad esempio, il <xref:System.Drawing.Imaging.BitmapData> classe è un supporto per il <xref:System.Drawing.Bitmap> (classe) e <xref:System.Drawing.Drawing2D.PathData> classe è un supporto per la <xref:System.Drawing.Drawing2D.GraphicsPath> classe.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]Definisce numerose enumerazioni, ovvero raccolte di costanti correlate. Ad esempio, il <xref:System.Drawing.Drawing2D.LineJoin> enumerazione contiene gli elementi <xref:System.Drawing.Drawing2D.LineJoin.Bevel>, <xref:System.Drawing.Drawing2D.LineJoin.Miter>, e <xref:System.Drawing.Drawing2D.LineJoin.Round>, che specificano gli stili che possono essere utilizzati per unire due linee.  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sulla grafica](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)  
 [Informazioni sul codice gestito GDI+](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)  
 [Uso di classi grafiche gestite](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)
