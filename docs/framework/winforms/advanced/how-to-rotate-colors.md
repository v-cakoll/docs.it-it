---
title: 'Procedura: ruotare i colori'
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
- colors [Windows Forms], rotating
- examples [Windows Forms], rotating colors
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c82a77ff3d643afc0ddd542868a96c17d31ef336
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-rotate-colors"></a><span data-ttu-id="23b57-102">Procedura: ruotare i colori</span><span class="sxs-lookup"><span data-stu-id="23b57-102">How to: Rotate Colors</span></span>
<span data-ttu-id="23b57-103">Rotazione in uno spazio colore quadridimensionale è difficile da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="23b57-103">Rotation in a four-dimensional color space is difficult to visualize.</span></span> <span data-ttu-id="23b57-104">È possibile rendere più semplice per visualizzare la rotazione, supponendo di mantenere uno dei componenti di colore predefiniti.</span><span class="sxs-lookup"><span data-stu-id="23b57-104">We can make it easier to visualize rotation by agreeing to keep one of the color components fixed.</span></span> <span data-ttu-id="23b57-105">Si supponga di mantenere il componente alfa pari a 1 (completamente opaco).</span><span class="sxs-lookup"><span data-stu-id="23b57-105">Suppose we agree to keep the alpha component fixed at 1 (fully opaque).</span></span> <span data-ttu-id="23b57-106">È quindi possibile visualizzare uno spazio tridimensionale colore degli assi del rosso, verde e blu come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="23b57-106">Then we can visualize a three-dimensional color space with red, green, and blue axes as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="23b57-107">![Nuova colorazione](../../../../docs/framework/winforms/advanced/media/recoloring03.gif "recoloring03")</span><span class="sxs-lookup"><span data-stu-id="23b57-107">![Recoloring](../../../../docs/framework/winforms/advanced/media/recoloring03.gif "recoloring03")</span></span>  
  
 <span data-ttu-id="23b57-108">Un colore può essere considerato come un punto nello spazio 3D.</span><span class="sxs-lookup"><span data-stu-id="23b57-108">A color can be thought of as a point in 3-D space.</span></span> <span data-ttu-id="23b57-109">Ad esempio, il punto in uno spazio (1, 0, 0) rappresenta il colore rosso e il punto in uno spazio (0, 1, 0) rappresenta il colore verde.</span><span class="sxs-lookup"><span data-stu-id="23b57-109">For example, the point (1, 0, 0) in space represents the color red, and the point (0, 1, 0) in space represents the color green.</span></span>  
  
 <span data-ttu-id="23b57-110">Nell'illustrazione seguente significato ruotare il colore (1, 0, 0) di un angolo di 60 gradi nel piano verde a rosso.</span><span class="sxs-lookup"><span data-stu-id="23b57-110">The following illustration shows what it means to rotate the color (1, 0, 0) through an angle of 60 degrees in the Red-Green plane.</span></span> <span data-ttu-id="23b57-111">Rotazione in un piano parallelo al piano verde a rosso può essere considerata come la rotazione intorno all'asse blu.</span><span class="sxs-lookup"><span data-stu-id="23b57-111">Rotation in a plane parallel to the Red-Green plane can be thought of as rotation about the blue axis.</span></span>  
  
 <span data-ttu-id="23b57-112">![Nuova colorazione](../../../../docs/framework/winforms/advanced/media/recoloring04.gif "recoloring04")</span><span class="sxs-lookup"><span data-stu-id="23b57-112">![Recoloring](../../../../docs/framework/winforms/advanced/media/recoloring04.gif "recoloring04")</span></span>  
  
 <span data-ttu-id="23b57-113">Nella figura seguente viene illustrato come inizializzare una matrice di colori per eseguire rotazioni su ciascuno dei tre assi delle coordinate (rosso, verde e blu).</span><span class="sxs-lookup"><span data-stu-id="23b57-113">The following illustration shows how to initialize a color matrix to perform rotations about each of the three coordinate axes (red, green, blue).</span></span>  
  
 <span data-ttu-id="23b57-114">![Nuova colorazione](../../../../docs/framework/winforms/advanced/media/recoloring05.gif "recoloring05")</span><span class="sxs-lookup"><span data-stu-id="23b57-114">![Recoloring](../../../../docs/framework/winforms/advanced/media/recoloring05.gif "recoloring05")</span></span>  
  
## <a name="example"></a><span data-ttu-id="23b57-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="23b57-115">Example</span></span>  
 <span data-ttu-id="23b57-116">Nell'esempio seguente accetta un'immagine è monocromatica (1, 0, 0,6) e applica una rotazione di 60 gradi sull'asse del blu.</span><span class="sxs-lookup"><span data-stu-id="23b57-116">The following example takes an image that is all one color (1, 0, 0.6) and applies a 60-degree rotation about the blue axis.</span></span> <span data-ttu-id="23b57-117">Angolo di rotazione viene effettuata su un piano parallelo al piano verde a rosso.</span><span class="sxs-lookup"><span data-stu-id="23b57-117">The angle of the rotation is swept out in a plane that is parallel to the red-green plane.</span></span>  
  
 <span data-ttu-id="23b57-118">Nella figura seguente mostra l'immagine originale sulla sinistra e l'immagine ruotata colore a destra.</span><span class="sxs-lookup"><span data-stu-id="23b57-118">The following illustration shows the original image on the left and the color-rotated image on the right.</span></span>  
  
 <span data-ttu-id="23b57-119">![Rotazione dei colori](../../../../docs/framework/winforms/advanced/media/colortrans5.png "colortrans5")</span><span class="sxs-lookup"><span data-stu-id="23b57-119">![Rotate Colors](../../../../docs/framework/winforms/advanced/media/colortrans5.png "colortrans5")</span></span>  
  
 <span data-ttu-id="23b57-120">Nella figura seguente mostra una visualizzazione della rotazione colore eseguita nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="23b57-120">The following illustration shows a visualization of the color rotation performed in the following code.</span></span>  
  
 <span data-ttu-id="23b57-121">![Nuova colorazione](../../../../docs/framework/winforms/advanced/media/recoloring06.gif "recoloring06")</span><span class="sxs-lookup"><span data-stu-id="23b57-121">![Recoloring](../../../../docs/framework/winforms/advanced/media/recoloring06.gif "recoloring06")</span></span>  
  
 [!code-csharp[System.Drawing.RotateColors#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="23b57-122">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="23b57-122">Compiling the Code</span></span>  
 <span data-ttu-id="23b57-123">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs>`e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="23b57-123">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="23b57-124">Sostituire `RotationInput.bmp` con un nome di file di immagine e un percorso valido per il sistema.</span><span class="sxs-lookup"><span data-stu-id="23b57-124">Replace `RotationInput.bmp` with an image file name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23b57-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23b57-125">See Also</span></span>  
 <xref:System.Drawing.Imaging.ColorMatrix>  
 <xref:System.Drawing.Imaging.ImageAttributes>  
 [<span data-ttu-id="23b57-126">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="23b57-126">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="23b57-127">Ricolorazione di immagini</span><span class="sxs-lookup"><span data-stu-id="23b57-127">Recoloring Images</span></span>](../../../../docs/framework/winforms/advanced/recoloring-images.md)
