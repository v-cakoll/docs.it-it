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
ms.openlocfilehash: 017b32dc07f62cc4553a84f7b91687fb34a53c65
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937464"
---
# <a name="how-to-add-an-event-handler-using-code"></a><span data-ttu-id="8d4bb-102">Procedura: Aggiungere un gestore eventi usando il codice</span><span class="sxs-lookup"><span data-stu-id="8d4bb-102">How to: Add an Event Handler Using Code</span></span>
<span data-ttu-id="8d4bb-103">Questo esempio illustra come aggiungere un gestore eventi a un elemento usando il codice.</span><span class="sxs-lookup"><span data-stu-id="8d4bb-103">This example shows how to add an event handler to an element by using code.</span></span>  
  
 <span data-ttu-id="8d4bb-104">Se si desidera aggiungere un gestore eventi a un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elemento e la pagina di markup che contiene l'elemento è già stata caricata, è necessario aggiungere il gestore utilizzando il codice.</span><span class="sxs-lookup"><span data-stu-id="8d4bb-104">If you want to add an event handler to a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] element, and the markup page that contains the element has already been loaded, you must add the handler using code.</span></span> <span data-ttu-id="8d4bb-105">In alternativa, se si sta compilando la struttura ad albero dell'elemento per un'applicazione usando interamente il codice e non [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]dichiarando alcun elemento usando, è possibile chiamare metodi specifici per aggiungere i gestori eventi all'albero degli elementi costruito.</span><span class="sxs-lookup"><span data-stu-id="8d4bb-105">Alternatively, if you are building up the element tree for an application entirely using code and not declaring any elements using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can call specific methods to add event handlers to the constructed element tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d4bb-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="8d4bb-106">Example</span></span>  
 <span data-ttu-id="8d4bb-107">Nell'esempio seguente viene aggiunto un <xref:System.Windows.Controls.Button> nuovo oggetto a una pagina esistente definita inizialmente in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d4bb-107">The following example adds a new <xref:System.Windows.Controls.Button> to an existing page that is initially defined in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="8d4bb-108">Un file code-behind implementa un metodo del gestore eventi e quindi aggiunge tale metodo come nuovo gestore eventi su <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="8d4bb-108">A code-behind file implements an event handler method and then adds that method as a new event handler on the <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="8d4bb-109">Nell' C# esempio viene utilizzato `+=` l'operatore per assegnare un gestore a un evento.</span><span class="sxs-lookup"><span data-stu-id="8d4bb-109">The C# example uses the `+=` operator to assign a handler to an event.</span></span> <span data-ttu-id="8d4bb-110">Si tratta dello stesso operatore utilizzato per assegnare un gestore nel modello di gestione degli eventi Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="8d4bb-110">This is the same operator that is used to assign a handler in the common language runtime (CLR) event handling model.</span></span> <span data-ttu-id="8d4bb-111">Microsoft Visual Basic non supporta questo operatore come mezzo per l'aggiunta di gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="8d4bb-111">Microsoft Visual Basic does not support this operator as a means of adding event handlers.</span></span> <span data-ttu-id="8d4bb-112">Richiede invece una delle due tecniche seguenti:</span><span class="sxs-lookup"><span data-stu-id="8d4bb-112">It instead requires one of two techniques:</span></span>  
  
- <span data-ttu-id="8d4bb-113">Usare il <xref:System.Windows.UIElement.AddHandler%2A> metodo, insieme a un `AddressOf` operatore, per fare riferimento all'implementazione del gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="8d4bb-113">Use the <xref:System.Windows.UIElement.AddHandler%2A> method, together with an `AddressOf` operator, to reference the event handler implementation.</span></span>  
  
- <span data-ttu-id="8d4bb-114">Utilizzare la `Handles` parola chiave come parte della definizione del gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="8d4bb-114">Use the `Handles` keyword as part of the event handler definition.</span></span> <span data-ttu-id="8d4bb-115">Questa tecnica non è illustrata di seguito. vedere [Visual Basic e gestione degli eventi WPF](visual-basic-and-wpf-event-handling.md).</span><span class="sxs-lookup"><span data-stu-id="8d4bb-115">This technique is not shown here; see [Visual Basic and WPF Event Handling](visual-basic-and-wpf-event-handling.md).</span></span>  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
> <span data-ttu-id="8d4bb-116">L'aggiunta di un gestore eventi nella [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pagina analizzata inizialmente è molto più semplice.</span><span class="sxs-lookup"><span data-stu-id="8d4bb-116">Adding an event handler in the initially parsed [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page is much simpler.</span></span> <span data-ttu-id="8d4bb-117">All'interno dell'elemento oggetto in cui si desidera aggiungere il gestore eventi, aggiungere un attributo che corrisponda al nome dell'evento che si desidera gestire.</span><span class="sxs-lookup"><span data-stu-id="8d4bb-117">Within the object element where you want to add the event handler, add an attribute that matches the name of the event that you want to handle.</span></span> <span data-ttu-id="8d4bb-118">Specificare quindi il valore di tale attributo come nome del metodo del gestore eventi definito nel file code-behind della [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pagina.</span><span class="sxs-lookup"><span data-stu-id="8d4bb-118">Then specify the value of that attribute as the name of the event handler method that you defined in the code-behind file of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page.</span></span> <span data-ttu-id="8d4bb-119">Per altre informazioni, vedere Cenni preliminari su [XAML (WPF)](xaml-overview-wpf.md) o [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8d4bb-119">For more information, see [XAML Overview (WPF)](xaml-overview-wpf.md) or [Routed Events Overview](routed-events-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d4bb-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d4bb-120">See also</span></span>

- [<span data-ttu-id="8d4bb-121">Cenni preliminari sugli eventi indirizzati</span><span class="sxs-lookup"><span data-stu-id="8d4bb-121">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="8d4bb-122">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="8d4bb-122">How-to Topics</span></span>](events-how-to-topics.md)
