---
title: 'Procedura: Eseguire il binding a una raccolta e visualizzare informazioni in base alla selezione'
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
ms.openlocfilehash: 61ced27ed80adf8ac5d543584f71794b9ee59676
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59188747"
---
# <a name="how-to-bind-to-a-collection-and-display-information-based-on-selection"></a>Procedura: Eseguire il binding a una raccolta e visualizzare informazioni in base alla selezione
In uno scenario master-dettagli semplice, è necessario con associazione a dati <xref:System.Windows.Controls.ItemsControl> , ad esempio un <xref:System.Windows.Controls.ListBox>. È basato sulla selezione dell'utente, visualizzare altre informazioni sull'elemento selezionato. In questo esempio viene illustrato come implementare questo scenario.  
  
## <a name="example"></a>Esempio  
 In questo esempio `People` è un <xref:System.Collections.ObjectModel.ObservableCollection%601> di `Person` classi. Ciò `Person` classe contiene tre proprietà: `FirstName`, `LastName`, e `HomeTown`, tutti di tipo `string`.  
  
 [!code-xaml[CollectionBinding#Source](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xaml[CollectionBinding#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 Il <xref:System.Windows.Controls.ContentControl> utilizza il seguente <xref:System.Windows.DataTemplate> che definisce come le informazioni di un `Person` viene presentato:  
  
 [!code-xaml[CollectionBinding#DetailTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 Di seguito è riportato uno screenshot del risultato dell'esempio. Il <xref:System.Windows.Controls.ContentControl> Mostra le altre proprietà della persona selezionata.  
  
 ![Associazione a una raccolta](./media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")  
  
 I due aspetti da notare in questo esempio sono:  
  
1.  Il <xref:System.Windows.Controls.ListBox> e il <xref:System.Windows.Controls.ContentControl> associare alla stessa origine. Il <xref:System.Windows.Data.Binding.Path%2A> le proprietà di entrambe le associazioni non vengono specificate perché entrambi i controlli vengono associati all'intero oggetto collection.  
  
2.  È necessario impostare il <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> proprietà `true` per il corretto funzionamento. Impostazione di questa proprietà garantisce che l'elemento selezionato è sempre impostato come il <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>. In alternativa, se il <xref:System.Windows.Controls.ListBox> Ottiene i dati da un <xref:System.Windows.Data.CollectionViewSource>, selezione e la valuta viene sincronizzato automaticamente.  
  
 Si noti che il `Person` classe esegue l'override di `ToString` metodo modo seguente. Per impostazione predefinita, il <xref:System.Windows.Controls.ListBox> chiamate `ToString` e visualizza una rappresentazione di stringa di ogni oggetto nella raccolta associata. Ecco perché ogni `Person` appare come un nome nel <xref:System.Windows.Controls.ListBox>.  
  
 [!code-csharp[CollectionBinding#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## <a name="see-also"></a>Vedere anche

- [Usare il modello Master-Details con dati gerarchici](how-to-use-the-master-detail-pattern-with-hierarchical-data.md)
- [Usare il modello Master-Details con dati XML gerarchici](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)
- [Panoramica sul data binding](data-binding-overview.md)
- [Cenni preliminari sui modelli di dati](data-templating-overview.md)
- [Procedure relative](data-binding-how-to-topics.md)
