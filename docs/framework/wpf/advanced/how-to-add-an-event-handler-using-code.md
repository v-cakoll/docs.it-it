---
title: 'Procedura: aggiungere un gestore eventi mediante codice'
description: Usare questo esempio per apprendere come aggiungere un gestore eventi a un elemento in Windows Presentation Foundation usando il codice, anziché dichiararlo usando XAML.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- event handlers [WPF], adding
- XAML [WPF], adding event handlers
ms.assetid: 269c61e0-6bd9-4291-9bed-1c5ee66da486
ms.openlocfilehash: b36969f7a65ccbf6c9d03b22767d9eacdc177ad1
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166363"
---
# <a name="how-to-add-an-event-handler-using-code"></a><span data-ttu-id="4c475-103">Procedura: aggiungere un gestore eventi mediante codice</span><span class="sxs-lookup"><span data-stu-id="4c475-103">How to: Add an Event Handler Using Code</span></span>
<span data-ttu-id="4c475-104">Questo esempio illustra come aggiungere un gestore eventi a un elemento usando il codice.</span><span class="sxs-lookup"><span data-stu-id="4c475-104">This example shows how to add an event handler to an element by using code.</span></span>  
  
 <span data-ttu-id="4c475-105">Se si desidera aggiungere un gestore eventi a un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elemento e la pagina di markup che contiene l'elemento è già stata caricata, è necessario aggiungere il gestore utilizzando il codice.</span><span class="sxs-lookup"><span data-stu-id="4c475-105">If you want to add an event handler to a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] element, and the markup page that contains the element has already been loaded, you must add the handler using code.</span></span> <span data-ttu-id="4c475-106">In alternativa, se si sta compilando la struttura ad albero dell'elemento per un'applicazione usando interamente il codice e non dichiarando alcun elemento usando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , è possibile chiamare metodi specifici per aggiungere i gestori eventi all'albero degli elementi costruito.</span><span class="sxs-lookup"><span data-stu-id="4c475-106">Alternatively, if you are building up the element tree for an application entirely using code and not declaring any elements using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can call specific methods to add event handlers to the constructed element tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c475-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="4c475-107">Example</span></span>  
 <span data-ttu-id="4c475-108">Nell'esempio seguente viene aggiunto un nuovo oggetto <xref:System.Windows.Controls.Button> a una pagina esistente definita inizialmente in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4c475-108">The following example adds a new <xref:System.Windows.Controls.Button> to an existing page that is initially defined in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="4c475-109">Un file code-behind implementa un metodo del gestore eventi e quindi aggiunge tale metodo come nuovo gestore eventi su <xref:System.Windows.Controls.Button> .</span><span class="sxs-lookup"><span data-stu-id="4c475-109">A code-behind file implements an event handler method and then adds that method as a new event handler on the <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="4c475-110">Nell'esempio C# viene usato l' `+=` operatore per assegnare un gestore a un evento.</span><span class="sxs-lookup"><span data-stu-id="4c475-110">The C# example uses the `+=` operator to assign a handler to an event.</span></span> <span data-ttu-id="4c475-111">Si tratta dello stesso operatore utilizzato per assegnare un gestore nel modello di gestione degli eventi Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="4c475-111">This is the same operator that is used to assign a handler in the common language runtime (CLR) event handling model.</span></span> <span data-ttu-id="4c475-112">Microsoft Visual Basic non supporta questo operatore come mezzo per l'aggiunta di gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="4c475-112">Microsoft Visual Basic does not support this operator as a means of adding event handlers.</span></span> <span data-ttu-id="4c475-113">Richiede invece una delle due tecniche seguenti:</span><span class="sxs-lookup"><span data-stu-id="4c475-113">It instead requires one of two techniques:</span></span>  
  
- <span data-ttu-id="4c475-114">Usare il <xref:System.Windows.UIElement.AddHandler%2A> metodo, insieme a un `AddressOf` operatore, per fare riferimento all'implementazione del gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="4c475-114">Use the <xref:System.Windows.UIElement.AddHandler%2A> method, together with an `AddressOf` operator, to reference the event handler implementation.</span></span>  
  
- <span data-ttu-id="4c475-115">Utilizzare la `Handles` parola chiave come parte della definizione del gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="4c475-115">Use the `Handles` keyword as part of the event handler definition.</span></span> <span data-ttu-id="4c475-116">Questa tecnica non è illustrata di seguito. vedere [Visual Basic e gestione degli eventi WPF](visual-basic-and-wpf-event-handling.md).</span><span class="sxs-lookup"><span data-stu-id="4c475-116">This technique is not shown here; see [Visual Basic and WPF Event Handling](visual-basic-and-wpf-event-handling.md).</span></span>  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
> <span data-ttu-id="4c475-117">L'aggiunta di un gestore eventi nella pagina analizzata inizialmente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] è molto più semplice.</span><span class="sxs-lookup"><span data-stu-id="4c475-117">Adding an event handler in the initially parsed [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page is much simpler.</span></span> <span data-ttu-id="4c475-118">All'interno dell'elemento oggetto in cui si desidera aggiungere il gestore eventi, aggiungere un attributo che corrisponda al nome dell'evento che si desidera gestire.</span><span class="sxs-lookup"><span data-stu-id="4c475-118">Within the object element where you want to add the event handler, add an attribute that matches the name of the event that you want to handle.</span></span> <span data-ttu-id="4c475-119">Specificare quindi il valore di tale attributo come nome del metodo del gestore eventi definito nel file code-behind della [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pagina.</span><span class="sxs-lookup"><span data-stu-id="4c475-119">Then specify the value of that attribute as the name of the event handler method that you defined in the code-behind file of the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page.</span></span> <span data-ttu-id="4c475-120">Per altre informazioni, vedere Cenni [preliminari su XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md) o [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4c475-120">For more information, see [XAML Overview (WPF)](../../../desktop-wpf/fundamentals/xaml.md) or [Routed Events Overview](routed-events-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c475-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c475-121">See also</span></span>

- [<span data-ttu-id="4c475-122">Cenni preliminari sugli eventi indirizzati</span><span class="sxs-lookup"><span data-stu-id="4c475-122">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="4c475-123">Procedure relative</span><span class="sxs-lookup"><span data-stu-id="4c475-123">How-to Topics</span></span>](events-how-to-topics.md)
