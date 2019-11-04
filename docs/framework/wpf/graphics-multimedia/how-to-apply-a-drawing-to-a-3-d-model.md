---
title: 'Procedura: applicare un disegno a un modello tridimensionale'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3-D models
- 3-D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 311a3ac1d9fa219a3a365d506d9d0c3e8b6bc229
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459373"
---
# <a name="how-to-apply-a-drawing-to-a-3-d-model"></a>Procedura: applicare un disegno a un modello tridimensionale

Questo esempio illustra come usare un <xref:System.Windows.Media.DrawingBrush> come <xref:System.Windows.Media.Media3D.Material> applicato a un modello 3D.

Nel codice seguente viene definito un <xref:System.Windows.Media.DrawingGroup> come contenuto di un <xref:System.Windows.Media.DrawingBrush>.  Il <xref:System.Windows.Media.DrawingBrush> viene impostato come proprietà <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> del <xref:System.Windows.Media.Media3D.DiffuseMaterial> applicato a un piano 3D.

> [!NOTE]
> Spesso è consigliabile definire oggetti e valori complessi come il disegno seguente come risorse che possono essere riutilizzate e semplificare il codice. Per ulteriori informazioni, vedere [risorse XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md) .

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]

## <a name="example"></a>Esempio

Il codice seguente illustra l'intero esempio.

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]

## <a name="see-also"></a>Vedere anche

- [Risorse XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Creare una scena tridimensionale](how-to-create-a-3-d-scene.md)
- [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md)
- [Panoramica sulla grafica tridimensionale](3-d-graphics-overview.md)
