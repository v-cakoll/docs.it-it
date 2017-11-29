---
title: 'Procedura: Gestire un evento indirizzato'
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
- routed events [WPF], handling
- bubbling events [WPF]
ms.assetid: 157787b4-f469-4047-8777-5b034145f32e
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 83f59f2df9311f30995b18529a733a5569c85ee0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-handle-a-routed-event"></a><span data-ttu-id="96a22-102">Procedura: Gestire un evento indirizzato</span><span class="sxs-lookup"><span data-stu-id="96a22-102">How to: Handle a Routed Event</span></span>
<span data-ttu-id="96a22-103">Questo esempio illustra il funzionamento degli eventi di bubbling e spiega come scrivere un gestore in grado di elaborare i dati dell'evento indirizzato.</span><span class="sxs-lookup"><span data-stu-id="96a22-103">This example shows how bubbling events work and how to write a handler that can process the routed event data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96a22-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="96a22-104">Example</span></span>  
 <span data-ttu-id="96a22-105">In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] gli elementi sono disposti in una struttura ad albero degli elementi.</span><span class="sxs-lookup"><span data-stu-id="96a22-105">In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], elements are arranged in an element tree structure.</span></span> <span data-ttu-id="96a22-106">L'elemento padre può partecipare alla gestione di eventi inizialmente generati dagli elementi figlio nell'albero degli elementi.</span><span class="sxs-lookup"><span data-stu-id="96a22-106">The parent element can participate in the handling of events that are initially raised by child elements in the element tree.</span></span> <span data-ttu-id="96a22-107">Questo è possibile grazie al routing di eventi.</span><span class="sxs-lookup"><span data-stu-id="96a22-107">This is possible because of event routing.</span></span>  
  
 <span data-ttu-id="96a22-108">Per gli eventi indirizzati si usa in genere una delle due strategie di routing seguenti: bubbling o tunneling.</span><span class="sxs-lookup"><span data-stu-id="96a22-108">Routed events typically follow one of two routing strategies, bubbling or tunneling.</span></span> <span data-ttu-id="96a22-109">In questo esempio si concentra sull'evento bubbling e utilizza il <xref:System.Windows.Controls.Primitives.ButtonBase.Click?displayProperty=nameWithType> Mostra il funzionamento del routing dell'evento.</span><span class="sxs-lookup"><span data-stu-id="96a22-109">This example focuses on the bubbling event and uses the <xref:System.Windows.Controls.Primitives.ButtonBase.Click?displayProperty=nameWithType> event to show how routing works.</span></span>  
  
 <span data-ttu-id="96a22-110">L'esempio seguente crea due <xref:System.Windows.Controls.Button> controlla e utilizza [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] la sintassi per collegare un gestore eventi a un elemento padre comune, ovvero in questo esempio di attributo <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="96a22-110">The following example creates two <xref:System.Windows.Controls.Button> controls and uses [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attribute syntax to attach an event handler to a common parent element, which in this example is <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="96a22-111">Anziché associare singoli gestori per ogni <xref:System.Windows.Controls.Button> elemento figlio, viene utilizzata la sintassi degli attributi per collegare il gestore eventi per il <xref:System.Windows.Controls.StackPanel> elemento padre.</span><span class="sxs-lookup"><span data-stu-id="96a22-111">Instead of attaching individual event handlers for each <xref:System.Windows.Controls.Button> child element, the example uses attribute syntax to attach the event handler to the <xref:System.Windows.Controls.StackPanel> parent element.</span></span> <span data-ttu-id="96a22-112">Questo criterio di gestione degli eventi illustra in che modo usare il routing di eventi come tecnica per ridurre il numero di elementi a cui è associato un gestore.</span><span class="sxs-lookup"><span data-stu-id="96a22-112">This event-handling pattern shows how to use event routing as a technique for reducing the number of elements where a handler is attached.</span></span> <span data-ttu-id="96a22-113">Tutti gli eventi bubbling per ogni <xref:System.Windows.Controls.Button> route tramite l'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="96a22-113">All the bubbling events for each <xref:System.Windows.Controls.Button> route through the parent element.</span></span>  
  
 <span data-ttu-id="96a22-114">Si noti che nell'elemento padre <xref:System.Windows.Controls.StackPanel> elemento, il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> nome dell'evento specificato, come l'attributo è parzialmente qualificato assegnando il <xref:System.Windows.Controls.Button> classe.</span><span class="sxs-lookup"><span data-stu-id="96a22-114">Note that on the parent <xref:System.Windows.Controls.StackPanel> element, the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event name specified as the attribute is partially qualified by naming the <xref:System.Windows.Controls.Button> class.</span></span> <span data-ttu-id="96a22-115">Il <xref:System.Windows.Controls.Button> classe è un <xref:System.Windows.Controls.Primitives.ButtonBase> classe derivata che ha il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento nel proprio elenco dei membri.</span><span class="sxs-lookup"><span data-stu-id="96a22-115">The <xref:System.Windows.Controls.Button> class is a <xref:System.Windows.Controls.Primitives.ButtonBase> derived class that has the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event in its members listing.</span></span> <span data-ttu-id="96a22-116">La tecnica della qualifica parziale per l'associazione di un gestore eventi è necessaria se l'evento che viene gestito non esiste nell'elenco dei membri dell'elemento a cui è associato il gestore dell'evento indirizzato.</span><span class="sxs-lookup"><span data-stu-id="96a22-116">This partial qualification technique for attaching an event handler is necessary if the event that is being handled does not exist in the members listing of the element where the routed event handler is attached.</span></span>  
  
 [!code-xaml[RoutedEventHandle#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventHandle/CSharp/default.xaml#xaml)]  
  
 <span data-ttu-id="96a22-117">L'esempio seguente viene gestito il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento.</span><span class="sxs-lookup"><span data-stu-id="96a22-117">The following example handles the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event.</span></span>  <span data-ttu-id="96a22-118">L'esempio stabilisce quale elemento gestisce l'evento e quale elemento genera l'evento.</span><span class="sxs-lookup"><span data-stu-id="96a22-118">The example reports which element handles the event and which element raises the event.</span></span> <span data-ttu-id="96a22-119">Il gestore eventi viene eseguito quando l'utente fa clic su uno dei pulsanti.</span><span class="sxs-lookup"><span data-stu-id="96a22-119">The event handler is executed when the user clicks either button.</span></span>  
  
 [!code-csharp[RoutedEventHandle#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventHandle/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventHandle#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventHandle/VisualBasic/MainWindow.xaml.vb#handler)]  
  
## <a name="see-also"></a><span data-ttu-id="96a22-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96a22-120">See Also</span></span>  
 <xref:System.Windows.RoutedEvent>  
 [<span data-ttu-id="96a22-121">Cenni preliminari sull'input</span><span class="sxs-lookup"><span data-stu-id="96a22-121">Input Overview</span></span>](../../../../docs/framework/wpf/advanced/input-overview.md)  
 [<span data-ttu-id="96a22-122">Cenni preliminari sugli eventi indirizzati</span><span class="sxs-lookup"><span data-stu-id="96a22-122">Routed Events Overview</span></span>](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [<span data-ttu-id="96a22-123">Procedure relative</span><span class="sxs-lookup"><span data-stu-id="96a22-123">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)  
 [<span data-ttu-id="96a22-124">Descrizione dettagliata della sintassi XAML</span><span class="sxs-lookup"><span data-stu-id="96a22-124">XAML Syntax In Detail</span></span>](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)
