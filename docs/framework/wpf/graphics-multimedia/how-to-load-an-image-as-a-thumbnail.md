---
title: "Procedura: Caricare un'immagine come anteprima"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- loading images as thumbnails [WPF]
- images [WPF], loading as thumbnails
- thumbnails [WPF], loading images as
ms.assetid: 02e055a0-54df-499a-b8b6-ab6ff7535cff
ms.openlocfilehash: d92a489f19f8c7160bed5ec83535bdc33cfe561b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54735987"
---
# <a name="how-to-load-an-image-as-a-thumbnail"></a><span data-ttu-id="1c98f-102">Procedura: Caricare un'immagine come anteprima</span><span class="sxs-lookup"><span data-stu-id="1c98f-102">How to: Load an Image as a Thumbnail</span></span>
<span data-ttu-id="1c98f-103">Gli esempi seguenti illustrano come caricare un <xref:System.Windows.Controls.Image> come anteprima per risparmiare memoria dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1c98f-103">The following examples show how to load an <xref:System.Windows.Controls.Image> as a thumbnail to conserve application memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c98f-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="1c98f-104">Example</span></span>  
 <span data-ttu-id="1c98f-105">L'esempio seguente imposta la <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> proprietà di un <xref:System.Windows.Media.Imaging.BitmapImage> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] per ridurre la memoria necessaria per caricare l'immagine.</span><span class="sxs-lookup"><span data-stu-id="1c98f-105">The following example sets the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> property of a <xref:System.Windows.Media.Imaging.BitmapImage> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to reduce the memory required to load the image.</span></span>  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a><span data-ttu-id="1c98f-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="1c98f-106">Example</span></span>  
 <span data-ttu-id="1c98f-107">L'esempio seguente imposta la <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> proprietà di un <xref:System.Windows.Media.Imaging.BitmapImage> nel codice per ridurre la memoria necessaria per caricare l'immagine.</span><span class="sxs-lookup"><span data-stu-id="1c98f-107">The following example sets the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> property of a <xref:System.Windows.Media.Imaging.BitmapImage> in code to reduce the memory required to load the image.</span></span>  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a><span data-ttu-id="1c98f-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c98f-108">See also</span></span>
- [<span data-ttu-id="1c98f-109">Cenni preliminari sulla creazione dell'immagine</span><span class="sxs-lookup"><span data-stu-id="1c98f-109">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
