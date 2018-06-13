---
title: 'Procedura: ottenere la visualizzazione predefinita di una raccolta dati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], creating views of
- data binding [WPF], creating views of data collections
ms.assetid: b641e96c-c2f6-42ea-9c5d-bac81176ad65
ms.openlocfilehash: e8e6928391a98a132f1dbb39edfda0d73d2eebdb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557173"
---
# <a name="how-to-get-the-default-view-of-a-data-collection"></a>Procedura: ottenere la visualizzazione predefinita di una raccolta dati
Le viste consentono la stessa raccolta di dati da visualizzare in modi diversi, a seconda di ordinamento, filtro o i criteri di raggruppamento. Ogni raccolta dispone di una visualizzazione predefinita condivisa, che viene utilizzata come origine di associazione effettiva quando un'associazione specifica una raccolta come origine. In questo esempio viene illustrato come ottenere la visualizzazione predefinita di una raccolta.  
  
## <a name="example"></a>Esempio  
 Per creare una vista, è necessario un riferimento all'oggetto alla raccolta. È possibile ottenere questo oggetto dati facendo riferimento a un oggetto di codice, ottenendo il contesto dei dati, una proprietà dell'origine dati o una proprietà dell'associazione. In questo esempio viene illustrato come ottenere il <xref:System.Windows.FrameworkElement.DataContext%2A> di un oggetto dati e utilizzarlo per ottenere direttamente l'insieme predefinito visualizzazione per questa raccolta.  
  
 [!code-csharp[CollectionView#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#2)]
 [!code-vb[CollectionView#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#2)]  
  
 In questo esempio, l'elemento radice è un <xref:System.Windows.Controls.StackPanel>. Il <xref:System.Windows.FrameworkElement.DataContext%2A> è impostato su *myDataSource*, che fa riferimento a un provider di dati che è un <xref:System.Collections.ObjectModel.ObservableCollection%601> di *ordine* oggetti.  
  
 [!code-xaml[CollectionView#CollectionViewDataContext](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml#collectionviewdatacontext)]  
  
 In alternativa, è possibile creare un'istanza e associare la propria visualizzazione raccolta utilizzando la <xref:System.Windows.Data.CollectionViewSource> classe. Questa visualizzazione della raccolta è condivisa solo dai controlli a esso associati direttamente. Per un esempio, vedere la procedura per creare una vista sezione la [Panoramica del Data Binding](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Per esempi delle funzionalità fornite da una vista di raccolta, vedere [ordinare i dati in una vista](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md), [filtrare i dati in una vista](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md), e [passare attraverso il oggetti in una visualizzazione di raccolta dati](../../../../docs/framework/wpf/data/how-to-navigate-through-the-objects-in-a-data-collectionview.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Ordinare e raggruppare dati con una visualizzazione in XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
