---
title: "Procedura: Aggiungere un'animazione a una proprietà senza usare uno storyboard"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- non-Storyboard animation
- local animation [WPF]
- animation [WPF], non-Storyboard (local)
ms.assetid: d411db70-4df7-487d-82bc-95a7c1b2e7f8
ms.openlocfilehash: 93609cdeb4d879cbec0f90096e4fa2c131a2ec5e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59091707"
---
# <a name="how-to-animate-a-property-without-using-a-storyboard"></a>Procedura: Aggiungere un'animazione a una proprietà senza usare uno storyboard
In questo esempio illustra un modo per applicare un'animazione a una proprietà senza utilizzare un <xref:System.Windows.Media.Animation.Storyboard>.  
  
> [!NOTE]
>  La funzionalità non è disponibile in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Per informazioni sull'animazione di proprietà in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], vedere [animare una proprietà utilizzando uno Storyboard](how-to-animate-a-property-by-using-a-storyboard.md).  
  
 Per applicare un'animazione locale a una proprietà, usare il <xref:System.Windows.UIElement.BeginAnimation%2A> (metodo). Questo metodo accetta due parametri: un <xref:System.Windows.DependencyProperty> che specifica la proprietà da animare e l'animazione da applicare a tale proprietà.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente illustra come animare il colore di larghezza e lo sfondo di un <xref:System.Windows.Controls.Button>.  
  
 [!code-cpp[animateproperty#11](~/samples/snippets/cpp/VS_Snippets_Wpf/animateproperty/CPP/LocalAnimationExample.cpp#11)]
 [!code-csharp[animateproperty#11](~/samples/snippets/csharp/VS_Snippets_Wpf/animateproperty/CSharp/LocalAnimationExample.cs#11)]
 [!code-vb[animateproperty#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animateproperty/VisualBasic/LocalAnimationExample.vb#11)]  
  
 Un'ampia gamma di classi di animazione di <xref:System.Windows.Media.Animation> dello spazio dei nomi presente per l'animazione di diversi tipi di proprietà. Per altre informazioni sulle proprietà di animazione vedere [Cenni preliminari sull'animazione](animation-overview.md). Per altre informazioni sulle proprietà di dipendenza (il tipo di proprietà che vengono visualizzate in questi esempi) e le relative funzionalità vedere [Cenni preliminari sulle proprietà di dipendenza](../advanced/dependency-properties-overview.md).  
  
 Esistono altri modi per aggiungere un'animazione senza usare <xref:System.Windows.Media.Animation.Storyboard> oggetti; per altre informazioni, vedere [Cenni preliminari sulle tecniche di animazione di proprietà](property-animation-techniques-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Animation.AnimationTimeline>
- <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>
- <xref:System.Windows.Media.Animation>
- <xref:System.Windows.Media.Animation.Storyboard>
- [Cenni preliminari sulle tecniche di animazione delle proprietà](property-animation-techniques-overview.md)
- [Cenni preliminari sull'animazione](animation-overview.md)
