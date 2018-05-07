---
title: 'Procedura: applicare un GuidelineSet a un disegno'
ms.date: 03/30/2017
helpviewer_keywords:
- GuidelineSet property [WPF], applying to drawings
- graphics [WPF], GuidelineSet property
ms.assetid: 45f3e0b4-8820-45a7-b865-b8ea5b17b0c8
ms.openlocfilehash: cd60ed8337aa802b808a515f9521b972869f6235
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-apply-a-guidelineset-to-a-drawing"></a>Procedura: applicare un GuidelineSet a un disegno
In questo esempio viene illustrato come applicare un <xref:System.Windows.Media.GuidelineSet> per un <xref:System.Windows.Media.DrawingGroup>.  
  
 Il <xref:System.Windows.Media.DrawingGroup> classe è l'unico tipo di <xref:System.Windows.Media.Drawing> che ha un <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> proprietà. Per applicare un <xref:System.Windows.Media.GuidelineSet> a un altro tipo di <xref:System.Windows.Media.Drawing>, aggiungerlo a un <xref:System.Windows.Media.DrawingGroup> e quindi applicare il <xref:System.Windows.Media.GuidelineSet> per il <xref:System.Windows.Media.DrawingGroup>.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea due <xref:System.Windows.Media.DrawingGroup> gli oggetti che sono quasi identici; l'unica differenza è: il secondo <xref:System.Windows.Media.DrawingGroup> ha un <xref:System.Windows.Media.GuidelineSet> e non il primo.  
  
 L'immagine seguente illustra l'output dell'esempio. Poiché il rendering delle differenze tra i due <xref:System.Windows.Media.DrawingGroup> oggetti è minima, alcune parti dei disegni sono ingrandite.  
  
 ![Oggetto DrawingGroup con e senza un GuidelineSet](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupGuidelineSetExample.cs#graphicsmmdrawinggroupguidelinesetexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupGuidelineSetExample.xaml#graphicsmmdrawinggroupguidelinesetexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.DrawingGroup>  
 <xref:System.Windows.Media.GuidelineSet>  
 [Cenni preliminari sugli oggetti Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
