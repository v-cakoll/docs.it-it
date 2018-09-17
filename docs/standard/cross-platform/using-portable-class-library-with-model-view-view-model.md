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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d2f07e471d4f0173f768b0d2a463d756b5be0682
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2018
ms.locfileid: "45964959"
---
# <a name="using-portable-class-library-with-model-view-view-model"></a>Utilizzo della libreria di classi portabile con MVVM (Model-View-View Model)
È possibile usare .NET Framework [libreria di classi portabile](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) per implementare il modello Model-View-View Model (MVVM) e condividere gli assembly su più piattaforme.  

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

 MVVM è un modello di applicazione tramite cui l'interfaccia utente viene isolata dalla logica di business sottostante. È possibile implementare il modello e visualizzare le classi del modello in un progetto [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] di [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)] e, successivamente, creare visualizzazioni personalizzate per piattaforme diverse. Questo approccio consente di scrivere una sola volta il modello dati e la logica di business e di utilizzare questo codice nelle applicazioni .NET Framework, Silverlight, Windows Phone e [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], come illustrato di seguito.  
  
 ![Portabile con diagramma MVVM](../../../docs/standard/cross-platform/media/portablemvvmdiagram.png "PortableMVVMdiagram")  
  
 In questo argomento non fornisce informazioni generali relative al modello MVVM. Fornisce solo le informazioni su come usare [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] implementare MVVM. Per altre informazioni su MVVM, vedere la [Guida introduttiva di MVVM](https://msdn.microsoft.com/library/gg430869(v=PandP.40).aspx).  
  
## <a name="classes-that-support-mvvm"></a>Classi che supportano MVVM  
 Se la destinazione di [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], Silverlight o Windows Phone 7.5 per il [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] progetto, le classi seguenti sono disponibili per l'implementazione del pattern MVVM:  
  
-   Classe <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType>  
  
-   Classe <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType>  
  
-   Classe <xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType>  
  
-   Classe <xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType>  
  
-   Classe <xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType>  
  
-   Classe <xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType>  
  
-   Classe <xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType>  
  
-   Classe <xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType>  
  
-   Classe <xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType>  
  
-   Classe <xref:System.Windows.Input.ICommand?displayProperty=nameWithType>  
  
-   Tutte le classi di <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> dello spazio dei nomi  
  
## <a name="implementing-mvvm"></a>Implementazione del modello MVVM  
 Per implementare MVVM, si crea in genere sia il modello e il modello di visualizzazione in un [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] del progetto, in quanto un [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] progetto non è possibile fare riferimento a un progetto non portatile. Il modello e il modello di visualizzazione può essere nello stesso progetto o in progetti separati. Se si usano progetti separati, aggiungere un riferimento dal progetto di modello di visualizzazione per il progetto di modello.  
  
 Dopo aver compilato il modello e visualizzare i progetti di modello, è fare riferimento a tali assembly nell'app contenente la vista. Se la vista interagisce solo con il modello di visualizzazione, è sufficiente fare riferimento all'assembly che contiene il modello di visualizzazione.  
  
### <a name="model"></a>Modello  
 Nell'esempio seguente viene illustrata una classe di modello semplificato che potrebbe trovarsi in un [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] progetto.  
  
 [!code-csharp[PortableClassLibraryMVVM#1](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customer.cs#1)]
 [!code-vb[PortableClassLibraryMVVM#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customer.vb#1)]  
  
 L'esempio seguente illustra un modo semplice per inserire, recuperare e aggiornare i dati in un [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] progetto. In una vera app, è necessario recuperare i dati da un'origine quale un servizio Windows Communication Foundation (WCF).  
  
 [!code-csharp[PortableClassLibraryMVVM#2](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customerrepository.cs#2)]
 [!code-vb[PortableClassLibraryMVVM#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerrepository.vb#2)]  
  
### <a name="view-model"></a>Modello di visualizzazione  
 Una classe di base per la visualizzazione di modelli spesso viene aggiunto quando si implementa il pattern MVVM. Nell'esempio seguente viene illustrata una classe base.  
  
 [!code-csharp[PortableClassLibraryMVVM#3](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/viewmodelbase.cs#3)]
 [!code-vb[PortableClassLibraryMVVM#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/viewmodelbase.vb#3)]  
  
 Un'implementazione del <xref:System.Windows.Input.ICommand> interfaccia viene spesso usata con il modello MVVM. Nell'esempio seguente viene illustrata un'implementazione dell'interfaccia <xref:System.Windows.Input.ICommand>.  
  
 [!code-csharp[PortableClassLibraryMVVM#4](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/relaycommand.cs#4)]
 [!code-vb[PortableClassLibraryMVVM#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/relaycommand.vb#4)]  
  
 Nell'esempio seguente viene illustrato un modello di visualizzazione semplificata.  
  
 [!code-csharp[PortableClassLibraryMVVM#5](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainpageviewmodel.cs#5)]
 [!code-vb[PortableClassLibraryMVVM#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerviewmodel.vb#5)]  
  
### <a name="view"></a>Visualizza  
 Da un [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] app, [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app, app basate su Silverlight o app di Windows Phone 7.5, è possibile fare riferimento all'assembly che contiene i progetti di modello modello e visualizzazione.  È quindi possibile creare una vista che interagisce con il modello di visualizzazione. Nell'esempio seguente mostra un'app Windows Presentation Foundation (WPF) semplificata che recupera e aggiorna i dati del modello di visualizzazione. È possibile creare visualizzazioni simili in Silverlight, Windows Phone, o [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app.  
  
 [!code-xaml[PortableClassLibraryMVVM#6](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainwindow.xaml#6)]  
  
## <a name="see-also"></a>Vedere anche

- [Libreria di classi portabile](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)
