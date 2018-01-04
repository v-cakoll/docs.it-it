---
title: Utilizzo della libreria di classi portabile con MVVM (Model-View-View Model)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Portable Class Library [.NET Framework], and MVVM
- MVVM, and Portable Class Library
ms.assetid: 41a0b9f8-15a2-431a-bc35-e310b2953b03
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: da1a05a6003d93727efd5749aac9a055c8c80d38
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="using-portable-class-library-with-model-view-view-model"></a>Utilizzo della libreria di classi portabile con MVVM (Model-View-View Model)
È possibile utilizzare .NET Framework [libreria di classi portabile](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) per implementare il modello Model-View-View MVVM (Model) e condividere gli assembly in più piattaforme.  
  
 MVVM è un modello di applicazione tramite cui l'interfaccia utente viene isolata dalla logica di business sottostante. È possibile implementare il modello e visualizzare le classi del modello in un progetto [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] di [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)] e, successivamente, creare visualizzazioni personalizzate per piattaforme diverse. Questo approccio consente di scrivere una sola volta il modello dati e la logica di business e di utilizzare questo codice nelle applicazioni .NET Framework, Silverlight, Windows Phone e [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], come illustrato di seguito.  
  
 ![Portabile con diagramma MVVM](../../../docs/standard/cross-platform/media/portablemvvmdiagram.png "PortableMVVMdiagram")  
  
 In questo argomento non fornisce informazioni generali sul modello MVVM. Fornisce solo informazioni su come usare [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] implementare MVVM. Per ulteriori informazioni su MVVM, vedere il [delle Guide rapide MVVM](http://go.microsoft.com/fwlink/?LinkId=234934).  
  
## <a name="classes-that-support-mvvm"></a>Classi che supportano MVVM  
 Se la destinazione di [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], Silverlight, o Windows Phone 7.5 per il [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] progetto, le classi seguenti sono disponibili per implementare il modello MVVM:  
  
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
  
## <a name="implementing-mvvm"></a>Implementazione MVVM  
 Per implementare MVVM, si crea in genere il modello sia il modello di visualizzazione in un [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] progetto, perché un [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] progetto non può fare riferimento a un progetto non portatile. Il modello e il modello di visualizzazione può essere nello stesso progetto o in progetti separati. Se si utilizzano progetti separati, aggiungere un riferimento dal progetto di modello di visualizzazione per il progetto di modello.  
  
 Dopo la compilazione del modello e visualizza i progetti di modello, fare riferimento a tali assembly nell'app contenente la vista. Se la vista interagisce solo con il modello di visualizzazione, è necessario fare riferimento all'assembly che contiene il modello di visualizzazione.  
  
### <a name="model"></a>Modello  
 Nell'esempio seguente viene illustrata una classe di modello semplificato che potrebbe trovarsi in un [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] progetto.  
  
 [!code-csharp[PortableClassLibraryMVVM#1](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customer.cs#1)]
 [!code-vb[PortableClassLibraryMVVM#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customer.vb#1)]  
  
 Nell'esempio seguente viene illustrato un modo semplice per inserire, recuperare e aggiornare i dati in un [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] progetto. In un'applicazione reale, è necessario recuperare i dati da un'origine, ad esempio un servizio Windows Communication Foundation (WCF).  
  
 [!code-csharp[PortableClassLibraryMVVM#2](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customerrepository.cs#2)]
 [!code-vb[PortableClassLibraryMVVM#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerrepository.vb#2)]  
  
### <a name="view-model"></a>Modello di visualizzazione  
 Una classe di base per i modelli di visualizzazione spesso viene aggiunto quando si implementa il modello MVVM. Nell'esempio seguente viene illustrata una classe base.  
  
 [!code-csharp[PortableClassLibraryMVVM#3](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/viewmodelbase.cs#3)]
 [!code-vb[PortableClassLibraryMVVM#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/viewmodelbase.vb#3)]  
  
 Un'implementazione del <xref:System.Windows.Input.ICommand> interfaccia viene spesso utilizzata con il modello MVVM. Nell'esempio seguente viene illustrata un'implementazione dell'interfaccia <xref:System.Windows.Input.ICommand>.  
  
 [!code-csharp[PortableClassLibraryMVVM#4](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/relaycommand.cs#4)]
 [!code-vb[PortableClassLibraryMVVM#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/relaycommand.vb#4)]  
  
 Nell'esempio seguente viene illustrato un modello di visualizzazione semplificata.  
  
 [!code-csharp[PortableClassLibraryMVVM#5](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainpageviewmodel.cs#5)]
 [!code-vb[PortableClassLibraryMVVM#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerviewmodel.vb#5)]  
  
### <a name="view"></a>Visualizza  
 Da un [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] app [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app, app basate su Silverlight o un'app di Windows Phone 7.5, è possibile fare riferimento all'assembly che contiene i progetti di modello e visualizzazione del modello.  Quindi possibile creare una vista che interagisce con il modello di visualizzazione. Nell'esempio seguente mostra un'app di Windows Presentation Foundation (WPF) semplificata che recupera e aggiorna i dati dal modello di visualizzazione. È possibile creare visualizzazioni analoghe in Silverlight, Windows Phone, o [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app.  
  
 [!code-xaml[PortableClassLibraryMVVM#6](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainwindow.xaml#6)]  
  
## <a name="see-also"></a>Vedere anche  
 [Libreria di classi portabile](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)
