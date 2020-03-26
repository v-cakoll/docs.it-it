---
title: 'Procedura: trasformare la scala di un modello 3DHow to: Transform the Scale of a 3D Model'
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], 3D objects
- 3D objects [WPF], scaling
ms.assetid: f3fdfe33-f7dc-44b0-84a5-e43b89947f35
ms.openlocfilehash: be41a0e10929912c1b54bf7140d743d9453199bf
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111985"
---
# <a name="how-to-transform-the-scale-of-a-3d-model"></a><span data-ttu-id="652dd-102">Procedura: trasformare la scala di un modello 3DHow to: Transform the Scale of a 3D Model</span><span class="sxs-lookup"><span data-stu-id="652dd-102">How to: Transform the Scale of a 3D Model</span></span>
<span data-ttu-id="652dd-103">In questo esempio viene illustrato come ridimensionare un oggetto 3D.</span><span class="sxs-lookup"><span data-stu-id="652dd-103">This example shows how to scale a 3D object.</span></span> <span data-ttu-id="652dd-104">Per ridimensionare un oggetto 3D, utilizzare un <xref:System.Windows.Media.Media3D.ScaleTransform3D>file .</span><span class="sxs-lookup"><span data-stu-id="652dd-104">To scale a 3D object, use a <xref:System.Windows.Media.Media3D.ScaleTransform3D>.</span></span> <span data-ttu-id="652dd-105">Le <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>proprietà <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> , e ridimensionano l'elemento in base al fattore specificato.</span><span class="sxs-lookup"><span data-stu-id="652dd-105">The <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>, and <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> properties resize the element by the factor you specify.</span></span> <span data-ttu-id="652dd-106">Ad esempio, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> un valore pari a 1,5 estende un oggetto fino al 150% della larghezza originale.</span><span class="sxs-lookup"><span data-stu-id="652dd-106">For example, a <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> value of 1.5 stretches an object to 150 percent of its original width.</span></span> <span data-ttu-id="652dd-107">Un <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> valore pari a 0,5 riduce l'altezza di un oggetto del 50%.</span><span class="sxs-lookup"><span data-stu-id="652dd-107">A <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> value of 0.5 shrinks the height of an object by 50 percent.</span></span> <span data-ttu-id="652dd-108">Nel codice riportato <xref:System.Windows.Media.Media3D.ScaleTransform3D> di seguito <xref:System.Windows.Media.Media3D.GeometryModel3D>viene illustrato l'utilizzo di a come trasformazione per un oggetto .</span><span class="sxs-lookup"><span data-stu-id="652dd-108">The code below shows using a <xref:System.Windows.Media.Media3D.ScaleTransform3D> as the transform for a <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="652dd-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="652dd-109">Example</span></span>  
 <span data-ttu-id="652dd-110">Il codice seguente mostra l'intero esempio.</span><span class="sxs-lookup"><span data-stu-id="652dd-110">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="652dd-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="652dd-111">See also</span></span>

- [<span data-ttu-id="652dd-112">Animare le conversioni 3D</span><span class="sxs-lookup"><span data-stu-id="652dd-112">Animate 3D Translations</span></span>](how-to-animate-3-d-translations.md)
- [<span data-ttu-id="652dd-113">Creare una scena 3D</span><span class="sxs-lookup"><span data-stu-id="652dd-113">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="652dd-114">Panoramica della grafica 3D</span><span class="sxs-lookup"><span data-stu-id="652dd-114">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
