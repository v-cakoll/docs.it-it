---
title: "Procedura: Riempire una forma con un'immagine"
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
ms.openlocfilehash: f2edde7e78f996d4a7bfbc636210f315c0718f6d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54693214"
---
# <a name="how-to-tile-a-shape-with-an-image"></a><span data-ttu-id="cf246-102">Procedura: Riempire una forma con un'immagine</span><span class="sxs-lookup"><span data-stu-id="cf246-102">How to: Tile a Shape with an Image</span></span>
<span data-ttu-id="cf246-103">Proprio come i riquadri possono essere inseriti uno accanto a altro per coprire un piano, rettangolare immagini possono essere inserite uno accanto a altro su fill (riquadro) una forma.</span><span class="sxs-lookup"><span data-stu-id="cf246-103">Just as tiles can be placed next to each other to cover a floor, rectangular images can be placed next to each other to fill (tile) a shape.</span></span> <span data-ttu-id="cf246-104">Per affiancare l'interno di una forma, usare un pennello di trama.</span><span class="sxs-lookup"><span data-stu-id="cf246-104">To tile the interior of a shape, use a texture brush.</span></span> <span data-ttu-id="cf246-105">Quando si costruisce una <xref:System.Drawing.TextureBrush> dell'oggetto, uno degli argomenti passati al costruttore è un <xref:System.Drawing.Image> oggetto.</span><span class="sxs-lookup"><span data-stu-id="cf246-105">When you construct a <xref:System.Drawing.TextureBrush> object, one of the arguments you pass to the constructor is an <xref:System.Drawing.Image> object.</span></span> <span data-ttu-id="cf246-106">Quando si usa il pennello di trama per colorare l'interno di una forma, la forma viene riempita con le copie ripetute di questa immagine.</span><span class="sxs-lookup"><span data-stu-id="cf246-106">When you use the texture brush to paint the interior of a shape, the shape is filled with repeated copies of this image.</span></span>  
  
 <span data-ttu-id="cf246-107">La proprietà modalità a capo automatico del <xref:System.Drawing.TextureBrush> oggetto determina come l'immagine quando viene ripetuta in una griglia rettangolare.</span><span class="sxs-lookup"><span data-stu-id="cf246-107">The wrap mode property of the <xref:System.Drawing.TextureBrush> object determines how the image is oriented as it is repeated in a rectangular grid.</span></span> <span data-ttu-id="cf246-108">È possibile apportare tutti i riquadri della griglia sono l'orientamento stesso, oppure è possibile rendere l'immagine di capovolgimento da una posizione della griglia a quella successiva.</span><span class="sxs-lookup"><span data-stu-id="cf246-108">You can make all the tiles in the grid have the same orientation, or you can make the image flip from one grid position to the next.</span></span> <span data-ttu-id="cf246-109">Il capovolgimento può essere orizzontale, verticale o entrambi.</span><span class="sxs-lookup"><span data-stu-id="cf246-109">The flipping can be horizontal, vertical, or both.</span></span> <span data-ttu-id="cf246-110">Gli esempi seguenti illustrano l'affiancamento con tipi diversi di capovolgimento.</span><span class="sxs-lookup"><span data-stu-id="cf246-110">The following examples demonstrate tiling with different types of flipping.</span></span>  
  
### <a name="to-tile-an-image"></a><span data-ttu-id="cf246-111">Per affiancare un'immagine</span><span class="sxs-lookup"><span data-stu-id="cf246-111">To tile an image</span></span>  
  
-   <span data-ttu-id="cf246-112">Questo esempio Usa l'immagine di 75 × 75 seguente a un rettangolo con 200 × 200.</span><span class="sxs-lookup"><span data-stu-id="cf246-112">This example uses the following 75×75 image to tile a 200×200 rectangle.</span></span>  
  
 <span data-ttu-id="cf246-113">![Riquadro 1](../../../../docs/framework/winforms/advanced/media/tile1.gif "tile1")</span><span class="sxs-lookup"><span data-stu-id="cf246-113">![Tile 1](../../../../docs/framework/winforms/advanced/media/tile1.gif "tile1")</span></span>  
  
-   <span data-ttu-id="cf246-114">La figura seguente mostra come il rettangolo viene affiancato con l'immagine.</span><span class="sxs-lookup"><span data-stu-id="cf246-114">The following illustration shows how the rectangle is tiled with the image.</span></span> <span data-ttu-id="cf246-115">Si noti che tutti i riquadri hanno lo stesso orientamento. non è disponibile alcun capovolgimento.</span><span class="sxs-lookup"><span data-stu-id="cf246-115">Note that all tiles have the same orientation; there is no flipping.</span></span>  
  
 <span data-ttu-id="cf246-116">![Riquadro 2](../../../../docs/framework/winforms/advanced/media/tile2.gif "tile2")</span><span class="sxs-lookup"><span data-stu-id="cf246-116">![Tile 2](../../../../docs/framework/winforms/advanced/media/tile2.gif "tile2")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingABrush#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#31)]  
  
