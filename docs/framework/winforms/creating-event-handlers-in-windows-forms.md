---
title: Creazione di gestori eventi in Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- event handling [Windows Forms]
- Windows Forms controls, event handling
- Windows Forms, event handling
- events [Windows Forms], event handlers
- event handlers [Windows Forms]
ms.assetid: 6514e530-c6b8-489c-a8d2-eda7b7072701
ms.openlocfilehash: 9095946d52360c69fd6c4dd6285039fb3e1874d5
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47197112"
---
# <a name="creating-event-handlers-in-windows-forms"></a><span data-ttu-id="58122-102">Creazione di gestori eventi in Windows Form</span><span class="sxs-lookup"><span data-stu-id="58122-102">Creating Event Handlers in Windows Forms</span></span>
<span data-ttu-id="58122-103">Un gestore eventi è una procedura nel codice che determina le azioni da eseguire quando si verifica un evento, ad esempio quando l'utente fa clic su un pulsante o una coda di messaggi riceve un messaggio.</span><span class="sxs-lookup"><span data-stu-id="58122-103">An event handler is a procedure in your code that determines what actions are performed when an event occurs, such as when the user clicks a button or a message queue receives a message.</span></span> <span data-ttu-id="58122-104">Al momento della generazione di un evento, vengono eseguiti i gestori eventi che ricevono l'evento.</span><span class="sxs-lookup"><span data-stu-id="58122-104">When an event is raised, the event handler or handlers that receive the event are executed.</span></span> <span data-ttu-id="58122-105">Gli eventi possono essere assegnati a più gestori e i metodi che gestiscono determinati eventi possono essere modificati in modo dinamico.</span><span class="sxs-lookup"><span data-stu-id="58122-105">Events can be assigned to multiple handlers, and the methods that handle particular events can be changed dynamically.</span></span> <span data-ttu-id="58122-106">Per creare i gestori eventi è possibile anche usare Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="58122-106">You can also use the Windows Forms Designer to create event handlers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="58122-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="58122-107">In This Section</span></span>  
 [<span data-ttu-id="58122-108">Informazioni generali sugli eventi</span><span class="sxs-lookup"><span data-stu-id="58122-108">Events Overview</span></span>](../../../docs/framework/winforms/events-overview-windows-forms.md)  
 <span data-ttu-id="58122-109">Illustra il modello di eventi e il ruolo dei delegati.</span><span class="sxs-lookup"><span data-stu-id="58122-109">Explains the event model and the role of delegates.</span></span>  
  
 [<span data-ttu-id="58122-110">Informazioni generali sui gestori eventi</span><span class="sxs-lookup"><span data-stu-id="58122-110">Event Handlers Overview</span></span>](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)  
 <span data-ttu-id="58122-111">Descrive come gestire gli eventi.</span><span class="sxs-lookup"><span data-stu-id="58122-111">Describes how to handle events.</span></span>  
  
 [<span data-ttu-id="58122-112">Procedura: creare gestori eventi in fase di esecuzione per Windows Form</span><span class="sxs-lookup"><span data-stu-id="58122-112">How to: Create Event Handlers at Run Time for Windows Forms</span></span>](../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md)  
 <span data-ttu-id="58122-113">Fornisce le istruzioni per rispondere dinamicamente agli eventi generati dall'utente o dal sistema.</span><span class="sxs-lookup"><span data-stu-id="58122-113">Gives directions for responding to system or user events dynamically.</span></span>  
  
 [<span data-ttu-id="58122-114">Procedura: connettere più eventi a un unico gestore eventi in Windows Form</span><span class="sxs-lookup"><span data-stu-id="58122-114">How to: Connect Multiple Events to a Single Event Handler in Windows Forms</span></span>](../../../docs/framework/winforms/how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)  
 <span data-ttu-id="58122-115">Fornisce le istruzioni per assegnare la stessa funzionalità a più controlli tramite gli eventi.</span><span class="sxs-lookup"><span data-stu-id="58122-115">Gives directions for assigning the same functionality to multiple controls through events.</span></span>  
  
 [<span data-ttu-id="58122-116">Ordine degli eventi in Windows Form</span><span class="sxs-lookup"><span data-stu-id="58122-116">Order of Events in Windows Forms</span></span>](../../../docs/framework/winforms/order-of-events-in-windows-forms.md)  
 <span data-ttu-id="58122-117">Descrive l'ordine in cui gli eventi vengono generati nei controlli Windows Form.</span><span class="sxs-lookup"><span data-stu-id="58122-117">Describes the order in which events are raised in Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="58122-118">Procedura: creare le impostazioni delle applicazioni usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="58122-118">How to: Create Event Handlers Using the Designer</span></span>](https://msdn.microsoft.com/library/8461e9b8-14e8-406f-936e-3726732b23d2)  
 <span data-ttu-id="58122-119">Descrive come usare Progettazione Windows Form per creare i gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="58122-119">Describes how to use the Windows Forms Designer to create event handlers.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="58122-120">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="58122-120">Related Sections</span></span>  
 [<span data-ttu-id="58122-121">Eventi</span><span class="sxs-lookup"><span data-stu-id="58122-121">Events</span></span>](../../../docs/standard/events/index.md)  
 <span data-ttu-id="58122-122">Fornisce i collegamenti ad argomenti relativi alla gestione e alla generazione di eventi con [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="58122-122">Provides links to topics on handling and raising events using the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span>  
  
 [<span data-ttu-id="58122-123">Risoluzione dei problemi relativi ai gestori eventi ereditati in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="58122-123">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)  
 <span data-ttu-id="58122-124">Elenca i problemi comuni che si verificano con i gestori eventi nei componenti ereditati.</span><span class="sxs-lookup"><span data-stu-id="58122-124">Lists common issues that occur with event handlers in inherited components.</span></span>
