---
title: 'Procedura: Navigare indietro nella cronologia di navigazione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating back
- navigation [WPF], through navigation history (back)
ms.assetid: 9343234b-d864-441d-b8a7-d895cba80a87
ms.openlocfilehash: c489a1593b3d1f22fe1ad6e648d3f8a3f7a6cd44
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377768"
---
# <a name="how-to-navigate-back-through-navigation-history"></a><span data-ttu-id="c17cf-102">Procedura: Navigare indietro nella cronologia di navigazione</span><span class="sxs-lookup"><span data-stu-id="c17cf-102">How to: Navigate Back Through Navigation History</span></span>
<span data-ttu-id="c17cf-103">In questo esempio viene illustrato come passare da voci presenti nella cronologia di navigazione.</span><span class="sxs-lookup"><span data-stu-id="c17cf-103">This example illustrates how to navigate to entries in back navigation history.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c17cf-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="c17cf-104">Example</span></span>  
 <span data-ttu-id="c17cf-105">Il codice eseguito dal contenuto ospitato in un <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame> utilizzando <xref:System.Windows.Navigation.NavigationService>, o [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)] possono spostarsi indietro nella cronologia di navigazione, una voce alla volta.</span><span class="sxs-lookup"><span data-stu-id="c17cf-105">Code that is running from content that is hosted in a <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame> using <xref:System.Windows.Navigation.NavigationService>, or [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)] can navigate back through navigation history, one entry at a time.</span></span>  
  
 <span data-ttu-id="c17cf-106">Come lo spostamento indietro di una voce richiede il controllo per verificare che siano presenti voci nella cronologia di navigazione indietro, controllando la **CanGoBack** proprietà, prima che lo spostamento indietro di una voce, chiamando la **GoBack** metodo.</span><span class="sxs-lookup"><span data-stu-id="c17cf-106">Navigating back one entry requires first checking that there are entries in back navigation history, by inspecting the **CanGoBack** property, before navigating back one entry, by calling the **GoBack** method.</span></span> <span data-ttu-id="c17cf-107">Come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="c17cf-107">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 <span data-ttu-id="c17cf-108">**CanGoBack** e **GoBack** implementate dal <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, e <xref:System.Windows.Navigation.NavigationService>.</span><span class="sxs-lookup"><span data-stu-id="c17cf-108">**CanGoBack** and **GoBack** are implemented by <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, and <xref:System.Windows.Navigation.NavigationService>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c17cf-109">Se si chiama **GoBack**, e non sono presenti voci nella cronologia di navigazione indietro un <xref:System.InvalidOperationException> viene generato.</span><span class="sxs-lookup"><span data-stu-id="c17cf-109">If you call **GoBack**, and there are no entries in back navigation history, an <xref:System.InvalidOperationException> is raised.</span></span>
