---
title: 'Procedura: Ottenere la visualizzazione predefinita di una raccolta dati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], creating views of
- data binding [WPF], creating views of data collections
ms.assetid: b641e96c-c2f6-42ea-9c5d-bac81176ad65
ms.openlocfilehash: 746331e69ee1e5eee795a0e35202f4889b72c53f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61931516"
---
# <a name="how-to-get-the-default-view-of-a-data-collection"></a><span data-ttu-id="883b0-102">Procedura: Ottenere la visualizzazione predefinita di una raccolta dati</span><span class="sxs-lookup"><span data-stu-id="883b0-102">How to: Get the Default View of a Data Collection</span></span>
<span data-ttu-id="883b0-103">Le viste consentono la stessa raccolta di dati da visualizzare in modi diversi, a seconda di ordinamento, filtro o criteri di raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="883b0-103">Views allow the same data collection to be viewed in different ways, depending on sorting, filtering, or grouping criteria.</span></span> <span data-ttu-id="883b0-104">Ogni raccolta ha una visualizzazione condivisa predefinita, viene usata come origine del binding effettivo quando un'associazione specifica una raccolta come origine.</span><span class="sxs-lookup"><span data-stu-id="883b0-104">Every collection has one shared default view, which is used as the actual binding source when a binding specifies a collection as its source.</span></span> <span data-ttu-id="883b0-105">In questo esempio viene illustrato come ottenere la visualizzazione predefinita di una raccolta.</span><span class="sxs-lookup"><span data-stu-id="883b0-105">This example shows how to get the default view of a collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="883b0-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="883b0-106">Example</span></span>  
 <span data-ttu-id="883b0-107">Per creare una vista, è necessario un riferimento all'oggetto alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="883b0-107">To create the view, you need an object reference to the collection.</span></span> <span data-ttu-id="883b0-108">È possibile ottenere questo oggetto dati facendo riferimento a un code-behind oggetto personalizzato, ottenendo il contesto dei dati, ottenendo una proprietà dell'origine dati oppure ottenendo una proprietà dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="883b0-108">This data object can be obtained by referencing your own code-behind object, by getting the data context, by getting a property of the data source, or by getting a property of the binding.</span></span> <span data-ttu-id="883b0-109">In questo esempio viene illustrato come ottenere il <xref:System.Windows.FrameworkElement.DataContext%2A> di un oggetto dati e utilizzarlo per ottenere direttamente la raccolta predefinita consente di visualizzare per questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="883b0-109">This example shows how to get the <xref:System.Windows.FrameworkElement.DataContext%2A> of a data object and use it to directly obtain the default collection view for this collection.</span></span>  
  
 [!code-csharp[CollectionView#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#2)]
 [!code-vb[CollectionView#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#2)]  
  
 <span data-ttu-id="883b0-110">In questo esempio, l'elemento radice è un <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="883b0-110">In this example, the root element is a <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="883b0-111">Il <xref:System.Windows.FrameworkElement.DataContext%2A> è impostata su *myDataSource*, che fa riferimento a un provider di dati che è un <xref:System.Collections.ObjectModel.ObservableCollection%601> dei *ordine* oggetti.</span><span class="sxs-lookup"><span data-stu-id="883b0-111">The <xref:System.Windows.FrameworkElement.DataContext%2A> is set to *myDataSource*, which refers to a data provider that is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of *Order* objects.</span></span>  
  
 [!code-xaml[CollectionView#CollectionViewDataContext](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml#collectionviewdatacontext)]  
  
 <span data-ttu-id="883b0-112">In alternativa, è possibile creare un'istanza e associare alla propria visualizzazione raccolta utilizzando il <xref:System.Windows.Data.CollectionViewSource> classe.</span><span class="sxs-lookup"><span data-stu-id="883b0-112">Alternatively, you can instantiate and bind to your own collection view using the <xref:System.Windows.Data.CollectionViewSource> class.</span></span> <span data-ttu-id="883b0-113">Questa vista raccolta è condivisa solo dai controlli associati a esso direttamente.</span><span class="sxs-lookup"><span data-stu-id="883b0-113">This collection view is only shared by controls that bind to it directly.</span></span> <span data-ttu-id="883b0-114">Per un esempio, vedere la procedura crea una visualizzazione sezione la [Panoramica sul Data Binding](data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="883b0-114">For an example, see the How to Create a View section in the [Data Binding Overview](data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="883b0-115">Per esempi delle funzionalità fornite da una visualizzazione di raccolta, vedere [ordinare i dati in una vista](how-to-sort-data-in-a-view.md), [filtrare i dati in una vista](how-to-filter-data-in-a-view.md), e [tra gli oggetti in una visualizzazione di raccolta dati](how-to-navigate-through-the-objects-in-a-data-collectionview.md).</span><span class="sxs-lookup"><span data-stu-id="883b0-115">For examples of the functionality provided by a collection view, see [Sort Data in a View](how-to-sort-data-in-a-view.md), [Filter Data in a View](how-to-filter-data-in-a-view.md), and [Navigate Through the Objects in a Data CollectionView](how-to-navigate-through-the-objects-in-a-data-collectionview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="883b0-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="883b0-116">See also</span></span>

- [<span data-ttu-id="883b0-117">Ordinare e raggruppare dati con una visualizzazione in XAML</span><span class="sxs-lookup"><span data-stu-id="883b0-117">Sort and Group Data Using a View in XAML</span></span>](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [<span data-ttu-id="883b0-118">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="883b0-118">How-to Topics</span></span>](data-binding-how-to-topics.md)
