---
title: Panoramica sul controllo ListView
description: Informazioni sul controllo Windows Presentation Foundation ListView, che fornisce l'infrastruttura per visualizzare gli elementi di dati in diversi layout o visualizzazioni.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ListView
- ListView controls [WPF], about ListView control
ms.assetid: 989e12b0-260e-4570-95c6-489284003ce2
ms.openlocfilehash: 419c6216f0af696ec71e7607c79c2db637caa785
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164564"
---
# <a name="listview-overview"></a>Panoramica sul controllo ListView
Il <xref:System.Windows.Controls.ListView> controllo fornisce l'infrastruttura per visualizzare un set di elementi di dati in layout o visualizzazioni differenti. Ad esempio, un utente può scegliere di visualizzare gli elementi dei dati in una tabella e anche di ordinarne le colonne.  

<a name="WhatisaListView"></a>
## <a name="what-is-a-listview"></a>Definizione del controllo ListView  
 Il <xref:System.Windows.Controls.ListView> controllo è un oggetto <xref:System.Windows.Controls.ItemsControl> derivato da <xref:System.Windows.Controls.ListBox> . In genere, i relativi elementi sono membri di una raccolta di dati e sono rappresentati come <xref:System.Windows.Controls.ListViewItem> oggetti. Un oggetto <xref:System.Windows.Controls.ListViewItem> è un oggetto <xref:System.Windows.Controls.ContentControl> e può contenere solo un singolo elemento figlio. Tale elemento figlio può tuttavia essere qualsiasi elemento visivo.  
  
