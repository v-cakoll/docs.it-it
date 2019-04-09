---
title: "Procedura: Ottenere l'offset di un oggetto visivo"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting offset values from visual objects [WPF]
- offset values [WPF], retrieving from visual objects [WPF]
- visual objects [WPF], retrieving offset values from
- retrieving offset values from visual objects [WPF]
ms.assetid: 889a1dd6-1b11-445a-b351-fbb04c53ee34
ms.openlocfilehash: 4787b771c7e59a8b033b9267079c068a5845a1e6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59093410"
---
# <a name="how-to-get-the-offset-of-a-visual"></a>Procedura: Ottenere l'offset di un oggetto visivo
Questi esempi illustrano come recuperare il valore di offset di un oggetto visivo che è relativo al relativo elemento padre, qualsiasi predecessore o discendente.  
  
## <a name="example"></a>Esempio  
 L'esempio di markup seguente mostra una <xref:System.Windows.Controls.TextBlock> che viene definita con <xref:System.Windows.FrameworkElement.Margin%2A> valore 4.  
  
 [!code-xaml[VisualSnippets#VisualSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml#visualsnippet1)]  
  
 Esempio di codice seguente viene illustrato come utilizzare il <xref:System.Windows.Media.VisualTreeHelper.GetOffset%2A> metodo per recuperare l'offset del <xref:System.Windows.Controls.TextBlock>. Sono contenuti i valori di offset all'interno di restituito <xref:System.Windows.Vector> valore.  
  
 [!code-csharp[VisualSnippets#VisualSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet2)]
 [!code-vb[VisualSnippets#VisualSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet2)]  
  
 L'offset prende in considerazione il <xref:System.Windows.FrameworkElement.Margin%2A> valore. In questo caso <xref:System.Windows.Vector.X%2A> è 4, e <xref:System.Windows.Vector.Y%2A> è 4.  
  
 Il valore di offset restituito è relativamente all'elemento padre del <xref:System.Windows.Media.Visual>. Se si vuole restituire un valore di offset non relativi all'elemento padre di un <xref:System.Windows.Media.Visual>, usare il <xref:System.Windows.Media.Visual.TransformToAncestor%2A> (metodo).  
  
## <a name="getting-the-offset-relative-to-an-ancestor"></a>Ottenere l'Offset relativo a un predecessore  
 L'esempio di markup seguente mostra una <xref:System.Windows.Controls.TextBlock> annidato all'interno di due <xref:System.Windows.Controls.StackPanel> oggetti.  
  
 [!code-xaml[VisualSnippets#VisualSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window2.xaml#visualsnippet7)]  
  
 La figura seguente mostra i risultati del markup.  
  
 ![Valori di offset degli oggetti](./media/visualoffset-01.png "VisualOffset_01")  
TextBlock annidati all'interno di due StackPanel  
  
 Esempio di codice seguente viene illustrato come utilizzare il <xref:System.Windows.Media.Visual.TransformToAncestor%2A> metodo per recuperare l'offset del <xref:System.Windows.Controls.TextBlock> rispetto al contenitore <xref:System.Windows.Window>. Sono contenuti i valori di offset all'interno di restituito <xref:System.Windows.Media.GeneralTransform> valore.  
  
 [!code-csharp[VisualSnippets#VisualSnippet5](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet5)]
 [!code-vb[VisualSnippets#VisualSnippet5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet5)]  
  
 L'offset prende in considerazione la <xref:System.Windows.FrameworkElement.Margin%2A> i valori per tutti gli oggetti nel contenitore <xref:System.Windows.Window>. In questo caso <xref:System.Windows.Vector.X%2A> è 28 (16 + 8 + 4), e <xref:System.Windows.Vector.Y%2A> è 28.  
  
 Il valore di offset restituito è relativo al predecessore del <xref:System.Windows.Media.Visual>. Se si vuole restituire un valore di offset è relativo al discendente di un <xref:System.Windows.Media.Visual>, usare il <xref:System.Windows.Media.Visual.TransformToDescendant%2A> (metodo).  
  
## <a name="getting-the-offset-relative-to-a-descendant"></a>Ottenere l'Offset relativo a un discendente  
 L'esempio di markup seguente mostra una <xref:System.Windows.Controls.TextBlock> contenuta all'interno di un <xref:System.Windows.Controls.StackPanel> oggetto.  
  
 [!code-xaml[VisualSnippets#VisualSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml#visualsnippet4)]  
  
 Esempio di codice seguente viene illustrato come utilizzare il <xref:System.Windows.Media.Visual.TransformToDescendant%2A> metodo per recuperare l'offset del <xref:System.Windows.Controls.StackPanel> rispetto al relativo elemento figlio <xref:System.Windows.Controls.TextBlock>. Sono contenuti i valori di offset all'interno di restituito <xref:System.Windows.Media.GeneralTransform> valore.  
  
 [!code-csharp[VisualSnippets#VisualSnippet9](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet9)]
 [!code-vb[VisualSnippets#VisualSnippet9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet9)]  
  
 L'offset prende in considerazione il <xref:System.Windows.FrameworkElement.Margin%2A> i valori per tutti gli oggetti. In questo caso <xref:System.Windows.Vector.X%2A> è -4, e <xref:System.Windows.Vector.Y%2A> è -4. I valori di offset sono valori negativi, poiché l'oggetto padre viene spostato negativamente rispetto al relativo oggetto figlio.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Visual>
- <xref:System.Windows.Media.VisualTreeHelper>
- [Cenni preliminari sul rendering della grafica WPF](wpf-graphics-rendering-overview.md)
