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
ms.openlocfilehash: e82d252ed82e4d2e6d641e8b60e890cc93bb0427
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459124"
---
# <a name="how-to-get-the-default-view-of-a-data-collection"></a>Procedura: ottenere la visualizzazione predefinita di una raccolta dati
Le visualizzazioni consentono di visualizzare la stessa raccolta dati in modi diversi, a seconda dei criteri di ordinamento, di filtro o di raggruppamento. Ogni raccolta dispone di una visualizzazione predefinita condivisa, che viene utilizzata come origine di associazione effettiva quando un'associazione specifica una raccolta come origine. Questo esempio illustra come ottenere la visualizzazione predefinita di una raccolta.  
  
## <a name="example"></a>Esempio  
 Per creare la vista, è necessario un riferimento a un oggetto alla raccolta. È possibile ottenere questo oggetto dati facendo riferimento al proprio oggetto code-behind, ottenendo il contesto dei dati, ottenendo una proprietà dell'origine dati o ottenendo una proprietà dell'associazione. In questo esempio viene illustrato come ottenere il <xref:System.Windows.FrameworkElement.DataContext%2A> di un oggetto dati e utilizzarlo per ottenere direttamente la visualizzazione di raccolta predefinita per questa raccolta.  
  
 [!code-csharp[CollectionView#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#2)]
 [!code-vb[CollectionView#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#2)]  
  
 In questo esempio, l'elemento radice è un <xref:System.Windows.Controls.StackPanel>. Il <xref:System.Windows.FrameworkElement.DataContext%2A> è impostato su *DataSource*, che fa riferimento a un provider di dati costituito da un <xref:System.Collections.ObjectModel.ObservableCollection%601> di oggetti *Order* .  
  
 [!code-xaml[CollectionView#CollectionViewDataContext](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml#collectionviewdatacontext)]  
  
 In alternativa, è possibile creare un'istanza di e associarla alla propria visualizzazione di raccolta usando la classe <xref:System.Windows.Data.CollectionViewSource>. Questa vista di raccolta è condivisa solo dai controlli che lo associano direttamente. Per un esempio, vedere la sezione come creare una vista nella panoramica sul [Data Binding](../../../desktop-wpf/data/data-binding-overview.md).  
  
 Per esempi della funzionalità fornita da una visualizzazione di raccolta, vedere [ordinare i dati in una visualizzazione](how-to-sort-data-in-a-view.md), [filtrare i dati in una visualizzazione](how-to-filter-data-in-a-view.md)e [spostarsi tra gli oggetti in una](how-to-navigate-through-the-objects-in-a-data-collectionview.md)raccolta di dati.  
  
## <a name="see-also"></a>Vedere anche

- [Ordinare e raggruppare dati con una visualizzazione in XAML](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
