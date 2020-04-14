---
title: 'Procedura: creare una modalità di visualizzazione personalizzata per un oggetto ListView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], creating custom View mode
ms.assetid: 71077349-eeb9-4344-ab29-b5df96df3314
ms.openlocfilehash: 3b9ca17bddcecb1895205fca76f0a489ecf25c4f
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243219"
---
# <a name="how-to-create-a-custom-view-mode-for-a-listview"></a>Procedura: creare una modalità di visualizzazione personalizzata per un controllo ListViewHow to: Create a custom view mode for a ListView

In questo esempio viene <xref:System.Windows.Controls.ListView.View%2A> illustrato come <xref:System.Windows.Controls.ListView> creare una modalità personalizzata per un controllo.  
  
## <a name="example"></a>Esempio  
 È necessario <xref:System.Windows.Controls.ViewBase> utilizzare la classe quando si <xref:System.Windows.Controls.ListView> crea una visualizzazione personalizzata per il controllo. Nell'esempio seguente viene `PlainView` illustrata una modalità di visualizzazione denominata derivata dalla <xref:System.Windows.Controls.ViewBase> classe .  
  
 [!code-csharp[ListViewCustomView#PlainView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/PlainView.cs#plainview)]
 [!code-vb[ListViewCustomView#PlainView](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/plainview.vb#plainview)]  
  
 Per applicare uno stile alla visualizzazione <xref:System.Windows.Style> personalizzata, utilizzare la classe . Nell'esempio seguente <xref:System.Windows.Style> viene `PlainView` definito un per la modalità di visualizzazione. Nell'esempio precedente, questo stile viene impostato <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> come valore della `PlainView`proprietà definita per .  
  
 [!code-xaml[ListViewCustomView#PlainViewStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Themes/Generic.xaml#plainviewstyle)]  
  
 Per definire il layout dei dati in <xref:System.Windows.DataTemplate> una modalità di visualizzazione personalizzata, definire un oggetto. Nell'esempio seguente <xref:System.Windows.DataTemplate> viene definito un oggetto che `PlainView` può essere utilizzato per visualizzare i dati in modalità di visualizzazione.  
  
 [!code-xaml[ListViewCustomView#PlainViewDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewdatatemplate)]  
  
 Nell'esempio seguente viene <xref:System.Windows.ResourceKey> illustrato `PlainView` come definire un <xref:System.Windows.DataTemplate> per la modalità di visualizzazione che utilizza l'oggetto definito nell'esempio precedente.  
  
 [!code-xaml[ListViewCustomView#PlainViewtileView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewtileview)]  
  
 Un <xref:System.Windows.Controls.ListView> controllo può utilizzare una visualizzazione <xref:System.Windows.Controls.ListView.View%2A> personalizzata se si imposta la proprietà sulla chiave di risorsa. Nell'esempio seguente viene `PlainView` illustrato come specificare come modalità di visualizzazione per un <xref:System.Windows.Controls.ListView>oggetto .  
  
 [!code-csharp[ListViewCustomView#ListViewtileViewmode](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml.cs#listviewtileviewmode)]
 [!code-vb[ListViewCustomView#ListViewtileViewmode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/window1.xaml.vb#listviewtileviewmode)]  
  
 Per l'esempio completo, vedere [ListView con più visualizzazioni (c'è)](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp) o [ListView con più visualizzazioni (Visual Basic)](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [Procedure](listview-how-to-topics.md)
- [Panoramica sul controllo ListView](listview-overview.md)
- [Cenni preliminari su GridView](gridview-overview.md)
