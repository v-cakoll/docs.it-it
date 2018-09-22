---
title: "Procedura: ritagliare un'immagine"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [WPF], cropping
- cropping images [WPF]
ms.assetid: c6bba109-c6e7-4cf8-bfe6-9cf8d01bb4fc
ms.openlocfilehash: 189cb92d581ccc9209ebdb4de18487951d17818a
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2018
ms.locfileid: "46581129"
---
# <a name="how-to-crop-an-image"></a><span data-ttu-id="d5ed9-102">Procedura: ritagliare un'immagine</span><span class="sxs-lookup"><span data-stu-id="d5ed9-102">How to: Crop an Image</span></span>
<span data-ttu-id="d5ed9-103">Questo esempio illustra come ritagliare un'immagine utilizzando <xref:System.Windows.Media.Imaging.CroppedBitmap>.</span><span class="sxs-lookup"><span data-stu-id="d5ed9-103">This example shows how to crop an image using <xref:System.Windows.Media.Imaging.CroppedBitmap>.</span></span>  
  
 <span data-ttu-id="d5ed9-104"><xref:System.Windows.Media.Imaging.CroppedBitmap> viene utilizzato principalmente durante la codifica di una versione di un'immagine ritagliata per salvare in un file.</span><span class="sxs-lookup"><span data-stu-id="d5ed9-104"><xref:System.Windows.Media.Imaging.CroppedBitmap> is primarily used when encoding a cropped version of an image to save out to a file.</span></span> <span data-ttu-id="d5ed9-105">Per ritagliare un'immagine per la visualizzazione, vedere la [creare un'area di ritaglio](https://msdn.microsoft.com/library/56e4bed6-78d7-4292-b917-d72d0b3e4376) argomento.</span><span class="sxs-lookup"><span data-stu-id="d5ed9-105">To crop an image for display purposes see the [Create a Clip Region](https://msdn.microsoft.com/library/56e4bed6-78d7-4292-b917-d72d0b3e4376) topic.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5ed9-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="d5ed9-106">Example</span></span>  
 <span data-ttu-id="d5ed9-107">Nell'esempio [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] definisce le risorse usate all'interno di esempi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="d5ed9-107">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] defines resources used within the samples below.</span></span>  
  
 [!code-xaml[imageelementexample#CroppedXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml1)]  
  
 <span data-ttu-id="d5ed9-108">L'esempio seguente crea un'immagine utilizzando un <xref:System.Windows.Media.Imaging.CroppedBitmap> come origine.</span><span class="sxs-lookup"><span data-stu-id="d5ed9-108">The following example creates an image using a <xref:System.Windows.Media.Imaging.CroppedBitmap> as its source.</span></span>  
  
 [!code-xaml[imageelementexample#CroppedXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml2)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp1)]
 [!code-vb[imageelementexample#CroppedCSharp1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp1)]  
  
 <span data-ttu-id="d5ed9-109">Il <xref:System.Windows.Media.Imaging.CroppedBitmap> può anche essere utilizzato come origine di un altro <xref:System.Windows.Media.Imaging.CroppedBitmap>, concatenando il ritaglio.</span><span class="sxs-lookup"><span data-stu-id="d5ed9-109">The <xref:System.Windows.Media.Imaging.CroppedBitmap> can also be used as the source of another <xref:System.Windows.Media.Imaging.CroppedBitmap>, chaining the cropping.</span></span> <span data-ttu-id="d5ed9-110">Si noti che il <xref:System.Windows.Media.Imaging.CroppedBitmap.SourceRect%2A> Usa i valori relativi a ritagliata bitmap e non all'immagine iniziale di origine.</span><span class="sxs-lookup"><span data-stu-id="d5ed9-110">Note that the <xref:System.Windows.Media.Imaging.CroppedBitmap.SourceRect%2A> uses values that are relative to the source cropped bitmap and not the initial image.</span></span>  
  
 [!code-xaml[imageelementexample#CroppedXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml3)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp2)]
 [!code-vb[imageelementexample#CroppedCSharp2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp2)]  
  
## <a name="see-also"></a><span data-ttu-id="d5ed9-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5ed9-111">See Also</span></span>  
 [<span data-ttu-id="d5ed9-112">Creare un'area di ritaglio</span><span class="sxs-lookup"><span data-stu-id="d5ed9-112">Create a Clip Region</span></span>](https://msdn.microsoft.com/library/56e4bed6-78d7-4292-b917-d72d0b3e4376)
