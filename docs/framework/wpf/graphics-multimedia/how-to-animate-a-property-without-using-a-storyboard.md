---
title: 'Procedura: animare una proprietà senza utilizzare uno storyboard'
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
ms.openlocfilehash: 18f8fb4edf5f71904335180e43dd65bd9910bdef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-animate-a-property-without-using-a-storyboard"></a>Procedura: animare una proprietà senza utilizzare uno storyboard
In questo esempio viene illustrato un modo per applicare un'animazione a una proprietà senza usare un <xref:System.Windows.Media.Animation.Storyboard>.  
  
> [!NOTE]
>  La funzionalità non è disponibile in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Per informazioni sull'animazione di proprietà in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], vedere [animare una proprietà utilizzando uno Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).  
  
 Per applicare un'animazione locale a una proprietà, utilizzare il <xref:System.Windows.UIElement.BeginAnimation%2A> metodo. Questo metodo accetta due parametri: un <xref:System.Windows.DependencyProperty> che specifica la proprietà da animare e l'animazione da applicare a tale proprietà.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come animare il colore di sfondo e di larghezza di un <xref:System.Windows.Controls.Button>.  
  
 [!code-cpp[animateproperty#11](../../../../samples/snippets/cpp/VS_Snippets_Wpf/animateproperty/CPP/LocalAnimationExample.cpp#11)]
 [!code-csharp[animateproperty#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animateproperty/CSharp/LocalAnimationExample.cs#11)]
 [!code-vb[animateproperty#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animateproperty/VisualBasic/LocalAnimationExample.vb#11)]  
  
 Un'ampia gamma di classi di <xref:System.Windows.Media.Animation> esiste spazio dei nomi per l'animazione di diversi tipi di proprietà. Per altre informazioni sulle proprietà di animazione vedere [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md). Per altre informazioni sulle proprietà di dipendenza (il tipo di proprietà che vengono visualizzate in questi esempi) e le relative funzionalità vedere [Cenni preliminari sulle proprietà di dipendenza](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
 Esistono altri modi per aggiungere un'animazione senza utilizzare <xref:System.Windows.Media.Animation.Storyboard> oggetti; per ulteriori informazioni, vedere [Property Animation Techniques Overview](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.Animation.AnimationTimeline>  
 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>  
 <xref:System.Windows.Media.Animation>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 [Cenni preliminari sulle tecniche di animazione delle proprietà](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)  
 [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
