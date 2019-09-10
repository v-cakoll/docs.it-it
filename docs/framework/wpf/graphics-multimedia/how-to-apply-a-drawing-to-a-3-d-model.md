---
title: 'Procedura: Applicare un disegno a un modello tridimensionale'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3-D models
- 3-D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 14470d0adeb948ea46a0720b5713c20fb7d8e6d8
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855877"
---
# <a name="how-to-apply-a-drawing-to-a-3-d-model"></a>Procedura: Applicare un disegno a un modello tridimensionale

Questo esempio illustra come usare un oggetto <xref:System.Windows.Media.DrawingBrush> <xref:System.Windows.Media.Media3D.Material> come applicato a un modello 3D.

Il codice seguente definisce un <xref:System.Windows.Media.DrawingGroup> oggetto come contenuto di un <xref:System.Windows.Media.DrawingBrush>oggetto.  Viene impostato come la <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> proprietà dell'oggetto <xref:System.Windows.Media.Media3D.DiffuseMaterial> applicato a un piano 3D. <xref:System.Windows.Media.DrawingBrush>

> [!NOTE]
> Spesso è consigliabile definire oggetti e valori complessi come il disegno seguente come risorse che possono essere riutilizzate e semplificare il codice. Per ulteriori informazioni, vedere [risorse XAML](../advanced/xaml-resources.md) .

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]

## <a name="example"></a>Esempio

Il codice seguente illustra l'intero esempio.

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]

## <a name="see-also"></a>Vedere anche

- [Risorse XAML](../advanced/xaml-resources.md)
- [Creare una scena tridimensionale](how-to-create-a-3-d-scene.md)
- [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md)
- [Panoramica sulla grafica tridimensionale](3-d-graphics-overview.md)
