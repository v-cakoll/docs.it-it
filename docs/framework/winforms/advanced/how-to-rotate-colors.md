---
title: 'Procedura: ruotare i colori'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], rotating
- examples [Windows Forms], rotating colors
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
ms.openlocfilehash: 8d2717dd7b819e963126072279b361fda02188bc
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111335"
---
# <a name="how-to-rotate-colors"></a><span data-ttu-id="55fd4-102">Procedura: ruotare i colori</span><span class="sxs-lookup"><span data-stu-id="55fd4-102">How to: Rotate Colors</span></span>
<span data-ttu-id="55fd4-103">La rotazione in uno spazio colore quadridimensionale è difficile da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="55fd4-103">Rotation in a four-dimensional color space is difficult to visualize.</span></span> <span data-ttu-id="55fd4-104">Possiamo rendere più facile visualizzare la rotazione accettando di mantenere fisso uno dei componenti di colore.</span><span class="sxs-lookup"><span data-stu-id="55fd4-104">We can make it easier to visualize rotation by agreeing to keep one of the color components fixed.</span></span> <span data-ttu-id="55fd4-105">Supponiamo di accettare di mantenere il componente alfa fisso a 1 (completamente opaco).</span><span class="sxs-lookup"><span data-stu-id="55fd4-105">Suppose we agree to keep the alpha component fixed at 1 (fully opaque).</span></span> <span data-ttu-id="55fd4-106">Quindi possiamo visualizzare uno spazio colore tridimensionale con gli assi rosso, verde e blu, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="55fd4-106">Then we can visualize a three-dimensional color space with red, green, and blue axes as shown in the following illustration.</span></span>  
  
 ![Illustrazione che mostra la rotazione con assi rossi, verdi e blu.](./media/how-to-rotate-colors/rotation-red-green-blue-axes.gif)  
  
 <span data-ttu-id="55fd4-108">Un colore può essere considerato come un punto nello spazio 3D.</span><span class="sxs-lookup"><span data-stu-id="55fd4-108">A color can be thought of as a point in 3D space.</span></span> <span data-ttu-id="55fd4-109">Ad esempio, il punto (1, 0, 0) nello spazio rappresenta il colore rosso e il punto (0, 1, 0) nello spazio rappresenta il colore verde.</span><span class="sxs-lookup"><span data-stu-id="55fd4-109">For example, the point (1, 0, 0) in space represents the color red, and the point (0, 1, 0) in space represents the color green.</span></span>  
  
 <span data-ttu-id="55fd4-110">La figura seguente mostra cosa significa ruotare il colore (1, 0, 0) attraverso un angolo di 60 gradi nel piano rosso-verde.</span><span class="sxs-lookup"><span data-stu-id="55fd4-110">The following illustration shows what it means to rotate the color (1, 0, 0) through an angle of 60 degrees in the Red-Green plane.</span></span> <span data-ttu-id="55fd4-111">La rotazione in un piano parallelo al piano rosso-verde può essere considerata come rotazione intorno all'asse blu.</span><span class="sxs-lookup"><span data-stu-id="55fd4-111">Rotation in a plane parallel to the Red-Green plane can be thought of as rotation about the blue axis.</span></span>  
  
 ![Illustrazione che mostra la rotazione attorno all'asse blu.](./media/how-to-rotate-colors/rotation-about-blue-axis.gif)  
  
 <span data-ttu-id="55fd4-113">Nella figura seguente viene illustrato come inizializzare una matrice di colori per eseguire rotazioni su ciascuno dei tre assi di coordinate (rosso, verde, blu):</span><span class="sxs-lookup"><span data-stu-id="55fd4-113">The following illustration shows how to initialize a color matrix to perform rotations about each of the three coordinate axes (red, green, blue):</span></span>  
  
 ![Inizializzare una matrice di colori per eseguire rotazioni su tre assi.](./media/how-to-rotate-colors/rotation-about-three-axes.gif)  
  
## <a name="example"></a><span data-ttu-id="55fd4-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="55fd4-115">Example</span></span>  
 <span data-ttu-id="55fd4-116">L'esempio seguente prende un'immagine che è tutto un colore (1, 0, 0,6) e applica una rotazione di 60 gradi intorno all'asse blu.</span><span class="sxs-lookup"><span data-stu-id="55fd4-116">The following example takes an image that is all one color (1, 0, 0.6) and applies a 60-degree rotation about the blue axis.</span></span> <span data-ttu-id="55fd4-117">L'angolo di rotazione viene spazzato via in un piano parallelo al piano rosso-verde.</span><span class="sxs-lookup"><span data-stu-id="55fd4-117">The angle of the rotation is swept out in a plane that is parallel to the red-green plane.</span></span>  
  
 <span data-ttu-id="55fd4-118">La figura seguente mostra l'immagine originale a sinistra e l'immagine ruotata a colori a destra:</span><span class="sxs-lookup"><span data-stu-id="55fd4-118">The following illustration shows the original image on the left and the color-rotated image on the right:</span></span>  
  
 ![Illustrazione che mostra l'immagine originale e l'immagine ruotata a colori.](./media/how-to-rotate-colors/original-color-rotated-images.png)  
  
 <span data-ttu-id="55fd4-120">Nella figura seguente viene illustrata una visualizzazione della rotazione dei colori eseguita nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="55fd4-120">The following illustration shows a visualization of the color rotation performed in the following code:</span></span>
  
 ![Illustrazione che mostra la visualizzazione della rotazione del colore.](./media/how-to-rotate-colors/visualization-color-rotation.gif)  
  
 [!code-csharp[System.Drawing.RotateColors#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="55fd4-122">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="55fd4-122">Compiling the Code</span></span>  
 <span data-ttu-id="55fd4-123">L'esempio precedente è progettato per l'utilizzo con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="55fd4-123">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="55fd4-124">Sostituire `RotationInput.bmp` con un nome di file di immagine e un percorso validi nel sistema.</span><span class="sxs-lookup"><span data-stu-id="55fd4-124">Replace `RotationInput.bmp` with an image file name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55fd4-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55fd4-125">See also</span></span>

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="55fd4-126">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="55fd4-126">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="55fd4-127">Ricolorazione di immagini</span><span class="sxs-lookup"><span data-stu-id="55fd4-127">Recoloring Images</span></span>](recoloring-images.md)
