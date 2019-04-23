---
title: 'Procedura: Creare una forma usando un oggetto StreamGeometry'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], shapes
- shapes [WPF], creating with StreamGeometry class
ms.assetid: 08f7c8ce-074b-49cd-9aba-cc9592d4ee51
ms.openlocfilehash: fd191e4cfdfa33c144389d4871a9641e9c811ed3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59108602"
---
# <a name="how-to-create-a-shape-using-a-streamgeometry"></a>Procedura: Creare una forma usando un oggetto StreamGeometry
<xref:System.Windows.Media.StreamGeometry> è un'alternativa semplificata a <xref:System.Windows.Media.PathGeometry> per la creazione di forme geometriche. Usare un <xref:System.Windows.Media.StreamGeometry> quando è necessario descrivere una geometria complessa, ma non si desidera il sovraccarico del supporto dell'associazione dati, l'animazione o la modifica. Ad esempio, grazie alla sua efficienza, il <xref:System.Windows.Media.StreamGeometry> classe è una buona scelta per descrivere gli strumenti decorativi.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa la sintassi degli attributi per creare una forma di triangolo <xref:System.Windows.Media.StreamGeometry> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 Per altre informazioni sulle <xref:System.Windows.Media.StreamGeometry> sintassi degli attributi, vedere la [sintassi di Markup del percorso](path-markup-syntax.md) pagina.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa un <xref:System.Windows.Media.StreamGeometry> per definire un triangolo nel codice. In primo luogo, l'esempio crea un <xref:System.Windows.Media.StreamGeometry>, quindi Ottiene un <xref:System.Windows.Media.StreamGeometryContext> e lo usa per descrivere il triangolo.  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryTriangleExample.cs#streamgeometrytriangleexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometrytriangleexample.vb#streamgeometrytriangleexamplewholepage)]  
  
## <a name="example"></a>Esempio  
 L'esempio successivo crea un metodo che usa un' <xref:System.Windows.Media.StreamGeometry> e <xref:System.Windows.Media.StreamGeometryContext> per definire una forma geometrica, in base ai parametri specificati.  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryExample.cs#streamgeometryexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometryexample.vb#streamgeometryexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Media.StreamGeometry>
- <xref:System.Windows.Media.StreamGeometryContext>
- [Creare una forma usando un oggetto PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md)
- [Cenni preliminari sulle classi Geometry](geometry-overview.md)
