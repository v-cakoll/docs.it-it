---
title: 'Procedura: ottenere la visualizzazione predefinita di una raccolta dati'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], creating views of
- data binding [WPF], creating views of data collections
ms.assetid: b641e96c-c2f6-42ea-9c5d-bac81176ad65
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 86d1ababcb7a00496b59005b5e90f875511fefc4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-get-the-default-view-of-a-data-collection"></a><span data-ttu-id="f3790-102">Procedura: ottenere la visualizzazione predefinita di una raccolta dati</span><span class="sxs-lookup"><span data-stu-id="f3790-102">How to: Get the Default View of a Data Collection</span></span>
<span data-ttu-id="f3790-103">Le viste consentono la stessa raccolta di dati da visualizzare in modi diversi, a seconda di ordinamento, filtro o i criteri di raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="f3790-103">Views allow the same data collection to be viewed in different ways, depending on sorting, filtering, or grouping criteria.</span></span> <span data-ttu-id="f3790-104">Ogni raccolta dispone di una visualizzazione predefinita condivisa, che viene utilizzata come origine di associazione effettiva quando un'associazione specifica una raccolta come origine.</span><span class="sxs-lookup"><span data-stu-id="f3790-104">Every collection has one shared default view, which is used as the actual binding source when a binding specifies a collection as its source.</span></span> <span data-ttu-id="f3790-105">In questo esempio viene illustrato come ottenere la visualizzazione predefinita di una raccolta.</span><span class="sxs-lookup"><span data-stu-id="f3790-105">This example shows how to get the default view of a collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3790-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="f3790-106">Example</span></span>  
 <span data-ttu-id="f3790-107">Per creare una vista, è necessario un riferimento all'oggetto alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="f3790-107">To create the view, you need an object reference to the collection.</span></span> <span data-ttu-id="f3790-108">È possibile ottenere questo oggetto dati facendo riferimento a un oggetto di codice, ottenendo il contesto dei dati, una proprietà dell'origine dati o una proprietà dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="f3790-108">This data object can be obtained by referencing your own code-behind object, by getting the data context, by getting a property of the data source, or by getting a property of the binding.</span></span> <span data-ttu-id="f3790-109">In questo esempio viene illustrato come ottenere il <xref:System.Windows.FrameworkElement.DataContext%2A> di un oggetto dati e utilizzarlo per ottenere direttamente l'insieme predefinito visualizzazione per questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="f3790-109">This example shows how to get the <xref:System.Windows.FrameworkElement.DataContext%2A> of a data object and use it to directly obtain the default collection view for this collection.</span></span>  
  
 [!code-csharp[CollectionView#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#2)]
 [!code-vb[CollectionView#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#2)]  
  
 <span data-ttu-id="f3790-110">In questo esempio, l'elemento radice è un <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="f3790-110">In this example, the root element is a <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="f3790-111">Il <xref:System.Windows.FrameworkElement.DataContext%2A> è impostato su *myDataSource*, che fa riferimento a un provider di dati che è un <xref:System.Collections.ObjectModel.ObservableCollection%601> di *ordine* oggetti.</span><span class="sxs-lookup"><span data-stu-id="f3790-111">The <xref:System.Windows.FrameworkElement.DataContext%2A> is set to *myDataSource*, which refers to a data provider that is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of *Order* objects.</span></span>  
  
 [!code-xaml[CollectionView#CollectionViewDataContext](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml#collectionviewdatacontext)]  
  
 <span data-ttu-id="f3790-112">In alternativa, è possibile creare un'istanza e associare la propria visualizzazione raccolta utilizzando la <xref:System.Windows.Data.CollectionViewSource> classe.</span><span class="sxs-lookup"><span data-stu-id="f3790-112">Alternatively, you can instantiate and bind to your own collection view using the <xref:System.Windows.Data.CollectionViewSource> class.</span></span> <span data-ttu-id="f3790-113">Questa visualizzazione della raccolta è condivisa solo dai controlli a esso associati direttamente.</span><span class="sxs-lookup"><span data-stu-id="f3790-113">This collection view is only shared by controls that bind to it directly.</span></span> <span data-ttu-id="f3790-114">Per un esempio, vedere la procedura per creare una vista sezione la [Panoramica del Data Binding](../../../../docs/framework/wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f3790-114">For an example, see the How to Create a View section in the [Data Binding Overview](../../../../docs/framework/wpf/data/data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="f3790-115">Per esempi delle funzionalità fornite da una vista di raccolta, vedere [ordinare i dati in una vista](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md), [filtrare i dati in una vista](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md), e [passare attraverso il oggetti in una visualizzazione di raccolta dati](../../../../docs/framework/wpf/data/how-to-navigate-through-the-objects-in-a-data-collectionview.md).</span><span class="sxs-lookup"><span data-stu-id="f3790-115">For examples of the functionality provided by a collection view, see [Sort Data in a View](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md), [Filter Data in a View](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md), and [Navigate Through the Objects in a Data CollectionView](../../../../docs/framework/wpf/data/how-to-navigate-through-the-objects-in-a-data-collectionview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3790-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3790-116">See Also</span></span>  
 [<span data-ttu-id="f3790-117">Ordinare e raggruppare dati con una visualizzazione in XAML</span><span class="sxs-lookup"><span data-stu-id="f3790-117">Sort and Group Data Using a View in XAML</span></span>](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)  
 [<span data-ttu-id="f3790-118">Procedure relative</span><span class="sxs-lookup"><span data-stu-id="f3790-118">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
