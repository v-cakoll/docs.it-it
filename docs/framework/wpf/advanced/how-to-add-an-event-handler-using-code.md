---
title: 'Procedura: aggiungere un gestore eventi mediante codice'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- event handlers [WPF], adding
- XAML [WPF], adding event handlers
ms.assetid: 269c61e0-6bd9-4291-9bed-1c5ee66da486
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4e7627589ff7e422c4ad3cd7a37fdc14c8a9c9f4
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-add-an-event-handler-using-code"></a><span data-ttu-id="49877-102">Procedura: aggiungere un gestore eventi mediante codice</span><span class="sxs-lookup"><span data-stu-id="49877-102">How to: Add an Event Handler Using Code</span></span>
<span data-ttu-id="49877-103">In questo esempio viene illustrato come aggiungere un gestore eventi a un elemento utilizzando il codice.</span><span class="sxs-lookup"><span data-stu-id="49877-103">This example shows how to add an event handler to an element by using code.</span></span>  
  
 <span data-ttu-id="49877-104">Se si desidera aggiungere un gestore eventi per un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elemento e la pagina di markup che contiene l'elemento è già stato caricato, è necessario aggiungere il gestore mediante codice.</span><span class="sxs-lookup"><span data-stu-id="49877-104">If you want to add an event handler to a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] element, and the markup page that contains the element has already been loaded, you must add the handler using code.</span></span> <span data-ttu-id="49877-105">In alternativa, se si sta compilando l'albero degli elementi di un'applicazione interamente mediante codice e non la dichiarazione di tutti gli elementi usando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], è possibile chiamare i metodi specifici per aggiungere gestori eventi per la struttura dell'elemento costruito.</span><span class="sxs-lookup"><span data-stu-id="49877-105">Alternatively, if you are building up the element tree for an application entirely using code and not declaring any elements using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can call specific methods to add event handlers to the constructed element tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49877-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="49877-106">Example</span></span>  
 <span data-ttu-id="49877-107">Nell'esempio seguente aggiunge un nuovo <xref:System.Windows.Controls.Button> a una pagina esistente definita inizialmente in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="49877-107">The following example adds a new <xref:System.Windows.Controls.Button> to an existing page that is initially defined in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="49877-108">Un file code-behind implementa un metodo del gestore eventi e quindi aggiunge tale metodo come un nuovo gestore eventi nel <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="49877-108">A code-behind file implements an event handler method and then adds that method as a new event handler on the <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="49877-109">Nell'esempio c# viene utilizzata la `+=` operatore per assegnare un gestore a un evento.</span><span class="sxs-lookup"><span data-stu-id="49877-109">The C# example uses the `+=` operator to assign a handler to an event.</span></span> <span data-ttu-id="49877-110">Questo è lo stesso operatore utilizzato per assegnare un gestore di [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] modello di gestione degli eventi.</span><span class="sxs-lookup"><span data-stu-id="49877-110">This is the same operator that is used to assign a handler in the [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] event handling model.</span></span> <span data-ttu-id="49877-111">Microsoft Visual Basic non supporta questo operatore come un modo per aggiungere gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="49877-111">Microsoft Visual Basic does not support this operator as a means of adding event handlers.</span></span> <span data-ttu-id="49877-112">Richiede invece una delle due tecniche seguenti:</span><span class="sxs-lookup"><span data-stu-id="49877-112">It instead requires one of two techniques:</span></span>  
  
-   <span data-ttu-id="49877-113">Utilizzare il <xref:System.Windows.UIElement.AddHandler%2A> metodo, insieme con un `AddressOf` operatore, fare riferimento all'implementazione del gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="49877-113">Use the <xref:System.Windows.UIElement.AddHandler%2A> method, together with an `AddressOf` operator, to reference the event handler implementation.</span></span>  
  
-   <span data-ttu-id="49877-114">Utilizzare il `Handles` (parola chiave) come parte della definizione del gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="49877-114">Use the `Handles` keyword as part of the event handler definition.</span></span> <span data-ttu-id="49877-115">Questa tecnica non viene visualizzata in questo contesto. vedere [Visual Basic e la gestione degli eventi di WPF](../../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md).</span><span class="sxs-lookup"><span data-stu-id="49877-115">This technique is not shown here; see [Visual Basic and WPF Event Handling](../../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md).</span></span>  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
>  <span data-ttu-id="49877-116">Aggiunta di un gestore eventi in inizialmente analizzata [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pagina è molto più semplice.</span><span class="sxs-lookup"><span data-stu-id="49877-116">Adding an event handler in the initially parsed [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page is much simpler.</span></span> <span data-ttu-id="49877-117">All'interno dell'elemento oggetto in cui si desidera aggiungere il gestore dell'evento, aggiungere un attributo che corrisponde al nome dell'evento che si desidera gestire.</span><span class="sxs-lookup"><span data-stu-id="49877-117">Within the object element where you want to add the event handler, add an attribute that matches the name of the event that you want to handle.</span></span> <span data-ttu-id="49877-118">Quindi specificare il valore dell'attributo come nome del metodo del gestore eventi definiti nel file di codice il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pagina.</span><span class="sxs-lookup"><span data-stu-id="49877-118">Then specify the value of that attribute as the name of the event handler method that you defined in the code-behind file of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page.</span></span> <span data-ttu-id="49877-119">Per ulteriori informazioni, vedere [Panoramica di XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) o [indirizzato Cenni preliminari sugli eventi](../../../../docs/framework/wpf/advanced/routed-events-overview.md).</span><span class="sxs-lookup"><span data-stu-id="49877-119">For more information, see [XAML Overview (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) or [Routed Events Overview](../../../../docs/framework/wpf/advanced/routed-events-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49877-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49877-120">See Also</span></span>  
 [<span data-ttu-id="49877-121">Cenni preliminari sugli eventi indirizzati</span><span class="sxs-lookup"><span data-stu-id="49877-121">Routed Events Overview</span></span>](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [<span data-ttu-id="49877-122">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="49877-122">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)
