---
title: 'Procedura: variare le componenti cromatiche'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], transforming with color matrices
- colors [Windows Forms], shearing
ms.assetid: 0a424171-5b8b-45c4-afef-e9720a6c3e22
ms.openlocfilehash: 204f15ce44d5ad688be0ea9ac0fa4a90781b25dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-shear-colors"></a>Procedura: variare le componenti cromatiche
Inclinazione aumenta o diminuisce di un componente di colore in modo proporzionale a un altro componente di colore. Si consideri ad esempio la trasformazione in cui il componente rosso viene aumentato la metà il valore del componente blu. In una trasformazione, il colore (0,2, 0,5, 1) diventa (0,7, 0,5, 1). Il nuovo componente rosso è 0,2 + (1/2)(1) = 0,7.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene costruito un <xref:System.Drawing.Image> oggetto dal file Colorbars4. Quindi il codice si applica la trasformazione di inclinazione descritta nel paragrafo precedente per ogni pixel dell'immagine.  
  
 Nella figura seguente mostra l'immagine originale a sinistra e l'immagine tagliata a destra.  
  
 ![Cromatiche](../../../../docs/framework/winforms/advanced/media/colortrans6.png "colortrans6")  
  
 Nella tabella seguente sono elencati i vettori di colore per le quattro barre prima e dopo la trasformazione di inclinazione.  
  
|Originale|Inclinato|  
|--------------|-------------|  
|(0, 0, 1, 1)|(0.5, 0, 1, 1)|  
|(0.5, 1, 0.5, 1)|(0.75, 1, 0.5, 1)|  
|(1, 1, 0, 1)|(1, 1, 0, 1)|  
|(0.4, 0.4, 0.4, 1)|(0.6, 0.4, 0.4, 1)|  
  
 [!code-csharp[System.Drawing.Misc3#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento. Sostituire `ColorBars.bmp` con un nome dell'immagine e un percorso valido per il sistema.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Drawing.Imaging.ColorMatrix>  
 <xref:System.Drawing.Imaging.ImageAttributes>  
 [Grafica e disegno in Windows Form](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Ricolorazione di immagini](../../../../docs/framework/winforms/advanced/recoloring-images.md)
