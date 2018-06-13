---
title: "Procedura: caricare un'immagine come anteprima"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- loading images as thumbnails [WPF]
- images [WPF], loading as thumbnails
- thumbnails [WPF], loading images as
ms.assetid: 02e055a0-54df-499a-b8b6-ab6ff7535cff
ms.openlocfilehash: 349a602a10b89931701e24334bf5ac5536f26400
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562323"
---
# <a name="how-to-load-an-image-as-a-thumbnail"></a><span data-ttu-id="9e11a-102">Procedura: caricare un'immagine come anteprima</span><span class="sxs-lookup"><span data-stu-id="9e11a-102">How to: Load an Image as a Thumbnail</span></span>
<span data-ttu-id="9e11a-103">Negli esempi seguenti viene illustrano come caricare un <xref:System.Windows.Controls.Image> come anteprima per risparmiare memoria dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9e11a-103">The following examples show how to load an <xref:System.Windows.Controls.Image> as a thumbnail to conserve application memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e11a-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="9e11a-104">Example</span></span>  
 <span data-ttu-id="9e11a-105">L'esempio seguente imposta il <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> proprietà di un <xref:System.Windows.Media.Imaging.BitmapImage> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] per ridurre la memoria necessaria per caricare l'immagine.</span><span class="sxs-lookup"><span data-stu-id="9e11a-105">The following example sets the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> property of a <xref:System.Windows.Media.Imaging.BitmapImage> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to reduce the memory required to load the image.</span></span>  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a><span data-ttu-id="9e11a-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="9e11a-106">Example</span></span>  
 <span data-ttu-id="9e11a-107">L'esempio seguente imposta il <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> proprietà di un <xref:System.Windows.Media.Imaging.BitmapImage> nel codice per ridurre la memoria necessaria per caricare l'immagine.</span><span class="sxs-lookup"><span data-stu-id="9e11a-107">The following example sets the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> property of a <xref:System.Windows.Media.Imaging.BitmapImage> in code to reduce the memory required to load the image.</span></span>  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a><span data-ttu-id="9e11a-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e11a-108">See Also</span></span>  
 [<span data-ttu-id="9e11a-109">Cenni preliminari sulla creazione dell'immagine</span><span class="sxs-lookup"><span data-stu-id="9e11a-109">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
