---
title: 'Procedura: Creare una geometria combinata'
ms.date: 03/30/2017
helpviewer_keywords:
- combining geometries [WPF]
- graphics [WPF], combining geometries
- geometries [WPF], combining
ms.assetid: 54c3277c-6b6e-4b25-91be-fda0bbc706b4
ms.openlocfilehash: c5ebe87abd4c2cf70f8fa17f1fcc773293f3ad27
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364788"
---
# <a name="how-to-create-a-combined-geometry"></a>Procedura: Creare una geometria combinata
In questo esempio viene illustrato come combinare le geometrie. Per combinare due geometrie, usare un <xref:System.Windows.Media.CombinedGeometry> oggetto. Impostare relativi <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> e <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> con le due geometrie per combinare e impostare il <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> proprietà, che determina come le geometrie vengono combinate insieme, alla `Union`, `Intersect`, `Exclude`, o `Xor`.  
  
 Per creare una geometria composta da due o più oggetti Geometry, usare un <xref:System.Windows.Media.GeometryGroup>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, un <xref:System.Windows.Media.CombinedGeometry> viene definito con una modalità di combinazione di geometria `Exclude`.  Entrambe <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> e il <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> sono definiti come cerchi dello stesso raggio, ma con scostamento dei centri di 50.  
  
 [!code-xaml[GeometrySample#21](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#21)]  
  
 ![Modalità di combinazione di risultati di Exclude](./media/mil-task-combined-geometry-exclude.PNG "mil_task_combined_geometry_exclude")  
Esclusione di geometria combinata  
  
 Nel markup seguente, un <xref:System.Windows.Media.CombinedGeometry> viene definito con una modalità di combinazione di `Intersect`.  Entrambe <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> e il <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> sono definiti come cerchi dello stesso raggio, ma con scostamento dei centri di 50.  
  
 [!code-xaml[GeometrySample#22](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#22)]  
  
 ![Modalità di combinazione di risultati di intersezione](./media/mil-task-combined-geometry-intersect.PNG "mil_task_combined_geometry_intersect")  
Si intersecano geometria combinata  
  
 Nel markup seguente, un <xref:System.Windows.Media.CombinedGeometry> viene definito con una modalità di combinazione di `Union`.  Entrambe <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> e il <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> sono definiti come cerchi dello stesso raggio, ma con scostamento dei centri di 50.  
  
 [!code-xaml[GeometrySample#23](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 ![Risultati della modalità di combinazione unione](./media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")  
Unione di geometria combinata  
  
 Nel markup seguente, un <xref:System.Windows.Media.CombinedGeometry> viene definito con una modalità di combinazione di `Xor`.  Entrambe <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> e il <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> sono definiti come cerchi dello stesso raggio, ma con scostamento dei centri di 50.  
  
 [!code-xaml[GeometrySample#24](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 ![Risultati della modalità di combinazione Xor](./media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")  
Xor geometria combinata
