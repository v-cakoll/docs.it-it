---
title: 'Procedura: Ordinare i dati in una visualizzazione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], sorting data in views
- data binding [WPF], grouping data in views
- grouping data in views [WPF]
- views [WPF], sorting data
- views [WPF], grouping data
- sorting data in views [WPF]
ms.assetid: f4c43578-01b7-4774-a953-acb95a13b94a
ms.openlocfilehash: 41ee5cded04559acac5e7270c5e1a2450c70a5aa
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377119"
---
# <a name="how-to-sort-data-in-a-view"></a><span data-ttu-id="dbdf9-102">Procedura: Ordinare i dati in una visualizzazione</span><span class="sxs-lookup"><span data-stu-id="dbdf9-102">How to: Sort Data in a View</span></span>
<span data-ttu-id="dbdf9-103">In questo esempio viene descritto come ordinare i dati in una vista.</span><span class="sxs-lookup"><span data-stu-id="dbdf9-103">This example describes how to sort data in a view.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dbdf9-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="dbdf9-104">Example</span></span>  
 <span data-ttu-id="dbdf9-105">L'esempio seguente crea una semplice <xref:System.Windows.Controls.ListBox> e un <xref:System.Windows.Controls.Button>:</span><span class="sxs-lookup"><span data-stu-id="dbdf9-105">The following example creates a simple <xref:System.Windows.Controls.ListBox> and a <xref:System.Windows.Controls.Button>:</span></span>  
  
 [!code-xaml[ListBoxSort_snip#HowTo](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml#howto)]  
  
 <span data-ttu-id="dbdf9-106">Il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestore dell'evento del pulsante contiene la logica per ordinare gli elementi nel <xref:System.Windows.Controls.ListBox> in ordine decrescente.</span><span class="sxs-lookup"><span data-stu-id="dbdf9-106">The <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler of the button contains logic to sort the items in the <xref:System.Windows.Controls.ListBox> in the descending order.</span></span> <span data-ttu-id="dbdf9-107">È possibile eseguire questa operazione perché l'aggiunta di elementi una <xref:System.Windows.Controls.ListBox> in questo modo vengono aggiunte al <xref:System.Windows.Controls.ItemCollection> delle <xref:System.Windows.Controls.ListBox>, e <xref:System.Windows.Controls.ItemCollection> deriva dal <xref:System.Windows.Data.CollectionView> classe.</span><span class="sxs-lookup"><span data-stu-id="dbdf9-107">You can do this because adding items to a <xref:System.Windows.Controls.ListBox> this way adds them to the <xref:System.Windows.Controls.ItemCollection> of the <xref:System.Windows.Controls.ListBox>, and <xref:System.Windows.Controls.ItemCollection> derives from the <xref:System.Windows.Data.CollectionView> class.</span></span> <span data-ttu-id="dbdf9-108">Quando si associa il <xref:System.Windows.Controls.ListBox> a una raccolta mediante il <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> proprietà, è possibile usare la stessa tecnica per ordinare.</span><span class="sxs-lookup"><span data-stu-id="dbdf9-108">If you are binding your <xref:System.Windows.Controls.ListBox> to a collection using the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property, you can use the same technique to sort.</span></span>  
  
 [!code-csharp[ListBoxSort_snip#HowToCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml.cs#howtocode)]
 [!code-vb[ListBoxSort_snip#HowToCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxSort_snip/visualbasic/window1.xaml.vb#howtocode)]  
  
 <span data-ttu-id="dbdf9-109">Purché si disponga di un riferimento all'oggetto di visualizzazione, è possibile usare la stessa tecnica per ordinare il contenuto di altre viste di raccolta.</span><span class="sxs-lookup"><span data-stu-id="dbdf9-109">As long as you have a reference to the view object, you can use the same technique to sort the content of other collection views.</span></span> <span data-ttu-id="dbdf9-110">Per un esempio di come ottenere una visualizzazione, vedere [ottenere la visualizzazione predefinita di una raccolta di dati](how-to-get-the-default-view-of-a-data-collection.md).</span><span class="sxs-lookup"><span data-stu-id="dbdf9-110">For an example of how to obtain a view, see [Get the Default View of a Data Collection](how-to-get-the-default-view-of-a-data-collection.md).</span></span> <span data-ttu-id="dbdf9-111">Per un altro esempio, vedere [ordinare un GridView colonna quando una si seleziona l'intestazione](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md).</span><span class="sxs-lookup"><span data-stu-id="dbdf9-111">For another example, see [Sort a GridView Column When a Header Is Clicked](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md).</span></span> <span data-ttu-id="dbdf9-112">Per altre informazioni sulle viste, vedere Binding alle raccolte [Panoramica sul Data Binding](data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="dbdf9-112">For more information about views, see Binding to Collections in [Data Binding Overview](data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="dbdf9-113">Per un esempio di come applicare la logica di ordinamento nel [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], vedere [ordinare e raggruppare i dati tramite una visualizzazione in XAML](how-to-sort-and-group-data-using-a-view-in-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="dbdf9-113">For an example of how to apply sorting logic in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], see [Sort and Group Data Using a View in XAML](how-to-sort-and-group-data-using-a-view-in-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbdf9-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dbdf9-114">See also</span></span>
- <xref:System.Windows.Data.ListCollectionView.CustomSort%2A>
- [<span data-ttu-id="dbdf9-115">Ordinare una colonna GridView quando si fa clic su un'intestazione</span><span class="sxs-lookup"><span data-stu-id="dbdf9-115">Sort a GridView Column When a Header Is Clicked</span></span>](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)
- [<span data-ttu-id="dbdf9-116">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="dbdf9-116">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="dbdf9-117">Filtrare i dati di una visualizzazione</span><span class="sxs-lookup"><span data-stu-id="dbdf9-117">Filter Data in a View</span></span>](how-to-filter-data-in-a-view.md)
- [<span data-ttu-id="dbdf9-118">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="dbdf9-118">How-to Topics</span></span>](data-binding-how-to-topics.md)
