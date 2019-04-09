---
title: 'Procedura: Capovolgere un oggetto UIElement orizzontalmente o verticalmente'
ms.date: 03/30/2017
helpviewer_keywords:
- flipping UIElements [WPF]
- UIElements [WPF], flipping
ms.assetid: 02c6730f-65c0-40d5-a553-4cb663721882
ms.openlocfilehash: 6b3da322493d17e4f8e36a35b9a0e40fdc9dc685
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59215521"
---
# <a name="how-to-flip-a-uielement-horizontally-or-vertically"></a>Procedura: Capovolgere un oggetto UIElement orizzontalmente o verticalmente
In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Media.ScaleTransform> capovolgere un <xref:System.Windows.UIElement> orizzontalmente o verticalmente. In questo esempio, un <xref:System.Windows.Controls.Button> controllo (un tipo di <xref:System.Windows.UIElement>) viene capovolto applicando una <xref:System.Windows.Media.ScaleTransform> al relativo <xref:System.Windows.UIElement.RenderTransform%2A> proprietà.  
  
## <a name="example"></a>Esempio  
 La figura seguente mostra il pulsante per capovolgere.  
  
 ![Un pulsante senza trasformazioni](./media/graphicsmm-buttonflipbeforeflip.gif "graphicsmm_buttonflipbeforeflip")  
UIElement da capovolgere  
  
 Di seguito viene illustrato il codice che crea il pulsante.  
  
 [!code-xaml[Transforms_snip#GraphicsMMButtonWithoutFlip](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmbuttonwithoutflip)]  
  
## <a name="example"></a>Esempio  
 Per capovolgere orizzontalmente il pulsante, creare un <xref:System.Windows.Media.ScaleTransform> e impostare il <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> proprietà su -1. Si applicano i <xref:System.Windows.Media.ScaleTransform> del pulsante <xref:System.Windows.UIElement.RenderTransform%2A> proprietà.  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample1)]  
  
 ![Pulsante capovolto orizzontalmente &#40;0,0&#41;](./media/graphicsmm-buttonfliphorizontalflip-displaced.gif "graphicsmm_buttonfliphorizontalflip_displaced")  
Il pulsante dopo l'applicazione ScaleTransform  
  
## <a name="example"></a>Esempio  
 Come può notare dalla figura precedente, il pulsante è stato capovolta, ma è anche stato spostato. Ciò avviene perché il pulsante è stato capovolta dall'angolo superiore sinistro. Per invertire il pulsante posto, si desidera applicare il <xref:System.Windows.Media.ScaleTransform> al relativo centro, non all'angolo. Un modo semplice per applicare la <xref:System.Windows.Media.ScaleTransform> ai pulsanti center consiste nell'impostare il pulsante <xref:System.Windows.UIElement.RenderTransformOrigin%2A> proprietà su 0,5, 0,5.  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample2)]  
  
 ![Pulsante capovolto orizzontalmente rispetto al proprio centro](./media/graphicsmm-buttonfliphorizontalflip-inplace.gif "graphicsmm_buttonfliphorizontalflip_inplace")  
Il pulsante con RenderTransformOrigin del valore pari a 0,5, 0,5  
  
## <a name="example"></a>Esempio  
 Per capovolgere verticalmente il pulsante, impostare il <xref:System.Windows.Media.ScaleTransform> dell'oggetto <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> proprietà invece della relativa <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> proprietà.  
  
 [!code-xaml[Transforms_snip#GraphicsMMVerticalFlipButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmverticalflipbuttonexample2)]  
  
 ![Pulsante capovolto verticalmente rispetto al proprio centro](./media/graphicsmm-buttonflipverticalflip-inplace.gif "graphicsmm_buttonflipverticalflip_inplace")  
Pulsante capovolto verticalmente  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulle trasformazioni](../graphics-multimedia/transforms-overview.md)
