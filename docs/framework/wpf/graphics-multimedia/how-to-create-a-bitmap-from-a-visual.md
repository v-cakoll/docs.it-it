---
title: 'Procedura: creare un oggetto Bitmap da un oggetto Visual'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [WPF], rendering from visuals
- visuals [WPF], rendering to bitmaps
ms.assetid: 103fc7f5-7306-4026-9d61-2005e79959f3
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7aabb01d35e02323785b6bae0764a8d8bc636e16
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-bitmap-from-a-visual"></a><span data-ttu-id="ef029-102">Procedura: creare un oggetto Bitmap da un oggetto Visual</span><span class="sxs-lookup"><span data-stu-id="ef029-102">How to: Create a Bitmap from a Visual</span></span>
<span data-ttu-id="ef029-103">Questo esempio viene illustrato come creare una bitmap da un <xref:System.Windows.Media.Visual>.</span><span class="sxs-lookup"><span data-stu-id="ef029-103">This example shows how you can create a bitmap from a <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="ef029-104">Oggetto <xref:System.Windows.Media.DrawingVisual> viene eseguito il rendering con <xref:System.Windows.Media.FormattedText>.</span><span class="sxs-lookup"><span data-stu-id="ef029-104">A <xref:System.Windows.Media.DrawingVisual> is rendered with <xref:System.Windows.Media.FormattedText>.</span></span> <span data-ttu-id="ef029-105">Il <xref:System.Windows.Media.Visual> viene quindi eseguito il rendering di <xref:System.Windows.Media.Imaging.RenderTargetBitmap> la creazione di una bitmap del testo specificato.</span><span class="sxs-lookup"><span data-stu-id="ef029-105">The <xref:System.Windows.Media.Visual> is then rendered to the <xref:System.Windows.Media.Imaging.RenderTargetBitmap> creating a bitmap of the given text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef029-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="ef029-106">Example</span></span>  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#CreateRTBImage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample.cs#creatertbimage)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#CreateRTBImage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample.vb#creatertbimage)]  
  
## <a name="see-also"></a><span data-ttu-id="ef029-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef029-107">See Also</span></span>  
 <xref:System.Windows.Media.DrawingContext>  
 [<span data-ttu-id="ef029-108">Cenni preliminari sulla creazione dell'immagine</span><span class="sxs-lookup"><span data-stu-id="ef029-108">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)  
 [<span data-ttu-id="ef029-109">Cenni preliminari sugli oggetti Drawing</span><span class="sxs-lookup"><span data-stu-id="ef029-109">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [<span data-ttu-id="ef029-110">Uso degli oggetti DrawingVisual</span><span class="sxs-lookup"><span data-stu-id="ef029-110">Using DrawingVisual Objects</span></span>](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)
