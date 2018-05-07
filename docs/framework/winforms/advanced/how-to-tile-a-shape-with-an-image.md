---
title: 'Procedura: riempire una forma con immagini affiancate'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- texture brushes [Windows Forms], tiling images with
- images [Windows Forms], filling shapes with
- shapes [Windows Forms], tiling with images
- bitmaps [Windows Forms], filling shapes with
ms.assetid: 6d407891-6e5c-4495-a546-3da5604e9fb8
ms.openlocfilehash: 0905f29b0f74c72979e252cf94e677d1c7e0525d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-tile-a-shape-with-an-image"></a>Procedura: riempire una forma con immagini affiancate
Come riquadri possono essere inseriti uno accanto a altro per coprire un piano, rettangolare immagini possono essere posizionate accanto a altro su fill (riquadro) una forma. Per affiancare l'area interna di una forma, utilizzare un pennello di trama. Quando si creano un <xref:System.Drawing.TextureBrush> dell'oggetto, uno degli argomenti passati al costruttore è un <xref:System.Drawing.Image> oggetto. Quando si utilizza il pennello di trama per colorare l'interno di una forma, la forma viene riempita con le copie ripetute di questa immagine.  
  
 La proprietà modalità di incapsulamento del <xref:System.Drawing.TextureBrush> oggetto determina come l'immagine quando viene ripetuta in una griglia rettangolare. È possibile rendere tutti i riquadri nella griglia hanno lo stesso orientamento oppure è possibile rendere l'immagine capovolgere da una posizione della griglia a quella successiva. L'inversione può essere orizzontale, verticale, o entrambi. Gli esempi seguenti illustrano l'affiancamento con tipi diversi di inversione.  
  
### <a name="to-tile-an-image"></a>Per affiancare un'immagine  
  
-   Questo esempio Usa l'immagine di 75 × 75 seguente per un rettangolo 200 × 200.  
  
 ![Riquadro 1](../../../../docs/framework/winforms/advanced/media/tile1.gif "tile1")  
  
-   Nella figura seguente viene illustrato come modalità di affiancamento con l'immagine nel rettangolo. Si noti che tutti i riquadri hanno lo stesso orientamento. non sussiste alcun capovolgimento.  
  
 ![Riquadro 2](../../../../docs/framework/winforms/advanced/media/tile2.gif "tile2")  
  
 [!code-csharp[System.Drawing.UsingABrush#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingABrush#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#31)]  
  
### <a name="to-flip-an-image-horizontally-while-tiling"></a>Per invertire un'immagine in senso orizzontale durante l'affiancamento  
  
-   Nell'esempio viene utilizzata la stessa immagine 75 × 75 per riempire un rettangolo 200 × 200. Capovolgere orizzontalmente l'immagine, è impostata la modalità di disposizione. Nella figura seguente viene illustrato come modalità di affiancamento con l'immagine nel rettangolo. Si noti che quando si sposta da un riquadro a quella successiva in una determinata riga, l'immagine viene capovolto orizzontalmente.  
  
 ![Riquadro 3](../../../../docs/framework/winforms/advanced/media/tile3.gif "tile3")  
  
 [!code-csharp[System.Drawing.UsingABrush#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.UsingABrush#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#32)]  
  
### <a name="to-flip-an-image-vertically-while-tiling"></a>Per invertire un'immagine verticalmente durante l'affiancamento  
  
-   Nell'esempio viene utilizzata la stessa immagine 75 × 75 per riempire un rettangolo 200 × 200. Capovolgere verticalmente l'immagine, è impostata la modalità di disposizione.  
  
     [!code-csharp[System.Drawing.UsingABrush#33](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#33)]
     [!code-vb[System.Drawing.UsingABrush#33](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#33)]  
  
### <a name="to-flip-an-image-horizontally-and-vertically-while-tiling"></a>Per invertire un'immagine orizzontalmente e verticalmente durante l'affiancamento  
  
-   Nell'esempio viene utilizzata la stessa immagine 75 × 75 per un rettangolo 200 × 200. La modalità di disposizione è impostata in modo l'immagine sia orizzontalmente che verticalmente. Nella figura seguente viene illustrato come il rettangolo viene affiancato dall'immagine. Si noti che quando si sposta da un riquadro a quella successiva in una determinata riga, l'immagine viene capovolto orizzontalmente e quando si sposta da un riquadro a quella successiva in una determinata colonna, l'immagine viene capovolto verticalmente.  
  
 ![Riquadro 5](../../../../docs/framework/winforms/advanced/media/tile5.gif "tile5")  
  
 [!code-csharp[System.Drawing.UsingABrush#34](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.UsingABrush#34](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#34)]  
  
## <a name="see-also"></a>Vedere anche  
 [Uso di un oggetto Brush per il riempimento di forme](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
