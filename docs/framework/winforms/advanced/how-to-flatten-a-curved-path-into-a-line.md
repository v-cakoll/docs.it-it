---
title: 'Procedura: trasformare un percorso curvo in una linea'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [Windows Forms], flattening curves into lines
- curves [Windows Forms], flattening
- GraphicsPath object
- paths [Windows Forms], flattening
- drawing [Windows Forms], flattening curves
ms.assetid: e654b8de-25f4-4735-9208-42e4514a589c
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 62dedc987c2b622dc3f3aa81dac3cdea6dd75740
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-flatten-a-curved-path-into-a-line"></a>Procedura: trasformare un percorso curvo in una linea
Oggetto <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto archivia una sequenza di righe e di spline di Bézier. È possibile aggiungere diversi tipi di curve (puntini di sospensione, archi, spline di tipo cardinal) a un percorso, ma ogni curva viene convertito in una spline di Bézier prima che venga archiviata nel percorso. Appiattimento di un percorso costituito dalla conversione ogni spline di Bézier nel percorso in una sequenza di linee rette. Nella figura seguente viene mostrato un percorso prima e dopo la conversione.  
  
 ![Linee rette e curve](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")  
  
### <a name="to-flatten-a-path"></a>Per trasformare un percorso  
  
-   chiamare il <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> metodo di un <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto. Il <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> metodo riceve un argomento di appiattimento che specifica la distanza massima tra il percorso bidimensionale e il percorso originale.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>  
 [Linee, curve e forme](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Costruzione e creazione di percorsi](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)
