---
title: 'Procedura: ridurre lo sfarfallio nella grafica con il doppio buffering per form e controlli'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing in Windows Forms
- graphics [Windows Forms], reducing double-buffered flicker
ms.assetid: 91083d3a-653f-4f15-a467-0f37b2aa39d6
ms.openlocfilehash: 6e11e364af5dc361a24cdd88d72432d6ba4d4058
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522854"
---
# <a name="how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls"></a>Procedura: ridurre lo sfarfallio nella grafica con il doppio buffering per form e controlli
Il doppio buffer usa un buffer di memoria per risolvere i problemi di sfarfallio associati a più operazioni di disegno. Quando il doppio buffer è abilitato, tutte le operazioni di disegno vengono prima sottoposte a rendering in un buffer di memoria invece che nella superficie di disegno visualizzata. Dopo che tutte le operazioni di disegno sono state completate, il buffer di memoria viene copiato direttamente nella superficie di disegno associata. Poiché solo una grafica operazione sullo schermo, viene eliminato lo sfarfallio dell'immagine associata a operazioni di disegno complesse. Per la maggior parte delle applicazioni, il doppio buffering predefinito fornito dal [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] fornirà i migliori risultati. Controlli Windows Form standard sono a doppio buffering per impostazione predefinita. È possibile abilitare l'impostazione predefinita il doppio buffer nei moduli e nei controlli modificati in due modi. È possibile impostare il <xref:System.Windows.Forms.Control.DoubleBuffered%2A> proprietà `true`, oppure è possibile chiamare il <xref:System.Windows.Forms.Control.SetStyle%2A> per impostare il <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> flag `true`. Entrambi i metodi consentirà buffering doppio predefinito per un form o controllo e fornire il rendering di grafica sfarfallio. La chiamata di <xref:System.Windows.Forms.Control.SetStyle%2A> metodo è consigliato solo per i controlli personalizzati per cui è stato scritto il codice di rendering.  
  
 Per scenari di memorizzazione nel buffer più avanzati, ad esempio animazione o gestione avanzata della memoria, è possibile implementare la propria logica di buffering doppio. Per ulteriori informazioni, vedere [procedura: gestire manualmente le immagini memorizzate nel buffer](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md).  
  
### <a name="to-reduce-flicker"></a>Per ridurre lo sfarfallio  
  
-   Impostare la proprietà <xref:System.Windows.Forms.Control.DoubleBuffered%2A> su `true`.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#31)]  
  
 \- oppure -  
  
-   Chiamare il <xref:System.Windows.Forms.Control.SetStyle%2A> per impostare il <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> flag `true`.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#32)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#32)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Control.DoubleBuffered%2A>  
 <xref:System.Windows.Forms.Control.SetStyle%2A>  
 [Grafica a doppio buffer](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)  
 [Grafica e disegno in Windows Form](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
