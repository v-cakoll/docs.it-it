---
title: 'Procedura: Raggruppare gli elementi di un controllo ListView che implementa un oggetto GridView'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], grouping items with GridViews
- grouping items in ListViews implementing GridViews [WPF]
- GridView controls [WPF], grouping items
ms.assetid: eebef25b-ddc6-424e-a66d-ea228d1bf33d
ms.openlocfilehash: b3dd6891976a942b299c87fca25e430e9ee59a51
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59177671"
---
# <a name="how-to-group-items-in-a-listview-that-implements-a-gridview"></a><span data-ttu-id="79fc8-102">Procedura: Raggruppare gli elementi di un controllo ListView che implementa un oggetto GridView</span><span class="sxs-lookup"><span data-stu-id="79fc8-102">How to: Group Items in a ListView That Implements a GridView</span></span>
<span data-ttu-id="79fc8-103">In questo esempio viene illustrato come visualizzare i gruppi di voci di <xref:System.Windows.Controls.GridView> modalità di visualizzazione di un <xref:System.Windows.Controls.ListView> controllo.</span><span class="sxs-lookup"><span data-stu-id="79fc8-103">This example shows how to display groups of items in the <xref:System.Windows.Controls.GridView> view mode of a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79fc8-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="79fc8-104">Example</span></span>  
 <span data-ttu-id="79fc8-105">Per visualizzare i gruppi di elementi in un <xref:System.Windows.Controls.ListView>, definire un <xref:System.Windows.Data.CollectionViewSource>.</span><span class="sxs-lookup"><span data-stu-id="79fc8-105">To display groups of items in a <xref:System.Windows.Controls.ListView>, define a <xref:System.Windows.Data.CollectionViewSource>.</span></span> <span data-ttu-id="79fc8-106">L'esempio seguente mostra una <xref:System.Windows.Data.CollectionViewSource> che raggruppa gli elementi di dati secondo il valore della `Catalog` campo dati.</span><span class="sxs-lookup"><span data-stu-id="79fc8-106">The following example shows a <xref:System.Windows.Data.CollectionViewSource> that groups data items according to the value of the `Catalog` data field.</span></span>  
  
 [!code-xaml[GridViewWithGroups#GroupingCollectionViewSource](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#groupingcollectionviewsource)]  
  
 <span data-ttu-id="79fc8-107">L'esempio seguente imposta la <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> per il <xref:System.Windows.Controls.ListView> per il <xref:System.Windows.Data.CollectionViewSource> definito nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="79fc8-107">The following example sets the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> for the <xref:System.Windows.Controls.ListView> to the <xref:System.Windows.Data.CollectionViewSource> that the previous example defines.</span></span> <span data-ttu-id="79fc8-108">L'esempio definisce anche un <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> che implementa un <xref:System.Windows.Controls.Expander> controllo.</span><span class="sxs-lookup"><span data-stu-id="79fc8-108">The example also defines a <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> that implements an <xref:System.Windows.Controls.Expander> control.</span></span>  
  
 [!code-xaml[GridViewWithGroups#ListViewGroups](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewgroups)]  
[!code-xaml[GridViewWithGroups#ListViewEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewend)]  
  
## <a name="see-also"></a><span data-ttu-id="79fc8-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79fc8-109">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="79fc8-110">Procedure relative</span><span class="sxs-lookup"><span data-stu-id="79fc8-110">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="79fc8-111">Panoramica sul controllo ListView</span><span class="sxs-lookup"><span data-stu-id="79fc8-111">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="79fc8-112">Cenni preliminari su GridView</span><span class="sxs-lookup"><span data-stu-id="79fc8-112">GridView Overview</span></span>](gridview-overview.md)
