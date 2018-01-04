---
title: 'Procedura: convertire i colori delle immagini'
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
- bitmaps [Windows Forms], changing colors
- images [Windows Forms], changing colors
- image colors [Windows Forms]
ms.assetid: 2106fb9a-4d60-4dcf-9220-9f189a6c4d19
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2a2147b9bc86aa7ec03e8455bb0dc51c89a8b282
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-translate-image-colors"></a><span data-ttu-id="cdc35-102">Procedura: convertire i colori delle immagini</span><span class="sxs-lookup"><span data-stu-id="cdc35-102">How to: Translate Image Colors</span></span>
<span data-ttu-id="cdc35-103">Una traduzione aggiunge un valore a una o più di quattro componenti di colore.</span><span class="sxs-lookup"><span data-stu-id="cdc35-103">A translation adds a value to one or more of the four color components.</span></span> <span data-ttu-id="cdc35-104">Le voci della matrice di colori che rappresentano le traduzioni sono indicate nella tabella riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="cdc35-104">The color matrix entries that represent translations are given in the following table.</span></span>  
  
|<span data-ttu-id="cdc35-105">Componente da convertire</span><span class="sxs-lookup"><span data-stu-id="cdc35-105">Component to be translated</span></span>|<span data-ttu-id="cdc35-106">Voce della matrice</span><span class="sxs-lookup"><span data-stu-id="cdc35-106">Matrix entry</span></span>|  
|--------------------------------|------------------|  
|<span data-ttu-id="cdc35-107">Rosso</span><span class="sxs-lookup"><span data-stu-id="cdc35-107">Red</span></span>|<span data-ttu-id="cdc35-108">[4][0]</span><span class="sxs-lookup"><span data-stu-id="cdc35-108">[4][0]</span></span>|  
|<span data-ttu-id="cdc35-109">Verde</span><span class="sxs-lookup"><span data-stu-id="cdc35-109">Green</span></span>|<span data-ttu-id="cdc35-110">[4][1]</span><span class="sxs-lookup"><span data-stu-id="cdc35-110">[4][1]</span></span>|  
|<span data-ttu-id="cdc35-111">Blu</span><span class="sxs-lookup"><span data-stu-id="cdc35-111">Blue</span></span>|<span data-ttu-id="cdc35-112">[4][2]</span><span class="sxs-lookup"><span data-stu-id="cdc35-112">[4][2]</span></span>|  
|<span data-ttu-id="cdc35-113">Alfa</span><span class="sxs-lookup"><span data-stu-id="cdc35-113">Alpha</span></span>|<span data-ttu-id="cdc35-114">[4][3]</span><span class="sxs-lookup"><span data-stu-id="cdc35-114">[4][3]</span></span>|  
  
## <a name="example"></a><span data-ttu-id="cdc35-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="cdc35-115">Example</span></span>  
 <span data-ttu-id="cdc35-116">Nell'esempio seguente viene costruito un <xref:System.Drawing.Image> oggetto dal file ColorBars.</span><span class="sxs-lookup"><span data-stu-id="cdc35-116">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars.bmp.</span></span> <span data-ttu-id="cdc35-117">Il codice aggiunge quindi 0,75 per il componente rosso di ogni pixel dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="cdc35-117">Then the code adds 0.75 to the red component of each pixel in the image.</span></span> <span data-ttu-id="cdc35-118">L'immagine originale viene disegnato accanto all'immagine trasformata.</span><span class="sxs-lookup"><span data-stu-id="cdc35-118">The original image is drawn alongside the transformed image.</span></span>  
  
 <span data-ttu-id="cdc35-119">Nella figura seguente mostra l'immagine originale a sinistra e l'immagine trasformato a destra.</span><span class="sxs-lookup"><span data-stu-id="cdc35-119">The following illustration shows the original image on the left and the transformed image on the right.</span></span>  
  
 <span data-ttu-id="cdc35-120">![Conversione dei colori](../../../../docs/framework/winforms/advanced/media/colortrans2.png "colortrans2")</span><span class="sxs-lookup"><span data-stu-id="cdc35-120">![Translate Colors](../../../../docs/framework/winforms/advanced/media/colortrans2.png "colortrans2")</span></span>  
  
 <span data-ttu-id="cdc35-121">Nella tabella seguente sono elencati i vettori di colore per le quattro barre prima e dopo la conversione di colore rossa.</span><span class="sxs-lookup"><span data-stu-id="cdc35-121">The following table lists the color vectors for the four bars before and after the red translation.</span></span> <span data-ttu-id="cdc35-122">Si noti che, poiché il valore massimo per un componente di colore è 1, non modificare il componente rosso nella seconda riga.</span><span class="sxs-lookup"><span data-stu-id="cdc35-122">Note that because the maximum value for a color component is 1, the red component in the second row does not change.</span></span> <span data-ttu-id="cdc35-123">(In modo analogo, il valore minimo per un componente di colore è 0.)</span><span class="sxs-lookup"><span data-stu-id="cdc35-123">(Similarly, the minimum value for a color component is 0.)</span></span>  
  
|<span data-ttu-id="cdc35-124">Originale</span><span class="sxs-lookup"><span data-stu-id="cdc35-124">Original</span></span>|<span data-ttu-id="cdc35-125">Tradotta</span><span class="sxs-lookup"><span data-stu-id="cdc35-125">Translated</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="cdc35-126">Nero (0, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="cdc35-126">Black (0, 0, 0, 1)</span></span>|<span data-ttu-id="cdc35-127">(0.75, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="cdc35-127">(0.75, 0, 0, 1)</span></span>|  
|<span data-ttu-id="cdc35-128">Rosso (1, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="cdc35-128">Red (1, 0, 0, 1)</span></span>|<span data-ttu-id="cdc35-129">(1, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="cdc35-129">(1, 0, 0, 1)</span></span>|  
|<span data-ttu-id="cdc35-130">Verde (0, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="cdc35-130">Green (0, 1, 0, 1)</span></span>|<span data-ttu-id="cdc35-131">(0.75, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="cdc35-131">(0.75, 1, 0, 1)</span></span>|  
|<span data-ttu-id="cdc35-132">Blu (0, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="cdc35-132">Blue (0, 0, 1, 1)</span></span>|<span data-ttu-id="cdc35-133">(0.75, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="cdc35-133">(0.75, 0, 1, 1)</span></span>|  
  
 [!code-csharp[System.Drawing.RecoloringImages#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.RecoloringImages#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cdc35-134">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="cdc35-134">Compiling the Code</span></span>  
 <span data-ttu-id="cdc35-135">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="cdc35-135">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="cdc35-136">Sostituire `ColorBars.bmp` con un nome di file di immagine e un percorso valido per il sistema.</span><span class="sxs-lookup"><span data-stu-id="cdc35-136">Replace `ColorBars.bmp` with an image file name and path that are valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdc35-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cdc35-137">See Also</span></span>  
 <xref:System.Drawing.Imaging.ColorMatrix>  
 <xref:System.Drawing.Imaging.ImageAttributes>  
 [<span data-ttu-id="cdc35-138">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="cdc35-138">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="cdc35-139">Ricolorazione di immagini</span><span class="sxs-lookup"><span data-stu-id="cdc35-139">Recoloring Images</span></span>](../../../../docs/framework/winforms/advanced/recoloring-images.md)
