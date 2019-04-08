---
title: 'Procedura: Variare le componenti cromatiche'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], transforming with color matrices
- colors [Windows Forms], shearing
ms.assetid: 0a424171-5b8b-45c4-afef-e9720a6c3e22
ms.openlocfilehash: bf645cf88c4905cd5cf47c2a6c7af088fa428c8a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59076247"
---
# <a name="how-to-shear-colors"></a>Procedura: Variare le componenti cromatiche
Inclinazione aumenta o diminuisce di un componente di colore in modo proporzionale a un altro componente di colore. Si consideri ad esempio la trasformazione in cui il componente rossa viene incrementato della metà di quella del valore del componente blu. In una trasformazione di questo tipo, il colore (0,2, 0.5, 1) diventerebbe (0,7, 0.5, 1). Il nuovo componente rossa è la 0.2 + (1/2)(1) = 0,7.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente si costruisce un <xref:System.Drawing.Image> oggetto Colorbars4 nel file. Il codice applica quindi la trasformazione di inclinazione descritta nel paragrafo precedente per ogni pixel nell'immagine.  
  
 Nella figura seguente mostra l'immagine originale a sinistra e l'immagine tagliata a destra: 
  
 ![Due dei quadrati con strisce colorato side-by-side che illustra l'immagine originale e l'immagine tagliata.](./media/how-to-shear-colors/original-image-sheared-image.png)  
  
 La tabella seguente elenca i vettori di colore per le quattro barre prima e dopo la trasformazione di inclinazione.  
  
|Originale|Inclinato|  
|--------------|-------------|  
|(0, 0, 1, 1)|(0.5, 0, 1, 1)|  
|(0.5, 1, 0.5, 1)|(0.75, 1, 0.5, 1)|  
|(1, 1, 0, 1)|(1, 1, 0, 1)|  
|(0.4, 0.4, 0.4, 1)|(0.6, 0.4, 0.4, 1)|  
  
 [!code-csharp[System.Drawing.Misc3#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs>`e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento. Sostituire `ColorBars.bmp` con un nome di immagine e un percorso valido nel sistema.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Grafica e disegno in Windows Form](graphics-and-drawing-in-windows-forms.md)
- [Ricolorazione di immagini](recoloring-images.md)
