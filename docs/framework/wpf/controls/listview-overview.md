---
title: Panoramica sul controllo ListView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ListView
- ListView controls [WPF], about ListView control
ms.assetid: 989e12b0-260e-4570-95c6-489284003ce2
ms.openlocfilehash: 2f336d1eb8dcdfec3c3c8059ba865147c6b6c825
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187512"
---
# <a name="listview-overview"></a>Panoramica sul controllo ListView
Il <xref:System.Windows.Controls.ListView> controllo fornisce l'infrastruttura per visualizzare un set di elementi di dati in diversi layout o visualizzazioni. Ad esempio, un utente può scegliere di visualizzare gli elementi dei dati in una tabella e anche di ordinarne le colonne.  

<a name="WhatisaListView"></a>
## <a name="what-is-a-listview"></a>Definizione del controllo ListView  
 Il <xref:System.Windows.Controls.ListView> controllo <xref:System.Windows.Controls.ItemsControl> è un <xref:System.Windows.Controls.ListBox>oggetto derivato da . In genere, i relativi elementi sono membri <xref:System.Windows.Controls.ListViewItem> di una raccolta di dati e sono rappresentati come oggetti. A <xref:System.Windows.Controls.ListViewItem> è <xref:System.Windows.Controls.ContentControl> un e può contenere un solo elemento figlio. Tale elemento figlio può tuttavia essere qualsiasi elemento visivo.  
  
<a name="DefiningaListViewView"></a>
## <a name="defining-a-view-mode-for-a-listview"></a>Definizione di una modalità di visualizzazione per un controllo ListView  
 Per specificare una modalità <xref:System.Windows.Controls.ListView> di visualizzazione per <xref:System.Windows.Controls.ListView.View%2A> il contenuto di un controllo, impostare la proprietà . Una modalità [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] di <xref:System.Windows.Controls.GridView>visualizzazione fornita è , che visualizza una raccolta di elementi di dati in una tabella con colonne personalizzabili.  
  
 Nell'esempio seguente viene <xref:System.Windows.Controls.GridView> illustrato <xref:System.Windows.Controls.ListView> come definire un per un controllo che visualizza le informazioni sui dipendenti.  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 La figura seguente illustra come vengono visualizzati i dati per l'esempio precedente.  
  
 ![Screenshot che mostra un controllo ListView con output di GridView.Screenshot that shows a ListView with GridView output.](./media/gridview-overview/listview-gridview-output.jpg)  
  
 È possibile creare una modalità di visualizzazione personalizzata definendo una classe che eredita dalla <xref:System.Windows.Controls.ViewBase> classe. La <xref:System.Windows.Controls.ViewBase> classe fornisce l'infrastruttura necessaria per creare una visualizzazione personalizzata. Per altre informazioni su come creare una visualizzazione personalizzata, vedere [Creare una modalità di visualizzazione personalizzata per un controllo ListView](how-to-create-a-custom-view-mode-for-a-listview.md).  
  
