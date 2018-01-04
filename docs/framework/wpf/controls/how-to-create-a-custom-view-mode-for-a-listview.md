---
title: "Procedura: creare una modalità di visualizzazione personalizzata per un oggetto ListView"
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
helpviewer_keywords: ListView controls [WPF], creating custom View mode
ms.assetid: 71077349-eeb9-4344-ab29-b5df96df3314
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e67777b5568214dff889088708db166efc6ae4dd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-custom-view-mode-for-a-listview"></a><span data-ttu-id="09fa2-102">Procedura: creare una modalità di visualizzazione personalizzata per un oggetto ListView</span><span class="sxs-lookup"><span data-stu-id="09fa2-102">How to: Create a Custom View Mode for a ListView</span></span>
<span data-ttu-id="09fa2-103">In questo esempio viene illustrato come creare un oggetto personalizzato <xref:System.Windows.Controls.ListView.View%2A> modalità per un <xref:System.Windows.Controls.ListView> controllo.</span><span class="sxs-lookup"><span data-stu-id="09fa2-103">This example shows how to create a custom <xref:System.Windows.Controls.ListView.View%2A> mode for a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09fa2-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="09fa2-104">Example</span></span>  
 <span data-ttu-id="09fa2-105">È necessario utilizzare il <xref:System.Windows.Controls.ViewBase> classe quando si crea una visualizzazione personalizzata per il <xref:System.Windows.Controls.ListView> controllo.</span><span class="sxs-lookup"><span data-stu-id="09fa2-105">You must use the <xref:System.Windows.Controls.ViewBase> class when you create a custom view for the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="09fa2-106">Nell'esempio seguente viene mostrata una modalità di visualizzazione che viene chiamata `PlainView`, che deriva dalla <xref:System.Windows.Controls.ViewBase> classe.</span><span class="sxs-lookup"><span data-stu-id="09fa2-106">The following example shows a view mode that is called `PlainView`, which is derived from the <xref:System.Windows.Controls.ViewBase> class.</span></span>  
  
 [!code-csharp[ListViewCustomView#PlainView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/PlainView.cs#plainview)]
 [!code-vb[ListViewCustomView#PlainView](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/plainview.vb#plainview)]  
  
 <span data-ttu-id="09fa2-107">Per applicare uno stile per la visualizzazione personalizzata, utilizzare la <xref:System.Windows.Style> classe.</span><span class="sxs-lookup"><span data-stu-id="09fa2-107">To apply a style to the custom view, use the <xref:System.Windows.Style> class.</span></span> <span data-ttu-id="09fa2-108">L'esempio seguente definisce un <xref:System.Windows.Style> per il `PlainView` modalità di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="09fa2-108">The following example defines a <xref:System.Windows.Style> for the `PlainView` view mode.</span></span> <span data-ttu-id="09fa2-109">Nell'esempio precedente, questo stile è impostato come valore della <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> proprietà definita per `PlainView`.</span><span class="sxs-lookup"><span data-stu-id="09fa2-109">In the previous example, this style is set as the value of the <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> property that is defined for `PlainView`.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Themes/Generic.xaml#plainviewstyle)]  
  
 <span data-ttu-id="09fa2-110">Per definire il layout dei dati in una modalità di visualizzazione personalizzato, definire un <xref:System.Windows.DataTemplate> oggetto.</span><span class="sxs-lookup"><span data-stu-id="09fa2-110">To define the layout of data in a custom view mode, define a <xref:System.Windows.DataTemplate> object.</span></span> <span data-ttu-id="09fa2-111">L'esempio seguente definisce un <xref:System.Windows.DataTemplate> che può essere utilizzato per visualizzare i dati nella `PlainView` modalità di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="09fa2-111">The following example defines a <xref:System.Windows.DataTemplate> that can be used to display data in the `PlainView` view mode.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewdatatemplate)]  
  
 <span data-ttu-id="09fa2-112">Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.ResourceKey> per il `PlainView` modalità di visualizzazione che utilizza il <xref:System.Windows.DataTemplate> definito nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="09fa2-112">The following example shows how to define a <xref:System.Windows.ResourceKey> for the `PlainView` view mode that uses the <xref:System.Windows.DataTemplate> that is defined in the previous example.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewtileView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewtileview)]  
  
 <span data-ttu-id="09fa2-113">Oggetto <xref:System.Windows.Controls.ListView> controllo può utilizzare una visualizzazione personalizzata se si imposta la <xref:System.Windows.Controls.ListView.View%2A> proprietà chiave di risorsa.</span><span class="sxs-lookup"><span data-stu-id="09fa2-113">A <xref:System.Windows.Controls.ListView> control can use a custom view if you set the <xref:System.Windows.Controls.ListView.View%2A> property to the resource key.</span></span> <span data-ttu-id="09fa2-114">Nell'esempio seguente viene illustrato come specificare `PlainView` come modalità di visualizzazione per un <xref:System.Windows.Controls.ListView>.</span><span class="sxs-lookup"><span data-stu-id="09fa2-114">The following example shows how to specify `PlainView` as the view mode for a <xref:System.Windows.Controls.ListView>.</span></span>  
  
 [!code-csharp[ListViewCustomView#ListViewtileViewmode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml.cs#listviewtileviewmode)]
 [!code-vb[ListViewCustomView#ListViewtileViewmode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/window1.xaml.vb#listviewtileviewmode)]  
  
 <span data-ttu-id="09fa2-115">Per l'esempio completo, vedere [ListView con più visualizzazioni](http://go.microsoft.com/fwlink/?LinkID=160013).</span><span class="sxs-lookup"><span data-stu-id="09fa2-115">For the complete sample, see [ListView with Multiple Views Sample](http://go.microsoft.com/fwlink/?LinkID=160013).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09fa2-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09fa2-116">See Also</span></span>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [<span data-ttu-id="09fa2-117">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="09fa2-117">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [<span data-ttu-id="09fa2-118">Panoramica sul controllo ListView</span><span class="sxs-lookup"><span data-stu-id="09fa2-118">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [<span data-ttu-id="09fa2-119">Cenni preliminari su GridView</span><span class="sxs-lookup"><span data-stu-id="09fa2-119">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)
