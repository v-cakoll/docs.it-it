---
title: 'Procedura: Trovare elementi generati da un oggetto DataTemplate'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- finding DataTemplate elements [WPF]
- DataTemplate [WPF]
ms.assetid: bfcd564e-5e9e-451e-8641-a9b5c3cfac90
ms.openlocfilehash: 4317d22a786caa6a191002ff411fe54436f3dbcc
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57362214"
---
# <a name="how-to-find-datatemplate-generated-elements"></a>Procedura: Trovare elementi generati da un oggetto DataTemplate
Questo esempio illustra come trovare gli elementi che vengono generati da un <xref:System.Windows.DataTemplate>.  
  
## <a name="example"></a>Esempio  
 In questo esempio, è presente una <xref:System.Windows.Controls.ListBox> che è associato ad alcune [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] dati:  
  
 [!code-xaml[FindGeneratedItems#LB](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#lb)]  
  
 Il <xref:System.Windows.Controls.ListBox> utilizza il seguente <xref:System.Windows.DataTemplate>:  
  
 [!code-xaml[FindGeneratedItems#DT](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#dt)]  
  
 Se si desidera recuperare il <xref:System.Windows.Controls.TextBlock> generato dall'elemento il <xref:System.Windows.DataTemplate> di un determinato <xref:System.Windows.Controls.ListBoxItem>, è necessario ottenere il <xref:System.Windows.Controls.ListBoxItem>, trovare il <xref:System.Windows.Controls.ContentPresenter> all'interno che <xref:System.Windows.Controls.ListBoxItem>e quindi chiamare <xref:System.Windows.FrameworkTemplate.FindName%2A> nel <xref:System.Windows.DataTemplate> che è impostato su esso <xref:System.Windows.Controls.ContentPresenter>. Nell'esempio seguente viene illustrato come eseguire questa procedura. A scopo dimostrativo, in questo esempio crea una finestra di messaggio che viene visualizzato il testo del contenuto del <xref:System.Windows.DataTemplate>-blocco di testo generato.  
  
 [!code-csharp[FindGeneratedItems#DTFindElement](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#dtfindelement)]
 [!code-vb[FindGeneratedItems#DTFindElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#dtfindelement)]  
  
 Di seguito è l'implementazione di `FindVisualChild`, che usa il <xref:System.Windows.Media.VisualTreeHelper> metodi:  
  
 [!code-csharp[FindGeneratedItems#FVC](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#fvc)]
 [!code-vb[FindGeneratedItems#FVC](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#fvc)]  
  
## <a name="see-also"></a>Vedere anche
- [Procedura: Trovare elementi generati da un oggetto ControlTemplate](../controls/how-to-find-controltemplate-generated-elements.md)
- [Panoramica sul data binding](data-binding-overview.md)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
- [Applicazione di stili e modelli](../controls/styling-and-templating.md)
- [Ambiti dei nomi XAML WPF](../advanced/wpf-xaml-namescopes.md)
- [Strutture ad albero in WPF](../advanced/trees-in-wpf.md)
