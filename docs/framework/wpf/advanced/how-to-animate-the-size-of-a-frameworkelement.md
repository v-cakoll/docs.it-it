---
title: "Procedura: aggiungere un'animazione alle dimensioni di un oggetto FrameworkElement"
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], FrameworkElement size
- FrameworkElement [WPF], animating size of
ms.assetid: d4cd5a13-c20d-4a6f-a2ba-14f2c9ce4cef
ms.openlocfilehash: 148e3d592e129984bd2f7ac062340c5169e48d30
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543985"
---
# <a name="how-to-animate-the-size-of-a-frameworkelement"></a>Procedura: aggiungere un'animazione alle dimensioni di un oggetto FrameworkElement
Per aggiungere un'animazione le dimensioni di un <xref:System.Windows.FrameworkElement>, è possibile aggiungere un'animazione relativo <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> proprietà o utilizzare un oggetto animato <xref:System.Windows.Media.ScaleTransform>.  
  
 Nell'esempio seguente aggiunge un'animazione le dimensioni dei due pulsanti usando questi due approcci. Un pulsante viene ridimensionato aggiungendo un'animazione relativo <xref:System.Windows.FrameworkElement.Width%2A> proprietà e un altro viene ridimensionato aggiungendo un'animazione un <xref:System.Windows.Media.ScaleTransform> applicato al relativo <xref:System.Windows.UIElement.RenderTransform%2A> proprietà. Ogni pulsante contiene del testo. Inizialmente, il testo viene visualizzato lo stesso in entrambi i pulsanti, ma come vengono ridimensionati i pulsanti, il testo del secondo pulsante diventa distorto.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[transformanimations_snip#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/AnimatingSizeExample.xaml#1)]  
  
 Quando si trasforma un elemento, l'intero elemento e il relativo contenuto viene trasformati. Quando si modificano direttamente le dimensioni di un elemento, come nel caso del primo pulsante, il contenuto dell'elemento non viene ridimensionato, a meno che le dimensioni e posizione dipendono dalle dimensioni del relativo elemento padre.  
  
 Animazione delle dimensioni di un elemento applicando una trasformazione animata alla relativa <xref:System.Windows.UIElement.RenderTransform%2A> proprietà offre prestazioni migliori rispetto all'animazione relativo <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> direttamente, poiché il <xref:System.Windows.UIElement.RenderTransform%2A> proprietà non attiva un passaggio di layout.  
  
 Per ulteriori informazioni su tali proprietà, vedere il [panoramica dell'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md). Per ulteriori informazioni sulle trasformazioni, vedere il [Trasforma Panoramica](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md).
