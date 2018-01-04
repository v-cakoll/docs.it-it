---
title: 'Procedura: riempire una forma con immagini affiancate'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- texture brushes [Windows Forms], tiling images with
- images [Windows Forms], filling shapes with
- shapes [Windows Forms], tiling with images
- bitmaps [Windows Forms], filling shapes with
ms.assetid: 6d407891-6e5c-4495-a546-3da5604e9fb8
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d8726322e9443042b76c28e7b4b22ebc51c871bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-tile-a-shape-with-an-image"></a><span data-ttu-id="15f11-102">Procedura: riempire una forma con immagini affiancate</span><span class="sxs-lookup"><span data-stu-id="15f11-102">How to: Tile a Shape with an Image</span></span>
<span data-ttu-id="15f11-103">Come riquadri possono essere inseriti uno accanto a altro per coprire un piano, rettangolare immagini possono essere posizionate accanto a altro su fill (riquadro) una forma.</span><span class="sxs-lookup"><span data-stu-id="15f11-103">Just as tiles can be placed next to each other to cover a floor, rectangular images can be placed next to each other to fill (tile) a shape.</span></span> <span data-ttu-id="15f11-104">Per affiancare l'area interna di una forma, utilizzare un pennello di trama.</span><span class="sxs-lookup"><span data-stu-id="15f11-104">To tile the interior of a shape, use a texture brush.</span></span> <span data-ttu-id="15f11-105">Quando si creano un <xref:System.Drawing.TextureBrush> dell'oggetto, uno degli argomenti passati al costruttore è un <xref:System.Drawing.Image> oggetto.</span><span class="sxs-lookup"><span data-stu-id="15f11-105">When you construct a <xref:System.Drawing.TextureBrush> object, one of the arguments you pass to the constructor is an <xref:System.Drawing.Image> object.</span></span> <span data-ttu-id="15f11-106">Quando si utilizza il pennello di trama per colorare l'interno di una forma, la forma viene riempita con le copie ripetute di questa immagine.</span><span class="sxs-lookup"><span data-stu-id="15f11-106">When you use the texture brush to paint the interior of a shape, the shape is filled with repeated copies of this image.</span></span>  
  
 <span data-ttu-id="15f11-107">La proprietà modalità di incapsulamento del <xref:System.Drawing.TextureBrush> oggetto determina come l'immagine quando viene ripetuta in una griglia rettangolare.</span><span class="sxs-lookup"><span data-stu-id="15f11-107">The wrap mode property of the <xref:System.Drawing.TextureBrush> object determines how the image is oriented as it is repeated in a rectangular grid.</span></span> <span data-ttu-id="15f11-108">È possibile rendere tutti i riquadri nella griglia hanno lo stesso orientamento oppure è possibile rendere l'immagine capovolgere da una posizione della griglia a quella successiva.</span><span class="sxs-lookup"><span data-stu-id="15f11-108">You can make all the tiles in the grid have the same orientation, or you can make the image flip from one grid position to the next.</span></span> <span data-ttu-id="15f11-109">L'inversione può essere orizzontale, verticale, o entrambi.</span><span class="sxs-lookup"><span data-stu-id="15f11-109">The flipping can be horizontal, vertical, or both.</span></span> <span data-ttu-id="15f11-110">Gli esempi seguenti illustrano l'affiancamento con tipi diversi di inversione.</span><span class="sxs-lookup"><span data-stu-id="15f11-110">The following examples demonstrate tiling with different types of flipping.</span></span>  
  
### <a name="to-tile-an-image"></a><span data-ttu-id="15f11-111">Per affiancare un'immagine</span><span class="sxs-lookup"><span data-stu-id="15f11-111">To tile an image</span></span>  
  
-   <span data-ttu-id="15f11-112">Questo esempio Usa l'immagine di 75 × 75 seguente per un rettangolo 200 × 200.</span><span class="sxs-lookup"><span data-stu-id="15f11-112">This example uses the following 75×75 image to tile a 200×200 rectangle.</span></span>  
  
 <span data-ttu-id="15f11-113">![Riquadro 1](../../../../docs/framework/winforms/advanced/media/tile1.gif "tile1")</span><span class="sxs-lookup"><span data-stu-id="15f11-113">![Tile 1](../../../../docs/framework/winforms/advanced/media/tile1.gif "tile1")</span></span>  
  
-   <span data-ttu-id="15f11-114">Nella figura seguente viene illustrato come modalità di affiancamento con l'immagine nel rettangolo.</span><span class="sxs-lookup"><span data-stu-id="15f11-114">The following illustration shows how the rectangle is tiled with the image.</span></span> <span data-ttu-id="15f11-115">Si noti che tutti i riquadri hanno lo stesso orientamento. non sussiste alcun capovolgimento.</span><span class="sxs-lookup"><span data-stu-id="15f11-115">Note that all tiles have the same orientation; there is no flipping.</span></span>  
  
 <span data-ttu-id="15f11-116">![Riquadro 2](../../../../docs/framework/winforms/advanced/media/tile2.gif "tile2")</span><span class="sxs-lookup"><span data-stu-id="15f11-116">![Tile 2](../../../../docs/framework/winforms/advanced/media/tile2.gif "tile2")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingABrush#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#31)]  
  
