---
title: 'Procedura: Utilizzare un MatrixTransform per creare trasformazioni personalizzate'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], custom Transforms
ms.assetid: 919381ca-989f-47cf-86b4-1094060236e4
ms.openlocfilehash: 1971d5fe9422c5138f140517e6fd4c9f9b2cf48b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913922"
---
# <a name="how-to-use-a-matrixtransform-to-create-custom-transforms"></a>Procedura: Utilizzare un MatrixTransform per creare trasformazioni personalizzate
Questo esempio illustra come usare un oggetto <xref:System.Windows.Media.MatrixTransform> per tradurre (spostare) la posizione, l'estensione e l'inclinazione <xref:System.Windows.Controls.Button>di un oggetto.  
  
> [!NOTE]
> Utilizzare la <xref:System.Windows.Media.MatrixTransform> classe per creare trasformazioni personalizzate che non sono fornite <xref:System.Windows.Media.RotateTransform>dalle classi, <xref:System.Windows.Media.SkewTransform>, <xref:System.Windows.Media.ScaleTransform>o <xref:System.Windows.Media.TranslateTransform> .  
  
## <a name="example"></a>Esempio  
 [!code-xaml[Transforms_snip#MatrixTransform](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MatrixTransformExample.xaml#matrixtransform)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.MatrixTransform>
- <xref:System.Windows.Media.Transform>
- [Cenni preliminari sulle trasformazioni](transforms-overview.md)
- [Procedure relative alle proprietà](transformations-how-to-topics.md)
- [Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF](shapes-and-basic-drawing-in-wpf-overview.md)
