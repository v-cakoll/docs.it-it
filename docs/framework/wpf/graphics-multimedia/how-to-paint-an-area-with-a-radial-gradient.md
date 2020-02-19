---
title: "Procedura: disegnare un'area con una sfumatura radiale"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with radial gradients
- radial gradients [WPF], painting with
- painting [WPF], with radial gradients
ms.assetid: b5d0fc8a-8986-4796-b003-a75b41a48928
ms.openlocfilehash: 8a53d5d7247f82905816265f7c92b22f287591c5
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452753"
---
# <a name="how-to-paint-an-area-with-a-radial-gradient"></a>Procedura: disegnare un'area con una sfumatura radiale
Questo esempio illustra come usare la classe <xref:System.Windows.Media.RadialGradientBrush> per disegnare un'area con una sfumatura radiale.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato un <xref:System.Windows.Media.RadialGradientBrush> per disegnare un rettangolo con una sfumatura radiale che passa da giallo a rosso a blu a verde limone.  
  
 [!code-csharp[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/RadialGradientBrushSnippet.cs#simpleradialgradientexamplewholepage)]
 [!code-vb[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/radialgradientbrushsnippet.vb#simpleradialgradientexamplewholepage)]
 [!code-xaml[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/RadialGradientBrushSnippet.xaml#simpleradialgradientexamplewholepage)]  
  
 Nella figura seguente viene illustrata la sfumatura dell'esempio precedente. I cursori della sfumatura sono stati evidenziati.  
  
 ![Cursori sfumatura in una sfumatura radiale](./media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")  
  
> [!NOTE]
> Negli esempi di questo argomento viene utilizzato il sistema di coordinate predefinito per l'impostazione dei punti di controllo. Il sistema di coordinate predefinito è relativo a un rettangolo di delimitazione: 0 indica lo 0% del rettangolo di delimitazione e 1 indica il 100% del rettangolo di delimitazione. È possibile modificare questo sistema di coordinate impostando la proprietà <xref:System.Windows.Media.GradientBrush.MappingMode%2A> sul valore <xref:System.Windows.Media.BrushMappingMode.Absolute>. Un sistema di coordinate assoluto non è relativo a un rettangolo di selezione. I valori vengono interpretati direttamente nello spazio locale.  
  
 Per ulteriori <xref:System.Windows.Media.RadialGradientBrush> esempi, vedere l' [esempio pennelli](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes). Per ulteriori informazioni sui gradienti e sugli altri tipi di pennelli, vedere [Cenni preliminari sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md).
