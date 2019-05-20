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
ms.openlocfilehash: e90e1d6643a30c1d2f4438e77317a2348b07fd71
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2019
ms.locfileid: "65882420"
---
# <a name="creating-event-handlers-in-windows-forms"></a><span data-ttu-id="66f59-102">Creazione di gestori eventi in Windows Form</span><span class="sxs-lookup"><span data-stu-id="66f59-102">Creating Event Handlers in Windows Forms</span></span>

<span data-ttu-id="66f59-103">Un gestore eventi è una procedura nel codice che determina le azioni da eseguire quando si verifica un evento, ad esempio quando l'utente fa clic su un pulsante o una coda di messaggi riceve un messaggio.</span><span class="sxs-lookup"><span data-stu-id="66f59-103">An event handler is a procedure in your code that determines what actions are performed when an event occurs, such as when the user clicks a button or a message queue receives a message.</span></span> <span data-ttu-id="66f59-104">Al momento della generazione di un evento, vengono eseguiti i gestori eventi che ricevono l'evento.</span><span class="sxs-lookup"><span data-stu-id="66f59-104">When an event is raised, the event handler or handlers that receive the event are executed.</span></span> <span data-ttu-id="66f59-105">Gli eventi possono essere assegnati a più gestori e i metodi che gestiscono determinati eventi possono essere modificati in modo dinamico.</span><span class="sxs-lookup"><span data-stu-id="66f59-105">Events can be assigned to multiple handlers, and the methods that handle particular events can be changed dynamically.</span></span> <span data-ttu-id="66f59-106">È anche possibile usare la finestra di progettazione Windows Form in Visual Studio per creare gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="66f59-106">You can also use the Windows Forms Designer in Visual Studio to create event handlers.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="66f59-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="66f59-107">In This Section</span></span>

 <span data-ttu-id="66f59-108">[Cenni preliminari sugli eventi](events-overview-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="66f59-108">[Events Overview](events-overview-windows-forms.md)\\</span></span>
 <span data-ttu-id="66f59-109">Illustra il modello di eventi e il ruolo dei delegati.</span><span class="sxs-lookup"><span data-stu-id="66f59-109">Explains the event model and the role of delegates.</span></span>

 <span data-ttu-id="66f59-110">[Panoramica sui gestori eventi](event-handlers-overview-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="66f59-110">[Event Handlers Overview](event-handlers-overview-windows-forms.md)\\</span></span>
 <span data-ttu-id="66f59-111">Descrive come gestire gli eventi.</span><span class="sxs-lookup"><span data-stu-id="66f59-111">Describes how to handle events.</span></span>

 <span data-ttu-id="66f59-112">[Procedura: Creare i gestori eventi in fase di esecuzione per Windows Form](how-to-create-event-handlers-at-run-time-for-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="66f59-112">[How to: Create Event Handlers at Run Time for Windows Forms](how-to-create-event-handlers-at-run-time-for-windows-forms.md)\\</span></span>
 <span data-ttu-id="66f59-113">Fornisce le istruzioni per rispondere dinamicamente agli eventi generati dall'utente o dal sistema.</span><span class="sxs-lookup"><span data-stu-id="66f59-113">Gives directions for responding to system or user events dynamically.</span></span>

 <span data-ttu-id="66f59-114">[Procedura: Connettere più eventi a un unico gestore eventi in Windows Form](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="66f59-114">[How to: Connect Multiple Events to a Single Event Handler in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)\\</span></span>
 <span data-ttu-id="66f59-115">Fornisce le istruzioni per assegnare la stessa funzionalità a più controlli tramite gli eventi.</span><span class="sxs-lookup"><span data-stu-id="66f59-115">Gives directions for assigning the same functionality to multiple controls through events.</span></span>

 <span data-ttu-id="66f59-116">[Ordine degli eventi in Windows Form](order-of-events-in-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="66f59-116">[Order of Events in Windows Forms](order-of-events-in-windows-forms.md)\\</span></span>
 <span data-ttu-id="66f59-117">Descrive l'ordine in cui gli eventi vengono generati nei controlli Windows Form.</span><span class="sxs-lookup"><span data-stu-id="66f59-117">Describes the order in which events are raised in Windows Forms controls.</span></span>

 <span data-ttu-id="66f59-118">[Procedura: Creare i gestori di eventi utilizzando la finestra di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)) viene descritto come utilizzare la finestra di progettazione Windows Form per creare gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="66f59-118">[How to: Create Event Handlers Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)) Describes how to use the Windows Forms Designer to create event handlers.</span></span>

## <a name="related-sections"></a><span data-ttu-id="66f59-119">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="66f59-119">Related Sections</span></span>

 <span data-ttu-id="66f59-120">[Eventi](../../standard/events/index.md)\\</span><span class="sxs-lookup"><span data-stu-id="66f59-120">[Events](../../standard/events/index.md)\\</span></span>
 <span data-ttu-id="66f59-121">Vengono forniti collegamenti ad argomenti relativi alla gestione e generazione di eventi usando .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="66f59-121">Provides links to topics on handling and raising events using the .NET Framework.</span></span>

 <span data-ttu-id="66f59-122">[Risoluzione dei problemi relativi ai gestori eventi ereditati in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)\\</span><span class="sxs-lookup"><span data-stu-id="66f59-122">[Troubleshooting Inherited Event Handlers in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)\\</span></span>
 <span data-ttu-id="66f59-123">Elenca i problemi comuni che si verificano con i gestori eventi nei componenti ereditati.</span><span class="sxs-lookup"><span data-stu-id="66f59-123">Lists common issues that occur with event handlers in inherited components.</span></span>
