---
title: 'Procedura: ordinare i dati in una visualizzazione'
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
- data binding [WPF], sorting data in views
- data binding [WPF], grouping data in views
- grouping data in views [WPF]
- views [WPF], sorting data
- views [WPF], grouping data
- sorting data in views [WPF]
ms.assetid: f4c43578-01b7-4774-a953-acb95a13b94a
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7467913f867ea0990ae85b0ad933c11f2fd271b9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-sort-data-in-a-view"></a><span data-ttu-id="1a679-102">Procedura: ordinare i dati in una visualizzazione</span><span class="sxs-lookup"><span data-stu-id="1a679-102">How to: Sort Data in a View</span></span>
<span data-ttu-id="1a679-103">In questo esempio viene descritto come ordinare i dati in una vista.</span><span class="sxs-lookup"><span data-stu-id="1a679-103">This example describes how to sort data in a view.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a679-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="1a679-104">Example</span></span>  
 <span data-ttu-id="1a679-105">Nell'esempio seguente viene creato un semplice <xref:System.Windows.Controls.ListBox> e <xref:System.Windows.Controls.Button>:</span><span class="sxs-lookup"><span data-stu-id="1a679-105">The following example creates a simple <xref:System.Windows.Controls.ListBox> and a <xref:System.Windows.Controls.Button>:</span></span>  
  
 [!code-xaml[ListBoxSort_snip#HowTo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml#howto)]  
  
 <span data-ttu-id="1a679-106">Il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestore dell'evento del pulsante contiene la logica per ordinare gli elementi di <xref:System.Windows.Controls.ListBox> in ordine decrescente.</span><span class="sxs-lookup"><span data-stu-id="1a679-106">The <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler of the button contains logic to sort the items in the <xref:System.Windows.Controls.ListBox> in the descending order.</span></span> <span data-ttu-id="1a679-107">È possibile farlo perché l'aggiunta di elementi un <xref:System.Windows.Controls.ListBox> in questo modo vengono aggiunte al <xref:System.Windows.Controls.ItemCollection> del <xref:System.Windows.Controls.ListBox>, e <xref:System.Windows.Controls.ItemCollection> deriva il <xref:System.Windows.Data.CollectionView> classe.</span><span class="sxs-lookup"><span data-stu-id="1a679-107">You can do this because adding items to a <xref:System.Windows.Controls.ListBox> this way adds them to the <xref:System.Windows.Controls.ItemCollection> of the <xref:System.Windows.Controls.ListBox>, and <xref:System.Windows.Controls.ItemCollection> derives from the <xref:System.Windows.Data.CollectionView> class.</span></span> <span data-ttu-id="1a679-108">Se si desidera associare il <xref:System.Windows.Controls.ListBox> a una raccolta mediante la <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> proprietà, è possibile utilizzare la stessa tecnica per l'ordinamento.</span><span class="sxs-lookup"><span data-stu-id="1a679-108">If you are binding your <xref:System.Windows.Controls.ListBox> to a collection using the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property, you can use the same technique to sort.</span></span>  
  
 [!code-csharp[ListBoxSort_snip#HowToCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml.cs#howtocode)]
 [!code-vb[ListBoxSort_snip#HowToCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxSort_snip/visualbasic/window1.xaml.vb#howtocode)]  
  
 <span data-ttu-id="1a679-109">Fino a quando è presente un riferimento all'oggetto view, è possibile utilizzare la stessa tecnica per ordinare il contenuto di altre viste di raccolta.</span><span class="sxs-lookup"><span data-stu-id="1a679-109">As long as you have a reference to the view object, you can use the same technique to sort the content of other collection views.</span></span> <span data-ttu-id="1a679-110">Per un esempio di come ottenere una vista, vedere [ottenere la visualizzazione predefinita di una raccolta di dati](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md).</span><span class="sxs-lookup"><span data-stu-id="1a679-110">For an example of how to obtain a view, see [Get the Default View of a Data Collection](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md).</span></span> <span data-ttu-id="1a679-111">Per un altro esempio, vedere [ordinare un GridView colonna quando un si seleziona l'intestazione](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md).</span><span class="sxs-lookup"><span data-stu-id="1a679-111">For another example, see [Sort a GridView Column When a Header Is Clicked](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md).</span></span> <span data-ttu-id="1a679-112">Per ulteriori informazioni sulle visualizzazioni, vedere l'associazione alle raccolte in [Panoramica del Data Binding](../../../../docs/framework/wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1a679-112">For more information about views, see Binding to Collections in [Data Binding Overview](../../../../docs/framework/wpf/data/data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="1a679-113">Per un esempio di come applicare la logica di ordinamento in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], vedere [ordinamento e gruppo di dati tramite una vista in XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="1a679-113">For an example of how to apply sorting logic in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], see [Sort and Group Data Using a View in XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a679-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a679-114">See Also</span></span>  
 <xref:System.Windows.Data.ListCollectionView.CustomSort%2A>  
 [<span data-ttu-id="1a679-115">Ordinare una colonna GridView quando si fa clic su un'intestazione</span><span class="sxs-lookup"><span data-stu-id="1a679-115">Sort a GridView Column When a Header Is Clicked</span></span>](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)  
 [<span data-ttu-id="1a679-116">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="1a679-116">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="1a679-117">Filtrare i dati di una visualizzazione</span><span class="sxs-lookup"><span data-stu-id="1a679-117">Filter Data in a View</span></span>](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)  
 [<span data-ttu-id="1a679-118">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="1a679-118">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
