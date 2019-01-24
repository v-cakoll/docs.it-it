---
title: 'Procedura: Disegnare una linea tratteggiata personalizzata'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines [Windows Forms], custom
- lines [Windows Forms], drawing
- lines [Windows Forms], dashed
ms.assetid: cd0ed96a-cce4-47b9-b58a-3bae2e3d1bee
ms.openlocfilehash: 77b4b959523c6d35dece2d759eeb71be04b53d93
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54538622"
---
# <a name="how-to-draw-a-custom-dashed-line"></a>Procedura: Disegnare una linea tratteggiata personalizzata
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] fornisce diversi stili di tratteggio elencati nel <xref:System.Drawing.Drawing2D.DashStyle> enumerazione. Se questi stili di tratteggio standard non soddisfano le proprie esigenze, è possibile creare un motivo a tratteggio personalizzati.  
  
## <a name="example"></a>Esempio  
 Per disegnare una linea tratteggiata personalizzata, inserire le lunghezze dei trattini e spazi in una matrice e assegnare la matrice come valore dei <xref:System.Drawing.Pen.DashPattern%2A> proprietà di un <xref:System.Drawing.Pen> oggetto. L'esempio seguente disegna una linea tratteggiata personalizzata in base alla matrice `{5, 2, 15, 4}`. Se si moltiplica gli elementi della matrice in base alla larghezza della penna pari a 5, otterrai `{25, 10, 75, 20}`. I trattini visualizzati alternano lunghezza compresa tra 25 e 75, mentre gli spazi lunghezza compresa tra 10 e 20.  
  
 La figura seguente mostra la linea tratteggiata risultante. Si noti che il trattino finale deve essere inferiore a 25 unità in modo che possa terminare la riga (405, 5).  
  
 ![Penne](../../../../docs/framework/winforms/advanced/media/pens6.gif "pens6")  
  
 [!code-csharp[System.Drawing.UsingAPen#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.UsingAPen#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Creare un modulo di Windows e la gestione del modulo <xref:System.Windows.Forms.Control.Paint> evento. Incollare il codice precedente nel <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.  
  
## <a name="see-also"></a>Vedere anche
- [Uso di un oggetto Pen per creare linee e forme](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
