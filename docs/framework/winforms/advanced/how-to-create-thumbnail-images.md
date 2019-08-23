---
title: 'Procedura: Creare miniature'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thumbnail images [Windows Forms], creating
- images [Windows Forms], creating thumbnails
ms.assetid: e956242a-1e5b-4217-a3cf-5f3fb45d00ba
ms.openlocfilehash: 786a92d99f5e7a0c27f502efa9a5fe617ac4d4d6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923740"
---
# <a name="how-to-create-thumbnail-images"></a>Procedura: Creare miniature
Un'immagine di anteprima è una versione ridotta di un'immagine. È possibile creare un'immagine di anteprima chiamando il <xref:System.Drawing.Image.GetThumbnailImage%2A> metodo di un <xref:System.Drawing.Image> oggetto.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene costruito un <xref:System.Drawing.Image> oggetto da un file jpg. L'immagine originale ha una larghezza di 640 pixel e un'altezza di 479 pixel. Il codice crea un'immagine di anteprima con una larghezza di 100 pixel e un'altezza di 100 pixel.  
  
 Nell'illustrazione seguente viene mostrata l'immagine di anteprima:  
  
 ![Screenshot che mostra l'anteprima di output.](./media/how-to-create-thumbnail-images/construct-thumbnail-image.png)  
  
> [!NOTE]
> In questo esempio viene dichiarato un metodo di callback, che non viene mai usato. Supporta tutte le versioni di GDI+.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.WorkingWithImages#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, che <xref:System.Windows.Forms.Control.Paint> è un parametro del gestore eventi. Per eseguire l'esempio, attenersi alla procedura seguente:  
  
1. Creare una nuova applicazione Windows Forms.  
  
2. Aggiungere il codice di esempio al modulo.  
  
3. Creare un gestore per l' <xref:System.Windows.Forms.Control.Paint> evento del form  
  
4. Nel gestore chiamare il `GetThumbnail` metodo e passare `e` per <xref:System.Windows.Forms.PaintEventArgs>. <xref:System.Windows.Forms.Control.Paint>  
  
5. Trovare un file di immagine di cui si vuole eseguire un'anteprima.  
  
6. `GetThumbnail` Nel metodo specificare il percorso e il nome file dell'immagine.  
  
7. Premere F5 per eseguire l'esempio.  
  
     Viene visualizzata un'immagine di anteprima 100 per 100 nel form.  
  
## <a name="see-also"></a>Vedere anche

- [Immagini, bitmap e metafile](images-bitmaps-and-metafiles.md)
- [Utilizzo di immagini, bitmap, icone e metafile](working-with-images-bitmaps-icons-and-metafiles.md)
