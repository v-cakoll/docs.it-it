---
title: 'Procedura: Migliorare le prestazioni evitando il ridimensionamento automatico'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- automatic scaling
- images [Windows Forms], improving performance
- images [Windows Forms], using without automatic scaling
- performance [Windows Forms], improving image
ms.assetid: 5fe2c95d-8653-4d55-bf0d-e5afa28f223b
ms.openlocfilehash: 8580bd2212a025edddada9e47b0dc2b6195b53c7
ms.sourcegitcommit: 15ab532fd5e1f8073a4b678922d93b68b521bfa0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/29/2019
ms.locfileid: "58653795"
---
# <a name="how-to-improve-performance-by-avoiding-automatic-scaling"></a>Procedura: Migliorare le prestazioni evitando il ridimensionamento automatico
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] durante il disegno, che ridurrebbe le prestazioni, può ridimensionare automaticamente un'immagine. In alternativa, è possibile controllare il ridimensionamento dell'immagine, passando le dimensioni del rettangolo di destinazione per il <xref:System.Drawing.Graphics.DrawImage%2A> (metodo).  
  
 Ad esempio, la chiamata seguente al <xref:System.Drawing.Graphics.DrawImage%2A> metodo specifica un angolo superiore sinistro del (50, 30) ma non specifica un rettangolo di destinazione.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.WorkingWithImages#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#31)]  
  
 Anche se questa è la versione più semplice del <xref:System.Drawing.Graphics.DrawImage%2A> metodo in termini di numero di argomenti obbligatori, non è necessariamente il più efficiente. Se la risoluzione utilizzata da [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] (in genere 96 punti per pollice) è diversa da quella memorizzata nel <xref:System.Drawing.Image> oggetto, quindi il <xref:System.Drawing.Graphics.DrawImage%2A> l'immagine verrà adattata (metodo). Ad esempio, si supponga che un <xref:System.Drawing.Image> oggetto ha una larghezza pari a 216 pixel e il valore archiviato risoluzione orizzontale 72 punti per pollice. Trattandosi di 3, 216/72 <xref:System.Drawing.Graphics.DrawImage%2A> l'immagine verrà adattata in modo che abbia una larghezza pari a 3 pollici una risoluzione di 96 punti per pollice. Vale a dire, <xref:System.Drawing.Graphics.DrawImage%2A> verranno visualizzati un'immagine con una larghezza pari a 96 x 3 = 288 pixel.  
  
 Anche se è diversa da 96 punti per pollice, della risoluzione dello schermo [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] verrà probabilmente la scala dell'immagine come se la risoluzione dello schermo fosse 96 punti per pollice. Infatti, una [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics> oggetto è associato un contesto di periferica e quando [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] query il contesto di dispositivo per la risoluzione dello schermo, il risultato in genere è 96, indipendentemente dalla risoluzione dello schermo effettivo. È possibile evitare il ridimensionamento automatico, specificando il rettangolo di destinazione nel <xref:System.Drawing.Graphics.DrawImage%2A> (metodo).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente disegna due volte la stessa immagine. Nel primo caso, la larghezza e altezza del rettangolo di destinazione non sono specificati e l'immagine viene ridimensionata automaticamente. Nel secondo caso, la larghezza e altezza, espresso in pixel, del rettangolo di destinazione vengono specificate sia lo stesso come la larghezza e altezza dell'immagine originale. Nella figura seguente mostra l'immagine visualizzata due volte:  
  
 ![Screenshot che mostra le immagini con trama in scala.](./media/how-to-improve-performance-by-avoiding-automatic-scaling/two-scaled-texture-images.png)  
  
 [!code-csharp[System.Drawing.WorkingWithImages#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.WorkingWithImages#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#32)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento. Sostituire texture. jpg con un nome di immagine e il percorso che sono validi per il sistema.  
  
## <a name="see-also"></a>Vedere anche
- [Immagini, bitmap e metafile](images-bitmaps-and-metafiles.md)
- [Utilizzo di immagini, bitmap, icone e metafile](working-with-images-bitmaps-icons-and-metafiles.md)
