---
title: 'Procedura: Riempire una forma con una trama basata su immagine'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using with brushes
- bitmaps [Windows Forms], using texture
- shapes [Windows Forms], filling with images
ms.assetid: 508da5a6-2433-4d2b-9680-eaeae4e96e3b
ms.openlocfilehash: 89ebad6773b076514f5a745db653e0e0a18d4b48
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708444"
---
# <a name="how-to-fill-a-shape-with-an-image-texture"></a>Procedura: Riempire una forma con una trama basata su immagine
È possibile riempire una forma chiusa con una trama utilizzando la <xref:System.Drawing.Image> classe e il <xref:System.Drawing.TextureBrush> classe.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene compilato un'ellisse con un'immagine. Nel codice viene creata un' <xref:System.Drawing.Image> dell'oggetto e quindi passa l'indirizzo di tale <xref:System.Drawing.Image> oggetto come argomento a un <xref:System.Drawing.TextureBrush.%23ctor%2A> costruttore. La terza istruzione Ridimensiona l'immagine, e la quarta si riempie l'ellisse con le copie ripetute dell'immagine in scala.  
  
 Nel codice seguente, il <xref:System.Drawing.TextureBrush.Transform%2A> proprietà contiene la trasformazione applicata all'immagine prima che questa venga disegnata. Si supponga che l'immagine originale abbia una larghezza pari a 640 pixel e un'altezza pari a 480 pixel. La trasformazione, l'immagine viene ridotta a 75 × 75 impostando i valori di scala orizzontali e verticali.  
  
> [!NOTE]
>  Nell'esempio seguente, le dimensioni dell'immagine sono 75 × 75, e le dimensioni di puntini di sospensione sono 150 × 250. Perché l'immagine è minore dell'ellisse che riempire, con l'immagine viene affiancata l'ellisse. Affiancamento significa che l'immagine viene ripetuta orizzontalmente e verticalmente fino al limite della forma è stata raggiunta. Per altre informazioni sul sezionamento, vedere [come: Riempire una forma con un'immagine](how-to-tile-a-shape-with-an-image.md).  
  
 [!code-csharp[System.Drawing.UsingABrush#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingABrush#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vedere anche
- [Uso di un oggetto Brush per il riempimento di forme](using-a-brush-to-fill-shapes.md)
