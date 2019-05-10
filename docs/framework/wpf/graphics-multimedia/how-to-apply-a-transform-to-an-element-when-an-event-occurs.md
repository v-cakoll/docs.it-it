---
title: 'Procedura: Applicare una trasformazione a un elemento quando si verifica un evento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], transformations as event responses
- properties [WPF], LayoutTransform
- transformations as event responses [WPF]
- properties [WPF], RenderTransform
- LayoutTransform property [WPF]
ms.assetid: 71e4327e-ca57-444c-a3cf-09fb381491a0
ms.openlocfilehash: 8f04db274432c0e89c6839bef825976c8a2f853c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64630746"
---
# <a name="how-to-apply-a-transform-to-an-element-when-an-event-occurs"></a>Procedura: Applicare una trasformazione a un elemento quando si verifica un evento
In questo esempio viene illustrato come applicare un <xref:System.Windows.Media.ScaleTransform> quando si verifica un evento. Il concetto illustrato è identico a quello usato per applicare altri tipi di trasformazioni. Per altre informazioni sui tipi di trasformazioni disponibili, vedere la <xref:System.Windows.Media.Transform> classe oppure [Cenni preliminari sulle trasformazioni](transforms-overview.md).  
  
 È possibile applicare una trasformazione a un elemento in uno dei due modi seguenti:  
  
- Se decidi *non* desidera che la trasformazione influisca sul layout, usare il <xref:System.Windows.UIElement.RenderTransform%2A> proprietà dell'elemento.  
  
- Se si desidera la trasformazione influisca sul layout, usare il <xref:System.Windows.FrameworkElement.LayoutTransform%2A> proprietà dell'elemento.  
  
 L'esempio seguente applica un' <xref:System.Windows.Media.ScaleTransform> per il <xref:System.Windows.UIElement.RenderTransform%2A> proprietà di un pulsante. Quando il mouse viene spostato su esso, il <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> e <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> proprietà delle <xref:System.Windows.Media.ScaleTransform> sono impostate su `2`, in modo che il pulsante diventerà più grandi. Quando il mouse viene spostato dal pulsante <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> e <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> sono impostati su `1`, in modo che il pulsante per tornare alle dimensioni originali.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[ButtonTransform#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml#1)]  
  
 [!code-csharp[ButtonTransform#1cb](~/samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml.cs#1cb)]
 [!code-vb[ButtonTransform#1cb](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ButtonTransform/VisualBasic/ButtonTransformExample.xaml.vb#1cb)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.ScaleTransform>
- [Cenni preliminari sulle trasformazioni](transforms-overview.md)
- [Procedure relative alle proprietà](transformations-how-to-topics.md)
- [Cenni preliminari sugli eventi indirizzati](../advanced/routed-events-overview.md)
