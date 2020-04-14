---
title: 'Procedura: creare una modalità di visualizzazione personalizzata per un oggetto ListView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], creating custom View mode
ms.assetid: 71077349-eeb9-4344-ab29-b5df96df3314
ms.openlocfilehash: 3b9ca17bddcecb1895205fca76f0a489ecf25c4f
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243219"
---
# <a name="how-to-create-a-custom-view-mode-for-a-listview"></a><span data-ttu-id="26209-102">Procedura: creare una modalità di visualizzazione personalizzata per un controllo ListViewHow to: Create a custom view mode for a ListView</span><span class="sxs-lookup"><span data-stu-id="26209-102">How to: Create a custom view mode for a ListView</span></span>

<span data-ttu-id="26209-103">In questo esempio viene <xref:System.Windows.Controls.ListView.View%2A> illustrato come <xref:System.Windows.Controls.ListView> creare una modalità personalizzata per un controllo.</span><span class="sxs-lookup"><span data-stu-id="26209-103">This example shows how to create a custom <xref:System.Windows.Controls.ListView.View%2A> mode for a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26209-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="26209-104">Example</span></span>  
 <span data-ttu-id="26209-105">È necessario <xref:System.Windows.Controls.ViewBase> utilizzare la classe quando si <xref:System.Windows.Controls.ListView> crea una visualizzazione personalizzata per il controllo.</span><span class="sxs-lookup"><span data-stu-id="26209-105">You must use the <xref:System.Windows.Controls.ViewBase> class when you create a custom view for the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="26209-106">Nell'esempio seguente viene `PlainView` illustrata una modalità di visualizzazione denominata derivata dalla <xref:System.Windows.Controls.ViewBase> classe .</span><span class="sxs-lookup"><span data-stu-id="26209-106">The following example shows a view mode called `PlainView` that's derived from the <xref:System.Windows.Controls.ViewBase> class.</span></span>  
  
 [!code-csharp[ListViewCustomView#PlainView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/PlainView.cs#plainview)]
 [!code-vb[ListViewCustomView#PlainView](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/plainview.vb#plainview)]  
  
 <span data-ttu-id="26209-107">Per applicare uno stile alla visualizzazione <xref:System.Windows.Style> personalizzata, utilizzare la classe .</span><span class="sxs-lookup"><span data-stu-id="26209-107">To apply a style to the custom view, use the <xref:System.Windows.Style> class.</span></span> <span data-ttu-id="26209-108">Nell'esempio seguente <xref:System.Windows.Style> viene `PlainView` definito un per la modalità di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="26209-108">The following example defines a <xref:System.Windows.Style> for the `PlainView` view mode.</span></span> <span data-ttu-id="26209-109">Nell'esempio precedente, questo stile viene impostato <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> come valore della `PlainView`proprietà definita per .</span><span class="sxs-lookup"><span data-stu-id="26209-109">In the previous example, this style is set as the value of the <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> property that's defined for `PlainView`.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Themes/Generic.xaml#plainviewstyle)]  
  
 <span data-ttu-id="26209-110">Per definire il layout dei dati in <xref:System.Windows.DataTemplate> una modalità di visualizzazione personalizzata, definire un oggetto.</span><span class="sxs-lookup"><span data-stu-id="26209-110">To define the layout of data in a custom view mode, define a <xref:System.Windows.DataTemplate> object.</span></span> <span data-ttu-id="26209-111">Nell'esempio seguente <xref:System.Windows.DataTemplate> viene definito un oggetto che `PlainView` può essere utilizzato per visualizzare i dati in modalità di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="26209-111">The following example defines a <xref:System.Windows.DataTemplate> that can be used to display data in the `PlainView` view mode.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewdatatemplate)]  
  
 <span data-ttu-id="26209-112">Nell'esempio seguente viene <xref:System.Windows.ResourceKey> illustrato `PlainView` come definire un <xref:System.Windows.DataTemplate> per la modalità di visualizzazione che utilizza l'oggetto definito nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="26209-112">The following example shows how to define a <xref:System.Windows.ResourceKey> for the `PlainView` view mode that uses the <xref:System.Windows.DataTemplate> that is defined in the previous example.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewtileView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewtileview)]  
  
 <span data-ttu-id="26209-113">Un <xref:System.Windows.Controls.ListView> controllo può utilizzare una visualizzazione <xref:System.Windows.Controls.ListView.View%2A> personalizzata se si imposta la proprietà sulla chiave di risorsa.</span><span class="sxs-lookup"><span data-stu-id="26209-113">A <xref:System.Windows.Controls.ListView> control can use a custom view if you set the <xref:System.Windows.Controls.ListView.View%2A> property to the resource key.</span></span> <span data-ttu-id="26209-114">Nell'esempio seguente viene `PlainView` illustrato come specificare come modalità di visualizzazione per un <xref:System.Windows.Controls.ListView>oggetto .</span><span class="sxs-lookup"><span data-stu-id="26209-114">The following example shows how to specify `PlainView` as the view mode for a <xref:System.Windows.Controls.ListView>.</span></span>  
  
 [!code-csharp[ListViewCustomView#ListViewtileViewmode](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml.cs#listviewtileviewmode)]
 [!code-vb[ListViewCustomView#ListViewtileViewmode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/window1.xaml.vb#listviewtileviewmode)]  
  
 <span data-ttu-id="26209-115">Per l'esempio completo, vedere [ListView con più visualizzazioni (c'è)](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp) o [ListView con più visualizzazioni (Visual Basic)](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic).</span><span class="sxs-lookup"><span data-stu-id="26209-115">For the complete sample, see [ListView with Multiple Views (C#)](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp) or [ListView with Multiple Views (Visual Basic)](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26209-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26209-116">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="26209-117">Procedure</span><span class="sxs-lookup"><span data-stu-id="26209-117">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="26209-118">Panoramica sul controllo ListView</span><span class="sxs-lookup"><span data-stu-id="26209-118">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="26209-119">Cenni preliminari su GridView</span><span class="sxs-lookup"><span data-stu-id="26209-119">GridView Overview</span></span>](gridview-overview.md)
