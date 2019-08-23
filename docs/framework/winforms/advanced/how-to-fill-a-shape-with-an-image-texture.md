---
title: "Procedura: Riempire una forma con una trama basata su un'immagine"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using with brushes
- bitmaps [Windows Forms], using texture
- shapes [Windows Forms], filling with images
ms.assetid: 508da5a6-2433-4d2b-9680-eaeae4e96e3b
ms.openlocfilehash: 42c456137f84c6fa657ba5a09727eae052a45376
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69911685"
---
# <a name="how-to-fill-a-shape-with-an-image-texture"></a>Procedura: Riempire una forma con una trama basata su un'immagine
È possibile riempire una forma chiusa con una trama usando la <xref:System.Drawing.Image> classe e la <xref:System.Drawing.TextureBrush> classe.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene riempita un'ellisse con un'immagine. Il codice costruisce un <xref:System.Drawing.Image> oggetto e quindi passa l'indirizzo di tale <xref:System.Drawing.Image> oggetto come argomento a un <xref:System.Drawing.TextureBrush.%23ctor%2A> costruttore. La terza istruzione ridimensiona l'immagine e la quarta viene riempita dall'ellisse con copie ripetute dell'immagine ridimensionata.  
  
 Nel codice seguente, la <xref:System.Drawing.TextureBrush.Transform%2A> proprietà contiene la trasformazione applicata all'immagine prima che venga disegnata. Si supponga che l'immagine originale abbia una larghezza di 640 pixel e un'altezza di 480 pixel. La trasformazione riduce l'immagine a 75 × 75 impostando i valori di ridimensionamento orizzontale e verticale.  
  
> [!NOTE]
> Nell'esempio seguente, la dimensione dell'immagine è 75 × 75 e la dimensione dell'ellisse è 150 × 250. Poiché l'immagine è più piccola dell'ellisse che sta riempiendo, l'ellisse viene affiancata all'immagine. L'affiancamento significa che l'immagine viene ripetuta orizzontalmente e verticalmente fino a quando non viene raggiunto il limite della forma. Per ulteriori informazioni sull'affiancamento, [vedere Procedura: Affiancare una forma a un'](how-to-tile-a-shape-with-an-image.md)immagine.  
  
 [!code-csharp[System.Drawing.UsingABrush#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingABrush#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, che <xref:System.Windows.Forms.Control.Paint> è un parametro del gestore eventi.  
  
## <a name="see-also"></a>Vedere anche

- [Uso di un oggetto Brush per il riempimento di forme](using-a-brush-to-fill-shapes.md)
