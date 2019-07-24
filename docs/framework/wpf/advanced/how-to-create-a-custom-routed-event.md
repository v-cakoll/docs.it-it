---
title: 'Procedura: Creare un evento indirizzato personalizzato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], creating
- events [WPF], routing
ms.assetid: b79f459a-1c3f-4045-b2d4-1659cc8eaa3c
ms.openlocfilehash: cbfb88af4e35e3f090248982bb14d6b7a3a03cef
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401463"
---
# <a name="how-to-create-a-custom-routed-event"></a><span data-ttu-id="c8001-102">Procedura: Creare un evento indirizzato personalizzato</span><span class="sxs-lookup"><span data-stu-id="c8001-102">How to: Create a Custom Routed Event</span></span>
<span data-ttu-id="c8001-103">Affinché l'evento personalizzato supporti il routing degli eventi, è necessario registrare un <xref:System.Windows.RoutedEvent> usando il <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="c8001-103">For your custom event to support event routing, you need to register a <xref:System.Windows.RoutedEvent> using the <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> method.</span></span> <span data-ttu-id="c8001-104">Questo esempio illustra le nozioni di base per la creazione di un evento indirizzato personalizzato.</span><span class="sxs-lookup"><span data-stu-id="c8001-104">This example demonstrates the basics of creating a custom routed event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8001-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="c8001-105">Example</span></span>  
 <span data-ttu-id="c8001-106">Come illustrato nell'esempio seguente, è necessario innanzitutto registrare un <xref:System.Windows.RoutedEvent> oggetto usando <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> il metodo.</span><span class="sxs-lookup"><span data-stu-id="c8001-106">As shown in the following example, you first register a <xref:System.Windows.RoutedEvent> using the <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> method.</span></span> <span data-ttu-id="c8001-107">Per convenzione, il <xref:System.Windows.RoutedEvent> nome del campo statico deve terminare con l' ***evento***suffisso.</span><span class="sxs-lookup"><span data-stu-id="c8001-107">By convention, the <xref:System.Windows.RoutedEvent> static field name should end with the suffix ***Event***.</span></span> <span data-ttu-id="c8001-108">In questo esempio, il nome dell'evento è `Tap` e la strategia di routing dell'evento è. <xref:System.Windows.RoutingStrategy.Bubble></span><span class="sxs-lookup"><span data-stu-id="c8001-108">In this example, the name of the event is `Tap` and the routing strategy of the event is <xref:System.Windows.RoutingStrategy.Bubble>.</span></span> <span data-ttu-id="c8001-109">Dopo la chiamata di registrazione, è possibile fornire funzioni di accesso agli eventi Common Language Runtime (CLR) Add-and-Remove per l'evento.</span><span class="sxs-lookup"><span data-stu-id="c8001-109">After the registration call, you can provide add-and-remove common language runtime (CLR) event accessors for the event.</span></span>  
  
 <span data-ttu-id="c8001-110">Si noti che anche se l'evento viene generato tramite il metodo virtuale `OnTap` in questo particolare esempio, la modalità di generazione dell'evento o la relativa risposta alle modifiche varierà in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="c8001-110">Note that even though the event is raised through the `OnTap` virtual method in this particular example, how you raise your event or how your event responds to changes depends on your needs.</span></span>  
  
 <span data-ttu-id="c8001-111">Si noti inoltre che in questo esempio viene implementata essenzialmente <xref:System.Windows.Controls.Button>un'intera sottoclasse di. tale sottoclasse viene compilata come assembly separato e quindi creata come [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] classe personalizzata in una pagina separata.</span><span class="sxs-lookup"><span data-stu-id="c8001-111">Note also that this example basically implements an entire subclass of <xref:System.Windows.Controls.Button>; that subclass is built as a separate assembly and then instantiated as a custom class on a separate [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] page.</span></span> <span data-ttu-id="c8001-112">Ciò dimostra che i controlli sottoclassati possono essere inseriti in alberi composti da altri controlli e che, in una situazione del genere, gli eventi personalizzati in questi controlli dispongono delle stesse funzionalità di routing di qualsiasi elemento [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] nativo.</span><span class="sxs-lookup"><span data-stu-id="c8001-112">This is to illustrate the concept that subclassed controls can be inserted into trees composed of other controls, and that in this situation, custom events on these controls have the very same event routing capabilities as any native [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] element does.</span></span>  
  
 [!code-csharp[RoutedEventCustom#CustomClass](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/SDKSampleLibrary/class1.cs#customclass)]
 [!code-vb[RoutedEventCustom#CustomClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventCustom/VB/SDKSampleLibrary/Class1.vb#customclass)]  
  
 [!code-xaml[RoutedEventCustom#Page](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/RoutedEventCustomApp/default.xaml#page)]  
  
 <span data-ttu-id="c8001-113">Gli eventi di tunneling vengono creati nello stesso modo, <xref:System.Windows.RoutedEvent.RoutingStrategy%2A> ma con <xref:System.Windows.RoutingStrategy.Tunnel> impostato su nella chiamata di registrazione.</span><span class="sxs-lookup"><span data-stu-id="c8001-113">Tunneling events are created the same way, but with <xref:System.Windows.RoutedEvent.RoutingStrategy%2A> set to <xref:System.Windows.RoutingStrategy.Tunnel> in the registration call.</span></span> <span data-ttu-id="c8001-114">Per convenzione, gli eventi di tunneling in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] vengono denominati con il prefisso "Preview".</span><span class="sxs-lookup"><span data-stu-id="c8001-114">By convention, tunneling events in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] are prefixed with the word "Preview".</span></span>  
  
 <span data-ttu-id="c8001-115">Per un esempio di funzionamento degli eventi di bubbling, vedere [Gestire un evento indirizzato](how-to-handle-a-routed-event.md).</span><span class="sxs-lookup"><span data-stu-id="c8001-115">To see an example of how bubbling events work, see [Handle a Routed Event](how-to-handle-a-routed-event.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8001-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8001-116">See also</span></span>

- [<span data-ttu-id="c8001-117">Cenni preliminari sugli eventi indirizzati</span><span class="sxs-lookup"><span data-stu-id="c8001-117">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="c8001-118">Cenni preliminari sull'input</span><span class="sxs-lookup"><span data-stu-id="c8001-118">Input Overview</span></span>](input-overview.md)
- [<span data-ttu-id="c8001-119">Cenni preliminari sulla modifica di controlli</span><span class="sxs-lookup"><span data-stu-id="c8001-119">Control Authoring Overview</span></span>](../controls/control-authoring-overview.md)
