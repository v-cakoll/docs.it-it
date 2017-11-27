---
title: 'Procedura: ottenere l''offset di un oggetto Visual'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting offset values from visual objects [WPF]
- offset values [WPF], retrieving from visual objects [WPF]
- visual objects [WPF], retrieving offset values from
- retrieving offset values from visual objects [WPF]
ms.assetid: 889a1dd6-1b11-445a-b351-fbb04c53ee34
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 22c35a683f479660a17f11e44f9a0721f9d35968
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-get-the-offset-of-a-visual"></a>Procedura: ottenere l'offset di un oggetto Visual
Questi esempi mostrano come recuperare il valore di offset di un oggetto visivo è relativo padre, qualsiasi predecessore o discendente.  
  
## <a name="example"></a>Esempio  
 Il markup seguente viene mostrato un <xref:System.Windows.Controls.TextBlock> definito con <xref:System.Windows.FrameworkElement.Margin%2A> valore 4.  
  
 [!code-xaml[VisualSnippets#VisualSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml#visualsnippet1)]  
  
 Esempio di codice seguente viene illustrato come utilizzare il <xref:System.Windows.Media.VisualTreeHelper.GetOffset%2A> metodo per recuperare l'offset del <xref:System.Windows.Controls.TextBlock>. Sono contenuti i valori di offset all'interno di restituito <xref:System.Windows.Vector> valore.  
  
 [!code-csharp[VisualSnippets#VisualSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet2)]
 [!code-vb[VisualSnippets#VisualSnippet2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet2)]  
  
 L'offset prende in considerazione il <xref:System.Windows.FrameworkElement.Margin%2A> valore. In questo caso, <xref:System.Windows.Vector.X%2A> è 4, e <xref:System.Windows.Vector.Y%2A> è 4.  
  
 Il valore di offset restituito è relativo elemento padre del <xref:System.Windows.Media.Visual>. Se si desidera restituire un valore di offset non specificato fa riferimento l'elemento padre di un <xref:System.Windows.Media.Visual>, utilizzare il <xref:System.Windows.Media.Visual.TransformToAncestor%2A> metodo.  
  
## <a name="getting-the-offset-relative-to-an-ancestor"></a>Acquisizione dell'Offset relativo a un predecessore  
 Il markup seguente viene mostrato un <xref:System.Windows.Controls.TextBlock> annidato all'interno di due <xref:System.Windows.Controls.StackPanel> oggetti.  
  
 [!code-xaml[VisualSnippets#VisualSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window2.xaml#visualsnippet7)]  
  
 Nella figura seguente mostra i risultati del markup.  
  
 ![Valori di offset degli oggetti](../../../../docs/framework/wpf/graphics-multimedia/media/visualoffset-01.png "VisualOffset_01")  
TextBlock annidato all'interno di due StackPanel  
  
 Esempio di codice seguente viene illustrato come utilizzare il <xref:System.Windows.Media.Visual.TransformToAncestor%2A> metodo per recuperare l'offset del <xref:System.Windows.Controls.TextBlock> relativo contenitore <xref:System.Windows.Window>. Sono contenuti i valori di offset all'interno di restituito <xref:System.Windows.Media.GeneralTransform> valore.  
  
 [!code-csharp[VisualSnippets#VisualSnippet5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet5)]
 [!code-vb[VisualSnippets#VisualSnippet5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet5)]  
  
 L'offset prende in considerazione il <xref:System.Windows.FrameworkElement.Margin%2A> i valori per tutti gli oggetti nel contenitore <xref:System.Windows.Window>. In questo caso, <xref:System.Windows.Vector.X%2A> è 28 (16 + 8 + 4), e <xref:System.Windows.Vector.Y%2A> è 28.  
  
 Il valore di offset restituito è relativo il predecessore di <xref:System.Windows.Media.Visual>. Se si desidera restituire un valore di offset è relativo al discendente di un <xref:System.Windows.Media.Visual>, utilizzare il <xref:System.Windows.Media.Visual.TransformToDescendant%2A> metodo.  
  
## <a name="getting-the-offset-relative-to-a-descendant"></a>Acquisizione dell'Offset relativo a un discendente  
 Il markup seguente viene mostrato un <xref:System.Windows.Controls.TextBlock> contenuta all'interno di un <xref:System.Windows.Controls.StackPanel> oggetto.  
  
 [!code-xaml[VisualSnippets#VisualSnippet4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml#visualsnippet4)]  
  
 Esempio di codice seguente viene illustrato come utilizzare il <xref:System.Windows.Media.Visual.TransformToDescendant%2A> metodo per recuperare l'offset del <xref:System.Windows.Controls.StackPanel> rispetto al relativo elemento figlio <xref:System.Windows.Controls.TextBlock>. Sono contenuti i valori di offset all'interno di restituito <xref:System.Windows.Media.GeneralTransform> valore.  
  
 [!code-csharp[VisualSnippets#VisualSnippet9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet9)]
 [!code-vb[VisualSnippets#VisualSnippet9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet9)]  
  
 L'offset prende in considerazione il <xref:System.Windows.FrameworkElement.Margin%2A> i valori per tutti gli oggetti. In questo caso, <xref:System.Windows.Vector.X%2A> è -4 e <xref:System.Windows.Vector.Y%2A> è -4. I valori di offset sono valori negativi, poiché l'oggetto padre viene spostato negativamente rispetto all'oggetto figlio.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.Visual>  
 <xref:System.Windows.Media.VisualTreeHelper>  
 [Cenni preliminari sul rendering della grafica WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)
