---
title: 'Procedura: eseguire un hit test utilizzando un contenitore di host Win32'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], using Win32 host containers
- visual objects [WPF], hit tests on
- Win32 host containers [WPF], hit tests using
ms.assetid: 9491f7f3-d8ba-4573-a888-2f064d1349dc
ms.openlocfilehash: 01c6a9dad6fccb38be4f240d0900727f776fd2b7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560508"
---
# <a name="how-to-hit-test-using-a-win32-host-container"></a><span data-ttu-id="e920f-102">Procedura: eseguire un hit test utilizzando un contenitore di host Win32</span><span class="sxs-lookup"><span data-stu-id="e920f-102">How to: Hit Test Using a Win32 Host Container</span></span>
<span data-ttu-id="e920f-103">È possibile creare oggetti visivi all'interno di un [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] finestra fornendo un finestra contenitore host per gli oggetti visivi.</span><span class="sxs-lookup"><span data-stu-id="e920f-103">You can create visual objects within a [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] window by providing a host window container for the visual objects.</span></span> <span data-ttu-id="e920f-104">Per fornire la gestione degli eventi per gli oggetti visivi contenuti, elaborare i messaggi passati al ciclo del filtro messaggi del contenitore della finestra host.</span><span class="sxs-lookup"><span data-stu-id="e920f-104">To provide event handling for the contained visual objects you process the messages passed to the host window container’s message filter loop.</span></span> <span data-ttu-id="e920f-105">Fare riferimento a [esercitazione: Hosting di oggetti visivi in un'applicazione Win32](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md) per ulteriori informazioni su come pubblicare gli oggetti visivi di un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] finestra.</span><span class="sxs-lookup"><span data-stu-id="e920f-105">Refer to [Tutorial: Hosting Visual Objects in a Win32 Application](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md) for more information on how to host visual objects in a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e920f-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="e920f-106">Example</span></span>  
 <span data-ttu-id="e920f-107">Il codice seguente viene illustrato come impostare i gestori di eventi del mouse per un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] finestra che viene utilizzato come contenitore host per gli oggetti visivi.</span><span class="sxs-lookup"><span data-stu-id="e920f-107">The following code shows how to set up mouse event handlers for a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] window that is used as a host container for visual objects.</span></span>  
  
 [!code-csharp[VisualsHitTesting#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
 <span data-ttu-id="e920f-108">Nell'esempio seguente viene illustrato come impostare un hit test in risposta all'intercettazione di eventi del mouse specifici.</span><span class="sxs-lookup"><span data-stu-id="e920f-108">The following example shows how to set up a hit test in response to trapping specific mouse events.</span></span>  
  
 [!code-csharp[VisualsHitTesting#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 <span data-ttu-id="e920f-109">Il <xref:System.Windows.Interop.HwndSource> oggetto presenta [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] contenuto all'interno di un [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] finestra.</span><span class="sxs-lookup"><span data-stu-id="e920f-109">The <xref:System.Windows.Interop.HwndSource> object presents [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] content within a [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] window.</span></span> <span data-ttu-id="e920f-110">Il valore della <xref:System.Windows.Interop.HwndSource.RootVisual%2A> proprietà del <xref:System.Windows.Interop.HwndSource> oggetto rappresenta il nodo superiore nella gerarchia di struttura ad albero visuale.</span><span class="sxs-lookup"><span data-stu-id="e920f-110">The value of the <xref:System.Windows.Interop.HwndSource.RootVisual%2A> property of the <xref:System.Windows.Interop.HwndSource> object represents the top-most node in the visual tree hierarchy.</span></span>  
  
 <span data-ttu-id="e920f-111">Per l'esempio completo sull'hit testing gli oggetti di utilizzo di un contenitore host Win32, vedere [Hit Test con interoperatività Win32](http://go.microsoft.com/fwlink/?LinkID=159995).</span><span class="sxs-lookup"><span data-stu-id="e920f-111">For the complete sample on hit testing objects using a Win32 host container, see [Hit Test with Win32 Interoperation Sample](http://go.microsoft.com/fwlink/?LinkID=159995).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e920f-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e920f-112">See Also</span></span>  
 <xref:System.Windows.Interop.HwndSource>  
 [<span data-ttu-id="e920f-113">Hit testing a livello visivo</span><span class="sxs-lookup"><span data-stu-id="e920f-113">Hit Testing in the Visual Layer</span></span>](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)  
 [<span data-ttu-id="e920f-114">Esercitazione: hosting di oggetti visivi in un'applicazione Win32</span><span class="sxs-lookup"><span data-stu-id="e920f-114">Tutorial: Hosting Visual Objects in a Win32 Application</span></span>](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md)
