---
title: 'Procedura: utilizzare una tabella di riassociazione cromatica'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- color tables [Windows Forms], remapping colors with
- custom colors [Windows Forms], creating with color remap table
- color remap tables [Windows Forms], using
ms.assetid: 977df1ce-8665-42d4-9fb1-ef7f0ff63419
ms.openlocfilehash: ba763cc7960e71c6fc705d40eefdbde163d06181
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-a-color-remap-table"></a>Procedura: utilizzare una tabella di riassociazione cromatica
Modifica del mapping è il processo di conversione dei colori in un'immagine in base a una tabella di modifica del mapping dei colori. La tabella è una matrice di <xref:System.Drawing.Imaging.ColorMap> oggetti. Ogni <xref:System.Drawing.Imaging.ColorMap> oggetto nella matrice è un <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> proprietà e un <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> proprietà.  
  
 Quando [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] disegna un'immagine, ogni pixel dell'immagine viene confrontato con la matrice di colori precedente. Se il colore del pixel corrisponde a un colore precedente, viene modificato il colore per il nuovo colore corrispondente. I colori vengono modificati solo per il rendering, i valori di colore dell'immagine (archiviati in un <xref:System.Drawing.Image> o <xref:System.Drawing.Bitmap> oggetto) non vengono modificati.  
  
 Per disegnare un'immagine riassociata, inizializzare una matrice di <xref:System.Drawing.Imaging.ColorMap> oggetti. Passare la matrice di <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> metodo di un <xref:System.Drawing.Imaging.ImageAttributes> dell'oggetto e quindi passare il <xref:System.Drawing.Imaging.ImageAttributes> dell'oggetto per il <xref:System.Drawing.Graphics.DrawImage%2A> metodo di un <xref:System.Drawing.Graphics> oggetto.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creato un <xref:System.Drawing.Image> oggetto dal file RemapInput. Il codice crea una tabella di riassociazione cromatica costituita da una singola <xref:System.Drawing.Imaging.ColorMap> oggetto. Il <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> proprietà del `ColorRemap` è rosso, oggetto e <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> proprietà è di colore blu. L'immagine viene disegnata una sola volta senza mapping e una volta con mapping. Il processo di modifica del mapping modifica tutti i pixel rossi blu.  
  
 Nella figura seguente mostra l'immagine originale a sinistra e l'immagine rimappato a destra.  
  
 ![Modifica del mapping dei colori](../../../../docs/framework/winforms/advanced/media/colortrans7.png "colortrans7")  
  
 [!code-csharp[System.Drawing.RecoloringImages#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.RecoloringImages#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.  
  
## <a name="see-also"></a>Vedere anche  
 [Ricolorazione di immagini](../../../../docs/framework/winforms/advanced/recoloring-images.md)  
 [Immagini, bitmap e metafile](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
