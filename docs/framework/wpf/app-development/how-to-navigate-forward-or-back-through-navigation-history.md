---
title: 'Procedura: navigare in avanti o indietro nella cronologia di navigazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating forward
- navigation [WPF], through navigation history (forward)
ms.assetid: 5939d574-5f53-469e-85f5-1f2b13607caa
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 78fd9fec6a93c100da6b4e7174376a963ae8beb2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-navigate-forward-or-back-through-navigation-history"></a><span data-ttu-id="b9fd5-102">Procedura: navigare in avanti o indietro nella cronologia di navigazione</span><span class="sxs-lookup"><span data-stu-id="b9fd5-102">How to: Navigate Forward or Back Through Navigation History</span></span>
<span data-ttu-id="b9fd5-103">In questo esempio viene illustrato come spostarsi in avanti o indietro per le voci nella cronologia di navigazione.</span><span class="sxs-lookup"><span data-stu-id="b9fd5-103">This example illustrates how to navigate forward or back to entries in navigation history.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9fd5-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="b9fd5-104">Example</span></span>  
 <span data-ttu-id="b9fd5-105">Codice che viene eseguita dal contenuto di host seguenti può spostarsi in avanti o indietro nella cronologia di navigazione, una voce per volta.</span><span class="sxs-lookup"><span data-stu-id="b9fd5-105">Code that runs from content in the following hosts can navigate forward or back through navigation history, one entry at a time.</span></span>  
  
-   <span data-ttu-id="b9fd5-106"><xref:System.Windows.Navigation.NavigationWindow>utilizzo<xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="b9fd5-106"><xref:System.Windows.Navigation.NavigationWindow> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
-   <span data-ttu-id="b9fd5-107"><xref:System.Windows.Controls.Frame>utilizzo<xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="b9fd5-107"><xref:System.Windows.Controls.Frame> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
-   [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)]  
  
 <span data-ttu-id="b9fd5-108">Prima è possibile spostarsi avanti di una voce, è necessario verificare che siano presenti voci nella cronologia di navigazione in avanti controllando il **CanGoForward** proprietà.</span><span class="sxs-lookup"><span data-stu-id="b9fd5-108">Before you can navigate forward one entry, you must first check that there are entries in forward navigation history by inspecting the **CanGoForward** property.</span></span> <span data-ttu-id="b9fd5-109">Per spostarsi avanti di una voce, si chiama il **GoForward** metodo.</span><span class="sxs-lookup"><span data-stu-id="b9fd5-109">To navigate forward one entry, you call the **GoForward** method.</span></span> <span data-ttu-id="b9fd5-110">Questo comportamento è illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="b9fd5-110">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 <span data-ttu-id="b9fd5-111">Prima di spostarsi indietro di una voce, è necessario innanzitutto controllare che siano presenti voci nella cronologia di navigazione all'indietro controllando il **CanGoBack** proprietà.</span><span class="sxs-lookup"><span data-stu-id="b9fd5-111">Before you can navigate back one entry, you must first check that there are entries in back navigation history by inspecting the **CanGoBack** property.</span></span> <span data-ttu-id="b9fd5-112">Per spostarsi indietro di una voce, si chiama il **GoBack** metodo.</span><span class="sxs-lookup"><span data-stu-id="b9fd5-112">To navigate back one entry, you call the **GoBack** method.</span></span> <span data-ttu-id="b9fd5-113">Questo comportamento è illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="b9fd5-113">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 <span data-ttu-id="b9fd5-114">**CanGoForward**, **GoForward**, **CanGoBack**, e **GoBack** vengono implementati da <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, e <xref:System.Windows.Navigation.NavigationService>.</span><span class="sxs-lookup"><span data-stu-id="b9fd5-114">**CanGoForward**, **GoForward**, **CanGoBack**, and **GoBack** are implemented by <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, and <xref:System.Windows.Navigation.NavigationService>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b9fd5-115">Se si chiama **GoForward**, e non sono presenti voci nella cronologia di navigazione in avanti, o se si chiama **GoBack**, e non sono presenti voci nella cronologia di navigazione all'indietro, un <xref:System.InvalidOperationException> viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="b9fd5-115">If you call **GoForward**, and there are no entries in forward navigation history, or if you call **GoBack**, and there are no entries in back navigation history, an <xref:System.InvalidOperationException> is thrown.</span></span>
