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
ms.openlocfilehash: 7a3ed1f3f6b3e89c8df160b7e753839e20acd877
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549759"
---
# <a name="how-to-translate-image-colors"></a><span data-ttu-id="4a425-102">Procedura: Convertire i colori delle immagini</span><span class="sxs-lookup"><span data-stu-id="4a425-102">How to: Translate Image Colors</span></span>
<span data-ttu-id="4a425-103">Una traduzione aggiunge un valore a una o più di quattro componenti di colore.</span><span class="sxs-lookup"><span data-stu-id="4a425-103">A translation adds a value to one or more of the four color components.</span></span> <span data-ttu-id="4a425-104">Le voci di matrice di colori che rappresentano le traduzioni sono indicate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="4a425-104">The color matrix entries that represent translations are given in the following table.</span></span>  
  
|<span data-ttu-id="4a425-105">Componente da tradurre</span><span class="sxs-lookup"><span data-stu-id="4a425-105">Component to be translated</span></span>|<span data-ttu-id="4a425-106">Voce della matrice</span><span class="sxs-lookup"><span data-stu-id="4a425-106">Matrix entry</span></span>|  
|--------------------------------|------------------|  
|<span data-ttu-id="4a425-107">Rosso</span><span class="sxs-lookup"><span data-stu-id="4a425-107">Red</span></span>|<span data-ttu-id="4a425-108">[4][0]</span><span class="sxs-lookup"><span data-stu-id="4a425-108">[4][0]</span></span>|  
|<span data-ttu-id="4a425-109">Verde</span><span class="sxs-lookup"><span data-stu-id="4a425-109">Green</span></span>|<span data-ttu-id="4a425-110">[4][1]</span><span class="sxs-lookup"><span data-stu-id="4a425-110">[4][1]</span></span>|  
|<span data-ttu-id="4a425-111">Blu</span><span class="sxs-lookup"><span data-stu-id="4a425-111">Blue</span></span>|<span data-ttu-id="4a425-112">[4][2]</span><span class="sxs-lookup"><span data-stu-id="4a425-112">[4][2]</span></span>|  
|<span data-ttu-id="4a425-113">Alfa</span><span class="sxs-lookup"><span data-stu-id="4a425-113">Alpha</span></span>|<span data-ttu-id="4a425-114">[4][3]</span><span class="sxs-lookup"><span data-stu-id="4a425-114">[4][3]</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4a425-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="4a425-115">Example</span></span>  
 <span data-ttu-id="4a425-116">Nell'esempio seguente si costruisce un <xref:System.Drawing.Image> oggetto ColorBars nel file.</span><span class="sxs-lookup"><span data-stu-id="4a425-116">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars.bmp.</span></span> <span data-ttu-id="4a425-117">Il codice aggiunge quindi 0,75 per il componente rosso di ogni pixel nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="4a425-117">Then the code adds 0.75 to the red component of each pixel in the image.</span></span> <span data-ttu-id="4a425-118">Accanto all'immagine trasformata viene disegnata l'immagine originale.</span><span class="sxs-lookup"><span data-stu-id="4a425-118">The original image is drawn alongside the transformed image.</span></span>  
  
 <span data-ttu-id="4a425-119">Nella figura seguente mostra l'immagine originale a sinistra e l'immagine trasformato a destra.</span><span class="sxs-lookup"><span data-stu-id="4a425-119">The following illustration shows the original image on the left and the transformed image on the right.</span></span>  
  
 <span data-ttu-id="4a425-120">![Convertire i colori](../../../../docs/framework/winforms/advanced/media/colortrans2.png "colortrans2")</span><span class="sxs-lookup"><span data-stu-id="4a425-120">![Translate Colors](../../../../docs/framework/winforms/advanced/media/colortrans2.png "colortrans2")</span></span>  
  
 <span data-ttu-id="4a425-121">La tabella seguente elenca i vettori di colore per le quattro barre prima e dopo la traduzione di colore rosso.</span><span class="sxs-lookup"><span data-stu-id="4a425-121">The following table lists the color vectors for the four bars before and after the red translation.</span></span> <span data-ttu-id="4a425-122">Si noti che, poiché il valore massimo per un componente di colore è 1, non modificare il componente rossa nella seconda riga.</span><span class="sxs-lookup"><span data-stu-id="4a425-122">Note that because the maximum value for a color component is 1, the red component in the second row does not change.</span></span> <span data-ttu-id="4a425-123">(In modo analogo, il valore minimo per un componente di colore è 0.)</span><span class="sxs-lookup"><span data-stu-id="4a425-123">(Similarly, the minimum value for a color component is 0.)</span></span>  
  
|<span data-ttu-id="4a425-124">Originale</span><span class="sxs-lookup"><span data-stu-id="4a425-124">Original</span></span>|<span data-ttu-id="4a425-125">Tradotta</span><span class="sxs-lookup"><span data-stu-id="4a425-125">Translated</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="4a425-126">Black (0, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="4a425-126">Black (0, 0, 0, 1)</span></span>|<span data-ttu-id="4a425-127">(0.75, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="4a425-127">(0.75, 0, 0, 1)</span></span>|  
|<span data-ttu-id="4a425-128">Rosso (1, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="4a425-128">Red (1, 0, 0, 1)</span></span>|<span data-ttu-id="4a425-129">(1, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="4a425-129">(1, 0, 0, 1)</span></span>|  
|<span data-ttu-id="4a425-130">Green (0, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="4a425-130">Green (0, 1, 0, 1)</span></span>|<span data-ttu-id="4a425-131">(0.75, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="4a425-131">(0.75, 1, 0, 1)</span></span>|  
|<span data-ttu-id="4a425-132">Blue (0, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="4a425-132">Blue (0, 0, 1, 1)</span></span>|<span data-ttu-id="4a425-133">(0.75, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="4a425-133">(0.75, 0, 1, 1)</span></span>|  
  
 [!code-csharp[System.Drawing.RecoloringImages#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.RecoloringImages#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4a425-134">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="4a425-134">Compiling the Code</span></span>  
 <span data-ttu-id="4a425-135">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="4a425-135">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="4a425-136">Sostituire `ColorBars.bmp` con un nome file di immagine e il percorso che sono validi per il sistema.</span><span class="sxs-lookup"><span data-stu-id="4a425-136">Replace `ColorBars.bmp` with an image file name and path that are valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a425-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a425-137">See also</span></span>
- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="4a425-138">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="4a425-138">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="4a425-139">Ricolorazione di immagini</span><span class="sxs-lookup"><span data-stu-id="4a425-139">Recoloring Images</span></span>](../../../../docs/framework/winforms/advanced/recoloring-images.md)
