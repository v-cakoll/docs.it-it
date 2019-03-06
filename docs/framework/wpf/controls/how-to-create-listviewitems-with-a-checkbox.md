---
title: 'Procedura: Creare ListViewItems con un CheckBox'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], ListView
- controls [WPF], CheckBox
- ListView controls [WPF], CheckBox controls
- CheckBox control [WPF], ListView control
ms.assetid: f6d66c7f-906c-4f65-a55a-0ede9d00e26a
ms.openlocfilehash: 31a500c3a592ff8d1dd839543171991e908c23c9
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57368532"
---
# <a name="how-to-create-listviewitems-with-a-checkbox"></a><span data-ttu-id="90023-102">Procedura: Creare ListViewItems con un CheckBox</span><span class="sxs-lookup"><span data-stu-id="90023-102">How to: Create ListViewItems with a CheckBox</span></span>
<span data-ttu-id="90023-103">Questo esempio viene illustrato come visualizzare una colonna <xref:System.Windows.Controls.CheckBox> controlli in un <xref:System.Windows.Controls.ListView> controllo che usa un <xref:System.Windows.Controls.GridView>.</span><span class="sxs-lookup"><span data-stu-id="90023-103">This example shows how to display a column of <xref:System.Windows.Controls.CheckBox> controls in a <xref:System.Windows.Controls.ListView> control that uses a <xref:System.Windows.Controls.GridView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="90023-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="90023-104">Example</span></span>  
 <span data-ttu-id="90023-105">Per creare una colonna che contiene <xref:System.Windows.Controls.CheckBox> controlli in un <xref:System.Windows.Controls.ListView>, creare un <xref:System.Windows.DataTemplate> che contiene un <xref:System.Windows.Controls.CheckBox>.</span><span class="sxs-lookup"><span data-stu-id="90023-105">To create a column that contains <xref:System.Windows.Controls.CheckBox> controls in a <xref:System.Windows.Controls.ListView>, create a <xref:System.Windows.DataTemplate> that contains a <xref:System.Windows.Controls.CheckBox>.</span></span> <span data-ttu-id="90023-106">Impostare quindi la <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> di un <xref:System.Windows.Controls.GridViewColumn> per il <xref:System.Windows.DataTemplate>.</span><span class="sxs-lookup"><span data-stu-id="90023-106">Then set the <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> of a <xref:System.Windows.Controls.GridViewColumn> to the <xref:System.Windows.DataTemplate>.</span></span>  
  
 <span data-ttu-id="90023-107">L'esempio seguente mostra una <xref:System.Windows.DataTemplate> che contiene un <xref:System.Windows.Controls.CheckBox>.</span><span class="sxs-lookup"><span data-stu-id="90023-107">The following example shows a <xref:System.Windows.DataTemplate> that contains a <xref:System.Windows.Controls.CheckBox>.</span></span> <span data-ttu-id="90023-108">Nell'esempio viene associato il <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> proprietà del <xref:System.Windows.Controls.CheckBox> per il <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> valore della proprietà di <xref:System.Windows.Controls.ListViewItem> che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="90023-108">The example binds the <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> property of the <xref:System.Windows.Controls.CheckBox> to the <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> property value of the <xref:System.Windows.Controls.ListViewItem> that contains it.</span></span> <span data-ttu-id="90023-109">Pertanto, quando la <xref:System.Windows.Controls.ListViewItem> che contiene il <xref:System.Windows.Controls.CheckBox> è selezionata, il <xref:System.Windows.Controls.CheckBox> sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="90023-109">Therefore, when the <xref:System.Windows.Controls.ListViewItem> that contains the <xref:System.Windows.Controls.CheckBox> is selected, the <xref:System.Windows.Controls.CheckBox> is checked.</span></span>  
  
 [!code-xaml[ListViewChkBox#CheckBoxDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#checkboxdatatemplate)]  
  
 <span data-ttu-id="90023-110">Nell'esempio seguente viene illustrato come creare una colonna di <xref:System.Windows.Controls.CheckBox> controlli.</span><span class="sxs-lookup"><span data-stu-id="90023-110">The following example shows how to create a column of <xref:System.Windows.Controls.CheckBox> controls.</span></span> <span data-ttu-id="90023-111">Impostare la colonna, nell'esempio viene impostata la <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> proprietà del <xref:System.Windows.Controls.GridViewColumn> per il <xref:System.Windows.DataTemplate>.</span><span class="sxs-lookup"><span data-stu-id="90023-111">To make the column, the example sets the <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> property of the <xref:System.Windows.Controls.GridViewColumn> to the <xref:System.Windows.DataTemplate>.</span></span>  
  
 [!code-xaml[ListViewChkBox#GridViewColumnCheckBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#gridviewcolumncheckbox)]  
  
## <a name="see-also"></a><span data-ttu-id="90023-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90023-112">See also</span></span>
- <xref:System.Windows.Controls.Control>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="90023-113">Panoramica sul controllo ListView</span><span class="sxs-lookup"><span data-stu-id="90023-113">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="90023-114">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="90023-114">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="90023-115">Cenni preliminari su GridView</span><span class="sxs-lookup"><span data-stu-id="90023-115">GridView Overview</span></span>](gridview-overview.md)
