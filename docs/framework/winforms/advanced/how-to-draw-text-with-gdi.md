---
title: 'Procedura: creare testo con GDI'
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
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing with TextRenderer
- drawing [Windows Forms], text
- Windows Forms, drawing text with GDI
ms.assetid: 2a19fe5d-2ace-451c-94db-01cb1118ef7b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 48644ce8449c8d8eea7306eff1e43539659370c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-text-with-gdi"></a>Procedura: creare testo con GDI
Con il <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodo il <xref:System.Windows.Forms.TextRenderer> (classe), è possibile accedere [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] funzionalità per il disegno di testo in un form o controllo. [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]il rendering del testo offre in genere prestazioni migliori e misurazione del testo più accurata [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
> [!NOTE]
>  Il <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodi di <xref:System.Windows.Forms.TextRenderer> classe non sono supportati per la stampa. Quando si stampa, utilizzare sempre il <xref:System.Drawing.Graphics.DrawString%2A> metodi il <xref:System.Drawing.Graphics> classe.  
  
## <a name="example"></a>Esempio  
 Esempio di codice riportato di seguito viene illustrato come disegnare testo su più righe all'interno di un rettangolo con il <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodo.  
  
 [!code-csharp[System.Windows.Forms.TextRendererExamples#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/CS/Form1.cs#7)]
 [!code-vb[System.Windows.Forms.TextRendererExamples#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/VB/Form1.vb#7)]  
  
 Per eseguire il rendering di testo con il <xref:System.Windows.Forms.TextRenderer> (classe), è necessario un <xref:System.Drawing.IDeviceContext>, ad esempio un <xref:System.Drawing.Graphics> e un <xref:System.Drawing.Font>, un percorso in cui disegnare il testo e il colore in cui deve essere disegnato. Facoltativamente, è possibile specificare il formattazione del testo utilizzando il <xref:System.Windows.Forms.TextFormatFlags> enumerazione.  
  
 Per ulteriori informazioni su come ottenere un <xref:System.Drawing.Graphics>, vedere [procedura: creazione di oggetti di grafica per il disegno](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md). Per ulteriori informazioni sulla creazione di un <xref:System.Drawing.Font>, vedere [procedura: creare famiglie di caratteri e i tipi di carattere](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md).  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio di codice precedente è progettato per l'uso con Windows Form e richiede la <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.TextRenderer>  
 <xref:System.Drawing.Font>  
 <xref:System.Drawing.Color>  
 <xref:System.Drawing.Color>  
 [Uso di tipi di carattere e testo](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
