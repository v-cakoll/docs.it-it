---
title: 'Procedura: ottenere la visualizzazione predefinita di una raccolta dati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], creating views of
- data binding [WPF], creating views of data collections
ms.assetid: b641e96c-c2f6-42ea-9c5d-bac81176ad65
ms.openlocfilehash: e82d252ed82e4d2e6d641e8b60e890cc93bb0427
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459124"
---
# <a name="how-to-get-the-default-view-of-a-data-collection"></a><span data-ttu-id="8b3c9-102">Procedura: ottenere la visualizzazione predefinita di una raccolta dati</span><span class="sxs-lookup"><span data-stu-id="8b3c9-102">How to: Get the Default View of a Data Collection</span></span>
<span data-ttu-id="8b3c9-103">Le visualizzazioni consentono di visualizzare la stessa raccolta dati in modi diversi, a seconda dei criteri di ordinamento, di filtro o di raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="8b3c9-103">Views allow the same data collection to be viewed in different ways, depending on sorting, filtering, or grouping criteria.</span></span> <span data-ttu-id="8b3c9-104">Ogni raccolta dispone di una visualizzazione predefinita condivisa, che viene utilizzata come origine di associazione effettiva quando un'associazione specifica una raccolta come origine.</span><span class="sxs-lookup"><span data-stu-id="8b3c9-104">Every collection has one shared default view, which is used as the actual binding source when a binding specifies a collection as its source.</span></span> <span data-ttu-id="8b3c9-105">Questo esempio illustra come ottenere la visualizzazione predefinita di una raccolta.</span><span class="sxs-lookup"><span data-stu-id="8b3c9-105">This example shows how to get the default view of a collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b3c9-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="8b3c9-106">Example</span></span>  
 <span data-ttu-id="8b3c9-107">Per creare la vista, è necessario un riferimento a un oggetto alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="8b3c9-107">To create the view, you need an object reference to the collection.</span></span> <span data-ttu-id="8b3c9-108">È possibile ottenere questo oggetto dati facendo riferimento al proprio oggetto code-behind, ottenendo il contesto dei dati, ottenendo una proprietà dell'origine dati o ottenendo una proprietà dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="8b3c9-108">This data object can be obtained by referencing your own code-behind object, by getting the data context, by getting a property of the data source, or by getting a property of the binding.</span></span> <span data-ttu-id="8b3c9-109">In questo esempio viene illustrato come ottenere il <xref:System.Windows.FrameworkElement.DataContext%2A> di un oggetto dati e utilizzarlo per ottenere direttamente la visualizzazione di raccolta predefinita per questa raccolta.</span><span class="sxs-lookup"><span data-stu-id="8b3c9-109">This example shows how to get the <xref:System.Windows.FrameworkElement.DataContext%2A> of a data object and use it to directly obtain the default collection view for this collection.</span></span>  
  
 [!code-csharp[CollectionView#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#2)]
 [!code-vb[CollectionView#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#2)]  
  
 <span data-ttu-id="8b3c9-110">In questo esempio, l'elemento radice è un <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="8b3c9-110">In this example, the root element is a <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="8b3c9-111">Il <xref:System.Windows.FrameworkElement.DataContext%2A> è impostato su *DataSource*, che fa riferimento a un provider di dati costituito da un <xref:System.Collections.ObjectModel.ObservableCollection%601> di oggetti *Order* .</span><span class="sxs-lookup"><span data-stu-id="8b3c9-111">The <xref:System.Windows.FrameworkElement.DataContext%2A> is set to *myDataSource*, which refers to a data provider that is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of *Order* objects.</span></span>  
  
 [!code-xaml[CollectionView#CollectionViewDataContext](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml#collectionviewdatacontext)]  
  
 <span data-ttu-id="8b3c9-112">In alternativa, è possibile creare un'istanza di e associarla alla propria visualizzazione di raccolta usando la classe <xref:System.Windows.Data.CollectionViewSource>.</span><span class="sxs-lookup"><span data-stu-id="8b3c9-112">Alternatively, you can instantiate and bind to your own collection view using the <xref:System.Windows.Data.CollectionViewSource> class.</span></span> <span data-ttu-id="8b3c9-113">Questa vista di raccolta è condivisa solo dai controlli che lo associano direttamente.</span><span class="sxs-lookup"><span data-stu-id="8b3c9-113">This collection view is only shared by controls that bind to it directly.</span></span> <span data-ttu-id="8b3c9-114">Per un esempio, vedere la sezione come creare una vista nella panoramica sul [Data Binding](../../../desktop-wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8b3c9-114">For an example, see the How to Create a View section in the [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="8b3c9-115">Per esempi della funzionalità fornita da una visualizzazione di raccolta, vedere [ordinare i dati in una visualizzazione](how-to-sort-data-in-a-view.md), [filtrare i dati in una visualizzazione](how-to-filter-data-in-a-view.md)e [spostarsi tra gli oggetti in una](how-to-navigate-through-the-objects-in-a-data-collectionview.md)raccolta di dati.</span><span class="sxs-lookup"><span data-stu-id="8b3c9-115">For examples of the functionality provided by a collection view, see [Sort Data in a View](how-to-sort-data-in-a-view.md), [Filter Data in a View](how-to-filter-data-in-a-view.md), and [Navigate Through the Objects in a Data CollectionView](how-to-navigate-through-the-objects-in-a-data-collectionview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b3c9-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b3c9-116">See also</span></span>

- [<span data-ttu-id="8b3c9-117">Ordinare e raggruppare dati con una visualizzazione in XAML</span><span class="sxs-lookup"><span data-stu-id="8b3c9-117">Sort and Group Data Using a View in XAML</span></span>](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [<span data-ttu-id="8b3c9-118">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="8b3c9-118">How-to Topics</span></span>](data-binding-how-to-topics.md)
