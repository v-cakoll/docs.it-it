---
title: 'Procedura: utilizzare l''antialiasing nel testo'
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
- strings [Windows Forms], smoothing drawn
- antialiasing [Windows Forms], using with text
- text [Windows Forms], smoothing
- text [Windows Forms], antialiasing
- strings [Windows Forms], antialiasing when drawing
ms.assetid: 48fc34f3-f236-4b01-a0cb-f0752e6d22ae
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: edd31ec5b9d94ac1791fb0f2a73522fdf4178627
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-antialiasing-with-text"></a>Procedura: utilizzare l'antialiasing nel testo
*Anti-aliasing* fa riferimento un arrotondamento dei margini irregolari di grafica e testo per migliorare l'aspetto o leggibilità disegnati. All'oggetto gestito [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] classi, è possibile eseguire il rendering di testo con antialias di alta qualità, come testo di qualità inferiore. In genere, rendering a qualità elevata richiede più tempo di elaborazione di rendering di qualità inferiore. Per impostare il livello di qualità del testo, impostare il <xref:System.Drawing.Graphics.TextRenderingHint%2A> proprietà di un <xref:System.Drawing.Graphics> a uno degli elementi del <xref:System.Drawing.Text.TextRenderingHint> enumerazione  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente disegna un testo con due diverse impostazioni di qualità.  
  
 Nella figura seguente mostra l'output del codice di esempio.  
  
 ![Tipi di carattere testo](../../../../docs/framework/winforms/advanced/media/fontstext10.png "FontsText10")  
  
 [!code-csharp[System.Drawing.FontsAndText#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio di codice precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vedere anche  
 [Uso di tipi di carattere e testo](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
