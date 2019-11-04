---
title: 'Procedura: implementare un oggetto CompositeCollection'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], CompositeCollection class
ms.assetid: 0d8fc84c-7920-427f-8ad7-d55ca656c170
ms.openlocfilehash: b3450cdc476b7090251a06b5b2b2718d29e18209
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454035"
---
# <a name="how-to-implement-a-compositecollection"></a>Procedura: implementare un oggetto CompositeCollection
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come visualizzare più raccolte ed elementi come un elenco usando la classe <xref:System.Windows.Data.CompositeCollection>. In questo esempio `GreekGods` è un <xref:System.Collections.ObjectModel.ObservableCollection%601> di `GreekGod` oggetti personalizzati. I modelli di dati vengono definiti in modo che gli oggetti `GreekGod` e gli oggetti di `GreekHero` vengano visualizzati rispettivamente con un colore di primo piano in oro e un ciano.  
  
 [!code-xaml[CompositeCollections#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CompositeCollections/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Data.CollectionContainer>
- <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>
- <xref:System.Windows.Data.XmlDataProvider>
- <xref:System.Windows.DataTemplate>
- [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
