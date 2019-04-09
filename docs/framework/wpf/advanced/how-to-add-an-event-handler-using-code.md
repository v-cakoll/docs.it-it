---
title: 'Procedura: Aggiungere un gestore eventi usando il codice'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- event handlers [WPF], adding
- XAML [WPF], adding event handlers
ms.assetid: 269c61e0-6bd9-4291-9bed-1c5ee66da486
ms.openlocfilehash: 10f8e0899e61d5d54589c910bdcbcd92d8ee947c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59129363"
---
# <a name="how-to-add-an-event-handler-using-code"></a><span data-ttu-id="79c27-102">Procedura: Aggiungere un gestore eventi usando il codice</span><span class="sxs-lookup"><span data-stu-id="79c27-102">How to: Add an Event Handler Using Code</span></span>
<span data-ttu-id="79c27-103">In questo esempio viene illustrato come aggiungere un gestore eventi a un elemento tramite il codice.</span><span class="sxs-lookup"><span data-stu-id="79c27-103">This example shows how to add an event handler to an element by using code.</span></span>  
  
 <span data-ttu-id="79c27-104">Se si desidera aggiungere un gestore eventi per un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elemento e la pagina di markup che contiene l'elemento è già stato caricato, è necessario aggiungere il gestore usando il codice.</span><span class="sxs-lookup"><span data-stu-id="79c27-104">If you want to add an event handler to a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] element, and the markup page that contains the element has already been loaded, you must add the handler using code.</span></span> <span data-ttu-id="79c27-105">In alternativa, se si sta compilando l'albero degli elementi per un'applicazione interamente tramite codice e non la dichiarazione di tutti gli elementi usando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], è possibile chiamare i metodi specifici per aggiungere i gestori eventi per la struttura dell'elemento costruito.</span><span class="sxs-lookup"><span data-stu-id="79c27-105">Alternatively, if you are building up the element tree for an application entirely using code and not declaring any elements using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can call specific methods to add event handlers to the constructed element tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79c27-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="79c27-106">Example</span></span>  
 <span data-ttu-id="79c27-107">L'esempio seguente aggiunge una nuova <xref:System.Windows.Controls.Button> a una pagina esistente che viene definita inizialmente in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="79c27-107">The following example adds a new <xref:System.Windows.Controls.Button> to an existing page that is initially defined in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="79c27-108">Un file code-behind implementa un metodo del gestore eventi e quindi aggiunge tale metodo come un nuovo gestore eventi nel <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="79c27-108">A code-behind file implements an event handler method and then adds that method as a new event handler on the <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="79c27-109">Il C# esempio Usa la `+=` operatore per assegnare un gestore a un evento.</span><span class="sxs-lookup"><span data-stu-id="79c27-109">The C# example uses the `+=` operator to assign a handler to an event.</span></span> <span data-ttu-id="79c27-110">Questo è lo stesso operatore che consente di assegnare un gestore nel [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] Gestione modelli di eventi.</span><span class="sxs-lookup"><span data-stu-id="79c27-110">This is the same operator that is used to assign a handler in the [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] event handling model.</span></span> <span data-ttu-id="79c27-111">Microsoft Visual Basic non supporta questo operatore come strumento di aggiunta di gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="79c27-111">Microsoft Visual Basic does not support this operator as a means of adding event handlers.</span></span> <span data-ttu-id="79c27-112">Richiede invece una delle due tecniche seguenti:</span><span class="sxs-lookup"><span data-stu-id="79c27-112">It instead requires one of two techniques:</span></span>  
  
-   <span data-ttu-id="79c27-113">Usare la <xref:System.Windows.UIElement.AddHandler%2A> metodo, insieme a un `AddressOf` operatore, fare riferimento l'implementazione del gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="79c27-113">Use the <xref:System.Windows.UIElement.AddHandler%2A> method, together with an `AddressOf` operator, to reference the event handler implementation.</span></span>  
  
-   <span data-ttu-id="79c27-114">Usare il `Handles` (parola chiave) come parte della definizione del gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="79c27-114">Use the `Handles` keyword as part of the event handler definition.</span></span> <span data-ttu-id="79c27-115">Questa tecnica non viene visualizzata in questa sede. visualizzare [Visual Basic e gestione degli eventi WPF](visual-basic-and-wpf-event-handling.md).</span><span class="sxs-lookup"><span data-stu-id="79c27-115">This technique is not shown here; see [Visual Basic and WPF Event Handling](visual-basic-and-wpf-event-handling.md).</span></span>  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
>  <span data-ttu-id="79c27-116">Aggiunta di un gestore eventi in inizialmente analizzata [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pagina è molto più semplice.</span><span class="sxs-lookup"><span data-stu-id="79c27-116">Adding an event handler in the initially parsed [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page is much simpler.</span></span> <span data-ttu-id="79c27-117">All'interno dell'elemento oggetto in cui si desidera aggiungere il gestore dell'evento, aggiungere un attributo che corrisponde al nome dell'evento che si desidera gestire.</span><span class="sxs-lookup"><span data-stu-id="79c27-117">Within the object element where you want to add the event handler, add an attribute that matches the name of the event that you want to handle.</span></span> <span data-ttu-id="79c27-118">Quindi specificare il valore dell'attributo come nome del metodo del gestore eventi che è definito nel file code-behind del [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pagina.</span><span class="sxs-lookup"><span data-stu-id="79c27-118">Then specify the value of that attribute as the name of the event handler method that you defined in the code-behind file of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page.</span></span> <span data-ttu-id="79c27-119">Per altre informazioni, vedere [Cenni preliminari su XAML (WPF)](xaml-overview-wpf.md) oppure [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md).</span><span class="sxs-lookup"><span data-stu-id="79c27-119">For more information, see [XAML Overview (WPF)](xaml-overview-wpf.md) or [Routed Events Overview](routed-events-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79c27-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79c27-120">See also</span></span>

- [<span data-ttu-id="79c27-121">Cenni preliminari sugli eventi indirizzati</span><span class="sxs-lookup"><span data-stu-id="79c27-121">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="79c27-122">Procedure relative</span><span class="sxs-lookup"><span data-stu-id="79c27-122">How-to Topics</span></span>](events-how-to-topics.md)
