---
title: "Procedura: eseguire l'associazione di una raccolta e visualizzare informazioni in base alla selezione effettuata"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], selecting data for views
- data binding [WPF], creating views of data collections
- data binding [WPF], selecting data for views
- data binding [WPF], binding to collections
ms.assetid: 952a7d76-dd29-49e5-86f5-32c4530e70eb
ms.openlocfilehash: 032a1d98e1aa80ea755f5922f79d43a796e9697e
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459152"
---
# <a name="how-to-bind-to-a-collection-and-display-information-based-on-selection"></a>Procedura: eseguire l'associazione di una raccolta e visualizzare informazioni in base alla selezione effettuata
In un semplice scenario Master-Details è presente una <xref:System.Windows.Controls.ItemsControl> associata a dati, ad esempio una <xref:System.Windows.Controls.ListBox>. In base alla selezione dell'utente, vengono visualizzate altre informazioni sull'elemento selezionato. In questo esempio viene illustrato come implementare questo scenario.  
  
## <a name="example"></a>Esempio  
 In questo esempio `People` è un <xref:System.Collections.ObjectModel.ObservableCollection%601> di classi di `Person`. Questa classe `Person` contiene tre proprietà: `FirstName`, `LastName`e `HomeTown`, tutti di tipo `string`.  
  
 [!code-xaml[CollectionBinding#Source](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xaml[CollectionBinding#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 Il <xref:System.Windows.Controls.ContentControl> usa il <xref:System.Windows.DataTemplate> seguente che definisce la modalità di presentazione delle informazioni di un `Person`:  
  
 [!code-xaml[CollectionBinding#DetailTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 Di seguito è riportata una schermata dell'esempio prodotto dall'esempio. Il <xref:System.Windows.Controls.ContentControl> Mostra le altre proprietà della persona selezionata.  
  
 ![Associazione a una raccolta](./media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")  
  
 I due aspetti da notare in questo esempio sono i seguenti:  
  
1. Il <xref:System.Windows.Controls.ListBox> e il <xref:System.Windows.Controls.ContentControl> vengono associati alla stessa origine. Le proprietà <xref:System.Windows.Data.Binding.Path%2A> di entrambe le associazioni non sono specificate perché entrambi i controlli sono associati all'intero oggetto Collection.  
  
2. Per il corretto funzionamento di questo, è necessario impostare la proprietà <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> su `true`. L'impostazione di questa proprietà garantisce che l'elemento selezionato sia sempre impostato come <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>. In alternativa, se il <xref:System.Windows.Controls.ListBox> ottiene i dati da un <xref:System.Windows.Data.CollectionViewSource>, sincronizza automaticamente la selezione e la valuta.  
  
 Si noti che la classe `Person` esegue l'override del metodo `ToString` nel modo seguente. Per impostazione predefinita, il <xref:System.Windows.Controls.ListBox> chiama `ToString` e visualizza una rappresentazione di stringa di ogni oggetto nella raccolta associata. Per questo motivo ogni `Person` viene visualizzato come nome nel <xref:System.Windows.Controls.ListBox>.  
  
 [!code-csharp[CollectionBinding#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## <a name="see-also"></a>Vedere anche

- [Usare il modello Master-Details con dati gerarchici](how-to-use-the-master-detail-pattern-with-hierarchical-data.md)
- [Usare il modello Master-Details con dati XML gerarchici](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)
- [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md)
- [Panoramica sui modelli di dati](data-templating-overview.md)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
