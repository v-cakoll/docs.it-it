---
title: 'Procedura: Ordinare i dati in una visualizzazione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], sorting data in views
- data binding [WPF], grouping data in views
- grouping data in views [WPF]
- views [WPF], sorting data
- views [WPF], grouping data
- sorting data in views [WPF]
ms.assetid: f4c43578-01b7-4774-a953-acb95a13b94a
ms.openlocfilehash: 50e1426f2a220c7d947f7feb9c3ec7e1c4de7643
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54522674"
---
# <a name="how-to-sort-data-in-a-view"></a>Procedura: Ordinare i dati in una visualizzazione
In questo esempio viene descritto come ordinare i dati in una vista.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea una semplice <xref:System.Windows.Controls.ListBox> e un <xref:System.Windows.Controls.Button>:  
  
 [!code-xaml[ListBoxSort_snip#HowTo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml#howto)]  
  
 Il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestore dell'evento del pulsante contiene la logica per ordinare gli elementi nel <xref:System.Windows.Controls.ListBox> in ordine decrescente. È possibile eseguire questa operazione perché l'aggiunta di elementi una <xref:System.Windows.Controls.ListBox> in questo modo vengono aggiunte al <xref:System.Windows.Controls.ItemCollection> delle <xref:System.Windows.Controls.ListBox>, e <xref:System.Windows.Controls.ItemCollection> deriva dal <xref:System.Windows.Data.CollectionView> classe. Quando si associa il <xref:System.Windows.Controls.ListBox> a una raccolta mediante il <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> proprietà, è possibile usare la stessa tecnica per ordinare.  
  
 [!code-csharp[ListBoxSort_snip#HowToCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml.cs#howtocode)]
 [!code-vb[ListBoxSort_snip#HowToCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxSort_snip/visualbasic/window1.xaml.vb#howtocode)]  
  
 Purché si disponga di un riferimento all'oggetto di visualizzazione, è possibile usare la stessa tecnica per ordinare il contenuto di altre viste di raccolta. Per un esempio di come ottenere una visualizzazione, vedere [ottenere la visualizzazione predefinita di una raccolta di dati](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md). Per un altro esempio, vedere [ordinare un GridView colonna quando una si seleziona l'intestazione](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md). Per altre informazioni sulle viste, vedere Binding alle raccolte [Panoramica sul Data Binding](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Per un esempio di come applicare la logica di ordinamento nel [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], vedere [ordinare e raggruppare i dati tramite una visualizzazione in XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md).  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Data.ListCollectionView.CustomSort%2A>
- [Ordinare una colonna GridView quando si fa clic su un'intestazione](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)
- [Panoramica sul data binding](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [Filtrare i dati di una visualizzazione](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)
- [Procedure relative alle proprietà](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
