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
ms.openlocfilehash: ff34b295ba443088115d470d8ade0c986ac1d856
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288849"
---
# <a name="using-portable-class-library-with-model-view-view-model"></a><span data-ttu-id="ada6f-102">Utilizzo della libreria di classi portabile con MVVM (Model-View-View Model)</span><span class="sxs-lookup"><span data-stu-id="ada6f-102">Using Portable Class Library with Model-View-View Model</span></span>
<span data-ttu-id="ada6f-103">È possibile usare la [libreria di classi](cross-platform-development-with-the-portable-class-library.md) portabile .NET Framework per implementare il modello MVVM (Model-View-View Model) e condividere gli assembly in più piattaforme.</span><span class="sxs-lookup"><span data-stu-id="ada6f-103">You can use the .NET Framework [Portable Class Library](cross-platform-development-with-the-portable-class-library.md) to implement the Model-View-View Model (MVVM) pattern and share assemblies across multiple platforms.</span></span>

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

 <span data-ttu-id="ada6f-104">MVVM è un modello di applicazione tramite cui l'interfaccia utente viene isolata dalla logica di business sottostante.</span><span class="sxs-lookup"><span data-stu-id="ada6f-104">MVVM is an application pattern that isolates the user interface from the underlying business logic.</span></span> <span data-ttu-id="ada6f-105">È possibile implementare le classi modello e visualizza modello in un progetto libreria di classi portabile in Visual Studio 2012, quindi creare visualizzazioni personalizzate per piattaforme diverse.</span><span class="sxs-lookup"><span data-stu-id="ada6f-105">You can implement the model and view model classes in a Portable Class Library project in Visual Studio 2012, and then create views that are customized for different platforms.</span></span> <span data-ttu-id="ada6f-106">Questo approccio consente di scrivere il modello di dati e la logica di business solo una volta e di utilizzare tale codice dalle app .NET Framework, Silverlight, Windows Phone e Windows 8. x Store, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="ada6f-106">This approach enables you to write the data model and business logic only once, and use that code from .NET Framework, Silverlight, Windows Phone, and Windows 8.x Store apps, as shown in the following illustration.</span></span>

 ![Mostra la libreria di classi portabile con gli assembly di condivisione MVVM su più piattaforme.](./media/using-portable-class-library-with-model-view-view-model/mvvm-share-assemblies-across-platforms.png)

 <span data-ttu-id="ada6f-108">In questo argomento non vengono fornite informazioni generali sul modello MVVM.</span><span class="sxs-lookup"><span data-stu-id="ada6f-108">This topic does not provide general information about the MVVM pattern.</span></span> <span data-ttu-id="ada6f-109">Fornisce solo informazioni su come usare la libreria di classi portabile per implementare MVVM.</span><span class="sxs-lookup"><span data-stu-id="ada6f-109">It only provides information about how to use Portable Class Library to implement MVVM.</span></span> <span data-ttu-id="ada6f-110">Per ulteriori informazioni su MVVM, vedere la [Guida introduttiva di MVVM utilizzando la libreria Prism 5,0 per WPF](https://docs.microsoft.com/previous-versions/msp-n-p/gg430857(v=pandp.40)).</span><span class="sxs-lookup"><span data-stu-id="ada6f-110">For more information about MVVM, see the [MVVM Quickstart Using the Prism Library 5.0 for WPF](https://docs.microsoft.com/previous-versions/msp-n-p/gg430857(v=pandp.40)).</span></span>

## <a name="classes-that-support-mvvm"></a><span data-ttu-id="ada6f-111">Classi che supportano MVVM</span><span class="sxs-lookup"><span data-stu-id="ada6f-111">Classes That Support MVVM</span></span>
 <span data-ttu-id="ada6f-112">Quando la destinazione è la .NET Framework 4,5, .NET per le app di Windows 8. x Store, Silverlight o Windows Phone 7,5 per il progetto libreria di classi portabile, sono disponibili le classi seguenti per implementare il modello MVVM:</span><span class="sxs-lookup"><span data-stu-id="ada6f-112">When you target the .NET Framework 4.5, .NET for Windows 8.x Store apps, Silverlight, or Windows Phone 7.5 for your Portable Class Library project, the following classes are available for implementing the MVVM pattern:</span></span>

- <span data-ttu-id="ada6f-113">Classe <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ada6f-113"><xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="ada6f-114">Classe <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ada6f-114"><xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="ada6f-115">Classe <xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ada6f-115"><xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="ada6f-116">Classe <xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ada6f-116"><xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="ada6f-117">Classe <xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ada6f-117"><xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="ada6f-118">Classe <xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ada6f-118"><xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="ada6f-119">Classe <xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ada6f-119"><xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="ada6f-120">Classe <xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ada6f-120"><xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="ada6f-121">Classe <xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ada6f-121"><xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="ada6f-122">Classe <xref:System.Windows.Input.ICommand?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ada6f-122"><xref:System.Windows.Input.ICommand?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="ada6f-123">Tutte le classi nello <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="ada6f-123">All classes in the <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> namespace</span></span>

## <a name="implementing-mvvm"></a><span data-ttu-id="ada6f-124">Implementazione di MVVM</span><span class="sxs-lookup"><span data-stu-id="ada6f-124">Implementing MVVM</span></span>
 <span data-ttu-id="ada6f-125">Per implementare MVVM, in genere si creano sia il modello che il modello di visualizzazione in un progetto libreria di classi portabile, perché un progetto libreria di classi portabile non può fare riferimento a un progetto non portabile.</span><span class="sxs-lookup"><span data-stu-id="ada6f-125">To implement MVVM, you typically create both the model and the view model in a Portable Class Library project, because a Portable Class Library project cannot reference a non-portable project.</span></span> <span data-ttu-id="ada6f-126">Il modello e il modello di visualizzazione possono trovarsi nello stesso progetto o in progetti distinti.</span><span class="sxs-lookup"><span data-stu-id="ada6f-126">The model and view model can be in the same project or in separate projects.</span></span> <span data-ttu-id="ada6f-127">Se si utilizzano progetti distinti, aggiungere un riferimento dal progetto di modello di visualizzazione al progetto di modello.</span><span class="sxs-lookup"><span data-stu-id="ada6f-127">If you use separate projects, add a reference from the view model project to the model project.</span></span>

 <span data-ttu-id="ada6f-128">Dopo la compilazione del modello e la visualizzazione dei progetti di modello, è possibile fare riferimento a tali assembly nell'app che contiene la vista.</span><span class="sxs-lookup"><span data-stu-id="ada6f-128">After you compile the model and view model projects, you reference those assemblies in the app that contains the view.</span></span> <span data-ttu-id="ada6f-129">Se la vista interagisce solo con il modello di visualizzazione, è necessario fare riferimento solo all'assembly che contiene il modello di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="ada6f-129">If the view interacts only with the view model, you only have to reference the assembly that contains the view model.</span></span>

### <a name="model"></a><span data-ttu-id="ada6f-130">Modello</span><span class="sxs-lookup"><span data-stu-id="ada6f-130">Model</span></span>
 <span data-ttu-id="ada6f-131">Nell'esempio seguente viene illustrata una classe di modello semplificata che può risiedere in un progetto libreria di classi portabile.</span><span class="sxs-lookup"><span data-stu-id="ada6f-131">The following example shows a simplified model class that could reside in a Portable Class Library project.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#1](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customer.cs#1)]
 [!code-vb[PortableClassLibraryMVVM#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customer.vb#1)]

 <span data-ttu-id="ada6f-132">Nell'esempio seguente viene illustrato un modo semplice per popolare, recuperare e aggiornare i dati in un progetto libreria di classi portabile.</span><span class="sxs-lookup"><span data-stu-id="ada6f-132">The following example shows a simple way to populate, retrieve, and update the data in a Portable Class Library project.</span></span> <span data-ttu-id="ada6f-133">In un'app reale è possibile recuperare i dati da un'origine, ad esempio un servizio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="ada6f-133">In a real app, you would retrieve the data from a source such as a Windows Communication Foundation (WCF) service.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#2](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customerrepository.cs#2)]
 [!code-vb[PortableClassLibraryMVVM#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerrepository.vb#2)]

### <a name="view-model"></a><span data-ttu-id="ada6f-134">Visualizza modello</span><span class="sxs-lookup"><span data-stu-id="ada6f-134">View Model</span></span>
 <span data-ttu-id="ada6f-135">Una classe di base per i modelli di visualizzazione viene aggiunta spesso quando si implementa il modello MVVM.</span><span class="sxs-lookup"><span data-stu-id="ada6f-135">A base class for view models is frequently added when implementing the MVVM pattern.</span></span> <span data-ttu-id="ada6f-136">Nell'esempio seguente viene illustrata una classe di base.</span><span class="sxs-lookup"><span data-stu-id="ada6f-136">The following example shows a base class.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#3](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/viewmodelbase.cs#3)]
 [!code-vb[PortableClassLibraryMVVM#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/viewmodelbase.vb#3)]

 <span data-ttu-id="ada6f-137"><xref:System.Windows.Input.ICommand>Con il modello MVVM viene spesso usata un'implementazione dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="ada6f-137">An implementation of the <xref:System.Windows.Input.ICommand> interface is frequently used with the MVVM pattern.</span></span> <span data-ttu-id="ada6f-138">Nell'esempio seguente viene illustrata un'implementazione dell'interfaccia <xref:System.Windows.Input.ICommand>.</span><span class="sxs-lookup"><span data-stu-id="ada6f-138">The following example shows an implementation of the <xref:System.Windows.Input.ICommand> interface.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#4](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/relaycommand.cs#4)]
 [!code-vb[PortableClassLibraryMVVM#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/relaycommand.vb#4)]

 <span data-ttu-id="ada6f-139">Nell'esempio seguente viene illustrato un modello di visualizzazione semplificato.</span><span class="sxs-lookup"><span data-stu-id="ada6f-139">The following example shows a simplified view model.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#5](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainpageviewmodel.cs#5)]
 [!code-vb[PortableClassLibraryMVVM#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerviewmodel.vb#5)]  
  
### <a name="view"></a><span data-ttu-id="ada6f-140">Visualizzazione</span><span class="sxs-lookup"><span data-stu-id="ada6f-140">View</span></span>  
 <span data-ttu-id="ada6f-141">Da un'app .NET Framework 4,5, un'app di Windows 8. x Store, un'app basata su Silverlight o un'app Windows Phone 7,5, è possibile fare riferimento all'assembly che contiene i progetti modello e visualizza modello.</span><span class="sxs-lookup"><span data-stu-id="ada6f-141">From a .NET Framework 4.5 app, Windows 8.x Store app, Silverlight-based app, or Windows Phone 7.5 app, you can reference the assembly that contains the model and view model projects.</span></span>  <span data-ttu-id="ada6f-142">Si crea quindi una vista che interagisce con il modello di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="ada6f-142">You then create a view that interacts with the view model.</span></span> <span data-ttu-id="ada6f-143">Nell'esempio seguente viene illustrata un'app semplificata Windows Presentation Foundation (WPF) che recupera e aggiorna i dati dal modello di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="ada6f-143">The following example shows a simplified Windows Presentation Foundation (WPF) app that retrieves and updates data from the view model.</span></span> <span data-ttu-id="ada6f-144">È possibile creare visualizzazioni simili in Silverlight, Windows Phone o app di Windows 8. x Store.</span><span class="sxs-lookup"><span data-stu-id="ada6f-144">You could create similar views in Silverlight, Windows Phone, or Windows 8.x Store apps.</span></span>  
  
 [!code-xaml[PortableClassLibraryMVVM#6](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainwindow.xaml#6)]  
  
## <a name="see-also"></a><span data-ttu-id="ada6f-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ada6f-145">See also</span></span>

- [<span data-ttu-id="ada6f-146">Libreria di classi portabile</span><span class="sxs-lookup"><span data-stu-id="ada6f-146">Portable Class Library</span></span>](cross-platform-development-with-the-portable-class-library.md)