### <a name="to-flip-an-image-horizontally-while-tiling"></a><span data-ttu-id="cf246-117">Capovolgere un'immagine orizzontalmente durante la visualizzazione affiancata</span><span class="sxs-lookup"><span data-stu-id="cf246-117">To flip an image horizontally while tiling</span></span>  
  
-   <span data-ttu-id="cf246-118">Questo esempio Usa la stessa immagine di 75 × 75 per riempire il rettangolo di 200 × 200.</span><span class="sxs-lookup"><span data-stu-id="cf246-118">This example uses the same 75×75 image to fill a 200×200 rectangle.</span></span> <span data-ttu-id="cf246-119">Capovolgere orizzontalmente l'immagine è impostata la modalità di disposizione.</span><span class="sxs-lookup"><span data-stu-id="cf246-119">The wrap mode is set to flip the image horizontally.</span></span> <span data-ttu-id="cf246-120">La figura seguente mostra come il rettangolo viene affiancato con l'immagine.</span><span class="sxs-lookup"><span data-stu-id="cf246-120">The following illustration shows how the rectangle is tiled with the image.</span></span> <span data-ttu-id="cf246-121">Si noti che quando si sposta da un'immagine a quella successiva in una determinata riga, l'immagine viene capovolta orizzontalmente.</span><span class="sxs-lookup"><span data-stu-id="cf246-121">Note that as you move from one tile to the next in a given row, the image is flipped horizontally.</span></span>  
  
 <span data-ttu-id="cf246-122">![Riquadro 3](../../../../docs/framework/winforms/advanced/media/tile3.gif "tile3")</span><span class="sxs-lookup"><span data-stu-id="cf246-122">![Tile 3](../../../../docs/framework/winforms/advanced/media/tile3.gif "tile3")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.UsingABrush#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#32)]  
  
### <a name="to-flip-an-image-vertically-while-tiling"></a><span data-ttu-id="cf246-123">Capovolgere un'immagine verticalmente durante la visualizzazione affiancata</span><span class="sxs-lookup"><span data-stu-id="cf246-123">To flip an image vertically while tiling</span></span>  
  
-   <span data-ttu-id="cf246-124">Questo esempio Usa la stessa immagine di 75 × 75 per riempire il rettangolo di 200 × 200.</span><span class="sxs-lookup"><span data-stu-id="cf246-124">This example uses the same 75×75 image to fill a 200×200 rectangle.</span></span> <span data-ttu-id="cf246-125">Capovolgere verticalmente l'immagine è impostata la modalità di disposizione.</span><span class="sxs-lookup"><span data-stu-id="cf246-125">The wrap mode is set to flip the image vertically.</span></span>  
  
     [!code-csharp[System.Drawing.UsingABrush#33](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#33)]
     [!code-vb[System.Drawing.UsingABrush#33](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#33)]  
  
### <a name="to-flip-an-image-horizontally-and-vertically-while-tiling"></a><span data-ttu-id="cf246-126">Capovolgere orizzontalmente e verticalmente un'immagine durante la visualizzazione affiancata</span><span class="sxs-lookup"><span data-stu-id="cf246-126">To flip an image horizontally and vertically while tiling</span></span>  
  
-   <span data-ttu-id="cf246-127">Questo esempio Usa la stessa immagine di 75 × 75 per un rettangolo con 200 × 200.</span><span class="sxs-lookup"><span data-stu-id="cf246-127">This example uses the same 75×75 image to tile a 200×200 rectangle.</span></span> <span data-ttu-id="cf246-128">La modalità a capo automatico è impostata per capovolgere l'immagine sia orizzontalmente che verticalmente.</span><span class="sxs-lookup"><span data-stu-id="cf246-128">The wrap mode is set to flip the image both horizontally and vertically.</span></span> <span data-ttu-id="cf246-129">La figura seguente mostra come viene affiancato il rettangolo nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="cf246-129">The following illustration shows how the rectangle is tiled by the image.</span></span> <span data-ttu-id="cf246-130">Si noti che quando si sposta da un'immagine a quella successiva in una determinata riga, l'immagine viene capovolta orizzontalmente e sposta da un riquadro a quella successiva in una determinata colonna, l'immagine viene capovolta orizzontalmente.</span><span class="sxs-lookup"><span data-stu-id="cf246-130">Note that as you move from one tile to the next in a given row, the image is flipped horizontally, and as you move from one tile to the next in a given column, the image is flipped vertically.</span></span>  
  
 <span data-ttu-id="cf246-131">![Riquadro 5](../../../../docs/framework/winforms/advanced/media/tile5.gif "tile5")</span><span class="sxs-lookup"><span data-stu-id="cf246-131">![Tile 5](../../../../docs/framework/winforms/advanced/media/tile5.gif "tile5")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#34](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.UsingABrush#34](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="cf246-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf246-132">See also</span></span>
- [<span data-ttu-id="cf246-133">Uso di un oggetto Brush per il riempimento di forme</span><span class="sxs-lookup"><span data-stu-id="cf246-133">Using a Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
