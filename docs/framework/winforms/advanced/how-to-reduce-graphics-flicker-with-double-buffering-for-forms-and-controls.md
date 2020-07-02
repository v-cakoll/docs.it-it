---
title: 'Procedura: ridurre lo sfarfallio nella grafica con il doppio buffering per form e controlli'
description: Informazioni su come ridurre lo sfarfallio nella grafica con il doppio buffer per Windows Forms e usare i controlli per risolvere i problemi di sfarfallio associati alle operazioni di disegno.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing in Windows Forms
- graphics [Windows Forms], reducing double-buffered flicker
ms.assetid: 91083d3a-653f-4f15-a467-0f37b2aa39d6
ms.openlocfilehash: f7c0425729f8a1a780124621788a1c49e06e0c4e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618129"
---
# <a name="how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls"></a>Procedura: ridurre lo sfarfallio nella grafica con il doppio buffering per form e controlli
Il doppio buffer usa un buffer di memoria per risolvere i problemi di sfarfallio associati a più operazioni di disegno. Quando il doppio buffer è abilitato, tutte le operazioni di disegno vengono prima sottoposte a rendering in un buffer di memoria invece che nella superficie di disegno visualizzata. Dopo che tutte le operazioni di disegno sono state completate, il buffer di memoria viene copiato direttamente nella superficie di disegno associata. Poiché sullo schermo viene eseguita una sola operazione grafica, lo sfarfallio dell'immagine associato a operazioni di disegno complesse viene eliminato. Per la maggior parte delle applicazioni, il doppio buffer predefinito fornito dal .NET Framework fornirà i risultati migliori. Per impostazione predefinita, i controlli Windows Forms standard vengono memorizzati nel buffer doppio. È possibile abilitare il doppio buffer predefinito nei form e nei controlli creati in due modi. È possibile impostare la <xref:System.Windows.Forms.Control.DoubleBuffered%2A> proprietà su `true` oppure è possibile chiamare il <xref:System.Windows.Forms.Control.SetStyle%2A> metodo per impostare il <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> flag su `true` . Entrambi i metodi consentiranno il doppio buffer predefinito per il form o il controllo e forniranno il rendering della grafica senza sfarfallio. La chiamata al <xref:System.Windows.Forms.Control.SetStyle%2A> metodo è consigliata solo per i controlli personalizzati per i quali è stato scritto tutto il codice di rendering.  
  
 Per gli scenari di doppio buffer più avanzati, ad esempio l'animazione o la gestione avanzata della memoria, è possibile implementare la logica di doppio buffer. Per altre informazioni, vedere [procedura: gestire manualmente le immagini memorizzate nel buffer](how-to-manually-manage-buffered-graphics.md).  
  
### <a name="to-reduce-flicker"></a>Per ridurre lo sfarfallio  
  
- Impostare la proprietà <xref:System.Windows.Forms.Control.DoubleBuffered%2A> su `true`.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#31)]  
  
 \- - oppure -  
  
- Chiamare il <xref:System.Windows.Forms.Control.SetStyle%2A> metodo per impostare il <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> flag su `true` .  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#32)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#32)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Control.DoubleBuffered%2A>
- <xref:System.Windows.Forms.Control.SetStyle%2A>
- [Grafica a doppio buffer](double-buffered-graphics.md)
- [Grafica e disegno in Windows Form](graphics-and-drawing-in-windows-forms.md)
