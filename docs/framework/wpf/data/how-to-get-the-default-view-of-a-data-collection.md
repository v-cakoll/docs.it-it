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
ms.openlocfilehash: 746331e69ee1e5eee795a0e35202f4889b72c53f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59222107"
---
# <a name="how-to-get-the-default-view-of-a-data-collection"></a>Procedura: Ottenere la visualizzazione predefinita di una raccolta dati
Le viste consentono la stessa raccolta di dati da visualizzare in modi diversi, a seconda di ordinamento, filtro o criteri di raggruppamento. Ogni raccolta ha una visualizzazione condivisa predefinita, viene usata come origine del binding effettivo quando un'associazione specifica una raccolta come origine. In questo esempio viene illustrato come ottenere la visualizzazione predefinita di una raccolta.  
  
## <a name="example"></a>Esempio  
 Per creare una vista, è necessario un riferimento all'oggetto alla raccolta. È possibile ottenere questo oggetto dati facendo riferimento a un code-behind oggetto personalizzato, ottenendo il contesto dei dati, ottenendo una proprietà dell'origine dati oppure ottenendo una proprietà dell'associazione. In questo esempio viene illustrato come ottenere il <xref:System.Windows.FrameworkElement.DataContext%2A> di un oggetto dati e utilizzarlo per ottenere direttamente la raccolta predefinita consente di visualizzare per questa raccolta.  
  
 [!code-csharp[CollectionView#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#2)]
 [!code-vb[CollectionView#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#2)]  
  
 In questo esempio, l'elemento radice è un <xref:System.Windows.Controls.StackPanel>. Il <xref:System.Windows.FrameworkElement.DataContext%2A> è impostata su *myDataSource*, che fa riferimento a un provider di dati che è un <xref:System.Collections.ObjectModel.ObservableCollection%601> dei *ordine* oggetti.  
  
 [!code-xaml[CollectionView#CollectionViewDataContext](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml#collectionviewdatacontext)]  
  
 In alternativa, è possibile creare un'istanza e associare alla propria visualizzazione raccolta utilizzando il <xref:System.Windows.Data.CollectionViewSource> classe. Questa vista raccolta è condivisa solo dai controlli associati a esso direttamente. Per un esempio, vedere la procedura crea una visualizzazione sezione la [Panoramica sul Data Binding](data-binding-overview.md).  
  
 Per esempi delle funzionalità fornite da una visualizzazione di raccolta, vedere [ordinare i dati in una vista](how-to-sort-data-in-a-view.md), [filtrare i dati in una vista](how-to-filter-data-in-a-view.md), e [tra gli oggetti in una visualizzazione di raccolta dati](how-to-navigate-through-the-objects-in-a-data-collectionview.md).  
  
## <a name="see-also"></a>Vedere anche

- [Ordinare e raggruppare dati con una visualizzazione in XAML](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
