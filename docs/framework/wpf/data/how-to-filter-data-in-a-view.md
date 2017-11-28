---
title: 'Procedura: filtrare i dati in una visualizzazione'
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
- views [WPF], filtering data
- filtering data in views [WPF]
- data binding [WPF], filtering data in views
ms.assetid: c76e8606-4cc4-45a8-9110-e2ec66dc6afd
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: de51aa83af71027ce86909a15f3ceee58fb47814
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-filter-data-in-a-view"></a>Procedura: filtrare i dati in una visualizzazione
In questo esempio viene illustrato come filtrare i dati in una vista.  
  
## <a name="example"></a>Esempio  
 Per creare un filtro, definire un metodo che fornisce la logica di filtro. Il metodo viene utilizzato come un callback e accetta un parametro di tipo `object`. Il metodo seguente restituisce tutti i `Order` gli oggetti con il `filled` proprietà è impostata su "No", per escludere il resto degli oggetti.  
  
 [!code-csharp[SortFilter#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#2)]
 [!code-vb[SortFilter#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#2)]  
  
 È quindi possibile applicare il filtro, come illustrato nell'esempio seguente. In questo esempio, `myCollectionView` è un <xref:System.Windows.Data.ListCollectionView> oggetto.  
  
 [!code-csharp[SortFilter#Filter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#filter)]
 [!code-vb[SortFilter#Filter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#filter)]  
  
 Per rimuovere il filtro, è possibile impostare il <xref:System.Windows.Data.CollectionView.Filter%2A> proprietà `null`:  
  
 [!code-csharp[SortFilter#Unfilter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#unfilter)]
 [!code-vb[SortFilter#Unfilter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#unfilter)]  
  
 Per informazioni su come creare o ottenere una visualizzazione, vedere [ottenere la visualizzazione predefinita di una raccolta di dati](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md). Per un esempio completo, vedere [ordinamento e filtro di elementi in una visualizzazione](http://go.microsoft.com/fwlink/?LinkID=160040).  
  
 Se l'oggetto visualizzazione proviene da un <xref:System.Windows.Data.CollectionViewSource> dell'oggetto, si applica la logica di filtro impostando un gestore eventi per il <xref:System.Windows.Data.CollectionViewSource.Filter> evento. Nell'esempio seguente, `listingDataView` è un'istanza di <xref:System.Windows.Data.CollectionViewSource>.  
  
 [!code-csharp[DataBindingLab#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 Nell'esempio viene illustrata l'implementazione dell'esempio `ShowOnlyBargainsFilter` gestore eventi del filtro. Questo gestore eventi viene utilizzato il <xref:System.Windows.Data.FilterEventArgs.Accepted%2A> proprietà da filtrare `AuctionItem` gli oggetti che hanno un `CurrentPrice` di $25 o superiore.  
  
 [!code-csharp[DataBindingLab#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Data.CollectionView.CanFilter%2A>  
 <xref:System.Windows.Data.BindingListCollectionView.CustomFilter%2A>  
 [Cenni preliminari sull'associazione dati](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Ordinare i dati in una visualizzazione](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)  
 [Procedure relative](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
