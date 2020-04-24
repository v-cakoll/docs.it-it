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
ms.openlocfilehash: 3b222880aa4eda32502e3dcece2fa5c0b57b7a51
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646430"
---
# <a name="how-to-find-datatemplate-generated-elements"></a>Procedura: trovare elementi generati da un oggetto DataTemplate
In questo esempio viene illustrato come <xref:System.Windows.DataTemplate>trovare gli elementi generati da un oggetto .  
  
## <a name="example"></a>Esempio  
 In questo esempio, <xref:System.Windows.Controls.ListBox> è presente un che è associato ad alcuni dati XML:In this example, there is a that is bound to some XML data:  
  
 [!code-xaml[FindGeneratedItems#LB](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#lb)]  
  
 Gli <xref:System.Windows.Controls.ListBox> utilizzi <xref:System.Windows.DataTemplate>sono i seguenti:  
  
 [!code-xaml[FindGeneratedItems#DT](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#dt)]  
  
 Se si desidera <xref:System.Windows.Controls.TextBlock> recuperare l'elemento generato <xref:System.Windows.DataTemplate> da di un determinato <xref:System.Windows.Controls.ListBoxItem>, è necessario ottenere il <xref:System.Windows.Controls.ListBoxItem>, trovare l'interno <xref:System.Windows.Controls.ContentPresenter> <xref:System.Windows.Controls.ListBoxItem>di tale , quindi chiamare <xref:System.Windows.FrameworkTemplate.FindName%2A> il <xref:System.Windows.DataTemplate> che è impostato su quello . <xref:System.Windows.Controls.ContentPresenter> Nell'esempio seguente viene illustrato come eseguire questi passaggi. A scopo dimostrativo, in questo esempio viene creata <xref:System.Windows.DataTemplate>una finestra di messaggio che mostra il contenuto di testo del blocco di testo generato.  
  
 [!code-csharp[FindGeneratedItems#DTFindElement](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#dtfindelement)]
 [!code-vb[FindGeneratedItems#DTFindElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#dtfindelement)]  
  
 Di seguito è `FindVisualChild`riportata l'implementazione di , che utilizza i <xref:System.Windows.Media.VisualTreeHelper> metodi :  
  
 [!code-csharp[FindGeneratedItems#FVC](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#fvc)]
 [!code-vb[FindGeneratedItems#FVC](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#fvc)]  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: trovare elementi generati da un oggetto ControlTemplate](../controls/how-to-find-controltemplate-generated-elements.md)
- [Cenni preliminari sull'associazione dati](../../../desktop-wpf/data/data-binding-overview.md)
- [Procedure](data-binding-how-to-topics.md)
- [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Ambiti dei nomi XAML WPF](../advanced/wpf-xaml-namescopes.md)
- [Strutture ad albero in WPF](../advanced/trees-in-wpf.md)
