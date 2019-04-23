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
ms.openlocfilehash: 099bc9f5359f19439f308f28a6766d470956daea
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59177320"
---
# <a name="how-to-fill-a-shape-with-an-image-texture"></a><span data-ttu-id="90f88-102">Procedura: Riempire una forma con una trama basata su un'immagine</span><span class="sxs-lookup"><span data-stu-id="90f88-102">How to: Fill a Shape with an Image Texture</span></span>
<span data-ttu-id="90f88-103">È possibile riempire una forma chiusa con una trama utilizzando la <xref:System.Drawing.Image> classe e il <xref:System.Drawing.TextureBrush> classe.</span><span class="sxs-lookup"><span data-stu-id="90f88-103">You can fill a closed shape with a texture by using the <xref:System.Drawing.Image> class and the <xref:System.Drawing.TextureBrush> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="90f88-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="90f88-104">Example</span></span>  
 <span data-ttu-id="90f88-105">Nell'esempio seguente viene compilato un'ellisse con un'immagine.</span><span class="sxs-lookup"><span data-stu-id="90f88-105">The following example fills an ellipse with an image.</span></span> <span data-ttu-id="90f88-106">Nel codice viene creata un' <xref:System.Drawing.Image> dell'oggetto e quindi passa l'indirizzo di tale <xref:System.Drawing.Image> oggetto come argomento a un <xref:System.Drawing.TextureBrush.%23ctor%2A> costruttore.</span><span class="sxs-lookup"><span data-stu-id="90f88-106">The code constructs an <xref:System.Drawing.Image> object, and then passes the address of that <xref:System.Drawing.Image> object as an argument to a <xref:System.Drawing.TextureBrush.%23ctor%2A> constructor.</span></span> <span data-ttu-id="90f88-107">La terza istruzione Ridimensiona l'immagine, e la quarta si riempie l'ellisse con le copie ripetute dell'immagine in scala.</span><span class="sxs-lookup"><span data-stu-id="90f88-107">The third statement scales the image, and the fourth statement fills the ellipse with repeated copies of the scaled image.</span></span>  
  
 <span data-ttu-id="90f88-108">Nel codice seguente, il <xref:System.Drawing.TextureBrush.Transform%2A> proprietà contiene la trasformazione applicata all'immagine prima che questa venga disegnata.</span><span class="sxs-lookup"><span data-stu-id="90f88-108">In the following code, the <xref:System.Drawing.TextureBrush.Transform%2A> property contains the transformation that is applied to the image before it is drawn.</span></span> <span data-ttu-id="90f88-109">Si supponga che l'immagine originale abbia una larghezza pari a 640 pixel e un'altezza pari a 480 pixel.</span><span class="sxs-lookup"><span data-stu-id="90f88-109">Assume that the original image has a width of 640 pixels and a height of 480 pixels.</span></span> <span data-ttu-id="90f88-110">La trasformazione, l'immagine viene ridotta a 75 × 75 impostando i valori di scala orizzontali e verticali.</span><span class="sxs-lookup"><span data-stu-id="90f88-110">The transform shrinks the image to 75×75 by setting the horizontal and vertical scaling values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="90f88-111">Nell'esempio seguente, le dimensioni dell'immagine sono 75 × 75, e le dimensioni di puntini di sospensione sono 150 × 250.</span><span class="sxs-lookup"><span data-stu-id="90f88-111">In the following example, the image size is 75×75, and the ellipse size is 150×250.</span></span> <span data-ttu-id="90f88-112">Perché l'immagine è minore dell'ellisse che riempire, con l'immagine viene affiancata l'ellisse.</span><span class="sxs-lookup"><span data-stu-id="90f88-112">Because the image is smaller than the ellipse it is filling, the ellipse is tiled with the image.</span></span> <span data-ttu-id="90f88-113">Affiancamento significa che l'immagine viene ripetuta orizzontalmente e verticalmente fino al limite della forma è stata raggiunta.</span><span class="sxs-lookup"><span data-stu-id="90f88-113">Tiling means that the image is repeated horizontally and vertically until the boundary of the shape is reached.</span></span> <span data-ttu-id="90f88-114">Per altre informazioni sul sezionamento, vedere [come: Riempire una forma con un'immagine](how-to-tile-a-shape-with-an-image.md).</span><span class="sxs-lookup"><span data-stu-id="90f88-114">For more information about tiling, see [How to: Tile a Shape with an Image](how-to-tile-a-shape-with-an-image.md).</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingABrush#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="90f88-115">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="90f88-115">Compiling the Code</span></span>  
 <span data-ttu-id="90f88-116">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="90f88-116">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90f88-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90f88-117">See also</span></span>

- [<span data-ttu-id="90f88-118">Uso di un oggetto Brush per il riempimento di forme</span><span class="sxs-lookup"><span data-stu-id="90f88-118">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
