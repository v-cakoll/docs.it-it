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
ms.openlocfilehash: a3b5805808ce2e84e7713f07694464b75d83a391
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43424262"
---
# <a name="listview-overview"></a>Panoramica sul controllo ListView
Il <xref:System.Windows.Controls.ListView> controllo fornisce l'infrastruttura per visualizzare un set di elementi di dati nel layout o visualizzazioni diverse. Ad esempio, un utente può scegliere di visualizzare gli elementi dei dati in una tabella e anche di ordinarne le colonne.  
  
  
<a name="WhatisaListView"></a>   
## <a name="what-is-a-listview"></a>Definizione del controllo ListView  
 Il <xref:System.Windows.Controls.ListView> controllo è un <xref:System.Windows.Controls.ItemsControl> che deriva da <xref:System.Windows.Controls.ListBox>. In genere, i relativi elementi sono membri di una raccolta di dati e sono rappresentati come <xref:System.Windows.Controls.ListViewItem> oggetti. Oggetto <xref:System.Windows.Controls.ListViewItem> è un <xref:System.Windows.Controls.ContentControl> e può contenere solo un singolo elemento figlio. Tale elemento figlio può tuttavia essere qualsiasi elemento visivo.  
  
<a name="DefiningaListViewView"></a>   
## <a name="defining-a-view-mode-for-a-listview"></a>Definizione di una modalità di visualizzazione per un controllo ListView  
 Per specificare una modalità di visualizzazione per il contenuto di un <xref:System.Windows.Controls.ListView> , si imposta il <xref:System.Windows.Controls.ListView.View%2A> proprietà. Una modalità di visualizzazione che [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce è <xref:System.Windows.Controls.GridView>, che consente di visualizzare una raccolta di elementi di dati in una tabella con colonne personalizzabili.  
  
 Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.GridView> per un <xref:System.Windows.Controls.ListView> controllo che visualizza informazioni sui dipendenti.  
  
 [!code-xaml[ListViewCode#ListViewEmployee](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 La figura seguente illustra come vengono visualizzati i dati per l'esempio precedente.  
  
 ![ListView con output GridView ](../../../../docs/framework/wpf/controls/media/listviewgridview.JPG "ListViewGridView")  
  
 È possibile creare una modalità di visualizzazione personalizzata definendo una classe che eredita dal <xref:System.Windows.Controls.ViewBase> classe. Il <xref:System.Windows.Controls.ViewBase> classe fornisce l'infrastruttura che è necessario creare una visualizzazione personalizzata. Per altre informazioni su come creare una visualizzazione personalizzata, vedere [Creare una modalità di visualizzazione personalizzata per un controllo ListView](../../../../docs/framework/wpf/controls/how-to-create-a-custom-view-mode-for-a-listview.md).  
  
<a name="BindingDatatoaListView"></a>   
## <a name="binding-data-to-a-listview"></a>Associazione di dati a un controllo ListView  
 Usare la <xref:System.Windows.Controls.ItemsControl.Items%2A> e <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> delle proprietà per specificare gli elementi per un <xref:System.Windows.Controls.ListView> controllo. L'esempio seguente imposta la <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> proprietà in una raccolta di dati che viene chiamata `EmployeeInfoDataSource`.  
  
 [!code-xaml[ListViewCode#ItemsSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#itemssource)]  
  
 In un <xref:System.Windows.Controls.GridView>, <xref:System.Windows.Controls.GridViewColumn> oggetti associati ai campi dati specificati. L'esempio seguente associa un <xref:System.Windows.Controls.GridViewColumn> oggetto a un campo dati specificando una <xref:System.Windows.Data.Binding> per il <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> proprietà.  
  
 [!code-csharp[ListViewCode#GridViewColumnProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml.cs#gridviewcolumnproperties)]
 [!code-vb[ListViewCode#GridViewColumnProperties](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCode/visualbasic/window1.xaml.vb#gridviewcolumnproperties)]
 [!code-xaml[ListViewCode#GridViewColumnProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#gridviewcolumnproperties)]  
  
 È inoltre possibile specificare una <xref:System.Windows.Data.Binding> come parte di un <xref:System.Windows.DataTemplate> definizione che usa uno stile alle celle in una colonna. Nell'esempio seguente, il <xref:System.Windows.DataTemplate> che viene identificato con un <xref:System.Windows.ResourceKey> imposta la <xref:System.Windows.Data.Binding> per un <xref:System.Windows.Controls.GridViewColumn>. Si noti che questo esempio non definisce il <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> perché altrimenti verrebbe override quindi, l'associazione specificata dal <xref:System.Windows.DataTemplate>.  
  
 [!code-xaml[ListViewTemplate#GridViewCellTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 [!code-xaml[ListViewTemplate#CellTemplateProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
<a name="StylingaListView"></a>   
## <a name="styling-a-listview-that-implements-a-gridview"></a>Applicazione di uno stile a un controllo ListView che implementa un oggetto GridView  
 Il <xref:System.Windows.Controls.ListView> controllo contiene <xref:System.Windows.Controls.ListViewItem> gli oggetti che rappresentano gli elementi di dati che vengono visualizzati. È possibile usare le proprietà seguenti per definire il contenuto e lo stile degli elementi di dati:  
  
-   Nel <xref:System.Windows.Controls.ListView> controllo, utilizzare il <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>, <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>, e <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> proprietà.  
  
-   Nel <xref:System.Windows.Controls.ListViewItem> controllo, utilizzare il <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> e <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A> proprietà.  
  
 Per evitare problemi di allineamento tra le celle in una <xref:System.Windows.Controls.GridView>, non usare il <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> per impostare le proprietà o aggiungere contenuto che influisca sulla larghezza di un elemento in un <xref:System.Windows.Controls.ListView>. Ad esempio, può verificarsi un problema di allineamento quando si impostano i <xref:System.Windows.FrameworkElement.Margin%2A> proprietà nel <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>. Per specificare le proprietà o definire contenuto che influisca sulla larghezza degli elementi in un <xref:System.Windows.Controls.GridView>, usare le proprietà della <xref:System.Windows.Controls.GridView> classe e le classi correlate, ad esempio <xref:System.Windows.Controls.GridViewColumn>.  
  
 Per altre informazioni su come usare <xref:System.Windows.Controls.GridView> e le relative classi di supporti, vedere [Cenni preliminari su GridView](../../../../docs/framework/wpf/controls/gridview-overview.md).  
  
 Se si definisce un <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> per un <xref:System.Windows.Controls.ListView> controllate e definite anche un' <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>, è necessario includere una <xref:System.Windows.Controls.ContentPresenter> nello stile affinché il <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> funzioni correttamente.  
  
 Non usare la <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> e <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> delle proprietà per <xref:System.Windows.Controls.ListView> contenuto visualizzato tramite un <xref:System.Windows.Controls.GridView>. Per specificare l'allineamento del contenuto in una colonna di una <xref:System.Windows.Controls.GridView>, definire un <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>.  
  
<a name="UsingtheSameViewMoreThanOnce"></a>   
## <a name="sharing-the-same-view-mode"></a>Condivisione della stessa modalità di visualizzazione  
 Due <xref:System.Windows.Controls.ListView> controlli non possono condividere la stessa modalità di visualizzazione nello stesso momento. Se si prova a usare la stessa modalità di visualizzazione con più di uno <xref:System.Windows.Controls.ListView> controllare, viene generata un'eccezione.  
  
 Per specificare una modalità di visualizzazione che può essere usata contemporaneamente da più di un <xref:System.Windows.Controls.ListView>, usare i modelli o stili. Per un esempio di come definire le visualizzazioni come <xref:System.Windows.FrameworkElement.Resources%2A>, vedere [ListView con più visualizzazioni](https://go.microsoft.com/fwlink/?LinkID=160013).  
  
<a name="CreatingaCustomView"></a>   
## <a name="creating-a-custom-view-mode"></a>Creazione di una modalità di visualizzazione personalizzata  
 Le visualizzazioni personalizzate come <xref:System.Windows.Controls.GridView> derivano dal <xref:System.Windows.Controls.ViewBase> classe, che fornisce gli strumenti per visualizzare gli elementi di dati che sono rappresentati come astratta <xref:System.Windows.Controls.ListViewItem> oggetti.  
  
 Per un esempio di una modalità di visualizzazione personalizzata, vedere [Esempio di ListView con visualizzazioni multiple](https://go.microsoft.com/fwlink/?LinkID=160013).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.GridView>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.ListViewItem>  
 <xref:System.Windows.Data.Binding>  
 [Cenni preliminari su GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [Controlli](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)
