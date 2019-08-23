---
title: 'Procedura: Utilizzare un MatrixTransform per creare trasformazioni personalizzate'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], custom Transforms
ms.assetid: 919381ca-989f-47cf-86b4-1094060236e4
ms.openlocfilehash: 1971d5fe9422c5138f140517e6fd4c9f9b2cf48b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913922"
---
# <a name="how-to-use-a-matrixtransform-to-create-custom-transforms"></a><span data-ttu-id="12195-102">Procedura: Utilizzare un MatrixTransform per creare trasformazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="12195-102">How to: Use a MatrixTransform to Create Custom Transforms</span></span>
<span data-ttu-id="12195-103">Questo esempio illustra come usare un oggetto <xref:System.Windows.Media.MatrixTransform> per tradurre (spostare) la posizione, l'estensione e l'inclinazione <xref:System.Windows.Controls.Button>di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="12195-103">This example shows how to use a <xref:System.Windows.Media.MatrixTransform> to translate (move) the position, stretch, and skew of a <xref:System.Windows.Controls.Button>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="12195-104">Utilizzare la <xref:System.Windows.Media.MatrixTransform> classe per creare trasformazioni personalizzate che non sono fornite <xref:System.Windows.Media.RotateTransform>dalle classi, <xref:System.Windows.Media.SkewTransform>, <xref:System.Windows.Media.ScaleTransform>o <xref:System.Windows.Media.TranslateTransform> .</span><span class="sxs-lookup"><span data-stu-id="12195-104">Use the <xref:System.Windows.Media.MatrixTransform> class to create custom transformations that are not provided by the <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.SkewTransform>, <xref:System.Windows.Media.ScaleTransform>, or <xref:System.Windows.Media.TranslateTransform> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="12195-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="12195-105">Example</span></span>  
 [!code-xaml[Transforms_snip#MatrixTransform](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MatrixTransformExample.xaml#matrixtransform)]  
  
## <a name="see-also"></a><span data-ttu-id="12195-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12195-106">See also</span></span>

- <xref:System.Windows.Media.MatrixTransform>
- <xref:System.Windows.Media.Transform>
- [<span data-ttu-id="12195-107">Cenni preliminari sulle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="12195-107">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="12195-108">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="12195-108">How-to Topics</span></span>](transformations-how-to-topics.md)
- [<span data-ttu-id="12195-109">Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF</span><span class="sxs-lookup"><span data-stu-id="12195-109">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
