---
title: 'Procedura: creare ListViewItem con un CheckBox'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [WPF], ListView
- controls [WPF], CheckBox
- ListView controls [WPF], CheckBox controls
- CheckBox control [WPF], ListView control
ms.assetid: f6d66c7f-906c-4f65-a55a-0ede9d00e26a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4cc6ebb3671dcc65d690fde5d4796c9034553eb7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-listviewitems-with-a-checkbox"></a><span data-ttu-id="23942-102">Procedura: creare ListViewItem con un CheckBox</span><span class="sxs-lookup"><span data-stu-id="23942-102">How to: Create ListViewItems with a CheckBox</span></span>
<span data-ttu-id="23942-103">In questo esempio viene illustrato come visualizzare una colonna di <xref:System.Windows.Controls.CheckBox> controlli in un <xref:System.Windows.Controls.ListView> controllo che utilizza un <xref:System.Windows.Controls.GridView>.</span><span class="sxs-lookup"><span data-stu-id="23942-103">This example shows how to display a column of <xref:System.Windows.Controls.CheckBox> controls in a <xref:System.Windows.Controls.ListView> control that uses a <xref:System.Windows.Controls.GridView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23942-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="23942-104">Example</span></span>  
 <span data-ttu-id="23942-105">Per creare una colonna che contiene <xref:System.Windows.Controls.CheckBox> controlli in un <xref:System.Windows.Controls.ListView>, creare un <xref:System.Windows.DataTemplate> che contiene un <xref:System.Windows.Controls.CheckBox>.</span><span class="sxs-lookup"><span data-stu-id="23942-105">To create a column that contains <xref:System.Windows.Controls.CheckBox> controls in a <xref:System.Windows.Controls.ListView>, create a <xref:System.Windows.DataTemplate> that contains a <xref:System.Windows.Controls.CheckBox>.</span></span> <span data-ttu-id="23942-106">Impostare quindi la <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> di un <xref:System.Windows.Controls.GridViewColumn> per il <xref:System.Windows.DataTemplate>.</span><span class="sxs-lookup"><span data-stu-id="23942-106">Then set the <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> of a <xref:System.Windows.Controls.GridViewColumn> to the <xref:System.Windows.DataTemplate>.</span></span>  
  
 <span data-ttu-id="23942-107">Nell'esempio seguente un <xref:System.Windows.DataTemplate> che contiene un <xref:System.Windows.Controls.CheckBox>.</span><span class="sxs-lookup"><span data-stu-id="23942-107">The following example shows a <xref:System.Windows.DataTemplate> that contains a <xref:System.Windows.Controls.CheckBox>.</span></span> <span data-ttu-id="23942-108">Nell'esempio viene associato il <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> proprietà del <xref:System.Windows.Controls.CheckBox> per il <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> valore della proprietà di <xref:System.Windows.Controls.ListViewItem> che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="23942-108">The example binds the <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> property of the <xref:System.Windows.Controls.CheckBox> to the <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> property value of the <xref:System.Windows.Controls.ListViewItem> that contains it.</span></span> <span data-ttu-id="23942-109">Pertanto, quando il <xref:System.Windows.Controls.ListViewItem> che contiene il <xref:System.Windows.Controls.CheckBox> è selezionata, il <xref:System.Windows.Controls.CheckBox> è selezionata.</span><span class="sxs-lookup"><span data-stu-id="23942-109">Therefore, when the <xref:System.Windows.Controls.ListViewItem> that contains the <xref:System.Windows.Controls.CheckBox> is selected, the <xref:System.Windows.Controls.CheckBox> is checked.</span></span>  
  
 [!code-xaml[ListViewChkBox#CheckBoxDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#checkboxdatatemplate)]  
  
 <span data-ttu-id="23942-110">Nell'esempio seguente viene illustrato come creare una colonna di <xref:System.Windows.Controls.CheckBox> controlli.</span><span class="sxs-lookup"><span data-stu-id="23942-110">The following example shows how to create a column of <xref:System.Windows.Controls.CheckBox> controls.</span></span> <span data-ttu-id="23942-111">Impostare la colonna, nell'esempio viene impostata la <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> proprietà del <xref:System.Windows.Controls.GridViewColumn> per il <xref:System.Windows.DataTemplate>.</span><span class="sxs-lookup"><span data-stu-id="23942-111">To make the column, the example sets the <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> property of the <xref:System.Windows.Controls.GridViewColumn> to the <xref:System.Windows.DataTemplate>.</span></span>  
  
 [!code-xaml[ListViewChkBox#GridViewColumnCheckBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#gridviewcolumncheckbox)]  
  
## <a name="see-also"></a><span data-ttu-id="23942-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23942-112">See Also</span></span>  
 <xref:System.Windows.Controls.Control>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [<span data-ttu-id="23942-113">Panoramica sul controllo ListView</span><span class="sxs-lookup"><span data-stu-id="23942-113">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [<span data-ttu-id="23942-114">Procedure relative</span><span class="sxs-lookup"><span data-stu-id="23942-114">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [<span data-ttu-id="23942-115">Cenni preliminari su GridView</span><span class="sxs-lookup"><span data-stu-id="23942-115">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)
