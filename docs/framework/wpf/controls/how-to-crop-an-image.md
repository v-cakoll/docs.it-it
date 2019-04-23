---
title: "Procedura: Ritagliare un'immagine"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [WPF], cropping
- cropping images [WPF]
ms.assetid: c6bba109-c6e7-4cf8-bfe6-9cf8d01bb4fc
ms.openlocfilehash: e672c7e24ec4db2d6424fa0b611cb1c135cf8eec
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59195553"
---
# <a name="how-to-crop-an-image"></a>Procedura: Ritagliare un'immagine
Questo esempio illustra come ritagliare un'immagine utilizzando <xref:System.Windows.Media.Imaging.CroppedBitmap>.  
  
 <xref:System.Windows.Media.Imaging.CroppedBitmap> viene utilizzato principalmente durante la codifica di una versione di un'immagine ritagliata per salvare in un file. Per ritagliare un'immagine per la visualizzazione, vedere il [come: Creare un'area di ritaglio](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms746710(v=vs.90)) argomento.  
  
## <a name="example"></a>Esempio  
 Nell'esempio [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] definisce le risorse usate all'interno di esempi riportati di seguito.  
  
 [!code-xaml[imageelementexample#CroppedXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml1)]  
  
 L'esempio seguente crea un'immagine utilizzando un <xref:System.Windows.Media.Imaging.CroppedBitmap> come origine.  
  
 [!code-xaml[imageelementexample#CroppedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml2)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp1)]
 [!code-vb[imageelementexample#CroppedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp1)]  
  
 Il <xref:System.Windows.Media.Imaging.CroppedBitmap> può anche essere utilizzato come origine di un altro <xref:System.Windows.Media.Imaging.CroppedBitmap>, concatenando il ritaglio. Si noti che il <xref:System.Windows.Media.Imaging.CroppedBitmap.SourceRect%2A> Usa i valori relativi a ritagliata bitmap e non all'immagine iniziale di origine.  
  
 [!code-xaml[imageelementexample#CroppedXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml3)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp2)]
 [!code-vb[imageelementexample#CroppedCSharp2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp2)]  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Creare un'area di ritaglio](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms746710(v=vs.90))
