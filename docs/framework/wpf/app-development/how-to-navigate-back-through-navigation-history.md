---
title: 'Procedura: spostarsi indietro nella cronologia di navigazione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating back
- navigation [WPF], through navigation history (back)
ms.assetid: 9343234b-d864-441d-b8a7-d895cba80a87
ms.openlocfilehash: 9acbc5d3388a8df0ec7d7b5326f449f092f0cb03
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33546672"
---
# <a name="how-to-navigate-back-through-navigation-history"></a><span data-ttu-id="68dbf-102">Procedura: spostarsi indietro nella cronologia di navigazione</span><span class="sxs-lookup"><span data-stu-id="68dbf-102">How to: Navigate Back Through Navigation History</span></span>
<span data-ttu-id="68dbf-103">In questo esempio viene illustrato come passare a voci presenti nella cronologia di navigazione.</span><span class="sxs-lookup"><span data-stu-id="68dbf-103">This example illustrates how to navigate to entries in back navigation history.</span></span>  
  
## <a name="example"></a><span data-ttu-id="68dbf-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="68dbf-104">Example</span></span>  
 <span data-ttu-id="68dbf-105">Codice che è in esecuzione dal contenuto ospitato in un <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame> utilizzare <xref:System.Windows.Navigation.NavigationService>, o [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)] possibile spostarsi indietro nella cronologia di navigazione, una voce alla volta.</span><span class="sxs-lookup"><span data-stu-id="68dbf-105">Code that is running from content that is hosted in a <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame> use <xref:System.Windows.Navigation.NavigationService>, or [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)] can navigate back through navigation history, one entry at a time.</span></span>  
  
 <span data-ttu-id="68dbf-106">Spostamento all'indietro di una voce richiede il controllo per verificare che siano presenti voci nella cronologia di navigazione all'indietro, controllando il **CanGoBack** proprietà, prima dello spostamento all'indietro di una voce, chiamando la **GoBack** metodo.</span><span class="sxs-lookup"><span data-stu-id="68dbf-106">Navigating back one entry requires first checking that there are entries in back navigation history, by inspecting the **CanGoBack** property, before navigating back one entry, by calling the **GoBack** method.</span></span> <span data-ttu-id="68dbf-107">Questo comportamento è illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="68dbf-107">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 <span data-ttu-id="68dbf-108">**CanGoBack** e **GoBack** implementate dal <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, e <xref:System.Windows.Navigation.NavigationService>.</span><span class="sxs-lookup"><span data-stu-id="68dbf-108">**CanGoBack** and **GoBack** are implemented by <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, and <xref:System.Windows.Navigation.NavigationService>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="68dbf-109">Se si chiama **GoBack**, e non sono presenti voci nella cronologia di navigazione all'indietro, un <xref:System.InvalidOperationException> viene generato.</span><span class="sxs-lookup"><span data-stu-id="68dbf-109">If you call **GoBack**, and there are no entries in back navigation history, an <xref:System.InvalidOperationException> is raised.</span></span>
