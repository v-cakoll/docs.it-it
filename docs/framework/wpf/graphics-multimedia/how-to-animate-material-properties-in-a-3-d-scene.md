---
title: 'Procedura: animare proprietà materiali in una scena tridimensionale'
ms.date: 03/30/2017
helpviewer_keywords:
- Material properties [WPF], animating in 3-D scenes
- animation [WPF], Material properties in 3-D scenes
- 3-D scenes [WPF], animating Material properties
ms.assetid: 229fd6eb-7401-4992-b0c9-8b28de230c0f
ms.openlocfilehash: ed4bbb3b22b09c24ed40b72a483db38b35038759
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559053"
---
# <a name="how-to-animate-material-properties-in-a-3-d-scene"></a><span data-ttu-id="08e26-102">Procedura: animare proprietà materiali in una scena tridimensionale</span><span class="sxs-lookup"><span data-stu-id="08e26-102">How to: Animate Material Properties in a 3-D Scene</span></span>
<span data-ttu-id="08e26-103">In questo esempio viene illustrato come animare la <xref:System.Windows.Media.Brush.Opacity%2A> proprietà del <xref:System.Windows.Media.Media3D.Material> applicato a un [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] modello.</span><span class="sxs-lookup"><span data-stu-id="08e26-103">This example shows how to animate the <xref:System.Windows.Media.Brush.Opacity%2A> property of the <xref:System.Windows.Media.Media3D.Material> applied to a [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] model.</span></span>  
  
 <span data-ttu-id="08e26-104">L'esempio di codice seguente definisce il <xref:System.Windows.Media.LinearGradientBrush> utilizzato come il <xref:System.Windows.Media.Media3D.Material> applicato all'oggetto 3D.</span><span class="sxs-lookup"><span data-stu-id="08e26-104">The following code example defines the <xref:System.Windows.Media.LinearGradientBrush> used as the <xref:System.Windows.Media.Media3D.Material> applied to the 3D object.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline1)]  
  
 <span data-ttu-id="08e26-105">Il <xref:System.Windows.Media.Brush.Opacity%2A> proprietà di questo <xref:System.Windows.Media.LinearGradientBrush> utilizzando l'esempio di codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="08e26-105">The <xref:System.Windows.Media.Brush.Opacity%2A> property of this <xref:System.Windows.Media.LinearGradientBrush> is animated using the code example below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline2)]  
  
## <a name="example"></a><span data-ttu-id="08e26-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="08e26-106">Example</span></span>  
 <span data-ttu-id="08e26-107">Il codice seguente viene illustrato l'esempio completo.</span><span class="sxs-lookup"><span data-stu-id="08e26-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="08e26-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08e26-108">See Also</span></span>  
 [<span data-ttu-id="08e26-109">Creare una scena tridimensionale</span><span class="sxs-lookup"><span data-stu-id="08e26-109">Create a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)  
 [<span data-ttu-id="08e26-110">Panoramica sulla grafica tridimensionale</span><span class="sxs-lookup"><span data-stu-id="08e26-110">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
