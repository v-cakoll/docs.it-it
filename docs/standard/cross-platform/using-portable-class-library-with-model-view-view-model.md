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
ms.openlocfilehash: e39a8df5c8aee05414e778f15a29bbeda8dba930
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="using-portable-class-library-with-model-view-view-model"></a><span data-ttu-id="405fc-102">Utilizzo della libreria di classi portabile con MVVM (Model-View-View Model)</span><span class="sxs-lookup"><span data-stu-id="405fc-102">Using Portable Class Library with Model-View-View Model</span></span>
<span data-ttu-id="405fc-103">È possibile utilizzare .NET Framework [libreria di classi portabile](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) per implementare il modello Model-View-View MVVM (Model) e condividere gli assembly in più piattaforme.</span><span class="sxs-lookup"><span data-stu-id="405fc-103">You can use the .NET Framework [Portable Class Library](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) to implement the Model-View-View Model (MVVM) pattern and share assemblies across multiple platforms.</span></span>  
  
 <span data-ttu-id="405fc-104">MVVM è un modello di applicazione tramite cui l'interfaccia utente viene isolata dalla logica di business sottostante.</span><span class="sxs-lookup"><span data-stu-id="405fc-104">MVVM is an application pattern that isolates the user interface from the underlying business logic.</span></span> <span data-ttu-id="405fc-105">È possibile implementare il modello e visualizzare le classi del modello in un progetto [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] di [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)] e, successivamente, creare visualizzazioni personalizzate per piattaforme diverse.</span><span class="sxs-lookup"><span data-stu-id="405fc-105">You can implement the model and view model classes in a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], and then create views that are customized for different platforms.</span></span> <span data-ttu-id="405fc-106">Questo approccio consente di scrivere una sola volta il modello dati e la logica di business e di utilizzare questo codice nelle applicazioni .NET Framework, Silverlight, Windows Phone e [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="405fc-106">This approach enables you to write the data model and business logic only once, and use that code from .NET Framework, Silverlight, Windows Phone, and [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps, as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="405fc-107">![Portabile con diagramma MVVM](../../../docs/standard/cross-platform/media/portablemvvmdiagram.png "PortableMVVMdiagram")</span><span class="sxs-lookup"><span data-stu-id="405fc-107">![Portable with MVVM diagram](../../../docs/standard/cross-platform/media/portablemvvmdiagram.png "PortableMVVMdiagram")</span></span>  
  
 <span data-ttu-id="405fc-108">In questo argomento non fornisce informazioni generali sul modello MVVM.</span><span class="sxs-lookup"><span data-stu-id="405fc-108">This topic does not provide general information about the MVVM pattern.</span></span> <span data-ttu-id="405fc-109">Fornisce solo informazioni su come usare [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] implementare MVVM.</span><span class="sxs-lookup"><span data-stu-id="405fc-109">It only provides information about how to use [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] to implement MVVM.</span></span> <span data-ttu-id="405fc-110">Per ulteriori informazioni su MVVM, vedere il [delle Guide rapide MVVM](http://go.microsoft.com/fwlink/?LinkId=234934).</span><span class="sxs-lookup"><span data-stu-id="405fc-110">For more information about MVVM, see the [MVVM Quickstart](http://go.microsoft.com/fwlink/?LinkId=234934).</span></span>  
  
## <a name="classes-that-support-mvvm"></a><span data-ttu-id="405fc-111">Classi che supportano MVVM</span><span class="sxs-lookup"><span data-stu-id="405fc-111">Classes That Support MVVM</span></span>  
 <span data-ttu-id="405fc-112">Se la destinazione di [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], Silverlight, o Windows Phone 7.5 per il [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] progetto, le classi seguenti sono disponibili per implementare il modello MVVM:</span><span class="sxs-lookup"><span data-stu-id="405fc-112">When you target the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], Silverlight, or Windows Phone 7.5 for your [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project, the following classes are available for implementing the MVVM pattern:</span></span>  
  
-   <span data-ttu-id="405fc-113">Classe <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="405fc-113"><xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="405fc-114">Classe <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="405fc-114"><xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="405fc-115">Classe <xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="405fc-115"><xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="405fc-116">Classe <xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="405fc-116"><xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="405fc-117">Classe <xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="405fc-117"><xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="405fc-118">Classe <xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="405fc-118"><xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="405fc-119">Classe <xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="405fc-119"><xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="405fc-120">Classe <xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="405fc-120"><xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="405fc-121">Classe <xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="405fc-121"><xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="405fc-122">Classe <xref:System.Windows.Input.ICommand?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="405fc-122"><xref:System.Windows.Input.ICommand?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="405fc-123">Tutte le classi di <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> dello spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="405fc-123">All classes in the <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> namespace</span></span>  
  
## <a name="implementing-mvvm"></a><span data-ttu-id="405fc-124">Implementazione MVVM</span><span class="sxs-lookup"><span data-stu-id="405fc-124">Implementing MVVM</span></span>  
 <span data-ttu-id="405fc-125">Per implementare MVVM, si crea in genere il modello sia il modello di visualizzazione in un [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] progetto, perché un [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] progetto non può fare riferimento a un progetto non portatile.</span><span class="sxs-lookup"><span data-stu-id="405fc-125">To implement MVVM, you typically create both the model and the view model in a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project, because a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project cannot reference a non-portable project.</span></span> <span data-ttu-id="405fc-126">Il modello e il modello di visualizzazione può essere nello stesso progetto o in progetti separati.</span><span class="sxs-lookup"><span data-stu-id="405fc-126">The model and view model can be in the same project or in separate projects.</span></span> <span data-ttu-id="405fc-127">Se si utilizzano progetti separati, aggiungere un riferimento dal progetto di modello di visualizzazione per il progetto di modello.</span><span class="sxs-lookup"><span data-stu-id="405fc-127">If you use separate projects, add a reference from the view model project to the model project.</span></span>  
  
 <span data-ttu-id="405fc-128">Dopo la compilazione del modello e visualizza i progetti di modello, fare riferimento a tali assembly nell'app contenente la vista.</span><span class="sxs-lookup"><span data-stu-id="405fc-128">After you compile the model and view model projects, you reference those assemblies in the app that contains the view.</span></span> <span data-ttu-id="405fc-129">Se la vista interagisce solo con il modello di visualizzazione, è necessario fare riferimento all'assembly che contiene il modello di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="405fc-129">If the view interacts only with the view model, you only have to reference the assembly that contains the view model.</span></span>  
  
### <a name="model"></a><span data-ttu-id="405fc-130">Modello</span><span class="sxs-lookup"><span data-stu-id="405fc-130">Model</span></span>  
 <span data-ttu-id="405fc-131">Nell'esempio seguente viene illustrata una classe di modello semplificato che potrebbe trovarsi in un [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] progetto.</span><span class="sxs-lookup"><span data-stu-id="405fc-131">The following example shows a simplified model class that could reside in a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project.</span></span>  
  
 [!code-csharp[PortableClassLibraryMVVM#1](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customer.cs#1)]
 [!code-vb[PortableClassLibraryMVVM#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customer.vb#1)]  
  
 <span data-ttu-id="405fc-132">Nell'esempio seguente viene illustrato un modo semplice per inserire, recuperare e aggiornare i dati in un [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] progetto.</span><span class="sxs-lookup"><span data-stu-id="405fc-132">The following example shows a simple way to populate, retrieve, and update the data in a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project.</span></span> <span data-ttu-id="405fc-133">In un'applicazione reale, è necessario recuperare i dati da un'origine, ad esempio un servizio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="405fc-133">In a real app, you would retrieve the data from a source such as a Windows Communication Foundation (WCF) service.</span></span>  
  
 [!code-csharp[PortableClassLibraryMVVM#2](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customerrepository.cs#2)]
 [!code-vb[PortableClassLibraryMVVM#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerrepository.vb#2)]  
  
### <a name="view-model"></a><span data-ttu-id="405fc-134">Modello di visualizzazione</span><span class="sxs-lookup"><span data-stu-id="405fc-134">View Model</span></span>  
 <span data-ttu-id="405fc-135">Una classe di base per i modelli di visualizzazione spesso viene aggiunto quando si implementa il modello MVVM.</span><span class="sxs-lookup"><span data-stu-id="405fc-135">A base class for view models is frequently added when implementing the MVVM pattern.</span></span> <span data-ttu-id="405fc-136">Nell'esempio seguente viene illustrata una classe base.</span><span class="sxs-lookup"><span data-stu-id="405fc-136">The following example shows a base class.</span></span>  
  
 [!code-csharp[PortableClassLibraryMVVM#3](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/viewmodelbase.cs#3)]
 [!code-vb[PortableClassLibraryMVVM#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/viewmodelbase.vb#3)]  
  
 <span data-ttu-id="405fc-137">Un'implementazione del <xref:System.Windows.Input.ICommand> interfaccia viene spesso utilizzata con il modello MVVM.</span><span class="sxs-lookup"><span data-stu-id="405fc-137">An implementation of the <xref:System.Windows.Input.ICommand> interface is frequently used with the MVVM pattern.</span></span> <span data-ttu-id="405fc-138">Nell'esempio seguente viene illustrata un'implementazione dell'interfaccia <xref:System.Windows.Input.ICommand>.</span><span class="sxs-lookup"><span data-stu-id="405fc-138">The following example shows an implementation of the <xref:System.Windows.Input.ICommand> interface.</span></span>  
  
 [!code-csharp[PortableClassLibraryMVVM#4](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/relaycommand.cs#4)]
 [!code-vb[PortableClassLibraryMVVM#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/relaycommand.vb#4)]  
  
 <span data-ttu-id="405fc-139">Nell'esempio seguente viene illustrato un modello di visualizzazione semplificata.</span><span class="sxs-lookup"><span data-stu-id="405fc-139">The following example shows a simplified view model.</span></span>  
  
 [!code-csharp[PortableClassLibraryMVVM#5](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainpageviewmodel.cs#5)]
 [!code-vb[PortableClassLibraryMVVM#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerviewmodel.vb#5)]  
  
### <a name="view"></a><span data-ttu-id="405fc-140">Visualizza</span><span class="sxs-lookup"><span data-stu-id="405fc-140">View</span></span>  
 <span data-ttu-id="405fc-141">Da un [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] app [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app, app basate su Silverlight o un'app di Windows Phone 7.5, è possibile fare riferimento all'assembly che contiene i progetti di modello e visualizzazione del modello.</span><span class="sxs-lookup"><span data-stu-id="405fc-141">From a [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] app, [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app, Silverlight-based app, or Windows Phone 7.5 app, you can reference the assembly that contains the model and view model projects.</span></span>  <span data-ttu-id="405fc-142">Quindi possibile creare una vista che interagisce con il modello di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="405fc-142">You then create a view that interacts with the view model.</span></span> <span data-ttu-id="405fc-143">Nell'esempio seguente mostra un'app di Windows Presentation Foundation (WPF) semplificata che recupera e aggiorna i dati dal modello di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="405fc-143">The following example shows a simplified Windows Presentation Foundation (WPF) app that retrieves and updates data from the view model.</span></span> <span data-ttu-id="405fc-144">È possibile creare visualizzazioni analoghe in Silverlight, Windows Phone, o [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app.</span><span class="sxs-lookup"><span data-stu-id="405fc-144">You could create similar views in Silverlight, Windows Phone, or [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span>  
  
 [!code-xaml[PortableClassLibraryMVVM#6](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainwindow.xaml#6)]  
  
## <a name="see-also"></a><span data-ttu-id="405fc-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="405fc-145">See Also</span></span>  
 [<span data-ttu-id="405fc-146">Libreria di classi portabile</span><span class="sxs-lookup"><span data-stu-id="405fc-146">Portable Class Library</span></span>](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)
