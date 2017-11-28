---
title: 'Procedura: creare forme tramite un oggetto StreamGeometry'
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
- graphics [WPF], shapes
- shapes [WPF], creating with StreamGeometry class
ms.assetid: 08f7c8ce-074b-49cd-9aba-cc9592d4ee51
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: caa97d0dbd4c847892e164ecb168349c38f7f271
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-shape-using-a-streamgeometry"></a><span data-ttu-id="bae43-102">Procedura: creare forme tramite un oggetto StreamGeometry</span><span class="sxs-lookup"><span data-stu-id="bae43-102">How to: Create a Shape Using a StreamGeometry</span></span>
<span data-ttu-id="bae43-103"><xref:System.Windows.Media.StreamGeometry>è un'alternativa semplificata a <xref:System.Windows.Media.PathGeometry> per la creazione di forme geometriche.</span><span class="sxs-lookup"><span data-stu-id="bae43-103"><xref:System.Windows.Media.StreamGeometry> is light-weight alternative to <xref:System.Windows.Media.PathGeometry> for creating geometric shapes.</span></span> <span data-ttu-id="bae43-104">Utilizzare un <xref:System.Windows.Media.StreamGeometry> quando è necessario descrivere una geometria complessa, ma non si desidera che l'overhead di supportare data binding, animazione o la modifica.</span><span class="sxs-lookup"><span data-stu-id="bae43-104">Use a <xref:System.Windows.Media.StreamGeometry> when you need to describe a complex geometry but do not want the overhead of supporting data binding, animation, or modification.</span></span> <span data-ttu-id="bae43-105">Ad esempio, grazie alla sua efficienza, il <xref:System.Windows.Media.StreamGeometry> classe è una buona scelta per descrivere gli strumenti decorativi.</span><span class="sxs-lookup"><span data-stu-id="bae43-105">For example, because of its efficiency, the <xref:System.Windows.Media.StreamGeometry> class is a good choice for describing adorners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bae43-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="bae43-106">Example</span></span>  
 <span data-ttu-id="bae43-107">L'esempio seguente usa la sintassi degli attributi per creare un oggetto triangolare <xref:System.Windows.Media.StreamGeometry> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bae43-107">The following example uses attribute syntax to create a triangular <xref:System.Windows.Media.StreamGeometry> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 <span data-ttu-id="bae43-108">Per ulteriori informazioni su <xref:System.Windows.Media.StreamGeometry> sintassi degli attributi, vedere il [sintassi del percorso di Markup](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) pagina.</span><span class="sxs-lookup"><span data-stu-id="bae43-108">For more information about <xref:System.Windows.Media.StreamGeometry> attribute syntax, see the [Path Markup Syntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) page.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bae43-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="bae43-109">Example</span></span>  
 <span data-ttu-id="bae43-110">Nell'esempio successivo viene utilizzato un <xref:System.Windows.Media.StreamGeometry> per definire un triangolo nel codice.</span><span class="sxs-lookup"><span data-stu-id="bae43-110">The next example uses a <xref:System.Windows.Media.StreamGeometry> to define a triangle in code.</span></span> <span data-ttu-id="bae43-111">Innanzitutto, nell'esempio viene creato un <xref:System.Windows.Media.StreamGeometry>, quindi ottenuto un <xref:System.Windows.Media.StreamGeometryContext> e viene utilizzato per descrivere il triangolo.</span><span class="sxs-lookup"><span data-stu-id="bae43-111">First, the example creates a <xref:System.Windows.Media.StreamGeometry>, then obtains a <xref:System.Windows.Media.StreamGeometryContext> and uses it to describe the triangle.</span></span>  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryTriangleExample.cs#streamgeometrytriangleexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometrytriangleexample.vb#streamgeometrytriangleexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="bae43-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="bae43-112">Example</span></span>  
 <span data-ttu-id="bae43-113">Nell'esempio successivo viene creato un metodo che utilizza un <xref:System.Windows.Media.StreamGeometry> e <xref:System.Windows.Media.StreamGeometryContext> per definire una forma geometrica in base ai parametri specificati.</span><span class="sxs-lookup"><span data-stu-id="bae43-113">The next example creates a method that uses a <xref:System.Windows.Media.StreamGeometry> and <xref:System.Windows.Media.StreamGeometryContext> to define a geometric shape based on specified parameters.</span></span>  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryExample.cs#streamgeometryexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometryexample.vb#streamgeometryexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="bae43-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bae43-114">See Also</span></span>  
 <xref:System.Windows.Media.PathGeometry>  
 <xref:System.Windows.Media.StreamGeometry>  
 <xref:System.Windows.Media.StreamGeometryContext>  
 [<span data-ttu-id="bae43-115">Creare una forma usando un oggetto PathGeometry</span><span class="sxs-lookup"><span data-stu-id="bae43-115">Create a Shape by Using a PathGeometry</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)  
 [<span data-ttu-id="bae43-116">Cenni preliminari sulle classi Geometry</span><span class="sxs-lookup"><span data-stu-id="bae43-116">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
