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
ms.openlocfilehash: 5762ef1a1526ba6f004917c8a947e35ce731c86d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916095"
---
# <a name="how-to-paint-an-area-with-a-radial-gradient"></a>Procedura: Disegnare un'area con una sfumatura radiale
Questo esempio illustra come usare la <xref:System.Windows.Media.RadialGradientBrush> classe per disegnare un'area con una sfumatura radiale.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato <xref:System.Windows.Media.RadialGradientBrush> un oggetto per disegnare un rettangolo con una sfumatura radiale che passa da giallo a rosso a blu a verde limone.  
  
 [!code-csharp[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/RadialGradientBrushSnippet.cs#simpleradialgradientexamplewholepage)]
 [!code-vb[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/radialgradientbrushsnippet.vb#simpleradialgradientexamplewholepage)]
 [!code-xaml[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/RadialGradientBrushSnippet.xaml#simpleradialgradientexamplewholepage)]  
  
 Nella figura seguente viene illustrata la sfumatura dell'esempio precedente. I cursori della sfumatura sono stati evidenziati.  
  
 ![Cursori sfumatura in una sfumatura radiale](./media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")  
  
> [!NOTE]
> Negli esempi di questo argomento viene utilizzato il sistema di coordinate predefinito per l'impostazione dei punti di controllo. Il sistema di coordinate predefinito è relativo a un rettangolo di delimitazione: 0 indica lo 0% del riquadro e 1 indica il 100% del riquadro. È possibile modificare questo sistema di coordinate impostando <xref:System.Windows.Media.GradientBrush.MappingMode%2A> la proprietà sul valore <xref:System.Windows.Media.BrushMappingMode.Absolute>. Un sistema di coordinate assoluto non è relativo a un rettangolo di selezione. I valori vengono interpretati direttamente nello spazio locale.  
  
 Per altri <xref:System.Windows.Media.RadialGradientBrush> esempi, vedere l' [esempio](https://go.microsoft.com/fwlink/?LinkID=159973)di pennelli. Per ulteriori informazioni sui gradienti e sugli altri tipi di pennelli, vedere [Cenni preliminari sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md).
