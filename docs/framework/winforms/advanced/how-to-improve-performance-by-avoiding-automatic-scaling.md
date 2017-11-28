---
title: 'Procedura: migliorare le prestazioni evitando l''adattamento automatico'
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
- automatic scaling
- images [Windows Forms], improving performance
- images [Windows Forms], using without automatic scaling
- performance [Windows Forms], improving image
ms.assetid: 5fe2c95d-8653-4d55-bf0d-e5afa28f223b
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0130e0745dfca20da5dc723bb7cc84748bb0b148
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-improve-performance-by-avoiding-automatic-scaling"></a>Procedura: migliorare le prestazioni evitando l'adattamento automatico
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]può applicare la scalabilità automatica un'immagine durante il disegno, che ridurrebbe le prestazioni. In alternativa, è possibile controllare il ridimensionamento dell'immagine passando le dimensioni del rettangolo di destinazione per il <xref:System.Drawing.Graphics.DrawImage%2A> metodo.  
  
 Ad esempio, la seguente chiamata per il <xref:System.Drawing.Graphics.DrawImage%2A> metodo specifica un angolo superiore sinistro di (50, 30) ma non specifica un rettangolo di destinazione.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.WorkingWithImages#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#31)]  
  
 Anche se questa è la versione più semplice la <xref:System.Drawing.Graphics.DrawImage%2A> metodo in termini di numero di argomenti obbligatori, non è necessariamente la più efficiente. Se la risoluzione utilizzata da [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] (in genere 96 punti per pollice) è diversa da quella memorizzata nel <xref:System.Drawing.Image> oggetto, quindi il <xref:System.Drawing.Graphics.DrawImage%2A> (metodo), l'immagine verrà adattata. Si supponga, ad esempio, un <xref:System.Drawing.Image> oggetto ha una larghezza di 216 pixel e un valore di risoluzione orizzontale memorizzato di 72 punti per pollice. Poiché 216/72 è uguale a 3, <xref:System.Drawing.Graphics.DrawImage%2A> l'immagine verrà adattata in modo che abbia una larghezza di 3 pollici una risoluzione di 96 punti per pollice. Vale a dire <xref:System.Drawing.Graphics.DrawImage%2A> verrà visualizzata un'immagine con una larghezza di 96 x 3 = 288 pixel.  
  
 Anche se la risoluzione dello schermo è diversa da 96 punti per pollice, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] verrà probabilmente scala dell'immagine come se la risoluzione dello schermo sono stati 96 punti per pollice. Poiché un [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics> oggetto è associato a un contesto di dispositivo e quando [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] il contesto di dispositivo per la risoluzione dello schermo, il risultato è in genere 96, indipendentemente dall'effettiva risoluzione di query. È possibile evitare il ridimensionamento automatico, specificando il rettangolo di destinazione nel <xref:System.Drawing.Graphics.DrawImage%2A> metodo.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente disegna due volte la stessa immagine. Nel primo caso, la larghezza e altezza del rettangolo di destinazione non è specificati e l'immagine viene ridimensionata automaticamente. Nel secondo caso, la larghezza e altezza, misurata in pixel, del rettangolo di destinazione specificati per essere uguale a larghezza e altezza dell'immagine originale. Nella figura seguente mostra l'immagine visualizzata due volte.  
  
 ![Trama ridimensionata](../../../../docs/framework/winforms/advanced/media/csscaledtexture1.png "csscaledtexture1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.WorkingWithImages#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#32)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>. Sostituire texture. jpg con un nome dell'immagine e un percorso valido per il sistema.  
  
## <a name="see-also"></a>Vedere anche  
 [Immagini, bitmap e metafile](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [Utilizzo di immagini, bitmap, icone e metafile](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
