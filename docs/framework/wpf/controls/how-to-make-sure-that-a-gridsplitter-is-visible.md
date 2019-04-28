---
title: 'Procedura: Assicurarsi che GridSplitter sia visibile'
ms.date: 03/30/2017
helpviewer_keywords:
- GridSplitter control [WPF], ensuring visibility of
ms.assetid: 0a62a964-89c8-48f0-9023-5df721a8cf47
ms.openlocfilehash: b7543d14ba39d854b5a2c3f4d0d19b9a457ea89b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61770851"
---
# <a name="how-to-make-sure-that-a-gridsplitter-is-visible"></a><span data-ttu-id="822c8-102">Procedura: Assicurarsi che GridSplitter sia visibile</span><span class="sxs-lookup"><span data-stu-id="822c8-102">How to: Make Sure That a GridSplitter Is Visible</span></span>
<span data-ttu-id="822c8-103">In questo esempio viene illustrato come assicurarsi che un <xref:System.Windows.Controls.GridSplitter> controllo non è nascosto da altri controlli in un <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="822c8-103">This example shows how to make sure a <xref:System.Windows.Controls.GridSplitter> control is not hidden by the other controls in a <xref:System.Windows.Controls.Grid>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="822c8-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="822c8-104">Example</span></span>  
 <span data-ttu-id="822c8-105">Il <xref:System.Windows.Controls.Panel.Children%2A> di un <xref:System.Windows.Controls.Grid> controllo vengono visualizzati in ordine che sono definiti nel codice o markup.</span><span class="sxs-lookup"><span data-stu-id="822c8-105">The <xref:System.Windows.Controls.Panel.Children%2A> of a <xref:System.Windows.Controls.Grid> control are rendered in the order that they are defined in markup or code.</span></span> <span data-ttu-id="822c8-106"><xref:System.Windows.Controls.GridSplitter> i controlli possono essere nascosti da altri controlli se si non vengono definiti come gli ultimi elementi nel <xref:System.Windows.Controls.Panel.Children%2A> raccolta o se si assegna ad altri controlli di un livello più elevato <xref:System.Windows.Controls.Panel.ZIndexProperty>.</span><span class="sxs-lookup"><span data-stu-id="822c8-106"><xref:System.Windows.Controls.GridSplitter> controls can be hidden by other controls if you do not define them as the last elements in the <xref:System.Windows.Controls.Panel.Children%2A> collection or if you give other controls a higher <xref:System.Windows.Controls.Panel.ZIndexProperty>.</span></span>  
  
 <span data-ttu-id="822c8-107">Per evitare nascosto <xref:System.Windows.Controls.GridSplitter> controlli, effettuare una delle operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="822c8-107">To prevent hidden <xref:System.Windows.Controls.GridSplitter> controls, do one of the following.</span></span>  
  
- <span data-ttu-id="822c8-108">Verificare che l'opzione <xref:System.Windows.Controls.GridSplitter> controlli sono l'ultima <xref:System.Windows.Controls.Panel.Children%2A> aggiunto al <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="822c8-108">Make sure that <xref:System.Windows.Controls.GridSplitter> controls are the last <xref:System.Windows.Controls.Panel.Children%2A> added to the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="822c8-109">L'esempio seguente illustra il <xref:System.Windows.Controls.GridSplitter> come l'ultimo elemento nel <xref:System.Windows.Controls.Panel.Children%2A> insieme del <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="822c8-109">The following example shows the <xref:System.Windows.Controls.GridSplitter> as the last element in the <xref:System.Windows.Controls.Panel.Children%2A> collection of the <xref:System.Windows.Controls.Grid>.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterLastChild](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterlastchild)]  
  
- <span data-ttu-id="822c8-110">Impostare il <xref:System.Windows.Controls.Panel.ZIndexProperty> nella <xref:System.Windows.Controls.GridSplitter> superiori rispetto a un controllo che sarebbe altrimenti nasconderlo.</span><span class="sxs-lookup"><span data-stu-id="822c8-110">Set the <xref:System.Windows.Controls.Panel.ZIndexProperty> on the <xref:System.Windows.Controls.GridSplitter> to be higher than a control that would otherwise hide it.</span></span> <span data-ttu-id="822c8-111">L'esempio seguente restituisce il <xref:System.Windows.Controls.GridSplitter> controllano un livello più elevato <xref:System.Windows.Controls.Panel.ZIndexProperty> rispetto al <xref:System.Windows.Controls.Button> controllo.</span><span class="sxs-lookup"><span data-stu-id="822c8-111">The following example gives the <xref:System.Windows.Controls.GridSplitter> control a higher <xref:System.Windows.Controls.Panel.ZIndexProperty> than the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterZIndex](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterzindex)]  
  
- <span data-ttu-id="822c8-112">Impostare i margini del controllo che in caso contrario nasconderà la <xref:System.Windows.Controls.GridSplitter> in modo che il <xref:System.Windows.Controls.GridSplitter> viene esposto.</span><span class="sxs-lookup"><span data-stu-id="822c8-112">Set margins on the control that would otherwise hide the <xref:System.Windows.Controls.GridSplitter> so that the <xref:System.Windows.Controls.GridSplitter> is exposed.</span></span> <span data-ttu-id="822c8-113">L'esempio seguente imposta i margini su un controllo che sarebbe altrimenti si sovrappongono e nascondono la <xref:System.Windows.Controls.GridSplitter>.</span><span class="sxs-lookup"><span data-stu-id="822c8-113">The following example sets margins on a control that would otherwise overlay and hide the <xref:System.Windows.Controls.GridSplitter>.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterMargin](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplittermargin)]  
  
## <a name="see-also"></a><span data-ttu-id="822c8-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="822c8-114">See also</span></span>

- <xref:System.Windows.Controls.GridSplitter>
- [<span data-ttu-id="822c8-115">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="822c8-115">How-to Topics</span></span>](gridsplitter-how-to-topics.md)
