---
title: 'Procedura: Navigare in avanti o indietro nella cronologia di navigazione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating forward
- navigation [WPF], through navigation history (forward)
ms.assetid: 5939d574-5f53-469e-85f5-1f2b13607caa
ms.openlocfilehash: 4c20ebfab45a24cf34b1476fb94dae6913fb4d99
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57366660"
---
# <a name="how-to-navigate-forward-or-back-through-navigation-history"></a><span data-ttu-id="dc0b8-102">Procedura: Navigare in avanti o indietro nella cronologia di navigazione</span><span class="sxs-lookup"><span data-stu-id="dc0b8-102">How to: Navigate Forward or Back Through Navigation History</span></span>
<span data-ttu-id="dc0b8-103">In questo esempio viene illustrato come spostarsi in avanti o indietro per le voci nella cronologia di navigazione.</span><span class="sxs-lookup"><span data-stu-id="dc0b8-103">This example illustrates how to navigate forward or back to entries in navigation history.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc0b8-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="dc0b8-104">Example</span></span>  
 <span data-ttu-id="dc0b8-105">Codice eseguito dai contenuti i seguenti host possibile spostarsi in avanti o indietro nella cronologia di navigazione, una voce alla volta.</span><span class="sxs-lookup"><span data-stu-id="dc0b8-105">Code that runs from content in the following hosts can navigate forward or back through navigation history, one entry at a time.</span></span>  
  
-   <span data-ttu-id="dc0b8-106"><xref:System.Windows.Navigation.NavigationWindow> Utilizzo <xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="dc0b8-106"><xref:System.Windows.Navigation.NavigationWindow> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
-   <span data-ttu-id="dc0b8-107"><xref:System.Windows.Controls.Frame> Utilizzo <xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="dc0b8-107"><xref:System.Windows.Controls.Frame> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
-   [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)]  
  
 <span data-ttu-id="dc0b8-108">Prima è possibile spostarsi in avanti di una voce, è necessario verificare che siano presenti voci nella cronologia di navigazione avanti controllando il **CanGoForward** proprietà.</span><span class="sxs-lookup"><span data-stu-id="dc0b8-108">Before you can navigate forward one entry, you must first check that there are entries in forward navigation history by inspecting the **CanGoForward** property.</span></span> <span data-ttu-id="dc0b8-109">Per spostarsi avanti di una voce, si chiama il **GoForward** (metodo).</span><span class="sxs-lookup"><span data-stu-id="dc0b8-109">To navigate forward one entry, you call the **GoForward** method.</span></span> <span data-ttu-id="dc0b8-110">Come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="dc0b8-110">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 <span data-ttu-id="dc0b8-111">Prima è possibile spostarsi indietro di una voce, è prima di tutto necessario verificare che siano presenti voci nella cronologia di navigazione indietro controllando il **CanGoBack** proprietà.</span><span class="sxs-lookup"><span data-stu-id="dc0b8-111">Before you can navigate back one entry, you must first check that there are entries in back navigation history by inspecting the **CanGoBack** property.</span></span> <span data-ttu-id="dc0b8-112">Per spostarsi indietro di una voce, si chiama il **GoBack** (metodo).</span><span class="sxs-lookup"><span data-stu-id="dc0b8-112">To navigate back one entry, you call the **GoBack** method.</span></span> <span data-ttu-id="dc0b8-113">Come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="dc0b8-113">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 <span data-ttu-id="dc0b8-114">**CanGoForward**, **GoForward**, **CanGoBack**, e **GoBack** implementate da <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, e <xref:System.Windows.Navigation.NavigationService>.</span><span class="sxs-lookup"><span data-stu-id="dc0b8-114">**CanGoForward**, **GoForward**, **CanGoBack**, and **GoBack** are implemented by <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, and <xref:System.Windows.Navigation.NavigationService>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc0b8-115">Se si chiama **GoForward**, e non sono presenti voci nella cronologia di navigazione avanti oppure se si chiama **GoBack**, e non sono presenti voci nella cronologia di navigazione indietro un <xref:System.InvalidOperationException> viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="dc0b8-115">If you call **GoForward**, and there are no entries in forward navigation history, or if you call **GoBack**, and there are no entries in back navigation history, an <xref:System.InvalidOperationException> is thrown.</span></span>
