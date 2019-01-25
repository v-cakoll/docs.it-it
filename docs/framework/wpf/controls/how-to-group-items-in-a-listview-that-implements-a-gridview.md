---
title: 'Procedura: Raggruppare gli elementi di un controllo ListView che implementa una GridView'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], grouping items with GridViews
- grouping items in ListViews implementing GridViews [WPF]
- GridView controls [WPF], grouping items
ms.assetid: eebef25b-ddc6-424e-a66d-ea228d1bf33d
ms.openlocfilehash: 1570eab70dae690f508975162b7553de92be6f12
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54664356"
---
# <a name="how-to-group-items-in-a-listview-that-implements-a-gridview"></a><span data-ttu-id="70a7c-102">Procedura: Raggruppare gli elementi di un controllo ListView che implementa una GridView</span><span class="sxs-lookup"><span data-stu-id="70a7c-102">How to: Group Items in a ListView That Implements a GridView</span></span>
<span data-ttu-id="70a7c-103">In questo esempio viene illustrato come visualizzare i gruppi di voci di <xref:System.Windows.Controls.GridView> modalità di visualizzazione di un <xref:System.Windows.Controls.ListView> controllo.</span><span class="sxs-lookup"><span data-stu-id="70a7c-103">This example shows how to display groups of items in the <xref:System.Windows.Controls.GridView> view mode of a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70a7c-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="70a7c-104">Example</span></span>  
 <span data-ttu-id="70a7c-105">Per visualizzare i gruppi di elementi in un <xref:System.Windows.Controls.ListView>, definire un <xref:System.Windows.Data.CollectionViewSource>.</span><span class="sxs-lookup"><span data-stu-id="70a7c-105">To display groups of items in a <xref:System.Windows.Controls.ListView>, define a <xref:System.Windows.Data.CollectionViewSource>.</span></span> <span data-ttu-id="70a7c-106">L'esempio seguente mostra una <xref:System.Windows.Data.CollectionViewSource> che raggruppa gli elementi di dati secondo il valore della `Catalog` campo dati.</span><span class="sxs-lookup"><span data-stu-id="70a7c-106">The following example shows a <xref:System.Windows.Data.CollectionViewSource> that groups data items according to the value of the `Catalog` data field.</span></span>  
  
 [!code-xaml[GridViewWithGroups#GroupingCollectionViewSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#groupingcollectionviewsource)]  
  
 <span data-ttu-id="70a7c-107">L'esempio seguente imposta la <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> per il <xref:System.Windows.Controls.ListView> per il <xref:System.Windows.Data.CollectionViewSource> definito nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="70a7c-107">The following example sets the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> for the <xref:System.Windows.Controls.ListView> to the <xref:System.Windows.Data.CollectionViewSource> that the previous example defines.</span></span> <span data-ttu-id="70a7c-108">L'esempio definisce anche un <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> che implementa un <xref:System.Windows.Controls.Expander> controllo.</span><span class="sxs-lookup"><span data-stu-id="70a7c-108">The example also defines a <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> that implements an <xref:System.Windows.Controls.Expander> control.</span></span>  
  
 [!code-xaml[GridViewWithGroups#ListViewGroups](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewgroups)]  
[!code-xaml[GridViewWithGroups#ListViewEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewend)]  
  
## <a name="see-also"></a><span data-ttu-id="70a7c-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70a7c-109">See also</span></span>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="70a7c-110">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="70a7c-110">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)
- [<span data-ttu-id="70a7c-111">Panoramica sul controllo ListView</span><span class="sxs-lookup"><span data-stu-id="70a7c-111">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)
- [<span data-ttu-id="70a7c-112">Cenni preliminari su GridView</span><span class="sxs-lookup"><span data-stu-id="70a7c-112">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)
