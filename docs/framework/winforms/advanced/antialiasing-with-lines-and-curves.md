---
title: Anti-aliasing con linee e curve
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
- antialiasing
- antialiasing [Windows Forms], smoothing modes
- GDI+, antialiasing
ms.assetid: 810da1a4-c136-4abf-88df-68e49efdd8d4
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d69d635fbdd8720937cd189826c1496b8126ddef
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="antialiasing-with-lines-and-curves"></a>Anti-aliasing con linee e curve
Quando si utilizza [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] per disegnare una linea, si forniscono i punti iniziale e finale della riga, ma non è necessario fornire le informazioni sui singoli pixel della riga. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]funziona in combinazione con il software dei driver di visualizzazione per determinare i pixel verranno attivati per visualizzare la riga in un particolare dispositivo di visualizzazione.  
  
## <a name="aliasing"></a>Alias  
 Prendere in considerazione la linea rossa direttamente che unisce il punto (4, 2) per il punto (16, 10). Si supponga che il sistema di coordinate ha origine nell'angolo superiore sinistro e che l'unità di misura è il pixel. Si supponga inoltre che l'asse x punta a destra e i punti di asse y verso il basso. Nella figura seguente mostra una linea rossa tracciata su uno sfondo ingrandita.  
  
 ![Linea, senza antialiasing](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art33.gif "AboutGdip02_Art33")  
  
 Il pixel rossi utilizzati per il rendering della linea sono opachi. Nella riga sono non presenti Nessun pixel semitrasparente. Questo tipo di rendering fornisce la riga di un aspetto irregolare, mentre la linea assomiglia scale. Questa tecnica di che rappresenta una riga con una scala è chiamata alias; la scala è un alias per la linea teorica.  
  
## <a name="antialiasing"></a>Anti-aliasing  
 Una tecnica più sofisticata per il rendering di una riga comporta l'utilizzo di pixel semitrasparente insieme ai pixel opachi. Pixel viene impostato su rosso puro, o per alcuni sfumatura di rosso e il colore di sfondo, a seconda di come chiudere siano alla riga. Questo tipo di rendering viene chiamato l'anti-aliasing e risultati in una riga che viene percepita come più uniforme. Nella figura seguente viene illustrato come determinate pixel vengono combinati con lo sfondo per produrre una riga di anti-aliasing.  
  
 ![Antialiasing di una linea](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art34.gif "AboutGdip02_Art34")  
  
 Anti-aliasing, smussamento, possono inoltre essere applicate alle curve. Nella figura seguente mostra una visualizzazione di un'ellisse smussata ingrandita.  
  
 ![Antialiasing di curve](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art35.gif "AboutGdip02_Art35")  
  
 Nella figura seguente viene mostrata la stessa ellisse dimensioni effettive, senza e una volta con anti-aliasing.  
  
 ![Esempio di antialiasing](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art36.gif "AboutGdip02_Art36")  
  
 Per disegnare linee e curve che utilizzano l'anti-aliasing, creare un'istanza del <xref:System.Drawing.Graphics> e impostare il relativo <xref:System.Drawing.Graphics.SmoothingMode%2A> proprietà <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> o <xref:System.Drawing.Drawing2D.SmoothingMode.HighQuality>. Quindi chiamare uno dei metodi di disegno che stesso <xref:System.Drawing.Graphics> classe.  
  
 [!code-csharp[LinesCurvesAndShapes#81](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#81)]
 [!code-vb[LinesCurvesAndShapes#81](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#81)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Drawing.Drawing2D.SmoothingMode?displayProperty=nameWithType>  
 [Linee, curve e forme](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Procedura: Usare l'antialiasing nel testo](../../../../docs/framework/winforms/advanced/how-to-use-antialiasing-with-text.md)
