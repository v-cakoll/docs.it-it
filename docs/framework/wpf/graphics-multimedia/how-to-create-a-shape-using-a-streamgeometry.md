---
title: 'Procedura: Creare una forma utilizzando un oggetto StreamGeometry'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], shapes
- shapes [WPF], creating with StreamGeometry class
ms.assetid: 08f7c8ce-074b-49cd-9aba-cc9592d4ee51
ms.openlocfilehash: 94e7683d22b685c95f9f70612bc0aacef06e23bd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554205"
---
# <a name="how-to-create-a-shape-using-a-streamgeometry"></a><span data-ttu-id="1f7d2-102">Procedura: Creare una forma utilizzando un oggetto StreamGeometry</span><span class="sxs-lookup"><span data-stu-id="1f7d2-102">How to: Create a Shape Using a StreamGeometry</span></span>
<span data-ttu-id="1f7d2-103"><xref:System.Windows.Media.StreamGeometry> è un'alternativa semplificata a <xref:System.Windows.Media.PathGeometry> per la creazione di forme geometriche.</span><span class="sxs-lookup"><span data-stu-id="1f7d2-103"><xref:System.Windows.Media.StreamGeometry> is light-weight alternative to <xref:System.Windows.Media.PathGeometry> for creating geometric shapes.</span></span> <span data-ttu-id="1f7d2-104">Usare un <xref:System.Windows.Media.StreamGeometry> quando è necessario descrivere una geometria complessa, ma non si desidera il sovraccarico del supporto dell'associazione dati, l'animazione o la modifica.</span><span class="sxs-lookup"><span data-stu-id="1f7d2-104">Use a <xref:System.Windows.Media.StreamGeometry> when you need to describe a complex geometry but do not want the overhead of supporting data binding, animation, or modification.</span></span> <span data-ttu-id="1f7d2-105">Ad esempio, grazie alla sua efficienza, il <xref:System.Windows.Media.StreamGeometry> classe è una buona scelta per descrivere gli strumenti decorativi.</span><span class="sxs-lookup"><span data-stu-id="1f7d2-105">For example, because of its efficiency, the <xref:System.Windows.Media.StreamGeometry> class is a good choice for describing adorners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f7d2-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="1f7d2-106">Example</span></span>  
 <span data-ttu-id="1f7d2-107">L'esempio seguente usa la sintassi degli attributi per creare una forma di triangolo <xref:System.Windows.Media.StreamGeometry> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f7d2-107">The following example uses attribute syntax to create a triangular <xref:System.Windows.Media.StreamGeometry> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 <span data-ttu-id="1f7d2-108">Per altre informazioni sulle <xref:System.Windows.Media.StreamGeometry> sintassi degli attributi, vedere la [sintassi di Markup del percorso](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) pagina.</span><span class="sxs-lookup"><span data-stu-id="1f7d2-108">For more information about <xref:System.Windows.Media.StreamGeometry> attribute syntax, see the [Path Markup Syntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) page.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f7d2-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="1f7d2-109">Example</span></span>  
 <span data-ttu-id="1f7d2-110">L'esempio seguente usa un <xref:System.Windows.Media.StreamGeometry> per definire un triangolo nel codice.</span><span class="sxs-lookup"><span data-stu-id="1f7d2-110">The next example uses a <xref:System.Windows.Media.StreamGeometry> to define a triangle in code.</span></span> <span data-ttu-id="1f7d2-111">In primo luogo, l'esempio crea un <xref:System.Windows.Media.StreamGeometry>, quindi Ottiene un <xref:System.Windows.Media.StreamGeometryContext> e lo usa per descrivere il triangolo.</span><span class="sxs-lookup"><span data-stu-id="1f7d2-111">First, the example creates a <xref:System.Windows.Media.StreamGeometry>, then obtains a <xref:System.Windows.Media.StreamGeometryContext> and uses it to describe the triangle.</span></span>  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryTriangleExample.cs#streamgeometrytriangleexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometrytriangleexample.vb#streamgeometrytriangleexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="1f7d2-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="1f7d2-112">Example</span></span>  
 <span data-ttu-id="1f7d2-113">L'esempio successivo crea un metodo che usa un' <xref:System.Windows.Media.StreamGeometry> e <xref:System.Windows.Media.StreamGeometryContext> per definire una forma geometrica, in base ai parametri specificati.</span><span class="sxs-lookup"><span data-stu-id="1f7d2-113">The next example creates a method that uses a <xref:System.Windows.Media.StreamGeometry> and <xref:System.Windows.Media.StreamGeometryContext> to define a geometric shape based on specified parameters.</span></span>  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryExample.cs#streamgeometryexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometryexample.vb#streamgeometryexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="1f7d2-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1f7d2-114">See also</span></span>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Media.StreamGeometry>
- <xref:System.Windows.Media.StreamGeometryContext>
- [<span data-ttu-id="1f7d2-115">Creare una forma usando un oggetto PathGeometry</span><span class="sxs-lookup"><span data-stu-id="1f7d2-115">Create a Shape by Using a PathGeometry</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
- [<span data-ttu-id="1f7d2-116">Cenni preliminari sulle classi Geometry</span><span class="sxs-lookup"><span data-stu-id="1f7d2-116">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
