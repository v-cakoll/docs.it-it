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
ms.openlocfilehash: 6b1d146dfd9d51641bc9eb5d8be4cd2508c223a1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963485"
---
# <a name="creating-event-handlers-in-windows-forms"></a><span data-ttu-id="af762-102">Creazione di gestori eventi in Windows Form</span><span class="sxs-lookup"><span data-stu-id="af762-102">Creating Event Handlers in Windows Forms</span></span>

<span data-ttu-id="af762-103">Un gestore eventi è una procedura nel codice che determina le azioni da eseguire quando si verifica un evento, ad esempio quando l'utente fa clic su un pulsante o una coda di messaggi riceve un messaggio.</span><span class="sxs-lookup"><span data-stu-id="af762-103">An event handler is a procedure in your code that determines what actions are performed when an event occurs, such as when the user clicks a button or a message queue receives a message.</span></span> <span data-ttu-id="af762-104">Al momento della generazione di un evento, vengono eseguiti i gestori eventi che ricevono l'evento.</span><span class="sxs-lookup"><span data-stu-id="af762-104">When an event is raised, the event handler or handlers that receive the event are executed.</span></span> <span data-ttu-id="af762-105">Gli eventi possono essere assegnati a più gestori e i metodi che gestiscono determinati eventi possono essere modificati in modo dinamico.</span><span class="sxs-lookup"><span data-stu-id="af762-105">Events can be assigned to multiple handlers, and the methods that handle particular events can be changed dynamically.</span></span> <span data-ttu-id="af762-106">È anche possibile usare la Progettazione Windows Form in Visual Studio per creare i gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="af762-106">You can also use the Windows Forms Designer in Visual Studio to create event handlers.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="af762-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="af762-107">In This Section</span></span>

 <span data-ttu-id="af762-108">[Cenni preliminari sugli eventi](events-overview-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="af762-108">[Events Overview](events-overview-windows-forms.md)</span></span>\
 <span data-ttu-id="af762-109">Illustra il modello di eventi e il ruolo dei delegati.</span><span class="sxs-lookup"><span data-stu-id="af762-109">Explains the event model and the role of delegates.</span></span>

 <span data-ttu-id="af762-110">[Panoramica sui gestori eventi](event-handlers-overview-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="af762-110">[Event Handlers Overview](event-handlers-overview-windows-forms.md)</span></span>\
 <span data-ttu-id="af762-111">Descrive come gestire gli eventi.</span><span class="sxs-lookup"><span data-stu-id="af762-111">Describes how to handle events.</span></span>

 <span data-ttu-id="af762-112">[Procedura: Creazione di gestori eventi in fase di esecuzione per Windows Forms](how-to-create-event-handlers-at-run-time-for-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="af762-112">[How to: Create Event Handlers at Run Time for Windows Forms](how-to-create-event-handlers-at-run-time-for-windows-forms.md)</span></span>\
 <span data-ttu-id="af762-113">Fornisce le istruzioni per rispondere dinamicamente agli eventi generati dall'utente o dal sistema.</span><span class="sxs-lookup"><span data-stu-id="af762-113">Gives directions for responding to system or user events dynamically.</span></span>

 <span data-ttu-id="af762-114">[Procedura: Connettere più eventi a un singolo gestore eventi in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="af762-114">[How to: Connect Multiple Events to a Single Event Handler in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)</span></span>\
 <span data-ttu-id="af762-115">Fornisce le istruzioni per assegnare la stessa funzionalità a più controlli tramite gli eventi.</span><span class="sxs-lookup"><span data-stu-id="af762-115">Gives directions for assigning the same functionality to multiple controls through events.</span></span>

 <span data-ttu-id="af762-116">[Ordine degli eventi nel Windows Forms](order-of-events-in-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="af762-116">[Order of Events in Windows Forms](order-of-events-in-windows-forms.md)</span></span>\
 <span data-ttu-id="af762-117">Descrive l'ordine in cui gli eventi vengono generati nei controlli Windows Form.</span><span class="sxs-lookup"><span data-stu-id="af762-117">Describes the order in which events are raised in Windows Forms controls.</span></span>

 <span data-ttu-id="af762-118">[Procedura: Creazione di gestori eventi tramite la finestra](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)) di progettazione viene descritto come utilizzare il progettazione Windows Form per creare i gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="af762-118">[How to: Create Event Handlers Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)) Describes how to use the Windows Forms Designer to create event handlers.</span></span>

## <a name="related-sections"></a><span data-ttu-id="af762-119">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="af762-119">Related Sections</span></span>

 <span data-ttu-id="af762-120">[Eventi](../../standard/events/index.md)</span><span class="sxs-lookup"><span data-stu-id="af762-120">[Events](../../standard/events/index.md)</span></span>\
 <span data-ttu-id="af762-121">Vengono forniti collegamenti ad argomenti relativi alla gestione e alla generazione di eventi tramite il .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="af762-121">Provides links to topics on handling and raising events using the .NET Framework.</span></span>

 <span data-ttu-id="af762-122">[Risoluzione dei problemi relativi ai gestori eventi ereditati in Visual Basic](../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)</span><span class="sxs-lookup"><span data-stu-id="af762-122">[Troubleshooting Inherited Event Handlers in Visual Basic](../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)</span></span>\
 <span data-ttu-id="af762-123">Elenca i problemi comuni che si verificano con i gestori eventi nei componenti ereditati.</span><span class="sxs-lookup"><span data-stu-id="af762-123">Lists common issues that occur with event handlers in inherited components.</span></span>
