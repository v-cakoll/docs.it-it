---
title: 'Procedura: Utilizzare un MatrixTransform per creare trasformazioni personalizzate'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], custom Transforms
ms.assetid: 919381ca-989f-47cf-86b4-1094060236e4
ms.openlocfilehash: aeccb961db539d4cc6dea75fb487fba06e59d6de
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59182312"
---
# <a name="how-to-use-a-matrixtransform-to-create-custom-transforms"></a>Procedura: Utilizzare un MatrixTransform per creare trasformazioni personalizzate
In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Media.MatrixTransform> traslare (spostare) la posizione dell'estensione e l'inclinazione di un <xref:System.Windows.Controls.Button>.  
  
> [!NOTE]
>  Usare la <xref:System.Windows.Media.MatrixTransform> classe per creare trasformazioni personalizzate non disponibili per il <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.SkewTransform>, <xref:System.Windows.Media.ScaleTransform>, o <xref:System.Windows.Media.TranslateTransform> classi.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[Transforms_snip#MatrixTransform](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MatrixTransformExample.xaml#matrixtransform)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.MatrixTransform>
- <xref:System.Windows.Media.Transform>
- [Cenni preliminari sulle trasformazioni](transforms-overview.md)
- [Procedure relative alle proprietà](transformations-how-to-topics.md)
- [Cenni preliminari sugli oggetti Shape e sulle funzionalità di disegno di base di WPF](shapes-and-basic-drawing-in-wpf-overview.md)
