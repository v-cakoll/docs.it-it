---
title: 'Procedura: utilizzare i modelli per applicare uno stile a un ListView che utilizza una GridView'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ListView controls [WPF], styling
ms.assetid: 94bf964b-96c8-4bdf-a0c3-f5271b7cb565
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 246c144a18d7c1014096a6e37ad09b6eec5ad932
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-templates-to-style-a-listview-that-uses-gridview"></a><span data-ttu-id="715e5-102">Procedura: utilizzare i modelli per applicare uno stile a un ListView che utilizza una GridView</span><span class="sxs-lookup"><span data-stu-id="715e5-102">How to: Use Templates to Style a ListView That Uses GridView</span></span>
<span data-ttu-id="715e5-103">In questo esempio viene illustrato come utilizzare il <xref:System.Windows.DataTemplate> e <xref:System.Windows.Style> gli oggetti per specificare l'aspetto di un <xref:System.Windows.Controls.ListView> controllo che utilizza un <xref:System.Windows.Controls.GridView> modalità di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="715e5-103">This example shows how to use the <xref:System.Windows.DataTemplate> and <xref:System.Windows.Style> objects to specify the appearance of a <xref:System.Windows.Controls.ListView> control that uses a <xref:System.Windows.Controls.GridView> view mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="715e5-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="715e5-104">Example</span></span>  
 <span data-ttu-id="715e5-105">Negli esempi seguenti <xref:System.Windows.Style> e <xref:System.Windows.DataTemplate> gli oggetti che consentono di personalizzare l'aspetto di un'intestazione di colonna per un <xref:System.Windows.Controls.GridViewColumn>.</span><span class="sxs-lookup"><span data-stu-id="715e5-105">The following examples show <xref:System.Windows.Style> and <xref:System.Windows.DataTemplate> objects that customize the appearance of a column header for a <xref:System.Windows.Controls.GridViewColumn>.</span></span>  
  
 [!code-xaml[ListViewTemplate#GridViewHeaderStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheaderstyle)]  
  
 [!code-xaml[ListViewTemplate#GridViewHeaderTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheadertemplate)]  
  
 <span data-ttu-id="715e5-106">Nell'esempio seguente viene illustrato come utilizzare questi <xref:System.Windows.Style> e <xref:System.Windows.DataTemplate> oggetti su cui impostare il <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> e <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> le proprietà di un <xref:System.Windows.Controls.GridViewColumn>.</span><span class="sxs-lookup"><span data-stu-id="715e5-106">The following example shows how to use these <xref:System.Windows.Style> and <xref:System.Windows.DataTemplate> objects to set the <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> and <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> properties of a <xref:System.Windows.Controls.GridViewColumn>.</span></span> <span data-ttu-id="715e5-107">Il <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> proprietà definisce il contenuto delle celle della colonna.</span><span class="sxs-lookup"><span data-stu-id="715e5-107">The <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> property defines the content of the column cells.</span></span>  
  
 [!code-xaml[ListViewTemplate#GridViewColumnTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcolumntemplate)]  
  
 <span data-ttu-id="715e5-108">Il <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> e <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> sono solo due delle numerose proprietà che è possibile utilizzare per personalizzare l'aspetto dell'intestazione di colonna per un <xref:System.Windows.Controls.GridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="715e5-108">The <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> and <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> are only two of several properties that you can use to customize column header appearance for a <xref:System.Windows.Controls.GridView> control.</span></span> <span data-ttu-id="715e5-109">Per altre informazioni, vedere [Panoramica sui modelli e sugli stili di intestazione delle colonne in GridView](../../../../docs/framework/wpf/controls/gridview-column-header-styles-and-templates-overview.md).</span><span class="sxs-lookup"><span data-stu-id="715e5-109">For more information, see [GridView Column Header Styles and Templates Overview](../../../../docs/framework/wpf/controls/gridview-column-header-styles-and-templates-overview.md).</span></span>  
  
 <span data-ttu-id="715e5-110">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.DataTemplate> che consente di personalizzare l'aspetto delle celle in un <xref:System.Windows.Controls.GridViewColumn>.</span><span class="sxs-lookup"><span data-stu-id="715e5-110">The following example shows how to define a <xref:System.Windows.DataTemplate> that customizes the appearance of the cells in a <xref:System.Windows.Controls.GridViewColumn>.</span></span>  
  
 [!code-xaml[ListViewTemplate#GridViewCellTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 <span data-ttu-id="715e5-111">Nell'esempio seguente viene illustrato come utilizzare questo <xref:System.Windows.DataTemplate> per definire il contenuto di un <xref:System.Windows.Controls.GridViewColumn> cella.</span><span class="sxs-lookup"><span data-stu-id="715e5-111">The following example shows how to use this <xref:System.Windows.DataTemplate> to define the content of a <xref:System.Windows.Controls.GridViewColumn> cell.</span></span> <span data-ttu-id="715e5-112">Questo modello viene utilizzato anziché il <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> proprietà visualizzate nella precedente <xref:System.Windows.Controls.GridViewColumn> esempio.</span><span class="sxs-lookup"><span data-stu-id="715e5-112">This template is used instead of the <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> property that is shown in the previous <xref:System.Windows.Controls.GridViewColumn> example.</span></span>  
  
 [!code-xaml[ListViewTemplate#CellTemplateProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
## <a name="see-also"></a><span data-ttu-id="715e5-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="715e5-113">See Also</span></span>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [<span data-ttu-id="715e5-114">Cenni preliminari su GridView</span><span class="sxs-lookup"><span data-stu-id="715e5-114">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)  
 [<span data-ttu-id="715e5-115">Procedure relative</span><span class="sxs-lookup"><span data-stu-id="715e5-115">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [<span data-ttu-id="715e5-116">Panoramica sul controllo ListView</span><span class="sxs-lookup"><span data-stu-id="715e5-116">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)
