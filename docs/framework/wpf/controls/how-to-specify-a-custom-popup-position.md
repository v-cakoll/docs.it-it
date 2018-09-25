---
title: 'Procedura: specificare una posizione personalizzata per un controllo Popup'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Popup control [WPF], specifying custom position
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
ms.openlocfilehash: e6e81a6e0819ba3eb39a1c568e6872414e671544
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2018
ms.locfileid: "47027765"
---
# <a name="how-to-specify-a-custom-popup-position"></a><span data-ttu-id="f4a61-102">Procedura: specificare una posizione personalizzata per un controllo Popup</span><span class="sxs-lookup"><span data-stu-id="f4a61-102">How to: Specify a Custom Popup Position</span></span>
<span data-ttu-id="f4a61-103">In questo esempio viene illustrato come specificare una posizione personalizzata per un <xref:System.Windows.Controls.Primitives.Popup> controllare quando i <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> è impostata su <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span><span class="sxs-lookup"><span data-stu-id="f4a61-103">This example shows how to specify a custom position for a <xref:System.Windows.Controls.Primitives.Popup> control when the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4a61-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="f4a61-104">Example</span></span>  
 <span data-ttu-id="f4a61-105">Quando la <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> è impostata su <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>, il <xref:System.Windows.Controls.Primitives.Popup> chiama un'istanza definita del <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegare.</span><span class="sxs-lookup"><span data-stu-id="f4a61-105">When the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>, the <xref:System.Windows.Controls.Primitives.Popup> calls a defined instance of the <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate.</span></span> <span data-ttu-id="f4a61-106">Questo delegato restituisce un set di possibili punti relativi rispetto all'angolo superiore sinistro dell'area di destinazione e l'angolo superiore sinistro del <xref:System.Windows.Controls.Primitives.Popup>.</span><span class="sxs-lookup"><span data-stu-id="f4a61-106">This delegate returns a set of possible points that are relative to the top left corner of the target area and the top left corner of the <xref:System.Windows.Controls.Primitives.Popup>.</span></span> <span data-ttu-id="f4a61-107">Il <xref:System.Windows.Controls.Primitives.Popup> posizionamento si verifica nel momento in cui offre la migliore visibilità.</span><span class="sxs-lookup"><span data-stu-id="f4a61-107">The <xref:System.Windows.Controls.Primitives.Popup> placement occurs at the point that provides the best visibility.</span></span>  
  
 <span data-ttu-id="f4a61-108">Nell'esempio seguente viene illustrato come definire la posizione di un <xref:System.Windows.Controls.Primitives.Popup> impostando la <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> proprietà <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span><span class="sxs-lookup"><span data-stu-id="f4a61-108">The following example shows how to define the position of a <xref:System.Windows.Controls.Primitives.Popup> by setting the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span> <span data-ttu-id="f4a61-109">Viene inoltre illustrato come creare e assegnare un <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegato per posizionare il <xref:System.Windows.Controls.Primitives.Popup>.</span><span class="sxs-lookup"><span data-stu-id="f4a61-109">It also shows how to create and assign a <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate in order to position the <xref:System.Windows.Controls.Primitives.Popup>.</span></span>  <span data-ttu-id="f4a61-110">Il delegato di callback restituisce due <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> oggetti.</span><span class="sxs-lookup"><span data-stu-id="f4a61-110">The callback delegate returns two <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> objects.</span></span>  <span data-ttu-id="f4a61-111">Se il <xref:System.Windows.Controls.Primitives.Popup> è nascosto da un bordo dello schermo in corrispondenza della prima posizione, la <xref:System.Windows.Controls.Primitives.Popup> viene posizionato in corrispondenza della posizione di secondo.</span><span class="sxs-lookup"><span data-stu-id="f4a61-111">If the <xref:System.Windows.Controls.Primitives.Popup> is hidden by a screen edge at the first position, the <xref:System.Windows.Controls.Primitives.Popup> is placed at the second position.</span></span>  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 <span data-ttu-id="f4a61-112">Per l'esempio completo, vedere [Popup Placement Sample](https://go.microsoft.com/fwlink/?LinkID=160032).</span><span class="sxs-lookup"><span data-stu-id="f4a61-112">For the complete sample, see [Popup Placement Sample](https://go.microsoft.com/fwlink/?LinkID=160032).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4a61-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4a61-113">See Also</span></span>  
 <xref:System.Windows.Controls.Primitives.Popup>  
 [<span data-ttu-id="f4a61-114">Panoramica sul controllo Popup</span><span class="sxs-lookup"><span data-stu-id="f4a61-114">Popup Overview</span></span>](../../../../docs/framework/wpf/controls/popup-overview.md)  
 [<span data-ttu-id="f4a61-115">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="f4a61-115">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/popup-how-to-topics.md)
