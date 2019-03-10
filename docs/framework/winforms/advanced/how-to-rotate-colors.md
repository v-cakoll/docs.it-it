---
title: 'Procedura: Rotazione dei colori'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], rotating
- examples [Windows Forms], rotating colors
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
ms.openlocfilehash: cb3824d8a5a5674b83124301dbfbd5a3ba60effa
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720618"
---
# <a name="how-to-rotate-colors"></a><span data-ttu-id="ce471-102">Procedura: Rotazione dei colori</span><span class="sxs-lookup"><span data-stu-id="ce471-102">How to: Rotate Colors</span></span>
<span data-ttu-id="ce471-103">È difficile identificare la rotazione in uno spazio dei colori quadridimensionale.</span><span class="sxs-lookup"><span data-stu-id="ce471-103">Rotation in a four-dimensional color space is difficult to visualize.</span></span> <span data-ttu-id="ce471-104">Abbiamo possiamo fare in modo più semplice visualizzare rotazione, supponendo di mantenere uno dei componenti di colore fisso.</span><span class="sxs-lookup"><span data-stu-id="ce471-104">We can make it easier to visualize rotation by agreeing to keep one of the color components fixed.</span></span> <span data-ttu-id="ce471-105">Si supponga di mantenere il componente alfa fissato a 1 (completamente opaco).</span><span class="sxs-lookup"><span data-stu-id="ce471-105">Suppose we agree to keep the alpha component fixed at 1 (fully opaque).</span></span> <span data-ttu-id="ce471-106">Quindi è possibile visualizzare uno spazio tridimensionale colore degli assi del colore rosso, verde e blu come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="ce471-106">Then we can visualize a three-dimensional color space with red, green, and blue axes as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="ce471-107">![Recoloring](./media/recoloring03.gif "recoloring03")</span><span class="sxs-lookup"><span data-stu-id="ce471-107">![Recoloring](./media/recoloring03.gif "recoloring03")</span></span>  
  
 <span data-ttu-id="ce471-108">Un colore può essere considerato come un punto nello spazio 3D.</span><span class="sxs-lookup"><span data-stu-id="ce471-108">A color can be thought of as a point in 3-D space.</span></span> <span data-ttu-id="ce471-109">Ad esempio, il punto nello spazio (1, 0, 0) rappresenta il colore rosso e il punto (0, 1, 0) nello spazio rappresenta il colore verde.</span><span class="sxs-lookup"><span data-stu-id="ce471-109">For example, the point (1, 0, 0) in space represents the color red, and the point (0, 1, 0) in space represents the color green.</span></span>  
  
 <span data-ttu-id="ce471-110">La figura seguente illustra che cosa significa ruotare i colori (1, 0, 0) di un angolo di 60 gradi nel piano di rosso-verde.</span><span class="sxs-lookup"><span data-stu-id="ce471-110">The following illustration shows what it means to rotate the color (1, 0, 0) through an angle of 60 degrees in the Red-Green plane.</span></span> <span data-ttu-id="ce471-111">Rotazione in un piano parallelo per il piano rosso-verde può essere considerata come una rotazione intorno all'asse blu.</span><span class="sxs-lookup"><span data-stu-id="ce471-111">Rotation in a plane parallel to the Red-Green plane can be thought of as rotation about the blue axis.</span></span>  
  
 <span data-ttu-id="ce471-112">![Recoloring](./media/recoloring04.gif "recoloring04")</span><span class="sxs-lookup"><span data-stu-id="ce471-112">![Recoloring](./media/recoloring04.gif "recoloring04")</span></span>  
  
 <span data-ttu-id="ce471-113">Nella figura seguente viene illustrato come inizializzare una matrice di colori per eseguire le rotazioni su ciascuno dei tre assi coordinati (rosso, verde, blu).</span><span class="sxs-lookup"><span data-stu-id="ce471-113">The following illustration shows how to initialize a color matrix to perform rotations about each of the three coordinate axes (red, green, blue).</span></span>  
  
 <span data-ttu-id="ce471-114">![Recoloring](./media/recoloring05.gif "recoloring05")</span><span class="sxs-lookup"><span data-stu-id="ce471-114">![Recoloring](./media/recoloring05.gif "recoloring05")</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce471-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="ce471-115">Example</span></span>  
 <span data-ttu-id="ce471-116">Nell'esempio seguente accetta un'immagine è monocromatica (1, 0, 0.6) e si applica una rotazione di 60 gradi intorno all'asse blu.</span><span class="sxs-lookup"><span data-stu-id="ce471-116">The following example takes an image that is all one color (1, 0, 0.6) and applies a 60-degree rotation about the blue axis.</span></span> <span data-ttu-id="ce471-117">L'angolo di rotazione viene effettuata su un piano parallelo per il piano rosso-verde.</span><span class="sxs-lookup"><span data-stu-id="ce471-117">The angle of the rotation is swept out in a plane that is parallel to the red-green plane.</span></span>  
  
 <span data-ttu-id="ce471-118">La figura seguente mostra l'immagine originale sulla sinistra e l'immagine ruotata colori a destra.</span><span class="sxs-lookup"><span data-stu-id="ce471-118">The following illustration shows the original image on the left and the color-rotated image on the right.</span></span>  
  
 <span data-ttu-id="ce471-119">![Ruotare i colori](./media/colortrans5.png "colortrans5")</span><span class="sxs-lookup"><span data-stu-id="ce471-119">![Rotate Colors](./media/colortrans5.png "colortrans5")</span></span>  
  
 <span data-ttu-id="ce471-120">La figura seguente mostra una visualizzazione della rotazione colore eseguita nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="ce471-120">The following illustration shows a visualization of the color rotation performed in the following code.</span></span>  
  
 <span data-ttu-id="ce471-121">![Recoloring](./media/recoloring06.gif "recoloring06")</span><span class="sxs-lookup"><span data-stu-id="ce471-121">![Recoloring](./media/recoloring06.gif "recoloring06")</span></span>  
  
 [!code-csharp[System.Drawing.RotateColors#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ce471-122">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="ce471-122">Compiling the Code</span></span>  
 <span data-ttu-id="ce471-123">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs>`e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="ce471-123">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="ce471-124">Sostituire `RotationInput.bmp` con un nome file di immagine e un percorso valido nel sistema.</span><span class="sxs-lookup"><span data-stu-id="ce471-124">Replace `RotationInput.bmp` with an image file name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce471-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce471-125">See also</span></span>
- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="ce471-126">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="ce471-126">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="ce471-127">Ricolorazione di immagini</span><span class="sxs-lookup"><span data-stu-id="ce471-127">Recoloring Images</span></span>](recoloring-images.md)
