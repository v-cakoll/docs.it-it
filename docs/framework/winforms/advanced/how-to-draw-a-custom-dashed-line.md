---
title: 'Procedura: disegnare una linea tratteggiata personalizzata'
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
- lines [Windows Forms], custom
- lines [Windows Forms], drawing
- lines [Windows Forms], dashed
ms.assetid: cd0ed96a-cce4-47b9-b58a-3bae2e3d1bee
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 770ce290b21f7d0094a487c30079063b79a7c08d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-a-custom-dashed-line"></a>Procedura: disegnare una linea tratteggiata personalizzata
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]fornisce diversi stili di tratteggio elencati nel <xref:System.Drawing.Drawing2D.DashStyle> enumerazione. Se questi stili di tratteggio standard non sono adatti alle proprie esigenze, è possibile creare un motivo a tratteggio personalizzato.  
  
## <a name="example"></a>Esempio  
 Per disegnare una linea tratteggiata personalizzata, inserire le lunghezze dei trattini e spazi in una matrice e assegnare la matrice come valore della <xref:System.Drawing.Pen.DashPattern%2A> proprietà di un <xref:System.Drawing.Pen> oggetto. Nell'esempio seguente disegna una linea tratteggiata personalizzata in base alla matrice `{5, 2, 15, 4}`. Se si moltiplica gli elementi della matrice in base alla larghezza della penna di 5, è possibile ottenere `{25, 10, 75, 20}`. I trattini visualizzati alternano lunghezza compresa tra 25 e 75, mentre gli spazi lunghezza compresa tra 10 e 20.  
  
 Nella figura seguente mostra la linea tratteggiata risultante. Si noti che il trattino finale deve essere inferiore a 25 unità in modo che possa terminare la riga (405, 5).  
  
 ![Penne](../../../../docs/framework/winforms/advanced/media/pens6.gif "pens6")  
  
 [!code-csharp[System.Drawing.UsingAPen#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.UsingAPen#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Creare un Windows Form e gestire il modulo <xref:System.Windows.Forms.Control.Paint> evento. Incollare il codice precedente nel <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.  
  
## <a name="see-also"></a>Vedere anche  
 [Uso di un oggetto Pen per creare linee e forme](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
