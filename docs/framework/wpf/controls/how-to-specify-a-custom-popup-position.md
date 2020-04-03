---
title: 'Procedura: specificare una posizione personalizzata per un controllo Popup'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Popup control [WPF], specifying custom position
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
ms.openlocfilehash: b48dedc044b418062642af5c5bb40afab78a3c97
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635746"
---
# <a name="how-to-specify-a-custom-popup-position"></a><span data-ttu-id="90f06-102">Procedura: specificare una posizione personalizzata per un controllo Popup</span><span class="sxs-lookup"><span data-stu-id="90f06-102">How to: Specify a Custom Popup Position</span></span>
<span data-ttu-id="90f06-103">In questo esempio viene illustrato come <xref:System.Windows.Controls.Primitives.Popup> specificare <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> una posizione <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>personalizzata per un controllo quando la proprietà è impostata su .</span><span class="sxs-lookup"><span data-stu-id="90f06-103">This example shows how to specify a custom position for a <xref:System.Windows.Controls.Primitives.Popup> control when the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="90f06-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="90f06-104">Example</span></span>  
 <span data-ttu-id="90f06-105">Quando <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> la proprietà <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>è <xref:System.Windows.Controls.Primitives.Popup> impostata su , <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> chiama un'istanza definita del delegato.</span><span class="sxs-lookup"><span data-stu-id="90f06-105">When the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>, the <xref:System.Windows.Controls.Primitives.Popup> calls a defined instance of the <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate.</span></span> <span data-ttu-id="90f06-106">Questo delegato restituisce un set di possibili punti relativi all'angolo superiore sinistro dell'area di destinazione e all'angolo superiore sinistro dell'oggetto <xref:System.Windows.Controls.Primitives.Popup>.</span><span class="sxs-lookup"><span data-stu-id="90f06-106">This delegate returns a set of possible points that are relative to the top-left corner of the target area and the top-left corner of the <xref:System.Windows.Controls.Primitives.Popup>.</span></span> <span data-ttu-id="90f06-107">Il <xref:System.Windows.Controls.Primitives.Popup> posizionamento avviene nel punto che offre la migliore visibilità.</span><span class="sxs-lookup"><span data-stu-id="90f06-107">The <xref:System.Windows.Controls.Primitives.Popup> placement occurs at the point that provides the best visibility.</span></span>  
  
 <span data-ttu-id="90f06-108">Nell'esempio riportato di seguito <xref:System.Windows.Controls.Primitives.Popup> viene illustrato <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> come <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>definire la posizione di un oggetto impostando la proprietà su .</span><span class="sxs-lookup"><span data-stu-id="90f06-108">The following example shows how to define the position of a <xref:System.Windows.Controls.Primitives.Popup> by setting the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span> <span data-ttu-id="90f06-109">Viene inoltre illustrato come creare <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> e assegnare <xref:System.Windows.Controls.Primitives.Popup>un delegato per posizionare il file .</span><span class="sxs-lookup"><span data-stu-id="90f06-109">It also shows how to create and assign a <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate in order to position the <xref:System.Windows.Controls.Primitives.Popup>.</span></span>  <span data-ttu-id="90f06-110">Il delegato di <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> callback restituisce due oggetti.</span><span class="sxs-lookup"><span data-stu-id="90f06-110">The callback delegate returns two <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> objects.</span></span>  <span data-ttu-id="90f06-111">Se <xref:System.Windows.Controls.Primitives.Popup> l'oggetto è nascosto da un <xref:System.Windows.Controls.Primitives.Popup> bordo dello schermo nella prima posizione, l'oggetto viene posizionato in corrispondenza della seconda posizione.</span><span class="sxs-lookup"><span data-stu-id="90f06-111">If the <xref:System.Windows.Controls.Primitives.Popup> is hidden by a screen edge at the first position, the <xref:System.Windows.Controls.Primitives.Popup> is placed at the second position.</span></span>  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 <span data-ttu-id="90f06-112">Per l'esempio completo, vedere Esempio di [posizionamento popup](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS).</span><span class="sxs-lookup"><span data-stu-id="90f06-112">For the complete sample, see [Popup Placement Sample](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90f06-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90f06-113">See also</span></span>

- <xref:System.Windows.Controls.Primitives.Popup>
- [<span data-ttu-id="90f06-114">Panoramica dei popup</span><span class="sxs-lookup"><span data-stu-id="90f06-114">Popup overview</span></span>](popup-overview.md)
- [<span data-ttu-id="90f06-115">Articoli pratici</span><span class="sxs-lookup"><span data-stu-id="90f06-115">How-to articles</span></span>](popup-how-to-topics.md)
