---
title: 'Procedura: Usare una tabella per modificare il mapping dei colori'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- color tables [Windows Forms], remapping colors with
- custom colors [Windows Forms], creating with color remap table
- color remap tables [Windows Forms], using
ms.assetid: 977df1ce-8665-42d4-9fb1-ef7f0ff63419
ms.openlocfilehash: 360ec30563ee5001d784dc7c4ccdb50563867c29
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505770"
---
# <a name="how-to-use-a-color-remap-table"></a>Procedura: Usare una tabella per modificare il mapping dei colori
Modifica del mapping è il processo di conversione dei colori in un'immagine in base a una tabella di rimappatura dei colori. La tabella di riassociazione cromatica è una matrice di <xref:System.Drawing.Imaging.ColorMap> oggetti. Ciascuna <xref:System.Drawing.Imaging.ColorMap> oggetto nella matrice ha un <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> proprietà e un <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> proprietà.  
  
 Quando GDI+ disegna un'immagine, ogni pixel dell'immagine viene confrontato con la matrice di colori precedente. Se il colore del pixel corrisponde a un colore precedente, il relativo colore viene modificato il nuovo colore corrispondente. I colori vengono modificati solo per il rendering, ovvero i valori di colore dell'immagine di se stesso (archiviati in un' <xref:System.Drawing.Image> o <xref:System.Drawing.Bitmap> oggetto) non vengono modificati.  
  
 Per disegnare un'immagine riassociata, inizializzare una matrice di <xref:System.Drawing.Imaging.ColorMap> oggetti. Passare la matrice per il <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> metodo di un <xref:System.Drawing.Imaging.ImageAttributes> dell'oggetto e quindi passare il <xref:System.Drawing.Imaging.ImageAttributes> dell'oggetto per il <xref:System.Drawing.Graphics.DrawImage%2A> metodo di un <xref:System.Drawing.Graphics> oggetto.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea un <xref:System.Drawing.Image> oggetto RemapInput nel file. Il codice crea una tabella di riassociazione cromatica costituito da un singolo <xref:System.Drawing.Imaging.ColorMap> oggetto. Il <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> proprietà del `ColorRemap` oggetto è in rosso e il <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> proprietà è blu. L'immagine viene disegnata una volta senza modifica del mapping e una con modifica del mapping. Il processo di modifica del mapping modifica tutti i pixel rosso a blu.  
  
 Nella figura seguente mostra l'immagine originale a sinistra e l'immagine rimappato a destra.  
  
 ![Screenshot che mostra l'immagine originale e l'immagine riassociata.](./media/how-to-use-a-color-remap-table/original-image-remap-colors.png)  
  
 [!code-csharp[System.Drawing.RecoloringImages#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.RecoloringImages#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.  
  
## <a name="see-also"></a>Vedere anche

- [Ricolorazione di immagini](recoloring-images.md)
- [Immagini, bitmap e metafile](images-bitmaps-and-metafiles.md)
