---
title: 'Procedura: Eseguire un hit test usando la geometria come parametro'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects using Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], hit tests on visual objects [WPF]
ms.assetid: 6c8bdbf2-19e0-4fbb-bf89-c1252b2ebc61
ms.openlocfilehash: 8bed7784b00f49178c9a87def74b62f7ce620ec7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923399"
---
# <a name="how-to-hit-test-using-geometry-as-a-parameter"></a>Procedura: Eseguire un hit test usando la geometria come parametro
Questo esempio illustra come eseguire un hit test su un oggetto visivo usando un <xref:System.Windows.Media.Geometry> come parametro dell'hit test.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come impostare un hit test utilizzando <xref:System.Windows.Media.GeometryHitTestParameters> per il <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> metodo. Il <xref:System.Windows.Point> valore passato `OnMouseDown` al metodo viene usato per creare un <xref:System.Windows.Media.Geometry> oggetto per espandere l'intervallo dell'hit test.  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet10](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet10)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet10)]  
  
 La <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> proprietà di <xref:System.Windows.Media.GeometryHitTestResult> fornisce informazioni sui risultati di un <xref:System.Windows.Media.Geometry> hit test che usa come parametro dell'hit test. La figura seguente mostra la relazione tra la geometria di hit test (cerchio blu) e il contenuto sottoposto a rendering dell'oggetto visivo di destinazione (quadrato rosso).  
  
 ![Diagramma che mostra IntersectionDetail usati nell'hit testing.](./media/how-to-hit-test-using-geometry-as-a-parameter/intersectiondetail-hit-test.png)  
  
 Nell'esempio seguente viene illustrato come implementare un callback di hit test quando <xref:System.Windows.Media.Geometry> un oggetto viene utilizzato come parametro dell'hit test. Viene `result` eseguito il cast del parametro <xref:System.Windows.Media.GeometryHitTestResult> a un oggetto per <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> recuperare il valore della proprietà. Il valore della proprietà consente di determinare se il <xref:System.Windows.Media.Geometry> parametro dell'hit test è completamente o parzialmente contenuto all'interno del contenuto sottoposto a rendering della destinazione dell'hit test. In questo caso, il codice di esempio aggiunge i risultati dell'hit test all'elenco solo per gli oggetti visivi completamente contenuti all'interno del limite della destinazione.  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet11)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet11)]  
  
> [!NOTE]
> Il <xref:System.Windows.Media.HitTestResult> callback non deve essere chiamato quando il dettaglio di intersezione è <xref:System.Windows.Media.IntersectionDetail.Empty>.  
  
## <a name="see-also"></a>Vedere anche

- [Hit testing a livello visivo](hit-testing-in-the-visual-layer.md)
- [Eseguire un hit test della geometria in un oggetto Visual](how-to-hit-test-geometry-in-a-visual.md)
