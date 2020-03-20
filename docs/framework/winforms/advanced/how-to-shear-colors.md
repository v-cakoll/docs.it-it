---
title: 'Procedura: variare le componenti cromatiche'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], transforming with color matrices
- colors [Windows Forms], shearing
ms.assetid: 0a424171-5b8b-45c4-afef-e9720a6c3e22
ms.openlocfilehash: 825e5a90ebb0d9df3b894ce7bd353e917b676939
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142394"
---
# <a name="how-to-shear-colors"></a><span data-ttu-id="7c81e-102">Procedura: variare le componenti cromatiche</span><span class="sxs-lookup"><span data-stu-id="7c81e-102">How to: Shear Colors</span></span>
<span data-ttu-id="7c81e-103">La tosatura aumenta o diminuisce una componente di colore di una quantità proporzionale a un'altra componente di colore.</span><span class="sxs-lookup"><span data-stu-id="7c81e-103">Shearing increases or decreases a color component by an amount proportional to another color component.</span></span> <span data-ttu-id="7c81e-104">Si consideri, ad esempio, la trasformazione in cui il componente rosso viene aumentato della metà del valore del componente blu.</span><span class="sxs-lookup"><span data-stu-id="7c81e-104">For example, consider the transformation where the red component is increased by one half the value of the blue component.</span></span> <span data-ttu-id="7c81e-105">In tale trasformazione, il colore (0.2, 0.5, 1) diventerebbe (0.7, 0.5, 1).</span><span class="sxs-lookup"><span data-stu-id="7c81e-105">Under such a transformation, the color (0.2, 0.5, 1) would become (0.7, 0.5, 1).</span></span> <span data-ttu-id="7c81e-106">Il nuovo componente rosso è 0,2 ( (1/2)(1) - 0,7.</span><span class="sxs-lookup"><span data-stu-id="7c81e-106">The new red component is 0.2 + (1/2)(1) = 0.7.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c81e-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="7c81e-107">Example</span></span>  
 <span data-ttu-id="7c81e-108">Nell'esempio seguente <xref:System.Drawing.Image> viene creato un oggetto dal file ColorBars4.bmp.</span><span class="sxs-lookup"><span data-stu-id="7c81e-108">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars4.bmp.</span></span> <span data-ttu-id="7c81e-109">Il codice applica quindi la trasformazione di taglio descritta nel paragrafo precedente a ogni pixel dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="7c81e-109">Then the code applies the shearing transformation described in the preceding paragraph to each pixel in the image.</span></span>  
  
 <span data-ttu-id="7c81e-110">La figura seguente mostra l'immagine originale a sinistra e l'immagine tosata a destra:</span><span class="sxs-lookup"><span data-stu-id="7c81e-110">The following illustration shows the original image on the left and the sheared image on the right:</span></span>
  
 ![Due quadrati con strisce colorate affiancate che illustrano l'immagine originale e l'immagine tranciata.](./media/how-to-shear-colors/original-image-sheared-image.png)  
  
 <span data-ttu-id="7c81e-112">Nella tabella seguente sono elencati i vettori di colore per le quattro barre prima e dopo la trasformazione di taglio.</span><span class="sxs-lookup"><span data-stu-id="7c81e-112">The following table lists the color vectors for the four bars before and after the shearing transformation.</span></span>  
  
|<span data-ttu-id="7c81e-113">Originale</span><span class="sxs-lookup"><span data-stu-id="7c81e-113">Original</span></span>|<span data-ttu-id="7c81e-114">Tosato</span><span class="sxs-lookup"><span data-stu-id="7c81e-114">Sheared</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="7c81e-115">(0, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="7c81e-115">(0, 0, 1, 1)</span></span>|<span data-ttu-id="7c81e-116">(0.5, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="7c81e-116">(0.5, 0, 1, 1)</span></span>|  
|<span data-ttu-id="7c81e-117">(0.5, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="7c81e-117">(0.5, 1, 0.5, 1)</span></span>|<span data-ttu-id="7c81e-118">(0.75, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="7c81e-118">(0.75, 1, 0.5, 1)</span></span>|  
|<span data-ttu-id="7c81e-119">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="7c81e-119">(1, 1, 0, 1)</span></span>|<span data-ttu-id="7c81e-120">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="7c81e-120">(1, 1, 0, 1)</span></span>|  
|<span data-ttu-id="7c81e-121">(0.4, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="7c81e-121">(0.4, 0.4, 0.4, 1)</span></span>|<span data-ttu-id="7c81e-122">(0.6, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="7c81e-122">(0.6, 0.4, 0.4, 1)</span></span>|  
  
 [!code-csharp[System.Drawing.Misc3#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7c81e-123">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="7c81e-123">Compiling the Code</span></span>  
 <span data-ttu-id="7c81e-124">L'esempio precedente è progettato per l'utilizzo con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="7c81e-124">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="7c81e-125">Sostituire `ColorBars.bmp` con un nome di immagine e un percorso validi nel sistema.</span><span class="sxs-lookup"><span data-stu-id="7c81e-125">Replace `ColorBars.bmp` with an image name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c81e-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c81e-126">See also</span></span>

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="7c81e-127">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="7c81e-127">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="7c81e-128">Ricolorazione di immagini</span><span class="sxs-lookup"><span data-stu-id="7c81e-128">Recoloring Images</span></span>](recoloring-images.md)
