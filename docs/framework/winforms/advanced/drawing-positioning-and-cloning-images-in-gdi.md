---
title: Disegno, posizionamento e duplicazione delle immagini in GDI+
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
ms.openlocfilehash: b5f98e7bdef9ff8ed0a4cd0e040cb92a31f30503
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59188448"
---
# <a name="drawing-positioning-and-cloning-images-in-gdi"></a>Disegno, posizionamento e duplicazione delle immagini in GDI+
È possibile usare la <xref:System.Drawing.Bitmap> classe per caricare e visualizzare le immagini raster e si può usare il <xref:System.Drawing.Imaging.Metafile> classe da caricare e visualizzare immagini vettoriali. Il <xref:System.Drawing.Bitmap> e <xref:System.Drawing.Imaging.Metafile> ereditino dal <xref:System.Drawing.Image> classe. Per visualizzare un'immagine del vettore, è necessario un'istanza di <xref:System.Drawing.Graphics> classe e un <xref:System.Drawing.Imaging.Metafile>. Per visualizzare un'immagine raster, è necessario un'istanza di <xref:System.Drawing.Graphics> classe e un <xref:System.Drawing.Bitmap>. L'istanza del <xref:System.Drawing.Graphics> classe fornisce il <xref:System.Drawing.Graphics.DrawImage%2A> metodo, che riceve il <xref:System.Drawing.Imaging.Metafile> o <xref:System.Drawing.Bitmap> come argomento.  
  
## <a name="file-types-and-cloning"></a>Tipi di file e clonare  
 Esempio di codice seguente viene illustrato come costruire un <xref:System.Drawing.Bitmap> dal file Climber. jpg e visualizza l'immagine bitmap. Il punto di destinazione per l'angolo superiore sinistro dell'immagine, (10, 10), specificato nel secondo e terzo parametro.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#11)]  
  
 La figura seguente mostra l'immagine.  
  
 ![Esempio di immagine](./media/aboutgdip03-art04.gif "AboutGdip03_Art04")  
  
 È possibile costruire <xref:System.Drawing.Bitmap> formati di file di oggetti da una varietà di grafici: BMP, GIF, JPEG, EXIF, PNG, TIFF e ICONA.  
  
 Esempio di codice seguente viene illustrato come costruire <xref:System.Drawing.Bitmap> oggetti da un'ampia gamma di tipi di file e quindi Visualizza il bitmap.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#12)]  
  
 Il <xref:System.Drawing.Bitmap> classe fornisce un <xref:System.Drawing.Bitmap.Clone%2A> metodo che è possibile usare per creare una copia di un oggetto esistente <xref:System.Drawing.Bitmap>. Il <xref:System.Drawing.Bitmap.Clone%2A> metodo ha un parametro di rettangolo di origine che è possibile usare per specificare la parte della bitmap originale che si desidera copiare. Esempio di codice seguente viene illustrato come creare un <xref:System.Drawing.Bitmap> clonando la metà superiore di un oggetto esistente <xref:System.Drawing.Bitmap>. Quindi vengono create entrambe le immagini.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#13)]  
  
 La figura seguente mostra le due immagini.  
  
 ![Cropping](./media/aboutgdip03-art05.gif "AboutGdip03_Art05")  
  
## <a name="see-also"></a>Vedere anche

- [Immagini, bitmap e metafile](images-bitmaps-and-metafiles.md)
- [Procedura: Creare oggetti Graphics per disegnare](how-to-create-graphics-objects-for-drawing.md)
- [Utilizzo di immagini, bitmap, icone e metafile](working-with-images-bitmaps-icons-and-metafiles.md)
