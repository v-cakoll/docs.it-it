---
title: "Procedura: creare una modalità di visualizzazione personalizzata per un oggetto ListView"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], creating custom View mode
ms.assetid: 71077349-eeb9-4344-ab29-b5df96df3314
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e67777b5568214dff889088708db166efc6ae4dd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-custom-view-mode-for-a-listview"></a>Procedura: creare una modalità di visualizzazione personalizzata per un oggetto ListView
In questo esempio viene illustrato come creare un oggetto personalizzato <xref:System.Windows.Controls.ListView.View%2A> modalità per un <xref:System.Windows.Controls.ListView> controllo.  
  
## <a name="example"></a>Esempio  
 È necessario utilizzare il <xref:System.Windows.Controls.ViewBase> classe quando si crea una visualizzazione personalizzata per il <xref:System.Windows.Controls.ListView> controllo. Nell'esempio seguente viene mostrata una modalità di visualizzazione che viene chiamata `PlainView`, che deriva dalla <xref:System.Windows.Controls.ViewBase> classe.  
  
 [!code-csharp[ListViewCustomView#PlainView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/PlainView.cs#plainview)]
 [!code-vb[ListViewCustomView#PlainView](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/plainview.vb#plainview)]  
  
 Per applicare uno stile per la visualizzazione personalizzata, utilizzare la <xref:System.Windows.Style> classe. L'esempio seguente definisce un <xref:System.Windows.Style> per il `PlainView` modalità di visualizzazione. Nell'esempio precedente, questo stile è impostato come valore della <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> proprietà definita per `PlainView`.  
  
 [!code-xaml[ListViewCustomView#PlainViewStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Themes/Generic.xaml#plainviewstyle)]  
  
 Per definire il layout dei dati in una modalità di visualizzazione personalizzato, definire un <xref:System.Windows.DataTemplate> oggetto. L'esempio seguente definisce un <xref:System.Windows.DataTemplate> che può essere utilizzato per visualizzare i dati nella `PlainView` modalità di visualizzazione.  
  
 [!code-xaml[ListViewCustomView#PlainViewDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewdatatemplate)]  
  
 Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.ResourceKey> per il `PlainView` modalità di visualizzazione che utilizza il <xref:System.Windows.DataTemplate> definito nell'esempio precedente.  
  
 [!code-xaml[ListViewCustomView#PlainViewtileView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewtileview)]  
  
 Oggetto <xref:System.Windows.Controls.ListView> controllo può utilizzare una visualizzazione personalizzata se si imposta la <xref:System.Windows.Controls.ListView.View%2A> proprietà chiave di risorsa. Nell'esempio seguente viene illustrato come specificare `PlainView` come modalità di visualizzazione per un <xref:System.Windows.Controls.ListView>.  
  
 [!code-csharp[ListViewCustomView#ListViewtileViewmode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml.cs#listviewtileviewmode)]
 [!code-vb[ListViewCustomView#ListViewtileViewmode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/window1.xaml.vb#listviewtileviewmode)]  
  
 Per l'esempio completo, vedere [ListView con più visualizzazioni](http://go.microsoft.com/fwlink/?LinkID=160013).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [Panoramica sul controllo ListView](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [Cenni preliminari su GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)