<a name="BindingDatatoaListView"></a>
## <a name="binding-data-to-a-listview"></a>Associazione di dati a un controllo ListView  
 Utilizzare <xref:System.Windows.Controls.ItemsControl.Items%2A> le <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> proprietà e per <xref:System.Windows.Controls.ListView> specificare gli elementi per un controllo . Nell'esempio riportato di seguito la proprietà viene impostata su <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> un insieme di dati denominato `EmployeeInfoDataSource`.  
  
 [!code-xaml[ListViewCode#ItemsSource](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#itemssource)]  
  
 In <xref:System.Windows.Controls.GridView>un <xref:System.Windows.Controls.GridViewColumn> oggetto , gli oggetti vengono associati a campi dati specificati. Nell'esempio seguente <xref:System.Windows.Controls.GridViewColumn> viene associato un oggetto a <xref:System.Windows.Data.Binding> un <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> campo dati specificando un per la proprietà.  
  
 [!code-csharp[ListViewCode#GridViewColumnProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml.cs#gridviewcolumnproperties)]
 [!code-vb[ListViewCode#GridViewColumnProperties](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCode/visualbasic/window1.xaml.vb#gridviewcolumnproperties)]
 [!code-xaml[ListViewCode#GridViewColumnProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#gridviewcolumnproperties)]  
  
 È inoltre possibile <xref:System.Windows.Data.Binding> specificare <xref:System.Windows.DataTemplate> un elemento come parte di una definizione utilizzata per definire lo stile delle celle di una colonna. Nell'esempio riportato <xref:System.Windows.DataTemplate> di seguito, <xref:System.Windows.ResourceKey> l'oggetto identificato con un imposta l'oggetto <xref:System.Windows.Data.Binding> for a <xref:System.Windows.Controls.GridViewColumn>. Si noti che in <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> questo esempio non viene definito <xref:System.Windows.DataTemplate>l'oggetto perché questa operazione esegue l'override dell'associazione specificata da .  
  
 [!code-xaml[ListViewTemplate#GridViewCellTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 [!code-xaml[ListViewTemplate#CellTemplateProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
<a name="StylingaListView"></a>
## <a name="styling-a-listview-that-implements-a-gridview"></a>Applicazione di uno stile a un controllo ListView che implementa un oggetto GridView  
 Il <xref:System.Windows.Controls.ListView> controllo <xref:System.Windows.Controls.ListViewItem> contiene oggetti, che rappresentano gli elementi di dati visualizzati. È possibile usare le proprietà seguenti per definire il contenuto e lo stile degli elementi di dati:  
  
- Nel <xref:System.Windows.Controls.ListView> controllo utilizzare <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>le <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>proprietà <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> , e .  
  
- Nel <xref:System.Windows.Controls.ListViewItem> controllo utilizzare <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> le <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A> proprietà e .  
  
 Per evitare problemi di <xref:System.Windows.Controls.GridView>allineamento tra <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> celle in un oggetto , non utilizzare <xref:System.Windows.Controls.ListView>l'oggetto per impostare proprietà o aggiungere contenuto che influisce sulla larghezza di un elemento in un oggetto . Ad esempio, un problema di allineamento può verificarsi quando si imposta la <xref:System.Windows.FrameworkElement.Margin%2A> proprietà nell'oggetto <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>. Per specificare proprietà o definire contenuto che <xref:System.Windows.Controls.GridView>influisce sulla larghezza <xref:System.Windows.Controls.GridView> degli elementi in un <xref:System.Windows.Controls.GridViewColumn>oggetto , utilizzare le proprietà della classe e le classi correlate, ad esempio .  
  
 Per ulteriori informazioni su <xref:System.Windows.Controls.GridView> come utilizzare e le relative classi di supporto, vedere Panoramica di [GridView](gridview-overview.md).  
  
 Se si <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> definisce <xref:System.Windows.Controls.ListView> un oggetto <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>per un controllo <xref:System.Windows.Controls.ContentPresenter> e si definisce <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> anche un oggetto , è necessario includere un oggetto nello stile affinché l'oggetto funzioni correttamente.  
  
 Non utilizzare <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> le <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> proprietà <xref:System.Windows.Controls.ListView> e per il contenuto <xref:System.Windows.Controls.GridView>visualizzato utilizzando un oggetto . Per specificare l'allineamento del <xref:System.Windows.Controls.GridView>contenuto <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>in una colonna di un oggetto , definire un oggetto .  
  
<a name="UsingtheSameViewMoreThanOnce"></a>
## <a name="sharing-the-same-view-mode"></a>Condivisione della stessa modalità di visualizzazione  
 Due <xref:System.Windows.Controls.ListView> controlli non possono condividere la stessa modalità di visualizzazione contemporaneamente. Se si tenta di utilizzare la stessa <xref:System.Windows.Controls.ListView> modalità di visualizzazione con più di un controllo, si verifica un'eccezione.  
  
 Per specificare una modalità di visualizzazione che <xref:System.Windows.Controls.ListView>può essere utilizzata contemporaneamente da più di un oggetto , utilizzare modelli o stili.
  
<a name="CreatingaCustomView"></a>
## <a name="creating-a-custom-view-mode"></a>Creazione di una modalità di visualizzazione personalizzata  
 Le visualizzazioni <xref:System.Windows.Controls.GridView> personalizzate come <xref:System.Windows.Controls.ViewBase> sono derivate dalla classe astratta, che <xref:System.Windows.Controls.ListViewItem> fornisce gli strumenti per visualizzare gli elementi di dati rappresentati come oggetti.
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.GridView>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.ListViewItem>
- <xref:System.Windows.Data.Binding>
- [Cenni preliminari su GridView](gridview-overview.md)
- [Argomenti relativi alle procedure](listview-how-to-topics.md)
- [Controlli](../advanced/optimizing-performance-controls.md)
