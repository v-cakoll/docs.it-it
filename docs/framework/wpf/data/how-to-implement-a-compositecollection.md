---
title: 'Procedura: Implementare un oggetto CompositeCollection'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], CompositeCollection class
ms.assetid: 0d8fc84c-7920-427f-8ad7-d55ca656c170
ms.openlocfilehash: 2021ed83a8f2a6896631fa69d5dd55a74cad8a8d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54691866"
---
# <a name="how-to-implement-a-compositecollection"></a>Procedura: Implementare un oggetto CompositeCollection
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come visualizzare più connessioni ed elementi come un elenco utilizzando il <xref:System.Windows.Data.CompositeCollection> classe. In questo esempio `GreekGods` è un <xref:System.Collections.ObjectModel.ObservableCollection%601> di `GreekGod` oggetti personalizzati. I modelli di dati sono definiti in modo che `GreekGod` gli oggetti e `GreekHero` oggetti vengano visualizzati rispettivamente con un gold e un colore ciano in primo piano.  
  
 [!code-xaml[CompositeCollections#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CompositeCollections/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Data.CollectionContainer>
- <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>
- <xref:System.Windows.Data.XmlDataProvider>
- <xref:System.Windows.DataTemplate>
- [Panoramica sul data binding](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [Procedure relative alle proprietà](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
