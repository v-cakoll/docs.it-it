---
title: 'Procedura: Creare una modalità di visualizzazione personalizzata per un oggetto ListView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], creating custom View mode
ms.assetid: 71077349-eeb9-4344-ab29-b5df96df3314
ms.openlocfilehash: de11250a2e7529fba3b262e42b6714262738fa90
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910910"
---
# <a name="how-to-create-a-custom-view-mode-for-a-listview"></a>Procedura: Creare una modalità di visualizzazione personalizzata per un oggetto ListView
Questo esempio viene illustrato come creare una classe personalizzata <xref:System.Windows.Controls.ListView.View%2A> modalità per un <xref:System.Windows.Controls.ListView> controllo.  
  
## <a name="example"></a>Esempio  
 È necessario usare il <xref:System.Windows.Controls.ViewBase> classe quando si crea una visualizzazione personalizzata per il <xref:System.Windows.Controls.ListView> controllo. L'esempio seguente illustra una modalità di visualizzazione che viene chiamata `PlainView`, che deriva dal <xref:System.Windows.Controls.ViewBase> classe.  
  
 [!code-csharp[ListViewCustomView#PlainView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/PlainView.cs#plainview)]
 [!code-vb[ListViewCustomView#PlainView](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/plainview.vb#plainview)]  
  
 Per applicare uno stile per la visualizzazione personalizzata, usare il <xref:System.Windows.Style> classe. L'esempio seguente definisce una <xref:System.Windows.Style> per il `PlainView` modalità di visualizzazione. Nell'esempio precedente, questo stile è impostato come valore dei <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> proprietà definita per `PlainView`.  
  
 [!code-xaml[ListViewCustomView#PlainViewStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Themes/Generic.xaml#plainviewstyle)]  
  
 Per definire il layout dei dati in una modalità di visualizzazione personalizzata, definire un <xref:System.Windows.DataTemplate> oggetto. L'esempio seguente definisce una <xref:System.Windows.DataTemplate> che può essere utilizzato per visualizzare i dati nel `PlainView` modalità di visualizzazione.  
  
 [!code-xaml[ListViewCustomView#PlainViewDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewdatatemplate)]  
  
 Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.ResourceKey> per il `PlainView` modalità di visualizzazione che utilizza il <xref:System.Windows.DataTemplate> definito nell'esempio precedente.  
  
 [!code-xaml[ListViewCustomView#PlainViewtileView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewtileview)]  
  
 Oggetto <xref:System.Windows.Controls.ListView> controllo può usare una visualizzazione personalizzata se si imposta il <xref:System.Windows.Controls.ListView.View%2A> proprietà chiave di risorsa. Nell'esempio seguente viene illustrato come specificare `PlainView` come modalità di visualizzazione per un <xref:System.Windows.Controls.ListView>.  
  
 [!code-csharp[ListViewCustomView#ListViewtileViewmode](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml.cs#listviewtileviewmode)]
 [!code-vb[ListViewCustomView#ListViewtileViewmode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/window1.xaml.vb#listviewtileviewmode)]  
  
 Per l'esempio completo, vedere [ListView con visualizzazioni Multiple (C#)](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp) oppure [ListView con più Views(Visual Basic)](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [Procedure relative alle proprietà](listview-how-to-topics.md)
- [Panoramica sul controllo ListView](listview-overview.md)
- [Cenni preliminari su GridView](gridview-overview.md)
