---
title: 'Procedura: Gestire manualmente la grafica memorizzata nel buffer'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing by manually managing graphics
- graphics [Windows Forms], managing buffered
ms.assetid: 4c2a90ee-bbbe-4ff6-9170-1b06c195c918
ms.openlocfilehash: 2cdcebd4e47996841ad58213d9c6252a6a3dd7b6
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591846"
---
# <a name="how-to-manually-manage-buffered-graphics"></a>Procedura: Gestire manualmente la grafica memorizzata nel buffer
Per scenari più avanzati doppio buffering, è possibile usare le classi di .NET Framework per implementare la propria logica di doppio buffer. La classe responsabile dell'allocazione e la gestione di singoli buffer di grafica è la <xref:System.Drawing.BufferedGraphicsContext> classe. Ogni applicazione dispone di un proprio predefinito <xref:System.Drawing.BufferedGraphicsContext> che gestisce tutto il doppio buffer predefinito per tale applicazione. È possibile recuperare un riferimento a questa istanza chiamando il <xref:System.Drawing.BufferedGraphicsManager.Current%2A>.  
  
### <a name="to-obtain-a-reference-to-the-default-bufferedgraphicscontext"></a>Per ottenere un riferimento a BufferedGraphicsContext predefinito  
  
- Impostare il <xref:System.Drawing.BufferedGraphicsManager.Current%2A> proprietà, come illustrato nell'esempio di codice seguente.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#11)]  
  
    > [!NOTE]
    >  Non è necessario chiamare il `Dispose` metodo sul <xref:System.Drawing.BufferedGraphicsContext> riferimento ricevuto dal <xref:System.Drawing.BufferedGraphicsManager> classe. Il <xref:System.Drawing.BufferedGraphicsManager> provvede a tutto l'allocazione di memoria e la distribuzione per impostazione predefinita <xref:System.Drawing.BufferedGraphicsContext> istanze.  
  
     Per le applicazioni a grafica intensiva, ad esempio di animazione, è talvolta possibile migliorare le prestazioni usando un oggetto dedicato <xref:System.Drawing.BufferedGraphicsContext> anziché il <xref:System.Drawing.BufferedGraphicsContext> forniti dal <xref:System.Drawing.BufferedGraphicsManager>. In questo modo è possibile creare e gestire singolarmente, buffer di grafica senza l'overhead delle prestazioni di gestione di tutti gli altri buffer grafici associati all'applicazione, anche se la memoria utilizzata dall'applicazione sarà maggiore.  
  
### <a name="to-create-a-dedicated-bufferedgraphicscontext"></a>Per creare un BufferedGraphicsContext dedicato  
  
- Dichiarare e creare una nuova istanza di <xref:System.Drawing.BufferedGraphicsContext> classe, come illustrato nell'esempio di codice seguente.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.BufferedGraphicsContext>
- [Grafica a doppio buffer](double-buffered-graphics.md)
- [Procedura: Eseguire il rendering manuale di grafica memorizzata nel buffer](how-to-manually-render-buffered-graphics.md)
