---
title: "Procedura: eseguire l'associazione di una raccolta e visualizzare informazioni in base alla selezione effettuata"
description: Seguire questo esempio per scoprire come eseguire l'associazione a una raccolta e visualizzare le informazioni in base alla selezione nel Windows Presentation Foundation (WPF).
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
ms.openlocfilehash: fb8757ee6818a2812308a0a132fa9d06951ad52e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619611"
---
# <a name="how-to-bind-to-a-collection-and-display-information-based-on-selection"></a>Procedura: eseguire l'associazione di una raccolta e visualizzare informazioni in base alla selezione effettuata
In un semplice scenario Master-Details è presente un oggetto con associazione a dati, <xref:System.Windows.Controls.ItemsControl> ad esempio <xref:System.Windows.Controls.ListBox> . In base alla selezione dell'utente, vengono visualizzate altre informazioni sull'elemento selezionato. In questo esempio viene illustrato come implementare questo scenario.  
  
## <a name="example"></a>Esempio  
 In questo esempio, `People` è un oggetto <xref:System.Collections.ObjectModel.ObservableCollection%601> di `Person` classi. Questa `Person` classe contiene tre proprietà: `FirstName` , `LastName` e `HomeTown` , tutti di tipo `string` .  
  
 [!code-xaml[CollectionBinding#Source](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xaml[CollectionBinding#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 In <xref:System.Windows.Controls.ContentControl> viene utilizzato il codice seguente <xref:System.Windows.DataTemplate> che definisce la modalità di presentazione delle informazioni di un oggetto `Person` :  
  
 [!code-xaml[CollectionBinding#DetailTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 Di seguito è riportata una schermata dell'esempio prodotto dall'esempio. <xref:System.Windows.Controls.ContentControl>Mostra le altre proprietà della persona selezionata.  
  
 ![Binding to a Collection](./media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")  
  
 I due aspetti da notare in questo esempio sono i seguenti:  
  
1. <xref:System.Windows.Controls.ListBox>E <xref:System.Windows.Controls.ContentControl> si associano alla stessa origine. Le <xref:System.Windows.Data.Binding.Path%2A> proprietà di entrambe le associazioni non sono specificate perché entrambi i controlli sono associati all'intero oggetto della raccolta.  
  
2. È necessario impostare la <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> proprietà su `true` affinché funzioni. L'impostazione di questa proprietà garantisce che l'elemento selezionato sia sempre impostato come <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A> . In alternativa, se <xref:System.Windows.Controls.ListBox> ottiene i dati da un <xref:System.Windows.Data.CollectionViewSource> , sincronizza automaticamente la selezione e la valuta.  
  
 Si noti che la `Person` classe esegue `ToString` l'override del metodo nel modo seguente. Per impostazione predefinita, <xref:System.Windows.Controls.ListBox> chiama `ToString` e visualizza una rappresentazione di stringa di ogni oggetto nella raccolta associata. Per questo motivo ogni `Person` viene visualizzato come nome in <xref:System.Windows.Controls.ListBox> .  
  
 [!code-csharp[CollectionBinding#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## <a name="see-also"></a>Vedere anche

- [Usare il modello Master-Details con dati gerarchici](how-to-use-the-master-detail-pattern-with-hierarchical-data.md)
- [Usare il modello Master-Details con dati XML gerarchici](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)
- [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md)
- [Cenni preliminari sui modelli di dati](data-templating-overview.md)
- [Procedure](data-binding-how-to-topics.md)
