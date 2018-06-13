---
title: 'Procedura: capovolgere un oggetto UIElement orizzontalmente o verticalmente'
ms.date: 03/30/2017
helpviewer_keywords:
- flipping UIElements [WPF]
- UIElements [WPF], flipping
ms.assetid: 02c6730f-65c0-40d5-a553-4cb663721882
ms.openlocfilehash: 89dcf668f1fe361480dabdab227a35ea40c344a4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544395"
---
# <a name="how-to-flip-a-uielement-horizontally-or-vertically"></a>Procedura: capovolgere un oggetto UIElement orizzontalmente o verticalmente
In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Media.ScaleTransform> scorrere un <xref:System.Windows.UIElement> orizzontalmente o verticalmente. In questo esempio, un <xref:System.Windows.Controls.Button> controllo (un tipo di <xref:System.Windows.UIElement>) viene capovolta applicando un <xref:System.Windows.Media.ScaleTransform> al relativo <xref:System.Windows.UIElement.RenderTransform%2A> proprietà.  
  
## <a name="example"></a>Esempio  
 Nella figura seguente viene illustrato il pulsante da capovolgere.  
  
 ![Un pulsante senza trasformazioni](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipbeforeflip.gif "graphicsmm_buttonflipbeforeflip")  
UIElement da capovolgere  
  
 Di seguito viene illustrato il codice che crea il pulsante.  
  
 [!code-xaml[Transforms_snip#GraphicsMMButtonWithoutFlip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmbuttonwithoutflip)]  
  
## <a name="example"></a>Esempio  
 Per invertire il pulsante orizzontalmente, creare un <xref:System.Windows.Media.ScaleTransform> e impostare il relativo <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> proprietà su -1. Applicare il <xref:System.Windows.Media.ScaleTransform> al pulsante <xref:System.Windows.UIElement.RenderTransform%2A> proprietà.  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample1)]  
  
 ![Pulsante capovolto orizzontalmente &#40;0,0&#41;](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-displaced.gif "graphicsmm_buttonfliphorizontalflip_displaced")  
Pulsante dopo l'applicazione di ScaleTransform  
  
## <a name="example"></a>Esempio  
 Come si vede nella figura precedente, il pulsante è stato capovolta, ma anche spostato. Ciò avviene perché il pulsante è stato capovolto dall'angolo superiore sinistro. Per invertire il pulsante sul posto, si desidera applicare il <xref:System.Windows.Media.ScaleTransform> al centro, non all'angolo. Un modo semplice per applicare il <xref:System.Windows.Media.ScaleTransform> ai pulsanti center consiste nell'impostare il pulsante <xref:System.Windows.UIElement.RenderTransformOrigin%2A> proprietà su 0,5, 0,5.  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample2)]  
  
 ![Pulsante capovolto orizzontalmente rispetto al proprio centro](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-inplace.gif "graphicsmm_buttonfliphorizontalflip_inplace")  
Il pulsante con RenderTransformOrigin pari a 0,5, 0,5  
  
## <a name="example"></a>Esempio  
 Per capovolgere verticalmente il pulsante, impostare il <xref:System.Windows.Media.ScaleTransform> dell'oggetto <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> proprietà invece della relativa <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> proprietà.  
  
 [!code-xaml[Transforms_snip#GraphicsMMVerticalFlipButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmverticalflipbuttonexample2)]  
  
 ![Pulsante capovolto verticalmente rispetto al proprio centro](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipverticalflip-inplace.gif "graphicsmm_buttonflipverticalflip_inplace")  
Pulsante capovolto verticalmente  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sulle trasformazioni](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
