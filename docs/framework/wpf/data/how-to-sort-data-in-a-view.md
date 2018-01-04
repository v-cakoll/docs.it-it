---
title: 'Procedura: ordinare i dati in una visualizzazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7467913f867ea0990ae85b0ad933c11f2fd271b9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-sort-data-in-a-view"></a>Procedura: ordinare i dati in una visualizzazione
In questo esempio viene descritto come ordinare i dati in una vista.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creato un semplice <xref:System.Windows.Controls.ListBox> e <xref:System.Windows.Controls.Button>:  
  
 [!code-xaml[ListBoxSort_snip#HowTo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml#howto)]  
  
 Il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestore dell'evento del pulsante contiene la logica per ordinare gli elementi di <xref:System.Windows.Controls.ListBox> in ordine decrescente. È possibile farlo perché l'aggiunta di elementi un <xref:System.Windows.Controls.ListBox> in questo modo vengono aggiunte al <xref:System.Windows.Controls.ItemCollection> del <xref:System.Windows.Controls.ListBox>, e <xref:System.Windows.Controls.ItemCollection> deriva il <xref:System.Windows.Data.CollectionView> classe. Se si desidera associare il <xref:System.Windows.Controls.ListBox> a una raccolta mediante la <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> proprietà, è possibile utilizzare la stessa tecnica per l'ordinamento.  
  
 [!code-csharp[ListBoxSort_snip#HowToCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml.cs#howtocode)]
 [!code-vb[ListBoxSort_snip#HowToCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxSort_snip/visualbasic/window1.xaml.vb#howtocode)]  
  
 Fino a quando è presente un riferimento all'oggetto view, è possibile utilizzare la stessa tecnica per ordinare il contenuto di altre viste di raccolta. Per un esempio di come ottenere una vista, vedere [ottenere la visualizzazione predefinita di una raccolta di dati](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md). Per un altro esempio, vedere [ordinare un GridView colonna quando un si seleziona l'intestazione](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md). Per ulteriori informazioni sulle visualizzazioni, vedere l'associazione alle raccolte in [Panoramica del Data Binding](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Per un esempio di come applicare la logica di ordinamento in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], vedere [ordinamento e gruppo di dati tramite una vista in XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Data.ListCollectionView.CustomSort%2A>  
 [Ordinare una colonna GridView quando si fa clic su un'intestazione](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)  
 [Panoramica sul data binding](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Filtrare i dati di una visualizzazione](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
