---
title: 'Procedura: Ridimensionare un modello tridimensionale'
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], 3-D objects
- 3-D objects [WPF], scaling
ms.assetid: f3fdfe33-f7dc-44b0-84a5-e43b89947f35
ms.openlocfilehash: 13f718451cb1b753a41304efde7db55360d3f687
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54672892"
---
# <a name="how-to-transform-the-scale-of-a-3-d-model"></a><span data-ttu-id="7167b-102">Procedura: Ridimensionare un modello tridimensionale</span><span class="sxs-lookup"><span data-stu-id="7167b-102">How to: Transform the Scale of a 3-D Model</span></span>
<span data-ttu-id="7167b-103">Questo esempio illustra come ridimensionare un oggetto 3D.</span><span class="sxs-lookup"><span data-stu-id="7167b-103">This example shows how to scale a 3-D object.</span></span> <span data-ttu-id="7167b-104">Per ridimensionare un oggetto 3D, usare un <xref:System.Windows.Media.Media3D.ScaleTransform3D>.</span><span class="sxs-lookup"><span data-stu-id="7167b-104">To scale a 3-D object, use a <xref:System.Windows.Media.Media3D.ScaleTransform3D>.</span></span> <span data-ttu-id="7167b-105">Il <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>, e <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> proprietà ridimensionano l'elemento in base al fattore specificato.</span><span class="sxs-lookup"><span data-stu-id="7167b-105">The <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>, and <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> properties resize the element by the factor you specify.</span></span> <span data-ttu-id="7167b-106">Ad esempio, un <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> valore pari a 1,5 adatta a un oggetto al 150% della sua larghezza originale.</span><span class="sxs-lookup"><span data-stu-id="7167b-106">For example, a <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> value of 1.5 stretches an object to 150 percent of its original width.</span></span> <span data-ttu-id="7167b-107">Oggetto <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> valore pari a 0,5 riduce l'altezza di un oggetto del 50%.</span><span class="sxs-lookup"><span data-stu-id="7167b-107">A <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> value of 0.5 shrinks the height of an object by 50 percent.</span></span> <span data-ttu-id="7167b-108">Il codice seguente viene illustrato l'utilizzo un <xref:System.Windows.Media.Media3D.ScaleTransform3D> come la trasformazione per un <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span><span class="sxs-lookup"><span data-stu-id="7167b-108">The code below shows using a <xref:System.Windows.Media.Media3D.ScaleTransform3D> as the transform for a <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="7167b-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="7167b-109">Example</span></span>  
 <span data-ttu-id="7167b-110">Il codice seguente illustra l'intero esempio.</span><span class="sxs-lookup"><span data-stu-id="7167b-110">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="7167b-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7167b-111">See also</span></span>
- [<span data-ttu-id="7167b-112">Aggiungere un'animazione alle conversioni tridimensionali</span><span class="sxs-lookup"><span data-stu-id="7167b-112">Animate 3-D Translations</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-3-d-translations.md)
- [<span data-ttu-id="7167b-113">Creare una scena tridimensionale</span><span class="sxs-lookup"><span data-stu-id="7167b-113">Create a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="7167b-114">Panoramica sulla grafica tridimensionale</span><span class="sxs-lookup"><span data-stu-id="7167b-114">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
