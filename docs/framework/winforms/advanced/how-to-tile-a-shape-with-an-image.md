---
title: 'Procedura: Riempire una forma con immagini affiancate'
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
ms.openlocfilehash: a906db44a548361df2822efa24d1dd1849cb5a24
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063743"
---
# <a name="how-to-tile-a-shape-with-an-image"></a>Procedura: Riempire una forma con immagini affiancate
Proprio come i riquadri possono essere inseriti uno accanto a altro per coprire un piano, rettangolare immagini possono essere inserite uno accanto a altro su fill (riquadro) una forma. Per affiancare l'interno di una forma, usare un pennello di trama. Quando si costruisce una <xref:System.Drawing.TextureBrush> dell'oggetto, uno degli argomenti passati al costruttore è un <xref:System.Drawing.Image> oggetto. Quando si usa il pennello di trama per colorare l'interno di una forma, la forma viene riempita con le copie ripetute di questa immagine.  
  
 La proprietà modalità a capo automatico del <xref:System.Drawing.TextureBrush> oggetto determina come l'immagine quando viene ripetuta in una griglia rettangolare. È possibile apportare tutti i riquadri della griglia sono l'orientamento stesso, oppure è possibile rendere l'immagine di capovolgimento da una posizione della griglia a quella successiva. Il capovolgimento può essere orizzontale, verticale o entrambi. Gli esempi seguenti illustrano l'affiancamento con tipi diversi di capovolgimento.  
  
### <a name="to-tile-an-image"></a>Per affiancare un'immagine  
  
- Questo esempio Usa l'immagine di 75 × 75 seguente a un rettangolo con 200 × 200.  
  
 ![L'immagine di riquadro che mostra una casa rossa e una struttura ad albero.](./media/how-to-tile-a-shape-with-an-image/rectangle-tile-200x200.gif)  
  
- La figura seguente mostra come il rettangolo viene affiancato con l'immagine. Si noti che tutti i riquadri hanno lo stesso orientamento. non è disponibile alcun capovolgimento.  
  
 ![Un rettangolo di tiled con l'immagine con l'orientamento stesso per tutti i riquadri.](./media/how-to-tile-a-shape-with-an-image/rectangle-tiled-image-no-flip.gif)  
  
 [!code-csharp[System.Drawing.UsingABrush#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingABrush#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#31)]  
  
### <a name="to-flip-an-image-horizontally-while-tiling"></a>Capovolgere un'immagine orizzontalmente durante la visualizzazione affiancata  
  
- Questo esempio Usa la stessa immagine di 75 × 75 per riempire il rettangolo di 200 × 200. Capovolgere orizzontalmente l'immagine è impostata la modalità di disposizione. La figura seguente mostra come il rettangolo viene affiancato con l'immagine. Si noti che quando si sposta da un'immagine a quella successiva in una determinata riga, l'immagine viene capovolta orizzontalmente.  
  
 ![Un rettangolo di tiled con l'immagine capovolta orizzontalmente.](./media/how-to-tile-a-shape-with-an-image/rectangle-tiled-image-horizontal-flip.gif)  
  
 [!code-csharp[System.Drawing.UsingABrush#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.UsingABrush#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#32)]  
  
### <a name="to-flip-an-image-vertically-while-tiling"></a>Capovolgere un'immagine verticalmente durante la visualizzazione affiancata  
  
- Questo esempio Usa la stessa immagine di 75 × 75 per riempire il rettangolo di 200 × 200. Capovolgere verticalmente l'immagine è impostata la modalità di disposizione.  
  
     [!code-csharp[System.Drawing.UsingABrush#33](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#33)]
     [!code-vb[System.Drawing.UsingABrush#33](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#33)]  
  
### <a name="to-flip-an-image-horizontally-and-vertically-while-tiling"></a>Capovolgere orizzontalmente e verticalmente un'immagine durante la visualizzazione affiancata  
  
- Questo esempio Usa la stessa immagine di 75 × 75 per un rettangolo con 200 × 200. La modalità a capo automatico è impostata per capovolgere l'immagine sia orizzontalmente che verticalmente. La figura seguente mostra come viene affiancato il rettangolo nell'immagine. Si noti che quando si sposta da un'immagine a quella successiva in una determinata riga, l'immagine viene capovolta orizzontalmente e sposta da un riquadro a quella successiva in una determinata colonna, l'immagine viene capovolta orizzontalmente.  
  
 ![Un rettangolo di tiled con l'immagine capovolta orizzontalmente e verticalmente.](./media/how-to-tile-a-shape-with-an-image/rectangle-tiled-image-horizontal-vertical-flip.gif)  
  
 [!code-csharp[System.Drawing.UsingABrush#34](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.UsingABrush#34](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#34)]  
  
## <a name="see-also"></a>Vedere anche

- [Uso di un oggetto Brush per il riempimento di forme](using-a-brush-to-fill-shapes.md)
