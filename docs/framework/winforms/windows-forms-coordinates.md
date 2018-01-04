---
title: Coordinate di Windows Form
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms coordinates
- screen coordinates
- client coordinates
- coordinates [Windows Forms], Windows Forms
ms.assetid: cc06e61f-43b6-4408-a676-2542dcfcd96e
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8f4b42fd71dacb0071013067dc3c14add96c8aca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="windows-forms-coordinates"></a>Coordinate di Windows Form
Il sistema di coordinate per un Windows Form è basato su coordinate dispositivo e l'unità di misura quando si disegna in Windows Form di base è l'unità di dispositivo (in genere, il pixel). I punti nella schermata sono descritti da coppie di coordinate x e y, con le coordinate x aumenta a destra e le coordinate y aumentano dall'alto verso il basso. Il percorso dell'origine, rispetto allo schermo, può variare a seconda se si specifica le coordinate dello schermo o client.  
  
## <a name="screen-coordinates"></a>Coordinate dello schermo  
 Un'applicazione Windows Forms specifica la posizione di una finestra sullo schermo in coordinate dello schermo. Per le coordinate dello schermo, l'origine è l'angolo superiore sinistro della schermata. La posizione completa di una finestra è spesso descritta da un <xref:System.Drawing.Rectangle> struttura che contiene le coordinate dello schermo di due punti che definiscono gli angoli in alto a sinistra e in basso a destra della finestra.  
  
## <a name="client-coordinates"></a>Coordinate del client  
 Un'applicazione Windows Form consente di specificare la posizione dei punti in un form o controllo usando le coordinate client. L'origine per le coordinate del client è l'angolo superiore sinistro dell'area client del controllo o del modulo. Le coordinate client assicurarsi che un'applicazione può utilizzare i valori delle coordinate coerenti durante il disegno in un form o controllo, indipendentemente dalla posizione del form o controllo sullo schermo.  
  
 Le dimensioni dell'area client vengono inoltre descritte da un <xref:System.Drawing.Rectangle> struttura che contiene le coordinate client per l'area. In tutti i casi, la coordinata superiore sinistro del rettangolo è incluso nell'area client, mentre è esclusa la coordinata in basso a destra. Le operazioni grafiche non includono i bordi destro e inferiore di un'area client. Ad esempio il <xref:System.Drawing.Graphics.FillRectangle%2A> metodo si riempie al bordo destro e inferiore del rettangolo specificato, ma non includerà tali margini.  
  
## <a name="mapping-from-one-type-of-coordinate-to-another"></a>Mapping da un tipo di Coordinate a un altro  
 In alcuni casi, potrebbe essere necessario eseguire il mapping da coordinate dello schermo a coordinate del client. È possibile effettuare facilmente questa operazione utilizzando il <xref:System.Windows.Forms.Control.PointToClient%2A> e <xref:System.Windows.Forms.Control.PointToScreen%2A> metodi disponibili nel <xref:System.Windows.Forms.Control> classe. Ad esempio, il <xref:System.Windows.Forms.Control.MousePosition%2A> proprietà <xref:System.Windows.Forms.Control> viene segnalato in coordinate dello schermo, ma è possibile eseguire la conversione in coordinate del client.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Control.PointToClient%2A>  
 <xref:System.Windows.Forms.Control.PointToScreen%2A>
