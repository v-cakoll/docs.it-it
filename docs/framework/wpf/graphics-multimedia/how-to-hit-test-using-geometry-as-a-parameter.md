---
title: 'Procedura: eseguire un hit test utilizzando la geometria come parametro'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects using Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], hit tests on visual objects [WPF]
ms.assetid: 6c8bdbf2-19e0-4fbb-bf89-c1252b2ebc61
ms.openlocfilehash: 57b04f7f8c9bcc21f6b970c2981c2bab51044c10
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-hit-test-using-geometry-as-a-parameter"></a>Procedura: eseguire un hit test utilizzando la geometria come parametro
In questo esempio viene illustrato come eseguire un hit test su un oggetto visivo utilizzando un <xref:System.Windows.Media.Geometry> come relativo parametro di test.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come impostare un hit test utilizzando <xref:System.Windows.Media.GeometryHitTestParameters> per il <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> metodo. Il <xref:System.Windows.Point> valore passato per il `OnMouseDown` metodo viene utilizzato per creare un <xref:System.Windows.Media.Geometry> oggetti per espandere l'intervallo dell'hit test.  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet10)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet10)]  
  
 Il <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> proprietà di <xref:System.Windows.Media.GeometryHitTestResult> vengono fornite informazioni sui risultati dell'hit test che utilizza un <xref:System.Windows.Media.Geometry> come relativo parametro di test. La figura seguente mostra la relazione tra la geometria di hit test (cerchio blu) e il contenuto sottoposto a rendering dell'oggetto visivo di destinazione (quadrato rosso).  
  
 ![Diagramma di IntersectionDetail usato nell'hit testing](../../../../docs/framework/wpf/graphics-multimedia/media/intersectiondetail01.png "IntersectionDetail01")  
Intersezione tra la geometria di hit test e l'oggetto visivo di destinazione  
  
 Nell'esempio seguente viene illustrato come implementare un callback dell'hit test quando un <xref:System.Windows.Media.Geometry> viene utilizzato come parametro di hit test. Il `result` parametro viene eseguito il cast a un <xref:System.Windows.Media.GeometryHitTestResult> per recuperare il valore della <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> proprietà. Il valore della proprietà consente di determinare se il <xref:System.Windows.Media.Geometry> parametro dell'hit test è completamente o parzialmente all'interno del contenuto sottoposto a rendering della destinazione dell'hit test. In questo caso, il codice di esempio aggiunge i risultati dell'hit test all'elenco solo per gli oggetti visivi completamente contenuti all'interno del limite della destinazione.  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet11)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet11)]  
  
> [!NOTE]
>  Il <xref:System.Windows.Media.HitTestResult> callback non deve essere chiamato quando il dettaglio dell'intersezione <xref:System.Windows.Media.IntersectionDetail.Empty>.  
  
## <a name="see-also"></a>Vedere anche  
 [Hit testing a livello visivo](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)  
 [Eseguire un hit test della geometria in un oggetto Visual](../../../../docs/framework/wpf/graphics-multimedia/how-to-hit-test-geometry-in-a-visual.md)
