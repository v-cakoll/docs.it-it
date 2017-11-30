---
title: 'Procedura: utilizzare i trigger per applicare uno stile agli elementi selezionati in un controllo ListView'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ListView controls [WPF], styling
ms.assetid: 1e2bdce0-afe8-4507-9b18-f33de43de25a
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e86c7f875376a4ab28eec7cd032a165745445441
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-triggers-to-style-selected-items-in-a-listview"></a><span data-ttu-id="d0ef5-102">Procedura: utilizzare i trigger per applicare uno stile agli elementi selezionati in un controllo ListView</span><span class="sxs-lookup"><span data-stu-id="d0ef5-102">How to: Use Triggers to Style Selected Items in a ListView</span></span>
<span data-ttu-id="d0ef5-103">In questo esempio viene illustrato come definire <xref:System.Windows.Style.Triggers%2A> per un <xref:System.Windows.Controls.ListViewItem> controllo in modo che quando un valore della proprietà di un <xref:System.Windows.Controls.ListViewItem> modifiche, il <xref:System.Windows.Style> del <xref:System.Windows.Controls.ListViewItem> modifiche in risposta.</span><span class="sxs-lookup"><span data-stu-id="d0ef5-103">This example shows how to define <xref:System.Windows.Style.Triggers%2A> for a <xref:System.Windows.Controls.ListViewItem> control so that when a property value of a <xref:System.Windows.Controls.ListViewItem> changes, the <xref:System.Windows.Style> of the <xref:System.Windows.Controls.ListViewItem> changes in response.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0ef5-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="d0ef5-104">Example</span></span>  
 <span data-ttu-id="d0ef5-105">Se si desidera che il <xref:System.Windows.Style> di un <xref:System.Windows.Controls.ListViewItem> per modificare in risposta alle modifiche di proprietà, definire <xref:System.Windows.Style.Triggers%2A> per il <xref:System.Windows.Style> modificare.</span><span class="sxs-lookup"><span data-stu-id="d0ef5-105">If you want the <xref:System.Windows.Style> of a <xref:System.Windows.Controls.ListViewItem> to change in response to property changes, define <xref:System.Windows.Style.Triggers%2A> for the <xref:System.Windows.Style> change.</span></span>  
  
 <span data-ttu-id="d0ef5-106">L'esempio seguente definisce un <xref:System.Windows.Trigger> che imposta il <xref:System.Windows.Controls.Control.Foreground%2A> proprietà <xref:System.Windows.Media.Brushes.Blue%2A> e le modifiche di <xref:System.Windows.FrameworkElement.Cursor%2A> per visualizzare un <xref:System.Windows.Input.CursorType.Hand> quando il <xref:System.Windows.UIElement.IsMouseOver%2A> le modifiche alle proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="d0ef5-106">The following example defines a <xref:System.Windows.Trigger> that sets the <xref:System.Windows.Controls.Control.Foreground%2A> property to <xref:System.Windows.Media.Brushes.Blue%2A> and changes the <xref:System.Windows.FrameworkElement.Cursor%2A> to display a <xref:System.Windows.Input.CursorType.Hand> when the <xref:System.Windows.UIElement.IsMouseOver%2A> property changes to `true`.</span></span>  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#Trigger](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#trigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
 <span data-ttu-id="d0ef5-107">L'esempio seguente definisce un <xref:System.Windows.MultiTrigger> che imposta il <xref:System.Windows.Controls.Control.Foreground%2A> proprietà di un <xref:System.Windows.Controls.ListViewItem> a <xref:System.Windows.Media.Brushes.Yellow%2A> quando il <xref:System.Windows.Controls.ListViewItem> è l'elemento selezionato e lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="d0ef5-107">The following example defines a <xref:System.Windows.MultiTrigger> that sets the <xref:System.Windows.Controls.Control.Foreground%2A> property of a <xref:System.Windows.Controls.ListViewItem> to <xref:System.Windows.Media.Brushes.Yellow%2A> when the <xref:System.Windows.Controls.ListViewItem> is the selected item and has keyboard focus.</span></span>  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#MultiTrigger](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#multitrigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
## <a name="see-also"></a><span data-ttu-id="d0ef5-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0ef5-108">See Also</span></span>  
 <xref:System.Windows.Controls.Control>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [<span data-ttu-id="d0ef5-109">Procedure relative</span><span class="sxs-lookup"><span data-stu-id="d0ef5-109">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [<span data-ttu-id="d0ef5-110">Panoramica sul controllo ListView</span><span class="sxs-lookup"><span data-stu-id="d0ef5-110">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [<span data-ttu-id="d0ef5-111">Cenni preliminari su GridView</span><span class="sxs-lookup"><span data-stu-id="d0ef5-111">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)
