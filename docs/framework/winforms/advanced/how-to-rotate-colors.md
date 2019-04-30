---
title: 'Procedura: Ruotare i colori'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], rotating
- examples [Windows Forms], rotating colors
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
ms.openlocfilehash: 241d2824fc2d87a0505eb6e790c865bfa7d8ef90
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967357"
---
# <a name="how-to-rotate-colors"></a><span data-ttu-id="aca63-102">Procedura: Ruotare i colori</span><span class="sxs-lookup"><span data-stu-id="aca63-102">How to: Rotate Colors</span></span>
<span data-ttu-id="aca63-103">È difficile identificare la rotazione in uno spazio dei colori quadridimensionale.</span><span class="sxs-lookup"><span data-stu-id="aca63-103">Rotation in a four-dimensional color space is difficult to visualize.</span></span> <span data-ttu-id="aca63-104">Abbiamo possiamo fare in modo più semplice visualizzare rotazione, supponendo di mantenere uno dei componenti di colore fisso.</span><span class="sxs-lookup"><span data-stu-id="aca63-104">We can make it easier to visualize rotation by agreeing to keep one of the color components fixed.</span></span> <span data-ttu-id="aca63-105">Si supponga di mantenere il componente alfa fissato a 1 (completamente opaco).</span><span class="sxs-lookup"><span data-stu-id="aca63-105">Suppose we agree to keep the alpha component fixed at 1 (fully opaque).</span></span> <span data-ttu-id="aca63-106">Quindi è possibile visualizzare uno spazio tridimensionale colore degli assi del colore rosso, verde e blu come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="aca63-106">Then we can visualize a three-dimensional color space with red, green, and blue axes as shown in the following illustration.</span></span>  
  
 ![Figura che illustra la rotazione con gli assi di colore rosso, verdi e blu.](./media/how-to-rotate-colors/rotation-red-green-blue-axes.gif)  
  
 <span data-ttu-id="aca63-108">Un colore può essere considerato come un punto nello spazio 3D.</span><span class="sxs-lookup"><span data-stu-id="aca63-108">A color can be thought of as a point in 3-D space.</span></span> <span data-ttu-id="aca63-109">Ad esempio, il punto nello spazio (1, 0, 0) rappresenta il colore rosso e il punto (0, 1, 0) nello spazio rappresenta il colore verde.</span><span class="sxs-lookup"><span data-stu-id="aca63-109">For example, the point (1, 0, 0) in space represents the color red, and the point (0, 1, 0) in space represents the color green.</span></span>  
  
 <span data-ttu-id="aca63-110">La figura seguente illustra che cosa significa ruotare i colori (1, 0, 0) di un angolo di 60 gradi nel piano di rosso-verde.</span><span class="sxs-lookup"><span data-stu-id="aca63-110">The following illustration shows what it means to rotate the color (1, 0, 0) through an angle of 60 degrees in the Red-Green plane.</span></span> <span data-ttu-id="aca63-111">Rotazione in un piano parallelo per il piano rosso-verde può essere considerata come una rotazione intorno all'asse blu.</span><span class="sxs-lookup"><span data-stu-id="aca63-111">Rotation in a plane parallel to the Red-Green plane can be thought of as rotation about the blue axis.</span></span>  
  
 ![Figura che illustra la rotazione intorno all'asse blu.](./media/how-to-rotate-colors/rotation-about-blue-axis.gif)  
  
 <span data-ttu-id="aca63-113">Nella figura seguente viene illustrato come inizializzare una matrice di colori per eseguire le rotazioni su ciascuno dei tre assi coordinati (rosso, verde, blu):</span><span class="sxs-lookup"><span data-stu-id="aca63-113">The following illustration shows how to initialize a color matrix to perform rotations about each of the three coordinate axes (red, green, blue):</span></span>  
  
 ![Inizializzare una matrice di colori per eseguire le rotazioni sui tre assi.](./media/how-to-rotate-colors/rotation-about-three-axes.gif)  
  
## <a name="example"></a><span data-ttu-id="aca63-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="aca63-115">Example</span></span>  
 <span data-ttu-id="aca63-116">Nell'esempio seguente accetta un'immagine è monocromatica (1, 0, 0.6) e si applica una rotazione di 60 gradi intorno all'asse blu.</span><span class="sxs-lookup"><span data-stu-id="aca63-116">The following example takes an image that is all one color (1, 0, 0.6) and applies a 60-degree rotation about the blue axis.</span></span> <span data-ttu-id="aca63-117">L'angolo di rotazione viene effettuata su un piano parallelo per il piano rosso-verde.</span><span class="sxs-lookup"><span data-stu-id="aca63-117">The angle of the rotation is swept out in a plane that is parallel to the red-green plane.</span></span>  
  
 <span data-ttu-id="aca63-118">La figura seguente mostra l'immagine originale sulla sinistra e l'immagine ruotata colori a destra:</span><span class="sxs-lookup"><span data-stu-id="aca63-118">The following illustration shows the original image on the left and the color-rotated image on the right:</span></span>  
  
 ![Figura che Mostra immagine originale e l'immagine ruotata di colore.](./media/how-to-rotate-colors/original-color-rotated-images.png)  
  
 <span data-ttu-id="aca63-120">La figura seguente mostra una visualizzazione della rotazione colore eseguita nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="aca63-120">The following illustration shows a visualization of the color rotation performed in the following code:</span></span>
  
 ![Figura che mostra la visualizzazione di rotazione del colore.](./media/how-to-rotate-colors/visualization-color-rotation.gif)  
  
 [!code-csharp[System.Drawing.RotateColors#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="aca63-122">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="aca63-122">Compiling the Code</span></span>  
 <span data-ttu-id="aca63-123">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs>`e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="aca63-123">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="aca63-124">Sostituire `RotationInput.bmp` con un nome file di immagine e un percorso valido nel sistema.</span><span class="sxs-lookup"><span data-stu-id="aca63-124">Replace `RotationInput.bmp` with an image file name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aca63-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aca63-125">See also</span></span>

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="aca63-126">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="aca63-126">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="aca63-127">Ricolorazione di immagini</span><span class="sxs-lookup"><span data-stu-id="aca63-127">Recoloring Images</span></span>](recoloring-images.md)
