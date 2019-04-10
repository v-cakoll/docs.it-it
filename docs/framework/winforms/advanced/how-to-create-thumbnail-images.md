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
ms.openlocfilehash: b9afbac85dee90938e2bd55ebe19d3b02c0d66d5
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59341491"
---
# <a name="how-to-create-thumbnail-images"></a>Procedura: Creare miniature
Un'immagine di anteprima è una versione ridotta dell'immagine. È possibile creare un'immagine di anteprima chiamando il <xref:System.Drawing.Image.GetThumbnailImage%2A> metodo di un <xref:System.Drawing.Image> oggetto.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente si costruisce un <xref:System.Drawing.Image> oggetto da un file JPG. L'immagine originale ha una larghezza pari a 640 pixel e un'altezza pari a 479 pixel. Il codice crea un'immagine di anteprima con una larghezza pari a 100 pixel e un'altezza pari a 100 pixel.  
  
 La figura seguente mostra l'immagine di anteprima.  
  
 ![Immagine di anteprima](./media/thumbnail1.png "Thumbnail1")  
  
> [!NOTE]
>  In questo esempio, un metodo di callback viene dichiarato, ma mai usato. Supporta tutte le versioni di GDI+.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.WorkingWithImages#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento. Per eseguire l'esempio, seguire questa procedura:  
  
1. Creare una nuova applicazione Windows Forms.  
  
2. Aggiungere il codice di esempio al form.  
  
3. Creare un gestore per il form <xref:System.Windows.Forms.Control.Paint> evento  
  
4. Nel <xref:System.Windows.Forms.Control.Paint> gestore, chiamare il `GetThumbnail` metodo e passare `e` per <xref:System.Windows.Forms.PaintEventArgs>.  
  
5. Trovare un file di immagine che si desidera creare un'anteprima.  
  
6. Nel `GetThumbnail` (metodo), specificare il percorso e nome dell'immagine del file.  
  
7. Premere F5 per eseguire l'esempio.  
  
     Un'immagine di anteprima di 100 per 100 viene visualizzato nel form.  
  
## <a name="see-also"></a>Vedere anche

- [Immagini, bitmap e metafile](images-bitmaps-and-metafiles.md)
- [Utilizzo di immagini, bitmap, icone e metafile](working-with-images-bitmaps-icons-and-metafiles.md)
