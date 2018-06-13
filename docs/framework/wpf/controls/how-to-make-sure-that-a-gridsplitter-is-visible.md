---
title: 'Procedura: assicurarsi che GridSplitter sia visibile'
ms.date: 03/30/2017
helpviewer_keywords:
- GridSplitter control [WPF], ensuring visibility of
ms.assetid: 0a62a964-89c8-48f0-9023-5df721a8cf47
ms.openlocfilehash: 926df118bfd8e7ab3d1f0c953d0b6debafd59073
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33554820"
---
# <a name="how-to-make-sure-that-a-gridsplitter-is-visible"></a><span data-ttu-id="fabcb-102">Procedura: assicurarsi che GridSplitter sia visibile</span><span class="sxs-lookup"><span data-stu-id="fabcb-102">How to: Make Sure That a GridSplitter Is Visible</span></span>
<span data-ttu-id="fabcb-103">In questo esempio viene illustrato come assicurarsi che un <xref:System.Windows.Controls.GridSplitter> controllo non è nascosto da altri controlli in un <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="fabcb-103">This example shows how to make sure a <xref:System.Windows.Controls.GridSplitter> control is not hidden by the other controls in a <xref:System.Windows.Controls.Grid>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fabcb-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="fabcb-104">Example</span></span>  
 <span data-ttu-id="fabcb-105">Il <xref:System.Windows.Controls.Panel.Children%2A> di un <xref:System.Windows.Controls.Grid> controllo vengono visualizzati in ordine di definizione nel markup o codice.</span><span class="sxs-lookup"><span data-stu-id="fabcb-105">The <xref:System.Windows.Controls.Panel.Children%2A> of a <xref:System.Windows.Controls.Grid> control are rendered in the order that they are defined in markup or code.</span></span> <span data-ttu-id="fabcb-106"><xref:System.Windows.Controls.GridSplitter> controlli possono essere nascosti da altri controlli se non vengono definiti come ultimi elementi nel <xref:System.Windows.Controls.Panel.Children%2A> insieme o se si assegna ad altri controlli di un livello più elevato <xref:System.Windows.Controls.Panel.ZIndexProperty>.</span><span class="sxs-lookup"><span data-stu-id="fabcb-106"><xref:System.Windows.Controls.GridSplitter> controls can be hidden by other controls if you do not define them as the last elements in the <xref:System.Windows.Controls.Panel.Children%2A> collection or if you give other controls a higher <xref:System.Windows.Controls.Panel.ZIndexProperty>.</span></span>  
  
 <span data-ttu-id="fabcb-107">Per evitare nascosto <xref:System.Windows.Controls.GridSplitter> controlli, eseguire una delle operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="fabcb-107">To prevent hidden <xref:System.Windows.Controls.GridSplitter> controls, do one of the following.</span></span>  
  
-   <span data-ttu-id="fabcb-108">Assicurarsi che <xref:System.Windows.Controls.GridSplitter> i controlli sono l'ultima <xref:System.Windows.Controls.Panel.Children%2A> aggiunti il <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="fabcb-108">Make sure that <xref:System.Windows.Controls.GridSplitter> controls are the last <xref:System.Windows.Controls.Panel.Children%2A> added to the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="fabcb-109">Nell'esempio seguente il <xref:System.Windows.Controls.GridSplitter> come l'ultimo elemento il <xref:System.Windows.Controls.Panel.Children%2A> insieme del <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="fabcb-109">The following example shows the <xref:System.Windows.Controls.GridSplitter> as the last element in the <xref:System.Windows.Controls.Panel.Children%2A> collection of the <xref:System.Windows.Controls.Grid>.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterLastChild](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterlastchild)]  
  
-   <span data-ttu-id="fabcb-110">Impostare il <xref:System.Windows.Controls.Panel.ZIndexProperty> sul <xref:System.Windows.Controls.GridSplitter> è superiore a un controllo che sarebbe altrimenti nasconderlo.</span><span class="sxs-lookup"><span data-stu-id="fabcb-110">Set the <xref:System.Windows.Controls.Panel.ZIndexProperty> on the <xref:System.Windows.Controls.GridSplitter> to be higher than a control that would otherwise hide it.</span></span> <span data-ttu-id="fabcb-111">Nell'esempio seguente consente di <xref:System.Windows.Controls.GridSplitter> controllano un livello più elevato <xref:System.Windows.Controls.Panel.ZIndexProperty> rispetto di <xref:System.Windows.Controls.Button> controllo.</span><span class="sxs-lookup"><span data-stu-id="fabcb-111">The following example gives the <xref:System.Windows.Controls.GridSplitter> control a higher <xref:System.Windows.Controls.Panel.ZIndexProperty> than the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterZIndex](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterzindex)]  
  
-   <span data-ttu-id="fabcb-112">Impostare i margini del controllo che in caso contrario nasconderà la <xref:System.Windows.Controls.GridSplitter> in modo che il <xref:System.Windows.Controls.GridSplitter> viene esposta.</span><span class="sxs-lookup"><span data-stu-id="fabcb-112">Set margins on the control that would otherwise hide the <xref:System.Windows.Controls.GridSplitter> so that the <xref:System.Windows.Controls.GridSplitter> is exposed.</span></span> <span data-ttu-id="fabcb-113">Nell'esempio seguente imposta i margini su un controllo che in caso contrario, verrebbe sovrapposto e nascondere il <xref:System.Windows.Controls.GridSplitter>.</span><span class="sxs-lookup"><span data-stu-id="fabcb-113">The following example sets margins on a control that would otherwise overlay and hide the <xref:System.Windows.Controls.GridSplitter>.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterMargin](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplittermargin)]  
  
## <a name="see-also"></a><span data-ttu-id="fabcb-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fabcb-114">See Also</span></span>  
 <xref:System.Windows.Controls.GridSplitter>  
 [<span data-ttu-id="fabcb-115">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="fabcb-115">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)
