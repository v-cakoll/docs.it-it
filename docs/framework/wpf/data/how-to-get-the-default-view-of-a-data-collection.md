---
title: 'Procedura: Ottenere la visualizzazione predefinita di una raccolta dati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], creating views of
- data binding [WPF], creating views of data collections
ms.assetid: b641e96c-c2f6-42ea-9c5d-bac81176ad65
ms.openlocfilehash: 386c25998c85de2f674200fe7d269ae2fdabd72d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54588402"
---
# <a name="how-to-get-the-default-view-of-a-data-collection"></a>Procedura: Ottenere la visualizzazione predefinita di una raccolta dati
Le viste consentono la stessa raccolta di dati da visualizzare in modi diversi, a seconda di ordinamento, filtro o criteri di raggruppamento. Ogni raccolta ha una visualizzazione condivisa predefinita, viene usata come origine del binding effettivo quando un'associazione specifica una raccolta come origine. In questo esempio viene illustrato come ottenere la visualizzazione predefinita di una raccolta.  
  
## <a name="example"></a>Esempio  
 Per creare una vista, è necessario un riferimento all'oggetto alla raccolta. È possibile ottenere questo oggetto dati facendo riferimento a un code-behind oggetto personalizzato, ottenendo il contesto dei dati, ottenendo una proprietà dell'origine dati oppure ottenendo una proprietà dell'associazione. In questo esempio viene illustrato come ottenere il <xref:System.Windows.FrameworkElement.DataContext%2A> di un oggetto dati e utilizzarlo per ottenere direttamente la raccolta predefinita consente di visualizzare per questa raccolta.  
  
 [!code-csharp[CollectionView#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#2)]
 [!code-vb[CollectionView#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#2)]  
  
 In questo esempio, l'elemento radice è un <xref:System.Windows.Controls.StackPanel>. Il <xref:System.Windows.FrameworkElement.DataContext%2A> è impostata su *myDataSource*, che fa riferimento a un provider di dati che è un <xref:System.Collections.ObjectModel.ObservableCollection%601> dei *ordine* oggetti.  
  
 [!code-xaml[CollectionView#CollectionViewDataContext](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml#collectionviewdatacontext)]  
  
 In alternativa, è possibile creare un'istanza e associare alla propria visualizzazione raccolta utilizzando il <xref:System.Windows.Data.CollectionViewSource> classe. Questa vista raccolta è condivisa solo dai controlli associati a esso direttamente. Per un esempio, vedere la procedura crea una visualizzazione sezione la [Panoramica sul Data Binding](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Per esempi delle funzionalità fornite da una visualizzazione di raccolta, vedere [ordinare i dati in una vista](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md), [filtrare i dati in una vista](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md), e [tra gli oggetti in una visualizzazione di raccolta dati](../../../../docs/framework/wpf/data/how-to-navigate-through-the-objects-in-a-data-collectionview.md).  
  
## <a name="see-also"></a>Vedere anche
- [Ordinare e raggruppare dati con una visualizzazione in XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [Procedure relative alle proprietà](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
