---
title: Utilizzo della libreria di classi portabile con MVVM (Model-View-View Model)
ms.date: 07/18/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Portable Class Library [.NET Framework], and MVVM
- MVVM, and Portable Class Library
ms.assetid: 41a0b9f8-15a2-431a-bc35-e310b2953b03
ms.openlocfilehash: f5312177b9f437d9b5474d38fca80db6fc45245b
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2020
ms.locfileid: "77123675"
---
# <a name="using-portable-class-library-with-model-view-view-model"></a>Utilizzo della libreria di classi portabile con MVVM (Model-View-View Model)
È possibile usare la [libreria di classi](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) portabile .NET Framework per implementare il modello MVVM (Model-View-View Model) e condividere gli assembly in più piattaforme.

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

 MVVM è un modello di applicazione tramite cui l'interfaccia utente viene isolata dalla logica di business sottostante. È possibile implementare le classi modello e visualizza modello in un progetto libreria di classi portabile in Visual Studio 2012, quindi creare visualizzazioni personalizzate per piattaforme diverse. Questo approccio consente di scrivere il modello di dati e la logica di business solo una volta e di utilizzare tale codice dalle app .NET Framework, Silverlight, Windows Phone e Windows 8. x Store, come illustrato nella figura seguente.

 ![Mostra la libreria di classi portabile con gli assembly di condivisione MVVM su più piattaforme.](./media/using-portable-class-library-with-model-view-view-model/mvvm-share-assemblies-across-platforms.png)

 In questo argomento non vengono fornite informazioni generali sul modello MVVM. Fornisce solo informazioni su come usare la libreria di classi portabile per implementare MVVM. Per ulteriori informazioni su MVVM, vedere la [Guida introduttiva di MVVM utilizzando la libreria Prism 5,0 per WPF](https://docs.microsoft.com/previous-versions/msp-n-p/gg430857(v=pandp.40)).

## <a name="classes-that-support-mvvm"></a>Classi che supportano MVVM
 Quando la destinazione è la .NET Framework 4,5, .NET per le app di Windows 8. x Store, Silverlight o Windows Phone 7,5 per il progetto libreria di classi portabile, sono disponibili le classi seguenti per implementare il modello MVVM:

- Classe <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType>

- Classe <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType>

- Classe <xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType>

- Classe <xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType>

- Classe <xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType>

- Classe <xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType>

- Classe <xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType>

- Classe <xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType>

- Classe <xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType>

- Classe <xref:System.Windows.Input.ICommand?displayProperty=nameWithType>

- Tutte le classi nello spazio dei nomi <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType>

## <a name="implementing-mvvm"></a>Implementazione di MVVM
 Per implementare MVVM, in genere si creano sia il modello che il modello di visualizzazione in un progetto libreria di classi portabile, perché un progetto libreria di classi portabile non può fare riferimento a un progetto non portabile. Il modello e il modello di visualizzazione possono trovarsi nello stesso progetto o in progetti distinti. Se si utilizzano progetti distinti, aggiungere un riferimento dal progetto di modello di visualizzazione al progetto di modello.

 Dopo la compilazione del modello e la visualizzazione dei progetti di modello, è possibile fare riferimento a tali assembly nell'app che contiene la vista. Se la vista interagisce solo con il modello di visualizzazione, è necessario fare riferimento solo all'assembly che contiene il modello di visualizzazione.

### <a name="model"></a>Modello
 Nell'esempio seguente viene illustrata una classe di modello semplificata che può risiedere in un progetto libreria di classi portabile.

 [!code-csharp[PortableClassLibraryMVVM#1](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customer.cs#1)]
 [!code-vb[PortableClassLibraryMVVM#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customer.vb#1)]

 Nell'esempio seguente viene illustrato un modo semplice per popolare, recuperare e aggiornare i dati in un progetto libreria di classi portabile. In un'app reale è possibile recuperare i dati da un'origine, ad esempio un servizio Windows Communication Foundation (WCF).

 [!code-csharp[PortableClassLibraryMVVM#2](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customerrepository.cs#2)]
 [!code-vb[PortableClassLibraryMVVM#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerrepository.vb#2)]

### <a name="view-model"></a>Visualizza modello
 Una classe di base per i modelli di visualizzazione viene aggiunta spesso quando si implementa il modello MVVM. Nell'esempio seguente viene illustrata una classe di base.

 [!code-csharp[PortableClassLibraryMVVM#3](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/viewmodelbase.cs#3)]
 [!code-vb[PortableClassLibraryMVVM#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/viewmodelbase.vb#3)]

 Con il modello MVVM viene spesso utilizzata un'implementazione dell'interfaccia <xref:System.Windows.Input.ICommand>. Nell'esempio seguente viene illustrata un'implementazione dell'interfaccia <xref:System.Windows.Input.ICommand>.

 [!code-csharp[PortableClassLibraryMVVM#4](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/relaycommand.cs#4)]
 [!code-vb[PortableClassLibraryMVVM#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/relaycommand.vb#4)]

 Nell'esempio seguente viene illustrato un modello di visualizzazione semplificato.

 [!code-csharp[PortableClassLibraryMVVM#5](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainpageviewmodel.cs#5)]
 [!code-vb[PortableClassLibraryMVVM#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerviewmodel.vb#5)]  
  
### <a name="view"></a>Visualizza  
 Da un'app .NET Framework 4,5, un'app di Windows 8. x Store, un'app basata su Silverlight o un'app Windows Phone 7,5, è possibile fare riferimento all'assembly che contiene i progetti modello e visualizza modello.  Si crea quindi una vista che interagisce con il modello di visualizzazione. Nell'esempio seguente viene illustrata un'app semplificata Windows Presentation Foundation (WPF) che recupera e aggiorna i dati dal modello di visualizzazione. È possibile creare visualizzazioni simili in Silverlight, Windows Phone o app di Windows 8. x Store.  
  
 [!code-xaml[PortableClassLibraryMVVM#6](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainwindow.xaml#6)]  
  
## <a name="see-also"></a>Vedere anche

- [Libreria di classi portabile](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)
