---
title: "Procedura: Disegnare un'area con una sfumatura radiale"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with radial gradients
- radial gradients [WPF], painting with
- painting [WPF], with radial gradients
ms.assetid: b5d0fc8a-8986-4796-b003-a75b41a48928
ms.openlocfilehash: c3bcc11dea4b1f223f629415591ab03588881dde
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57379783"
---
# <a name="how-to-paint-an-area-with-a-radial-gradient"></a>Procedura: Disegnare un'area con una sfumatura radiale
In questo esempio viene illustrato come utilizzare il <xref:System.Windows.Media.RadialGradientBrush> classe disegnare un'area con una sfumatura radiale.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa un <xref:System.Windows.Media.RadialGradientBrush> per disegnare un rettangolo con una sfumatura radiale che effettua la transizione da giallo a rosso a blu al verde limone.  
  
 [!code-csharp[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/RadialGradientBrushSnippet.cs#simpleradialgradientexamplewholepage)]
 [!code-vb[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/radialgradientbrushsnippet.vb#simpleradialgradientexamplewholepage)]
 [!code-xaml[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/RadialGradientBrushSnippet.xaml#simpleradialgradientexamplewholepage)]  
  
 Nella figura seguente illustra la sfumatura dell'esempio precedente. È stata evidenziata della sfumatura.  
  
 ![Cursori sfumatura in una sfumatura radiale](./media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")  
  
> [!NOTE]
>  Gli esempi in questo argomento usano il sistema di coordinate predefinito per l'impostazione di punti di controllo. Il sistema di coordinate è relativo a un rettangolo: 0 indica lo 0% del rettangolo di selezione, mentre 1 indica il 100% del rettangolo di selezione. È possibile modificare il sistema di coordinate impostando il <xref:System.Windows.Media.GradientBrush.MappingMode%2A> il valore della proprietà <xref:System.Windows.Media.BrushMappingMode.Absolute>. Un sistema di coordinate assoluto non è relativo a un rettangolo di selezione. I valori vengono interpretati direttamente nello spazio locale.  
  
 Per ulteriori <xref:System.Windows.Media.RadialGradientBrush> esempi, vedere la [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973). Per altre informazioni su sfumature e altri tipi di pennelli, vedere [disegno con colori a tinta unita e sfumature Panoramica](painting-with-solid-colors-and-gradients-overview.md).
