---
title: "Procedura: Aggiungere un'animazione alle dimensioni di un oggetto FrameworkElement"
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], FrameworkElement size
- FrameworkElement [WPF], animating size of
ms.assetid: d4cd5a13-c20d-4a6f-a2ba-14f2c9ce4cef
ms.openlocfilehash: d1995deec5ab2c9bf405911af43b4d242d599119
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360992"
---
# <a name="how-to-animate-the-size-of-a-frameworkelement"></a>Procedura: Aggiungere un'animazione alle dimensioni di un oggetto FrameworkElement
Per animare la proprietà size di un <xref:System.Windows.FrameworkElement>, è possibile aggiungere un'animazione relativa <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> delle proprietà o utilizzare un oggetto animato <xref:System.Windows.Media.ScaleTransform>.  
  
 Nell'esempio seguente anima le dimensioni dei due pulsanti utilizzando questi due approcci. Tramite l'animazione viene ridimensionato un pulsante relativi <xref:System.Windows.FrameworkElement.Width%2A> proprietà e un altro ridimensionamento aggiungendo un'animazione una <xref:System.Windows.Media.ScaleTransform> applicati a relativo <xref:System.Windows.UIElement.RenderTransform%2A> proprietà. Ogni pulsante contiene testo. Inizialmente, il testo viene visualizzato lo stesso in entrambi i pulsanti, ma come vengono ridimensionati i pulsanti, il testo del secondo pulsante diventa distorto.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[transformanimations_snip#1](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/AnimatingSizeExample.xaml#1)]  
  
 Quando si trasforma un elemento, l'intero elemento e il relativo contenuto viene trasformate. Quando si modifica direttamente la dimensione di un elemento, come nel caso del primo pulsante, il contenuto dell'elemento non viene ridimensionato, a meno che le dimensioni e posizione dipendono dalle dimensioni del relativo elemento padre.  
  
 Animazione delle dimensioni di un elemento applicando una trasformazione animata in relativi <xref:System.Windows.UIElement.RenderTransform%2A> proprietà offre prestazioni migliori rispetto all'animazione relativi <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> direttamente, poiché il <xref:System.Windows.UIElement.RenderTransform%2A> proprietà non attiva un passaggio di layout.  
  
 Per altre informazioni sulle proprietà di animazione, vedere la [Cenni preliminari sull'animazione](../graphics-multimedia/animation-overview.md). Per altre informazioni sulle trasformazioni, vedere la [Cenni preliminari sulle trasformazioni](../graphics-multimedia/transforms-overview.md).
