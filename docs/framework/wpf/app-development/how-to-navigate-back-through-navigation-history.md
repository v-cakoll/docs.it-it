---
title: 'Procedura: navigare indietro nella cronologia di navigazione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating back
- navigation [WPF], through navigation history (back)
ms.assetid: 9343234b-d864-441d-b8a7-d895cba80a87
ms.openlocfilehash: 7266c9486524e962a859c34c9be5ab8f6d7bf7d5
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/11/2018
ms.locfileid: "44367914"
---
# <a name="how-to-navigate-back-through-navigation-history"></a><span data-ttu-id="41558-102">Procedura: navigare indietro nella cronologia di navigazione</span><span class="sxs-lookup"><span data-stu-id="41558-102">How to: Navigate Back Through Navigation History</span></span>
<span data-ttu-id="41558-103">In questo esempio viene illustrato come passare da voci presenti nella cronologia di navigazione.</span><span class="sxs-lookup"><span data-stu-id="41558-103">This example illustrates how to navigate to entries in back navigation history.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41558-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="41558-104">Example</span></span>  
 <span data-ttu-id="41558-105">Il codice eseguito dal contenuto ospitato in un <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame> utilizzando <xref:System.Windows.Navigation.NavigationService>, o [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)] possono spostarsi indietro nella cronologia di navigazione, una voce alla volta.</span><span class="sxs-lookup"><span data-stu-id="41558-105">Code that is running from content that is hosted in a <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame> using <xref:System.Windows.Navigation.NavigationService>, or [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)] can navigate back through navigation history, one entry at a time.</span></span>  
  
 <span data-ttu-id="41558-106">Come lo spostamento indietro di una voce richiede il controllo per verificare che siano presenti voci nella cronologia di navigazione indietro, controllando la **CanGoBack** proprietà, prima che lo spostamento indietro di una voce, chiamando la **GoBack** metodo.</span><span class="sxs-lookup"><span data-stu-id="41558-106">Navigating back one entry requires first checking that there are entries in back navigation history, by inspecting the **CanGoBack** property, before navigating back one entry, by calling the **GoBack** method.</span></span> <span data-ttu-id="41558-107">Come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="41558-107">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 <span data-ttu-id="41558-108">**CanGoBack** e **GoBack** implementate dal <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, e <xref:System.Windows.Navigation.NavigationService>.</span><span class="sxs-lookup"><span data-stu-id="41558-108">**CanGoBack** and **GoBack** are implemented by <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, and <xref:System.Windows.Navigation.NavigationService>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="41558-109">Se si chiama **GoBack**, e non sono presenti voci nella cronologia di navigazione indietro un <xref:System.InvalidOperationException> viene generato.</span><span class="sxs-lookup"><span data-stu-id="41558-109">If you call **GoBack**, and there are no entries in back navigation history, an <xref:System.InvalidOperationException> is raised.</span></span>
