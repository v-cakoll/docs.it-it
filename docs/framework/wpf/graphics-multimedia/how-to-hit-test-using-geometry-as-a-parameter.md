---
title: 'Procedura: Eseguire un hit test utilizzando la geometria come parametro'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects using Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], hit tests on visual objects [WPF]
ms.assetid: 6c8bdbf2-19e0-4fbb-bf89-c1252b2ebc61
ms.openlocfilehash: d52f8da891ecdf632952c441f94aab4c0b56da7f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564253"
---
# <a name="how-to-hit-test-using-geometry-as-a-parameter"></a>Procedura: Eseguire un hit test utilizzando la geometria come parametro
Questo esempio viene illustrato come eseguire un hit test su un oggetto visivo usando un <xref:System.Windows.Media.Geometry> come relativo parametro di test.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come impostare un hit test utilizzando <xref:System.Windows.Media.GeometryHitTestParameters> per il <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> (metodo). Il <xref:System.Windows.Point> valore passato per il `OnMouseDown` metodo viene utilizzato per creare un <xref:System.Windows.Media.Geometry> oggetti ed espandere l'intervallo dell'hit test.  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet10)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet10)]  
  
 Il <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> proprietà di <xref:System.Windows.Media.GeometryHitTestResult> fornisce informazioni sui risultati di un hit test che usa un <xref:System.Windows.Media.Geometry> come relativo parametro di test. La figura seguente mostra la relazione tra la geometria di hit test (cerchio blu) e il contenuto sottoposto a rendering dell'oggetto visivo di destinazione (quadrato rosso).  
  
 ![Diagramma di IntersectionDetail usato nell'hit testing](../../../../docs/framework/wpf/graphics-multimedia/media/intersectiondetail01.png "IntersectionDetail01")  
Intersezione tra la geometria di hit test e l'oggetto visivo di destinazione  
  
 Nell'esempio seguente viene illustrato come implementare un callback dell'hit test quando un <xref:System.Windows.Media.Geometry> viene usato come parametro di hit test. Il `result` parametro viene eseguito il cast a un <xref:System.Windows.Media.GeometryHitTestResult> per recuperare il valore della <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> proprietà. Il valore della proprietà consente di determinare se il <xref:System.Windows.Media.Geometry> parametro di hit test è contenuto completamente o parzialmente all'interno di contenuto di cui viene eseguito il rendering di destinazione dell'hit test. In questo caso, il codice di esempio aggiunge i risultati dell'hit test all'elenco solo per gli oggetti visivi completamente contenuti all'interno del limite della destinazione.  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet11)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet11)]  
  
> [!NOTE]
>  Il <xref:System.Windows.Media.HitTestResult> callback non deve essere chiamato una volta il dettaglio dell'intersezione <xref:System.Windows.Media.IntersectionDetail.Empty>.  
  
## <a name="see-also"></a>Vedere anche
- [Hit testing a livello visivo](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)
- [Eseguire un hit test della geometria in un oggetto Visual](../../../../docs/framework/wpf/graphics-multimedia/how-to-hit-test-geometry-in-a-visual.md)
