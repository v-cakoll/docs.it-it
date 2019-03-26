---
title: 'Procedura: Convertire i colori delle immagini'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], changing colors
- images [Windows Forms], changing colors
- image colors [Windows Forms]
ms.assetid: 2106fb9a-4d60-4dcf-9220-9f189a6c4d19
ms.openlocfilehash: 8b2e28cab2d2d04f7c99880f2b35a02ebe80dcd8
ms.sourcegitcommit: 7156c0b9e4ce4ce5ecf48ce3d925403b638b680c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2019
ms.locfileid: "58464463"
---
# <a name="how-to-translate-image-colors"></a><span data-ttu-id="25ea6-102">Procedura: Convertire i colori delle immagini</span><span class="sxs-lookup"><span data-stu-id="25ea6-102">How to: Translate Image Colors</span></span>
<span data-ttu-id="25ea6-103">Una traduzione aggiunge un valore a una o più di quattro componenti di colore.</span><span class="sxs-lookup"><span data-stu-id="25ea6-103">A translation adds a value to one or more of the four color components.</span></span> <span data-ttu-id="25ea6-104">Le voci di matrice di colori che rappresentano le traduzioni sono indicate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="25ea6-104">The color matrix entries that represent translations are given in the following table.</span></span>  
  
|<span data-ttu-id="25ea6-105">Componente da tradurre</span><span class="sxs-lookup"><span data-stu-id="25ea6-105">Component to be translated</span></span>|<span data-ttu-id="25ea6-106">Voce della matrice</span><span class="sxs-lookup"><span data-stu-id="25ea6-106">Matrix entry</span></span>|  
|--------------------------------|------------------|  
|<span data-ttu-id="25ea6-107">Rosso</span><span class="sxs-lookup"><span data-stu-id="25ea6-107">Red</span></span>|<span data-ttu-id="25ea6-108">[4][0]</span><span class="sxs-lookup"><span data-stu-id="25ea6-108">[4][0]</span></span>|  
|<span data-ttu-id="25ea6-109">Verde</span><span class="sxs-lookup"><span data-stu-id="25ea6-109">Green</span></span>|<span data-ttu-id="25ea6-110">[4][1]</span><span class="sxs-lookup"><span data-stu-id="25ea6-110">[4][1]</span></span>|  
|<span data-ttu-id="25ea6-111">Blu</span><span class="sxs-lookup"><span data-stu-id="25ea6-111">Blue</span></span>|<span data-ttu-id="25ea6-112">[4][2]</span><span class="sxs-lookup"><span data-stu-id="25ea6-112">[4][2]</span></span>|  
|<span data-ttu-id="25ea6-113">Alfa</span><span class="sxs-lookup"><span data-stu-id="25ea6-113">Alpha</span></span>|<span data-ttu-id="25ea6-114">[4][3]</span><span class="sxs-lookup"><span data-stu-id="25ea6-114">[4][3]</span></span>|  
  
## <a name="example"></a><span data-ttu-id="25ea6-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="25ea6-115">Example</span></span>  
 <span data-ttu-id="25ea6-116">Nell'esempio seguente si costruisce un <xref:System.Drawing.Image> oggetto ColorBars nel file.</span><span class="sxs-lookup"><span data-stu-id="25ea6-116">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars.bmp.</span></span> <span data-ttu-id="25ea6-117">Il codice aggiunge quindi 0,75 per il componente rosso di ogni pixel nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="25ea6-117">Then the code adds 0.75 to the red component of each pixel in the image.</span></span> <span data-ttu-id="25ea6-118">Accanto all'immagine trasformata viene disegnata l'immagine originale.</span><span class="sxs-lookup"><span data-stu-id="25ea6-118">The original image is drawn alongside the transformed image.</span></span>  
  
 <span data-ttu-id="25ea6-119">Nella figura seguente mostra l'immagine originale a sinistra e l'immagine trasformato a destra:</span><span class="sxs-lookup"><span data-stu-id="25ea6-119">The following illustration shows the original image on the left and the transformed image on the right:</span></span>  
  
 ![Screenshot dell'immagine originale e trasformato.](./media/how-to-translate-image-colors/original-image-translate-colors.png)  
  
 <span data-ttu-id="25ea6-121">La tabella seguente elenca i vettori di colore per le quattro barre prima e dopo la traduzione di colore rosso.</span><span class="sxs-lookup"><span data-stu-id="25ea6-121">The following table lists the color vectors for the four bars before and after the red translation.</span></span> <span data-ttu-id="25ea6-122">Si noti che, poiché il valore massimo per un componente di colore è 1, non modificare il componente rossa nella seconda riga.</span><span class="sxs-lookup"><span data-stu-id="25ea6-122">Note that because the maximum value for a color component is 1, the red component in the second row does not change.</span></span> <span data-ttu-id="25ea6-123">(In modo analogo, il valore minimo per un componente di colore è 0.)</span><span class="sxs-lookup"><span data-stu-id="25ea6-123">(Similarly, the minimum value for a color component is 0.)</span></span>  
  
|<span data-ttu-id="25ea6-124">Originale</span><span class="sxs-lookup"><span data-stu-id="25ea6-124">Original</span></span>|<span data-ttu-id="25ea6-125">Tradotta</span><span class="sxs-lookup"><span data-stu-id="25ea6-125">Translated</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="25ea6-126">Black (0, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="25ea6-126">Black (0, 0, 0, 1)</span></span>|<span data-ttu-id="25ea6-127">(0.75, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="25ea6-127">(0.75, 0, 0, 1)</span></span>|  
|<span data-ttu-id="25ea6-128">Rosso (1, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="25ea6-128">Red (1, 0, 0, 1)</span></span>|<span data-ttu-id="25ea6-129">(1, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="25ea6-129">(1, 0, 0, 1)</span></span>|  
|<span data-ttu-id="25ea6-130">Green (0, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="25ea6-130">Green (0, 1, 0, 1)</span></span>|<span data-ttu-id="25ea6-131">(0.75, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="25ea6-131">(0.75, 1, 0, 1)</span></span>|  
|<span data-ttu-id="25ea6-132">Blue (0, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="25ea6-132">Blue (0, 0, 1, 1)</span></span>|<span data-ttu-id="25ea6-133">(0.75, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="25ea6-133">(0.75, 0, 1, 1)</span></span>|  
  
 [!code-csharp[System.Drawing.RecoloringImages#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.RecoloringImages#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="25ea6-134">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="25ea6-134">Compiling the Code</span></span>  
 <span data-ttu-id="25ea6-135">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs>`e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="25ea6-135">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="25ea6-136">Sostituire `ColorBars.bmp` con un nome file di immagine e il percorso che sono validi per il sistema.</span><span class="sxs-lookup"><span data-stu-id="25ea6-136">Replace `ColorBars.bmp` with an image file name and path that are valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25ea6-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25ea6-137">See also</span></span>
- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="25ea6-138">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="25ea6-138">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="25ea6-139">Ricolorazione di immagini</span><span class="sxs-lookup"><span data-stu-id="25ea6-139">Recoloring Images</span></span>](recoloring-images.md)
