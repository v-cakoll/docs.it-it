---
title: 'Procedura: filtrare i dati in una visualizzazione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- views [WPF], filtering data
- filtering data in views [WPF]
- data binding [WPF], filtering data in views
ms.assetid: c76e8606-4cc4-45a8-9110-e2ec66dc6afd
ms.openlocfilehash: ea49897ca5e9cb6b639cf7d98ff05bd287c51761
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73453474"
---
# <a name="how-to-filter-data-in-a-view"></a>Procedura: filtrare i dati in una visualizzazione
Questo esempio Mostra come filtrare i dati in una visualizzazione.  
  
## <a name="example"></a>Esempio  
 Per creare un filtro, definire un metodo che fornisca la logica di filtro. Il metodo viene utilizzato come callback e accetta un parametro di tipo `object`. Il metodo seguente restituisce tutti gli oggetti `Order` con la proprietà `filled` impostata su "No", filtrando il resto degli oggetti.  
  
 [!code-csharp[SortFilter#2](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#2)]
 [!code-vb[SortFilter#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#2)]  
  
 È quindi possibile applicare il filtro, come illustrato nell'esempio seguente. In questo esempio `myCollectionView` è un oggetto <xref:System.Windows.Data.ListCollectionView>.  
  
 [!code-csharp[SortFilter#Filter](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#filter)]
 [!code-vb[SortFilter#Filter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#filter)]  
  
 Per annullare l'applicazione di filtri, è possibile impostare la proprietà <xref:System.Windows.Data.CollectionView.Filter%2A> su `null`:  
  
 [!code-csharp[SortFilter#Unfilter](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#unfilter)]
 [!code-vb[SortFilter#Unfilter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#unfilter)]  
  
 Per informazioni su come creare o ottenere una vista, vedere [ottenere la visualizzazione predefinita di una raccolta di dati](how-to-get-the-default-view-of-a-data-collection.md). Per l'esempio completo, vedere [ordinamento e filtro degli elementi in un esempio di visualizzazione](https://go.microsoft.com/fwlink/?LinkID=160040).  
  
 Se l'oggetto visualizzazione deriva da un oggetto <xref:System.Windows.Data.CollectionViewSource>, applicare la logica di filtro impostando un gestore eventi per l'evento <xref:System.Windows.Data.CollectionViewSource.Filter>. Nell'esempio seguente `listingDataView` è un'istanza di <xref:System.Windows.Data.CollectionViewSource>.  
  
 [!code-csharp[DataBindingLab#10](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 Di seguito viene illustrata l'implementazione dell'esempio `ShowOnlyBargainsFilter` gestore dell'evento Filter. Questo gestore eventi usa la proprietà <xref:System.Windows.Data.FilterEventArgs.Accepted%2A> per filtrare gli oggetti `AuctionItem` con un `CurrentPrice` di $25 o superiore.  
  
 [!code-csharp[DataBindingLab#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Data.CollectionView.CanFilter%2A>
- <xref:System.Windows.Data.BindingListCollectionView.CustomFilter%2A>
- [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md)
- [Ordinare i dati in una visualizzazione](how-to-sort-data-in-a-view.md)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
