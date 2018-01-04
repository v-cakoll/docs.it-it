---
title: 'Procedura: riempire una forma con una trama basata su un''immagine'
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
- images [Windows Forms], using with brushes
- bitmaps [Windows Forms], using texture
- shapes [Windows Forms], filling with images
ms.assetid: 508da5a6-2433-4d2b-9680-eaeae4e96e3b
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7b5ef87762b08daa973237e7b3da1068640e08bd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-fill-a-shape-with-an-image-texture"></a><span data-ttu-id="b026c-102">Procedura: riempire una forma con una trama basata su un'immagine</span><span class="sxs-lookup"><span data-stu-id="b026c-102">How to: Fill a Shape with an Image Texture</span></span>
<span data-ttu-id="b026c-103">È possibile riempire una forma chiusa con una trama utilizzando il <xref:System.Drawing.Image> classe e <xref:System.Drawing.TextureBrush> classe.</span><span class="sxs-lookup"><span data-stu-id="b026c-103">You can fill a closed shape with a texture by using the <xref:System.Drawing.Image> class and the <xref:System.Drawing.TextureBrush> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b026c-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="b026c-104">Example</span></span>  
 <span data-ttu-id="b026c-105">Nell'esempio seguente inserisce un'ellisse con un'immagine.</span><span class="sxs-lookup"><span data-stu-id="b026c-105">The following example fills an ellipse with an image.</span></span> <span data-ttu-id="b026c-106">Nel codice viene creata un <xref:System.Drawing.Image> dell'oggetto e quindi passa l'indirizzo di tale <xref:System.Drawing.Image> oggetto come argomento a un <xref:System.Drawing.TextureBrush.%23ctor%2A> costruttore.</span><span class="sxs-lookup"><span data-stu-id="b026c-106">The code constructs an <xref:System.Drawing.Image> object, and then passes the address of that <xref:System.Drawing.Image> object as an argument to a <xref:System.Drawing.TextureBrush.%23ctor%2A> constructor.</span></span> <span data-ttu-id="b026c-107">La terza istruzione consente di ridimensionare l'immagine e la quarta si riempie l'ellisse con le copie ripetute di immagine ridimensionati.</span><span class="sxs-lookup"><span data-stu-id="b026c-107">The third statement scales the image, and the fourth statement fills the ellipse with repeated copies of the scaled image.</span></span>  
  
 <span data-ttu-id="b026c-108">Nel codice seguente, la <xref:System.Drawing.TextureBrush.Transform%2A> proprietà contiene la trasformazione applicata all'immagine prima che venga disegnato.</span><span class="sxs-lookup"><span data-stu-id="b026c-108">In the following code, the <xref:System.Drawing.TextureBrush.Transform%2A> property contains the transformation that is applied to the image before it is drawn.</span></span> <span data-ttu-id="b026c-109">Si supponga che l'immagine originale ha una larghezza di 640 pixel e un'altezza di 480 pixel.</span><span class="sxs-lookup"><span data-stu-id="b026c-109">Assume that the original image has a width of 640 pixels and a height of 480 pixels.</span></span> <span data-ttu-id="b026c-110">La trasformazione, l'immagine viene ridotta a 75 × 75 impostando i valori di scalabilità orizzontali e verticali.</span><span class="sxs-lookup"><span data-stu-id="b026c-110">The transform shrinks the image to 75×75 by setting the horizontal and vertical scaling values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b026c-111">Nell'esempio seguente, le dimensioni dell'immagine sono 75 × 75, e la dimensione di puntini di sospensione è 150 × 250.</span><span class="sxs-lookup"><span data-stu-id="b026c-111">In the following example, the image size is 75×75, and the ellipse size is 150×250.</span></span> <span data-ttu-id="b026c-112">Perché l'immagine è minore dell'ellisse da riempire, con l'immagine viene affiancata l'ellisse.</span><span class="sxs-lookup"><span data-stu-id="b026c-112">Because the image is smaller than the ellipse it is filling, the ellipse is tiled with the image.</span></span> <span data-ttu-id="b026c-113">Affiancamento che l'immagine viene ripetuta orizzontalmente e verticalmente fino al limite della forma viene raggiunto.</span><span class="sxs-lookup"><span data-stu-id="b026c-113">Tiling means that the image is repeated horizontally and vertically until the boundary of the shape is reached.</span></span> <span data-ttu-id="b026c-114">Per ulteriori informazioni sull'affiancamento, vedere [procedura: riempire una forma con un'immagine](../../../../docs/framework/winforms/advanced/how-to-tile-a-shape-with-an-image.md).</span><span class="sxs-lookup"><span data-stu-id="b026c-114">For more information about tiling, see [How to: Tile a Shape with an Image](../../../../docs/framework/winforms/advanced/how-to-tile-a-shape-with-an-image.md).</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingABrush#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b026c-115">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="b026c-115">Compiling the Code</span></span>  
 <span data-ttu-id="b026c-116">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="b026c-116">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b026c-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b026c-117">See Also</span></span>  
 [<span data-ttu-id="b026c-118">Uso di un oggetto Brush per il riempimento di forme</span><span class="sxs-lookup"><span data-stu-id="b026c-118">Using a Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
