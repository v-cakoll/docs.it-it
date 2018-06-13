---
title: Grafica a doppio buffer
ms.date: 03/30/2017
helpviewer_keywords:
- double buffering
- graphics [Windows Forms], double-buffered
- flicker [Windows Forms], reducing with double buffering
- examples [Windows Forms], double-buffered graphics
ms.assetid: 4f6fef99-0972-436e-9d73-0167e4033f71
ms.openlocfilehash: ea4b4b8616ed0b3eab2ddd6b2ec57a39909a0fce
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524066"
---
# <a name="double-buffered-graphics"></a>Grafica a doppio buffer
Lo sfarfallio è un problema comune della programmazione della grafica. Le operazioni di grafica che richiedono più operazioni complesse di disegno possono causare lo sfarfallio o altri gravi problemi delle immagini sottoposte a rendering. Per risolvere questi problemi, .NET Framework fornisce l'accesso al doppio buffer.  
  
 Il doppio buffer usa un buffer di memoria per risolvere i problemi di sfarfallio associati a più operazioni di disegno. Quando il doppio buffer è abilitato, tutte le operazioni di disegno vengono prima sottoposte a rendering in un buffer di memoria invece che nella superficie di disegno visualizzata. Dopo che tutte le operazioni di disegno sono state completate, il buffer di memoria viene copiato direttamente nella superficie di disegno associata. Poiché sullo schermo viene eseguita una sola operazione di disegno, lo sfarfallio dell'immagine associato alle operazioni di disegno complesse viene eliminato.  
  
## <a name="default-double-buffering"></a>Doppio buffer predefinito  
 Il modo più semplice per usare il doppio buffer nelle applicazioni consiste nell'usare il doppio buffer predefinito per form e controlli disponibile in .NET Framework. È possibile abilitare il doppio buffering per Windows Form predefinito e modificati per i controlli di Windows mediante l'impostazione di <xref:System.Windows.Forms.Control.DoubleBuffered%2A> proprietà `true` o utilizzando il <xref:System.Windows.Forms.Control.SetStyle%2A> metodo. Per altre informazioni, vedere [Procedura: Ridurre lo sfarfallio nella grafica con il doppio buffering per form e controlli](../../../../docs/framework/winforms/advanced/how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md).  
  
## <a name="manually-managing-buffered-graphics"></a>Gestione manuale delle immagini memorizzate nel buffer  
 Per scenari di doppio buffer più avanzati, ad esempio l'animazione o la gestione avanzata della memoria, è possibile usare le classi di .NET Framework per implementare la propria logica di doppio buffer. La classe responsabile per l'allocazione e gestione dei singoli buffer grafici è la <xref:System.Drawing.BufferedGraphicsContext> classe. Ogni dominio applicazione con il proprio valore predefinito <xref:System.Drawing.BufferedGraphicsContext> dell'istanza che gestisce tutto il buffering doppio predefinito per tale applicazione. Nella maggior parte dei casi esisterà un solo dominio applicazione per ogni applicazione, pertanto non c'è in genere un valore predefinito <xref:System.Drawing.BufferedGraphicsContext> per ogni applicazione. Predefinito <xref:System.Drawing.BufferedGraphicsContext> gestite da istanze di <xref:System.Drawing.BufferedGraphicsManager> classe. È possibile recuperare un riferimento all'impostazione predefinita <xref:System.Drawing.BufferedGraphicsContext> istanza chiamando il <xref:System.Drawing.BufferedGraphicsManager.Current%2A>. È inoltre possibile creare una dedicata <xref:System.Drawing.BufferedGraphicsContext> istanza, che può migliorare le prestazioni per applicazioni grafiche. Per informazioni su come creare un <xref:System.Drawing.BufferedGraphicsContext> dell'istanza, vedere [procedura: gestire manualmente le immagini memorizzate nel buffer](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md).  
  
## <a name="manually-displaying-buffered-graphics"></a>Visualizzazione manuale della grafica memorizzata nel buffer  
 È possibile utilizzare un'istanza di <xref:System.Drawing.BufferedGraphicsContext> classe per creare il buffer di grafica chiamando il <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A?displayProperty=nameWithType>, che restituisce un'istanza del <xref:System.Drawing.BufferedGraphics> classe. Oggetto <xref:System.Drawing.BufferedGraphics> oggetto gestisce un buffer di memoria che è associato a una superficie di rendering, ad esempio un form o controllo.  
  
 Dopo che viene creata un'istanza, la <xref:System.Drawing.BufferedGraphics> classe gestisce il rendering in un buffer di grafica in memoria. È possibile eseguire il rendering di grafica nel buffer di memoria tramite il <xref:System.Drawing.BufferedGraphics.Graphics%2A>, che espone un <xref:System.Drawing.Graphics> oggetto che rappresenta direttamente il buffer di memoria. È possibile disegnare in questo <xref:System.Drawing.Graphics> oggetto esattamente come farebbe con un <xref:System.Drawing.Graphics> oggetto che rappresenta un'area di disegno. Tutti gli elementi grafici sono stati disegnati nel buffer, è possibile utilizzare il <xref:System.Drawing.BufferedGraphics.Render%2A?displayProperty=nameWithType> per copiare il contenuto del buffer nell'area di disegno sullo schermo.  
  
 Per ulteriori informazioni sull'utilizzo di <xref:System.Drawing.BufferedGraphics> classe, vedere [Rendering manuale di grafica memorizzata nel buffer](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md). Per altre informazioni sul rendering della grafica, vedere [Grafica e disegno in Windows Form](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Drawing.BufferedGraphics>  
 <xref:System.Drawing.BufferedGraphicsContext>  
 <xref:System.Drawing.BufferedGraphicsManager>  
 [Procedura: Eseguire il rendering manuale di grafica memorizzata nel buffer](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)  
 [Procedura: Ridurre lo sfarfallio nella grafica con il doppio buffering per form e controlli](../../../../docs/framework/winforms/advanced/how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 [Procedura: Gestire manualmente le immagini memorizzate nel buffer](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)  
 [Grafica e disegno in Windows Form](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
