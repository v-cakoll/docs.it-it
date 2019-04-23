---
title: 'Procedura: Ridimensionare un modello tridimensionale'
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], 3-D objects
- 3-D objects [WPF], scaling
ms.assetid: f3fdfe33-f7dc-44b0-84a5-e43b89947f35
ms.openlocfilehash: 6d668de08201d819ce9f8752bedf6c388a6bc718
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59165087"
---
# <a name="how-to-transform-the-scale-of-a-3-d-model"></a><span data-ttu-id="1d6b4-102">Procedura: Ridimensionare un modello tridimensionale</span><span class="sxs-lookup"><span data-stu-id="1d6b4-102">How to: Transform the Scale of a 3-D Model</span></span>
<span data-ttu-id="1d6b4-103">Questo esempio illustra come ridimensionare un oggetto 3D.</span><span class="sxs-lookup"><span data-stu-id="1d6b4-103">This example shows how to scale a 3-D object.</span></span> <span data-ttu-id="1d6b4-104">Per ridimensionare un oggetto 3D, usare un <xref:System.Windows.Media.Media3D.ScaleTransform3D>.</span><span class="sxs-lookup"><span data-stu-id="1d6b4-104">To scale a 3-D object, use a <xref:System.Windows.Media.Media3D.ScaleTransform3D>.</span></span> <span data-ttu-id="1d6b4-105">Il <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>, e <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> proprietà ridimensionano l'elemento in base al fattore specificato.</span><span class="sxs-lookup"><span data-stu-id="1d6b4-105">The <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>, and <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> properties resize the element by the factor you specify.</span></span> <span data-ttu-id="1d6b4-106">Ad esempio, un <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> valore pari a 1,5 adatta a un oggetto al 150% della sua larghezza originale.</span><span class="sxs-lookup"><span data-stu-id="1d6b4-106">For example, a <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> value of 1.5 stretches an object to 150 percent of its original width.</span></span> <span data-ttu-id="1d6b4-107">Oggetto <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> valore pari a 0,5 riduce l'altezza di un oggetto del 50%.</span><span class="sxs-lookup"><span data-stu-id="1d6b4-107">A <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> value of 0.5 shrinks the height of an object by 50 percent.</span></span> <span data-ttu-id="1d6b4-108">Il codice seguente viene illustrato l'utilizzo un <xref:System.Windows.Media.Media3D.ScaleTransform3D> come la trasformazione per un <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span><span class="sxs-lookup"><span data-stu-id="1d6b4-108">The code below shows using a <xref:System.Windows.Media.Media3D.ScaleTransform3D> as the transform for a <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="1d6b4-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="1d6b4-109">Example</span></span>  
 <span data-ttu-id="1d6b4-110">Il codice seguente illustra l'intero esempio.</span><span class="sxs-lookup"><span data-stu-id="1d6b4-110">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="1d6b4-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d6b4-111">See also</span></span>

- [<span data-ttu-id="1d6b4-112">Aggiungere un'animazione alle conversioni tridimensionali</span><span class="sxs-lookup"><span data-stu-id="1d6b4-112">Animate 3-D Translations</span></span>](how-to-animate-3-d-translations.md)
- [<span data-ttu-id="1d6b4-113">Creare una scena tridimensionale</span><span class="sxs-lookup"><span data-stu-id="1d6b4-113">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="1d6b4-114">Panoramica sulla grafica tridimensionale</span><span class="sxs-lookup"><span data-stu-id="1d6b4-114">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
