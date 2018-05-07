---
title: 'Procedura: creare una geometria combinata'
ms.date: 03/30/2017
helpviewer_keywords:
- combining geometries [WPF]
- graphics [WPF], combining geometries
- geometries [WPF], combining
ms.assetid: 54c3277c-6b6e-4b25-91be-fda0bbc706b4
ms.openlocfilehash: 107e0342b822633ccb4f51f256c121cc80c297f4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-combined-geometry"></a>Procedura: creare una geometria combinata
In questo esempio viene illustrato come combinare le geometrie. Per combinare due geometrie, utilizzare un <xref:System.Windows.Media.CombinedGeometry> oggetto. Impostare il relativo <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> e <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> con le due geometrie da combinare e impostare il <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> proprietà che determina come le geometrie saranno combinate insieme, per `Union`, `Intersect`, `Exclude`, o `Xor`.  
  
 Per creare una geometria composta da due o più geometrie, utilizzare un <xref:System.Windows.Media.GeometryGroup>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, un <xref:System.Windows.Media.CombinedGeometry> viene definito con una modalità di combinazione di geometria `Exclude`.  Entrambi <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> e <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> sono definiti come cerchi dello stesso raggio, ma con offset dei centri di 50.  
  
 [!code-xaml[GeometrySample#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#21)]  
  
 ![Modalità di combinazione di risultati di Exclude](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-exclude.PNG "mil_task_combined_geometry_exclude")  
Esclusione di geometria combinata  
  
 Nel codice seguente, un <xref:System.Windows.Media.CombinedGeometry> viene definito con una modalità di combinazione `Intersect`.  Entrambi <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> e <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> sono definiti come cerchi dello stesso raggio, ma con offset dei centri di 50.  
  
 [!code-xaml[GeometrySample#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#22)]  
  
 ![Risultato dell'intersezione tra modalità di combinazione](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-intersect.PNG "mil_task_combined_geometry_intersect")  
Geometria combinata Intersect  
  
 Nel codice seguente, un <xref:System.Windows.Media.CombinedGeometry> viene definito con una modalità di combinazione `Union`.  Entrambi <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> e <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> sono definiti come cerchi dello stesso raggio, ma con offset dei centri di 50.  
  
 [!code-xaml[GeometrySample#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 ![Risultati della modalità di combinazione unione](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")  
Unione di geometria combinato  
  
 Nel codice seguente, un <xref:System.Windows.Media.CombinedGeometry> viene definito con una modalità di combinazione `Xor`.  Entrambi <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> e <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> sono definiti come cerchi dello stesso raggio, ma con offset dei centri di 50.  
  
 [!code-xaml[GeometrySample#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 ![Risultati della modalità di combinazione Xor](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")  
Geometria combinata Xor
