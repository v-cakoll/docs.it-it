---
title: Ritaglio e ridimensionamento di immagini in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, scaling images
- GDI+, cropping images
- images [Windows Forms], cropping
- compressing data [Windows Forms], images
- images [Windows Forms], expansion
- images [Windows Forms], scaling
- rectangles [Windows Forms], source
- rectangles [Windows Forms], destination
- images [Windows Forms], compression
ms.assetid: ad5daf26-005f-45bc-a2af-e0e97777a21a
ms.openlocfilehash: c3cdb06e99770808461f9266fb5f07df9074149b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183729"
---
# <a name="cropping-and-scaling-images-in-gdi"></a>Ritaglio e ridimensionamento di immagini in GDI+
È possibile usare il <xref:System.Drawing.Graphics.DrawImage%2A> metodo di <xref:System.Drawing.Graphics> classe per creare e posizionare immagini vettoriali e raster. <xref:System.Drawing.Graphics.DrawImage%2A> è un metodo di overload, quindi esistono diversi modi, è possibile fornire argomenti.  
  
## <a name="drawimage-variations"></a>DrawImage varianti  
 Una variazione del <xref:System.Drawing.Graphics.DrawImage%2A> metodo riceve un <xref:System.Drawing.Bitmap> e un <xref:System.Drawing.Rectangle>. Il rettangolo specifica la destinazione per l'operazione di disegno. vale a dire, specifica il rettangolo in cui disegnare l'immagine. Se le dimensioni del rettangolo di destinazione sono diversa dalla dimensione dell'immagine originale, l'immagine viene adattata al rettangolo di destinazione. Esempio di codice seguente illustra come disegnare l'immagine stessa tre volte: una volta senza ridimensionamento, una volta con un'espansione e una volta con la compressione:  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#31)]  
  
 La figura seguente illustra le tre immagini.  
  
 ![Scaling](./media/aboutgdip03-art06.gif "AboutGdip03_Art06")  
  
 Alcune variazioni del <xref:System.Drawing.Graphics.DrawImage%2A> metodo hanno un parametro del rettangolo di origine, nonché un parametro del rettangolo di destinazione. Il parametro del rettangolo di origine specifica la parte dell'immagine originale da disegnare. Il rettangolo di destinazione specifica il rettangolo in cui disegnare la parte dell'immagine. Se le dimensioni del rettangolo di destinazione sono diversa dalla dimensione del rettangolo di origine, l'immagine viene adattata al rettangolo di destinazione.  
  
 Esempio di codice seguente viene illustrato come costruire un <xref:System.Drawing.Bitmap> Runner nel file. L'intera immagine viene disegnata con alcuna implementazione della scalabilità a (0, 0). Quindi una piccola parte dell'immagine viene disegnata due volte: una volta con la compressione e la seconda con un'espansione.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#32)]  
  
 La figura seguente mostra l'immagine non in scala e le parti immagine compresso ed espanso.  
  
 ![Ritaglio e ridimensionamento](./media/aboutgdip03-art07.gif "AboutGdip03_Art07")  
  
## <a name="see-also"></a>Vedere anche

- [Immagini, bitmap e metafile](images-bitmaps-and-metafiles.md)
- [Utilizzo di immagini, bitmap, icone e metafile](working-with-images-bitmaps-icons-and-metafiles.md)