### <a name="to-flip-an-image-horizontally-while-tiling"></a><span data-ttu-id="15f11-117">Per invertire un'immagine in senso orizzontale durante l'affiancamento</span><span class="sxs-lookup"><span data-stu-id="15f11-117">To flip an image horizontally while tiling</span></span>  
  
-   <span data-ttu-id="15f11-118">Nell'esempio viene utilizzata la stessa immagine 75 × 75 per riempire un rettangolo 200 × 200.</span><span class="sxs-lookup"><span data-stu-id="15f11-118">This example uses the same 75×75 image to fill a 200×200 rectangle.</span></span> <span data-ttu-id="15f11-119">Capovolgere orizzontalmente l'immagine, è impostata la modalità di disposizione.</span><span class="sxs-lookup"><span data-stu-id="15f11-119">The wrap mode is set to flip the image horizontally.</span></span> <span data-ttu-id="15f11-120">Nella figura seguente viene illustrato come modalità di affiancamento con l'immagine nel rettangolo.</span><span class="sxs-lookup"><span data-stu-id="15f11-120">The following illustration shows how the rectangle is tiled with the image.</span></span> <span data-ttu-id="15f11-121">Si noti che quando si sposta da un riquadro a quella successiva in una determinata riga, l'immagine viene capovolto orizzontalmente.</span><span class="sxs-lookup"><span data-stu-id="15f11-121">Note that as you move from one tile to the next in a given row, the image is flipped horizontally.</span></span>  
  
 <span data-ttu-id="15f11-122">![Riquadro 3](../../../../docs/framework/winforms/advanced/media/tile3.gif "tile3")</span><span class="sxs-lookup"><span data-stu-id="15f11-122">![Tile 3](../../../../docs/framework/winforms/advanced/media/tile3.gif "tile3")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.UsingABrush#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#32)]  
  
### <a name="to-flip-an-image-vertically-while-tiling"></a><span data-ttu-id="15f11-123">Per invertire un'immagine verticalmente durante l'affiancamento</span><span class="sxs-lookup"><span data-stu-id="15f11-123">To flip an image vertically while tiling</span></span>  
  
-   <span data-ttu-id="15f11-124">Nell'esempio viene utilizzata la stessa immagine 75 × 75 per riempire un rettangolo 200 × 200.</span><span class="sxs-lookup"><span data-stu-id="15f11-124">This example uses the same 75×75 image to fill a 200×200 rectangle.</span></span> <span data-ttu-id="15f11-125">Capovolgere verticalmente l'immagine, è impostata la modalità di disposizione.</span><span class="sxs-lookup"><span data-stu-id="15f11-125">The wrap mode is set to flip the image vertically.</span></span>  
  
     [!code-csharp[System.Drawing.UsingABrush#33](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#33)]
     [!code-vb[System.Drawing.UsingABrush#33](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#33)]  
  
### <a name="to-flip-an-image-horizontally-and-vertically-while-tiling"></a><span data-ttu-id="15f11-126">Per invertire un'immagine orizzontalmente e verticalmente durante l'affiancamento</span><span class="sxs-lookup"><span data-stu-id="15f11-126">To flip an image horizontally and vertically while tiling</span></span>  
  
-   <span data-ttu-id="15f11-127">Nell'esempio viene utilizzata la stessa immagine 75 × 75 per un rettangolo 200 × 200.</span><span class="sxs-lookup"><span data-stu-id="15f11-127">This example uses the same 75×75 image to tile a 200×200 rectangle.</span></span> <span data-ttu-id="15f11-128">La modalità di disposizione è impostata in modo l'immagine sia orizzontalmente che verticalmente.</span><span class="sxs-lookup"><span data-stu-id="15f11-128">The wrap mode is set to flip the image both horizontally and vertically.</span></span> <span data-ttu-id="15f11-129">Nella figura seguente viene illustrato come il rettangolo viene affiancato dall'immagine.</span><span class="sxs-lookup"><span data-stu-id="15f11-129">The following illustration shows how the rectangle is tiled by the image.</span></span> <span data-ttu-id="15f11-130">Si noti che quando si sposta da un riquadro a quella successiva in una determinata riga, l'immagine viene capovolto orizzontalmente e quando si sposta da un riquadro a quella successiva in una determinata colonna, l'immagine viene capovolto verticalmente.</span><span class="sxs-lookup"><span data-stu-id="15f11-130">Note that as you move from one tile to the next in a given row, the image is flipped horizontally, and as you move from one tile to the next in a given column, the image is flipped vertically.</span></span>  
  
 <span data-ttu-id="15f11-131">![Riquadro 5](../../../../docs/framework/winforms/advanced/media/tile5.gif "tile5")</span><span class="sxs-lookup"><span data-stu-id="15f11-131">![Tile 5](../../../../docs/framework/winforms/advanced/media/tile5.gif "tile5")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#34](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.UsingABrush#34](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="15f11-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15f11-132">See Also</span></span>  
 [<span data-ttu-id="15f11-133">Uso di un oggetto Brush per il riempimento di forme</span><span class="sxs-lookup"><span data-stu-id="15f11-133">Using a Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
