---
title: 'Procedura: gestire un evento caricato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XAML [WPF], Loaded events
- events [WPF], Loaded
- Loaded events [WPF]
ms.assetid: 0cf8d003-8441-4df4-807a-6db09347e829
ms.openlocfilehash: 6f3520fc3bc2a64d76083af415588ff819890eb9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544196"
---
# <a name="how-to-handle-a-loaded-event"></a><span data-ttu-id="1617f-102">Procedura: gestire un evento caricato</span><span class="sxs-lookup"><span data-stu-id="1617f-102">How to: Handle a Loaded Event</span></span>
<span data-ttu-id="1617f-103">In questo esempio viene illustrato come gestire il <xref:System.Windows.FrameworkElement.Loaded?displayProperty=nameWithType> evento e uno scenario appropriato per la gestione di tale evento.</span><span class="sxs-lookup"><span data-stu-id="1617f-103">This example shows how to handle the <xref:System.Windows.FrameworkElement.Loaded?displayProperty=nameWithType> event, and an appropriate scenario for handling that event.</span></span> <span data-ttu-id="1617f-104">Il gestore crea un <xref:System.Windows.Controls.Button> quando il caricamento della pagina.</span><span class="sxs-lookup"><span data-stu-id="1617f-104">The handler  creates a <xref:System.Windows.Controls.Button> when the page loads.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1617f-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="1617f-105">Example</span></span>  
 <span data-ttu-id="1617f-106">L'esempio seguente usa [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] insieme a un file code-behind.</span><span class="sxs-lookup"><span data-stu-id="1617f-106">The following example uses [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] together with a code-behind file.</span></span>  
  
 [!code-xaml[FELoaded#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FELoaded#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml.cs#handler)]
 [!code-vb[FELoaded#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FELoaded/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a><span data-ttu-id="1617f-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1617f-107">See Also</span></span>  
 <xref:System.Windows.FrameworkElement>  
 [<span data-ttu-id="1617f-108">Eventi di durata degli oggetti</span><span class="sxs-lookup"><span data-stu-id="1617f-108">Object Lifetime Events</span></span>](../../../../docs/framework/wpf/advanced/object-lifetime-events.md)  
 [<span data-ttu-id="1617f-109">Cenni preliminari sugli eventi indirizzati</span><span class="sxs-lookup"><span data-stu-id="1617f-109">Routed Events Overview</span></span>](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [<span data-ttu-id="1617f-110">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="1617f-110">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