<a name="DefiningaListViewView"></a>
## <a name="defining-a-view-mode-for-a-listview"></a>Definizione di una modalità di visualizzazione per un controllo ListView  
 Per specificare una modalità di visualizzazione per il contenuto di un <xref:System.Windows.Controls.ListView> controllo, impostare la <xref:System.Windows.Controls.ListView.View%2A> Proprietà. Una modalità di visualizzazione [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornita da è <xref:System.Windows.Controls.GridView> , che consente di visualizzare una raccolta di elementi di dati in una tabella con colonne personalizzabili.  
  
 Nell'esempio seguente viene illustrato come definire un oggetto <xref:System.Windows.Controls.GridView> per un <xref:System.Windows.Controls.ListView> controllo che visualizza informazioni sui dipendenti.  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 La figura seguente illustra come vengono visualizzati i dati per l'esempio precedente.  
  
 ![Screenshot che mostra un ListView con l'output di GridView.](./media/gridview-overview/listview-gridview-output.jpg)  
  
 È possibile creare una modalità di visualizzazione personalizzata definendo una classe che eredita dalla <xref:System.Windows.Controls.ViewBase> classe. La <xref:System.Windows.Controls.ViewBase> classe fornisce l'infrastruttura necessaria per creare una visualizzazione personalizzata. Per altre informazioni su come creare una visualizzazione personalizzata, vedere [Creare una modalità di visualizzazione personalizzata per un controllo ListView](how-to-create-a-custom-view-mode-for-a-listview.md).  
  
<a name="BindingDatatoaListView"></a>
## <a name="binding-data-to-a-listview"></a>Associazione di dati a un controllo ListView  
 Usare le <xref:System.Windows.Controls.ItemsControl.Items%2A> <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> proprietà e per specificare gli elementi per un <xref:System.Windows.Controls.ListView> controllo. Nell'esempio seguente la <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> proprietà viene impostata su una raccolta di dati denominata `EmployeeInfoDataSource` .  
  
 [!code-xaml[ListViewCode#ItemsSource](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#itemssource)]  
  
 In <xref:System.Windows.Controls.GridView> , <xref:System.Windows.Controls.GridViewColumn> gli oggetti vengono associati ai campi dati specificati. Nell'esempio seguente viene associato un <xref:System.Windows.Controls.GridViewColumn> oggetto a un campo dati specificando un oggetto <xref:System.Windows.Data.Binding> per la <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> Proprietà.  
  
 [!code-csharp[ListViewCode#GridViewColumnProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml.cs#gridviewcolumnproperties)]
 [!code-vb[ListViewCode#GridViewColumnProperties](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCode/visualbasic/window1.xaml.vb#gridviewcolumnproperties)]
 [!code-xaml[ListViewCode#GridViewColumnProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#gridviewcolumnproperties)]  
  
 È inoltre possibile specificare un <xref:System.Windows.Data.Binding> come parte di una <xref:System.Windows.DataTemplate> definizione utilizzata per applicare uno stile alle celle in una colonna. Nell'esempio seguente, l'oggetto <xref:System.Windows.DataTemplate> identificato con un oggetto <xref:System.Windows.ResourceKey> imposta l'oggetto <xref:System.Windows.Data.Binding> per un oggetto <xref:System.Windows.Controls.GridViewColumn> . Si noti che questo esempio non definisce <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> perché questa operazione esegue l'override dell'associazione specificata da <xref:System.Windows.DataTemplate> .  
  
 [!code-xaml[ListViewTemplate#GridViewCellTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 [!code-xaml[ListViewTemplate#CellTemplateProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
<a name="StylingaListView"></a>
## <a name="styling-a-listview-that-implements-a-gridview"></a>Applicazione di uno stile a un controllo ListView che implementa un oggetto GridView  
 Il <xref:System.Windows.Controls.ListView> controllo contiene <xref:System.Windows.Controls.ListViewItem> oggetti, che rappresentano gli elementi di dati visualizzati. È possibile usare le proprietà seguenti per definire il contenuto e lo stile degli elementi di dati:  
  
- Nel <xref:System.Windows.Controls.ListView> controllo usare le <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A> proprietà, e <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> .  
  
- Nel <xref:System.Windows.Controls.ListViewItem> controllo usare le <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A> proprietà e.  
  
 Per evitare problemi di allineamento tra le celle di un <xref:System.Windows.Controls.GridView> , non usare <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> per impostare le proprietà o aggiungere contenuto che influisca sulla larghezza di un elemento in un oggetto <xref:System.Windows.Controls.ListView> . È ad esempio possibile che si verifichi un problema di allineamento quando si imposta la <xref:System.Windows.FrameworkElement.Margin%2A> Proprietà in <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> . Per specificare le proprietà o definire il contenuto che influisca sulla larghezza degli elementi in un oggetto <xref:System.Windows.Controls.GridView> , usare le proprietà della <xref:System.Windows.Controls.GridView> classe e le classi correlate, ad esempio <xref:System.Windows.Controls.GridViewColumn> .  
  
 Per ulteriori informazioni sull'utilizzo di <xref:System.Windows.Controls.GridView> e delle relative classi di supporto, vedere [Cenni preliminari su GridView](gridview-overview.md).  
  
 Se si definisce un oggetto <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> per un <xref:System.Windows.Controls.ListView> controllo e si definisce anche un oggetto <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> , è necessario includere un oggetto <xref:System.Windows.Controls.ContentPresenter> nello stile affinché il <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> funzioni correttamente.  
  
 Non usare le <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> proprietà e <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> per il <xref:System.Windows.Controls.ListView> contenuto visualizzato tramite un <xref:System.Windows.Controls.GridView> . Per specificare l'allineamento del contenuto in una colonna di un oggetto <xref:System.Windows.Controls.GridView> , definire un oggetto <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> .  
  
<a name="UsingtheSameViewMoreThanOnce"></a>
## <a name="sharing-the-same-view-mode"></a>Condivisione della stessa modalità di visualizzazione  
 Due <xref:System.Windows.Controls.ListView> controlli non possono condividere la stessa modalità di visualizzazione nello stesso momento. Se si tenta di utilizzare la stessa modalità di visualizzazione con più di un <xref:System.Windows.Controls.ListView> controllo, si verificherà un'eccezione.  
  
 Per specificare una modalità di visualizzazione che può essere usata contemporaneamente da più di una <xref:System.Windows.Controls.ListView> , usare modelli o stili.
  
<a name="CreatingaCustomView"></a>
## <a name="creating-a-custom-view-mode"></a>Creazione di una modalità di visualizzazione personalizzata  
 Le visualizzazioni personalizzate come <xref:System.Windows.Controls.GridView> sono derivate dalla <xref:System.Windows.Controls.ViewBase> classe astratta, che fornisce gli strumenti per visualizzare gli elementi di dati rappresentati come <xref:System.Windows.Controls.ListViewItem> oggetti.
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.GridView>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.ListViewItem>
- <xref:System.Windows.Data.Binding>
- [Cenni preliminari su GridView](gridview-overview.md)
- [Procedure relative](listview-how-to-topics.md)
- [Controlli](../advanced/optimizing-performance-controls.md)
