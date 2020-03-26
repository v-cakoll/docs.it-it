---
title: 'Procedura: applicare un disegno a un modello 3DHow to: Apply a Drawing to a 3D Model'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3D models
- 3D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 5b10630ab674fa9489cdf7ad53516a680f19da08
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112180"
---
# <a name="how-to-apply-a-drawing-to-a-3d-model"></a>Procedura: applicare un disegno a un modello 3DHow to: Apply a Drawing to a 3D Model

In questo esempio viene <xref:System.Windows.Media.DrawingBrush> illustrato <xref:System.Windows.Media.Media3D.Material> come utilizzare un come applicato a un modello 3D.

Il codice seguente <xref:System.Windows.Media.DrawingGroup> definisce un <xref:System.Windows.Media.DrawingBrush>come contenuto di un oggetto .  L'oggetto <xref:System.Windows.Media.DrawingBrush> viene <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> impostato <xref:System.Windows.Media.Media3D.DiffuseMaterial> come proprietà dell'oggetto applicato a un piano 3D.

> [!NOTE]
> È spesso opportuno definire oggetti complessi e valori come il disegno seguente come risorse che possono essere riutilizzate e semplificare il codice. Per altre informazioni, vedere [Risorse XAML.](../../../desktop-wpf/fundamentals/xaml-resources-define.md)

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]

## <a name="example"></a>Esempio

Il codice seguente mostra l'intero esempio.

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]

## <a name="see-also"></a>Vedere anche

- [Risorse XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Creare una scena 3D](how-to-create-a-3-d-scene.md)
- [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md)
- [Panoramica della grafica 3D](3-d-graphics-overview.md)
