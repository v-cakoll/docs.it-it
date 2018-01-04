---
title: 'Procedura: aggiungere la gestione di classi per un evento indirizzato'
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
- routed events [WPF], class handlers
- task_core_add_class_handling_routed_properties [WPF]
- class handlers [WPF], routed events
ms.assetid: 15b7b06c-9112-4ee5-b30a-65d10c5c5df6
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1f0315bbd1d1a5ab2ae08d8bc1810e240cb6a5a7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-class-handling-for-a-routed-event"></a><span data-ttu-id="5d15f-102">Procedura: aggiungere la gestione di classi per un evento indirizzato</span><span class="sxs-lookup"><span data-stu-id="5d15f-102">How to: Add Class Handling for a Routed Event</span></span>
<span data-ttu-id="5d15f-103">Gli eventi indirizzati possono essere gestiti tramite gestori di classi o gestori di istanza su qualsiasi nodo specificato nella route.</span><span class="sxs-lookup"><span data-stu-id="5d15f-103">Routed events can be handled either by class handlers or instance handlers on any given node in the route.</span></span> <span data-ttu-id="5d15f-104">Gestori di classi vengono richiamati prima e utilizzabile da implementazioni della classe per eliminare gli eventi dalla gestione di istanze o introdurre altri comportamenti specifici degli eventi per gli eventi che appartengono a classi di base.</span><span class="sxs-lookup"><span data-stu-id="5d15f-104">Class handlers are invoked first, and can be used by class implementations to suppress events from instance handling or introduce other event specific behaviors on events that are owned by base classes.</span></span> <span data-ttu-id="5d15f-105">In questo esempio vengono illustrate due tecniche strettamente correlate per l'implementazione di gestori di classi.</span><span class="sxs-lookup"><span data-stu-id="5d15f-105">This example illustrates two closely related techniques for implementing class handlers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d15f-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="5d15f-106">Example</span></span>  
 <span data-ttu-id="5d15f-107">Nell'esempio viene utilizzata una classe personalizzata in base il <xref:System.Windows.Controls.Canvas> pannello.</span><span class="sxs-lookup"><span data-stu-id="5d15f-107">This example uses a custom class based on the <xref:System.Windows.Controls.Canvas> panel.</span></span> <span data-ttu-id="5d15f-108">Il presupposto di base dell'applicazione è che la classe personalizzata introduce i comportamenti relativi elementi figlio, inclusi l'intercettazione di che qualsiasi pulsante sinistro del mouse e il contrassegno che li gestiti, prima che la classe di elementi figlio o eventuali gestori di istanza su di essa verranno richiamati.</span><span class="sxs-lookup"><span data-stu-id="5d15f-108">The basic premise of the application is that the custom class introduces behaviors on its child elements, including intercepting any left mouse button clicks and marking them handled, before the child element class or any instance handlers on it will be invoked.</span></span>  
  
 <span data-ttu-id="5d15f-109">Il <xref:System.Windows.UIElement> classe espone un metodo virtuale che consente la gestione nella classe di <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> eventi, sostituendo semplicemente l'evento.</span><span class="sxs-lookup"><span data-stu-id="5d15f-109">The <xref:System.Windows.UIElement> class exposes a virtual method that enables class handling on the <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> event, by simply overriding the event.</span></span> <span data-ttu-id="5d15f-110">Questo è il modo più semplice per implementare la gestione di classi, se tale metodo virtuale è disponibile nella gerarchia delle classi.</span><span class="sxs-lookup"><span data-stu-id="5d15f-110">This is the simplest way to implement class handling if such a virtual method is available somewhere in your class' hierarchy.</span></span> <span data-ttu-id="5d15f-111">Il codice seguente illustra il <xref:System.Windows.UIElement.OnPreviewMouseLeftButtonDown%2A> implementazione in "MyEditContainer" derivato da <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="5d15f-111">The following code shows the <xref:System.Windows.UIElement.OnPreviewMouseLeftButtonDown%2A> implementation in the "MyEditContainer" that is derived from <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="5d15f-112">L'implementazione contrassegna l'evento come gestito negli argomenti e quindi aggiunge codice per fornire l'elemento di origine di una modifica visibile di base.</span><span class="sxs-lookup"><span data-stu-id="5d15f-112">The implementation marks the event as handled in the arguments, and then adds some code to give the source element a basic visible change.</span></span>  
  
 [!code-csharp[ClassHandling#OnStarClassHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#onstarclasshandler)]
 [!code-vb[ClassHandling#OnStarClassHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#onstarclasshandler)]  
  
 <span data-ttu-id="5d15f-113">Se non virtuale è disponibile sulle classi di base o per il metodo specifico, la gestione di classi è possibile aggiungere direttamente tramite un metodo di utilità del <xref:System.Windows.EventManager> (classe), <xref:System.Windows.EventManager.RegisterClassHandler%2A>.</span><span class="sxs-lookup"><span data-stu-id="5d15f-113">If no virtual is available on base classes or for that particular method, class handling can be added directly using a utility method of the <xref:System.Windows.EventManager> class, <xref:System.Windows.EventManager.RegisterClassHandler%2A>.</span></span> <span data-ttu-id="5d15f-114">Questo metodo deve essere chiamato solo all'interno dell'inizializzazione statica delle classi che aggiungono la gestione di classi.</span><span class="sxs-lookup"><span data-stu-id="5d15f-114">This method should only be called within the static initialization of classes that are adding class handling.</span></span> <span data-ttu-id="5d15f-115">Questo esempio viene aggiunto un altro gestore per <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> , e in questo caso la classe registrata è la classe personalizzata.</span><span class="sxs-lookup"><span data-stu-id="5d15f-115">This example adds another handler for <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> , and in this case the registered class is the custom class.</span></span> <span data-ttu-id="5d15f-116">Al contrario, quando l'utilizzo di virtuali, la classe registrata è effettivamente il <xref:System.Windows.UIElement> classe di base.</span><span class="sxs-lookup"><span data-stu-id="5d15f-116">In contrast, when using the virtuals, the registered class is really the <xref:System.Windows.UIElement> base class.</span></span> <span data-ttu-id="5d15f-117">In casi in cui le classi base e sottoclasse registrare la gestione di classi, i gestori della sottoclasse vengono richiamati prima.</span><span class="sxs-lookup"><span data-stu-id="5d15f-117">In cases where base classes and subclass each register class handling, the subclass handlers are invoked first.</span></span> <span data-ttu-id="5d15f-118">Si sarebbe il comportamento in un'applicazione che prima di tutto questo gestore permetterebbe di visualizzare la finestra di messaggio e quindi verranno visualizzata la modifica visiva nel gestore del metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="5d15f-118">The behavior in an application would be that first this handler would show its message box and then the visual change in the virtual method's handler would be shown.</span></span>  
  
 [!code-csharp[ClassHandling#StaticAndRegisterClassHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#staticandregisterclasshandler)]
 [!code-vb[ClassHandling#StaticAndRegisterClassHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#staticandregisterclasshandler)]  
  
## <a name="see-also"></a><span data-ttu-id="5d15f-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d15f-119">See Also</span></span>  
 <xref:System.Windows.EventManager>  
 [<span data-ttu-id="5d15f-120">Contrassegno degli eventi indirizzati come gestiti e gestione delle classi</span><span class="sxs-lookup"><span data-stu-id="5d15f-120">Marking Routed Events as Handled, and Class Handling</span></span>](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md)  
 [<span data-ttu-id="5d15f-121">Gestire un evento indirizzato</span><span class="sxs-lookup"><span data-stu-id="5d15f-121">Handle a Routed Event</span></span>](../../../../docs/framework/wpf/advanced/how-to-handle-a-routed-event.md)  
 [<span data-ttu-id="5d15f-122">Cenni preliminari sugli eventi indirizzati</span><span class="sxs-lookup"><span data-stu-id="5d15f-122">Routed Events Overview</span></span>](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
