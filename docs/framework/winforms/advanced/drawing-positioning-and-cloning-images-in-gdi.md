---
title: Disegno, posizionamento e clonazione delle immagini in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- raster images [Windows Forms]
- images [Windows Forms], positioning
- drawing [Windows Forms], images
- drawing [Windows Forms], raster images
- images [Windows Forms], cloning
- images [Windows Forms], drawing
- GDI+, drawing images
- GDI+, cloning images
- GDI+, positioning images
ms.assetid: 09f0c07a-19c0-43b4-90a2-862a10545ce8
ms.openlocfilehash: 5ff502884874e21e8f34acb2f15db4c651a0a273
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="drawing-positioning-and-cloning-images-in-gdi"></a>Disegno, posizionamento e clonazione delle immagini in GDI+
È possibile utilizzare il <xref:System.Drawing.Bitmap> classe per caricare e visualizzare le immagini raster e si può utilizzare il <xref:System.Drawing.Imaging.Metafile> classe per caricare e visualizzare immagini vettoriali. Il <xref:System.Drawing.Bitmap> e <xref:System.Drawing.Imaging.Metafile> le classi ereditano dalla <xref:System.Drawing.Image> classe. Per visualizzare un'immagine vettoriale, sono necessari un'istanza di <xref:System.Drawing.Graphics> classe e un <xref:System.Drawing.Imaging.Metafile>. Per visualizzare un'immagine raster, sono necessari un'istanza di <xref:System.Drawing.Graphics> classe e un <xref:System.Drawing.Bitmap>. L'istanza del <xref:System.Drawing.Graphics> classe fornisce il <xref:System.Drawing.Graphics.DrawImage%2A> metodo che riceve il <xref:System.Drawing.Imaging.Metafile> o <xref:System.Drawing.Bitmap> come argomento.  
  
## <a name="file-types-and-cloning"></a>Tipi di file e la clonazione  
 Esempio di codice seguente viene illustrato come costruire un <xref:System.Drawing.Bitmap> dal file Climber. jpg e visualizzare la bitmap. Il punto di destinazione per l'angolo superiore sinistro dell'immagine, (10, 10), specificato nel secondo e il terzo parametro.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#11)]  
  
 Nella figura seguente mostra l'immagine.  
  
 ![Esempio di immagine](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art04.gif "AboutGdip03_Art04")  
  
 È possibile costruire <xref:System.Drawing.Bitmap> formati di file di oggetti da una varietà di grafica: BMP, GIF, JPEG, EXIF, PNG, TIFF e ICONA.  
  
 Esempio di codice seguente viene illustrato come costruire <xref:System.Drawing.Bitmap> degli oggetti da una varietà di tipi di file e quindi visualizzare le bitmap.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#12)]  
  
 Il <xref:System.Drawing.Bitmap> classe fornisce un <xref:System.Drawing.Bitmap.Clone%2A> metodo che è possibile utilizzare per creare una copia di un oggetto esistente <xref:System.Drawing.Bitmap>. Il <xref:System.Drawing.Bitmap.Clone%2A> metodo ha un parametro rettangolo di origine che è possibile utilizzare per specificare la parte della bitmap originale che si desidera copiare. Esempio di codice seguente viene illustrato come creare un <xref:System.Drawing.Bitmap> clonando la metà superiore di un oggetto esistente <xref:System.Drawing.Bitmap>. Quindi vengono disegnate entrambe le immagini.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#13)]  
  
 Nella figura seguente mostra le due immagini.  
  
 ![Il ritaglio](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art05.gif "AboutGdip03_Art05")  
  
## <a name="see-also"></a>Vedere anche  
 [Immagini, bitmap e metafile](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [Procedura: Creare oggetti Graphics per disegnare](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [Utilizzo di immagini, bitmap, icone e metafile](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
