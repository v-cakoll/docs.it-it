---
title: 'Procedura: ritagliare un''immagine'
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
- images [WPF], cropping
- cropping images [WPF]
ms.assetid: c6bba109-c6e7-4cf8-bfe6-9cf8d01bb4fc
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 11f5b280635d2fe7b83d8c4496606ed02bc44149
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-crop-an-image"></a><span data-ttu-id="8e9d1-102">Procedura: ritagliare un'immagine</span><span class="sxs-lookup"><span data-stu-id="8e9d1-102">How to: Crop an Image</span></span>
<span data-ttu-id="8e9d1-103">In questo esempio viene illustrato come ritagliare un'immagine utilizzando <xref:System.Windows.Media.Imaging.CroppedBitmap>.</span><span class="sxs-lookup"><span data-stu-id="8e9d1-103">This example shows how to crop an image using <xref:System.Windows.Media.Imaging.CroppedBitmap>.</span></span>  
  
 <span data-ttu-id="8e9d1-104"><xref:System.Windows.Media.Imaging.CroppedBitmap>viene utilizzato principalmente per la codifica di una versione di un'immagine ritagliata per salvare in un file.</span><span class="sxs-lookup"><span data-stu-id="8e9d1-104"><xref:System.Windows.Media.Imaging.CroppedBitmap> is primarily used when encoding a cropped version of an image to save out to a file.</span></span> <span data-ttu-id="8e9d1-105">Per ritagliare un'immagine per la visualizzazione, vedere il [creare un'area di ritaglio](http://msdn.microsoft.com/library/56e4bed6-78d7-4292-b917-d72d0b3e4376) argomento.</span><span class="sxs-lookup"><span data-stu-id="8e9d1-105">To crop an image for display purposes see the [Create a Clip Region](http://msdn.microsoft.com/library/56e4bed6-78d7-4292-b917-d72d0b3e4376) topic.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e9d1-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="8e9d1-106">Example</span></span>  
 <span data-ttu-id="8e9d1-107">Le operazioni seguenti [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] definisce le risorse utilizzate all'interno di esempi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="8e9d1-107">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] defines resources used within the samples below.</span></span>  
  
 [!code-xaml[imageelementexample#CroppedXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml1)]  
  
 <span data-ttu-id="8e9d1-108">L'esempio seguente crea un'immagine utilizzando un <xref:System.Windows.Media.Imaging.CroppedBitmap> come origine.</span><span class="sxs-lookup"><span data-stu-id="8e9d1-108">The following example creates an image using a <xref:System.Windows.Media.Imaging.CroppedBitmap> as its source.</span></span>  
  
 [!code-xaml[imageelementexample#CroppedXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml2)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp1)]
 [!code-vb[imageelementexample#CroppedCSharp1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp1)]  
  
 <span data-ttu-id="8e9d1-109">Il <xref:System.Windows.Media.Imaging.CroppedBitmap> può anche essere utilizzato come origine di un altro <xref:System.Windows.Media.Imaging.CroppedBitmap>, concatenando il ritaglio.</span><span class="sxs-lookup"><span data-stu-id="8e9d1-109">The <xref:System.Windows.Media.Imaging.CroppedBitmap> can also be used as the source of another <xref:System.Windows.Media.Imaging.CroppedBitmap>, chaining the cropping.</span></span> <span data-ttu-id="8e9d1-110">Si noti che il <xref:System.Windows.Media.Imaging.CroppedBitmap.SourceRect%2A> utilizza i valori relativi a ritagliata bitmap e non all'immagine iniziale di origine.</span><span class="sxs-lookup"><span data-stu-id="8e9d1-110">Note that the <xref:System.Windows.Media.Imaging.CroppedBitmap.SourceRect%2A> uses values that are relative to the source cropped bitmap and not the initial image.</span></span>  
  
 [!code-xaml[imageelementexample#CroppedXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml3)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp2)]
 [!code-vb[imageelementexample#CroppedCSharp2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp2)]  
  
## <a name="see-also"></a><span data-ttu-id="8e9d1-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e9d1-111">See Also</span></span>  
 [<span data-ttu-id="8e9d1-112">Creare un'area di ritaglio</span><span class="sxs-lookup"><span data-stu-id="8e9d1-112">Create a Clip Region</span></span>](http://msdn.microsoft.com/library/56e4bed6-78d7-4292-b917-d72d0b3e4376)
