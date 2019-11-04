---
title: 'Procedura: trovare elementi generati da un oggetto DataTemplate'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- finding DataTemplate elements [WPF]
- DataTemplate [WPF]
ms.assetid: bfcd564e-5e9e-451e-8641-a9b5c3cfac90
ms.openlocfilehash: f9265e3f7b287e1e8c264e89325f7c9649eebe2c
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459141"
---
# <a name="how-to-find-datatemplate-generated-elements"></a>Procedura: trovare elementi generati da un oggetto DataTemplate
Questo esempio illustra come trovare elementi generati da un <xref:System.Windows.DataTemplate>.  
  
## <a name="example"></a>Esempio  
 In questo esempio è presente un <xref:System.Windows.Controls.ListBox> associato ad alcuni dati [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]:  
  
 [!code-xaml[FindGeneratedItems#LB](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#lb)]  
  
 Il <xref:System.Windows.Controls.ListBox> usa i <xref:System.Windows.DataTemplate>seguenti:  
  
 [!code-xaml[FindGeneratedItems#DT](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#dt)]  
  
 Se si desidera recuperare l'elemento <xref:System.Windows.Controls.TextBlock> generato dall'<xref:System.Windows.DataTemplate> di un determinato <xref:System.Windows.Controls.ListBoxItem>, è necessario ottenere il <xref:System.Windows.Controls.ListBoxItem>, trovare il <xref:System.Windows.Controls.ContentPresenter> all'interno di tale <xref:System.Windows.Controls.ListBoxItem>e quindi chiamare <xref:System.Windows.FrameworkTemplate.FindName%2A> nell'<xref:System.Windows.DataTemplate> impostata su Questo <xref:System.Windows.Controls.ContentPresenter>. Nell'esempio seguente viene illustrato come eseguire questi passaggi. A scopo dimostrativo, in questo esempio viene creata una finestra di messaggio che mostra il contenuto di testo del blocco di testo generato dal <xref:System.Windows.DataTemplate>.  
  
 [!code-csharp[FindGeneratedItems#DTFindElement](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#dtfindelement)]
 [!code-vb[FindGeneratedItems#DTFindElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#dtfindelement)]  
  
 Di seguito è riportata l'implementazione di `FindVisualChild`, che usa i metodi di <xref:System.Windows.Media.VisualTreeHelper>:  
  
 [!code-csharp[FindGeneratedItems#FVC](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#fvc)]
 [!code-vb[FindGeneratedItems#FVC](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#fvc)]  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: trovare elementi generati da un oggetto ControlTemplate](../controls/how-to-find-controltemplate-generated-elements.md)
- [Panoramica sul data binding](data-binding-overview.md)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
- [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Ambiti dei nomi XAML WPF](../advanced/wpf-xaml-namescopes.md)
- [Strutture ad albero in WPF](../advanced/trees-in-wpf.md)
