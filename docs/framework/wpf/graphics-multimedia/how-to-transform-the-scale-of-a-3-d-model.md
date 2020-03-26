---
title: 'Procedura: trasformare la scala di un modello 3DHow to: Transform the Scale of a 3D Model'
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], 3D objects
- 3D objects [WPF], scaling
ms.assetid: f3fdfe33-f7dc-44b0-84a5-e43b89947f35
ms.openlocfilehash: be41a0e10929912c1b54bf7140d743d9453199bf
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111985"
---
# <a name="how-to-transform-the-scale-of-a-3d-model"></a>Procedura: trasformare la scala di un modello 3DHow to: Transform the Scale of a 3D Model
In questo esempio viene illustrato come ridimensionare un oggetto 3D. Per ridimensionare un oggetto 3D, utilizzare un <xref:System.Windows.Media.Media3D.ScaleTransform3D>file . Le <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>proprietà <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> , e ridimensionano l'elemento in base al fattore specificato. Ad esempio, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> un valore pari a 1,5 estende un oggetto fino al 150% della larghezza originale. Un <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> valore pari a 0,5 riduce l'altezza di un oggetto del 50%. Nel codice riportato <xref:System.Windows.Media.Media3D.ScaleTransform3D> di seguito <xref:System.Windows.Media.Media3D.GeometryModel3D>viene illustrato l'utilizzo di a come trasformazione per un oggetto .  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexampleinline1)]  
  
## <a name="example"></a>Esempio  
 Il codice seguente mostra l'intero esempio.  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- [Animare le conversioni 3D](how-to-animate-3-d-translations.md)
- [Creare una scena 3D](how-to-create-a-3-d-scene.md)
- [Panoramica della grafica 3D](3-d-graphics-overview.md)
