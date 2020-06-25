---
title: Creazione di gestori eventi
description: Informazioni sul modo in cui gli eventi in Windows Forms possono essere assegnati a più gestori e sul modo in cui i metodi che gestiscono determinati eventi possono essere modificati dinamicamente.
ms.date: 03/30/2017
helpviewer_keywords:
- event handling [Windows Forms]
- Windows Forms controls, event handling
- Windows Forms, event handling
- events [Windows Forms], event handlers
- event handlers [Windows Forms]
ms.assetid: 6514e530-c6b8-489c-a8d2-eda7b7072701
ms.openlocfilehash: 4dca198be69c200ea8dfc741a43801bf8f631b9d
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85326016"
---
# <a name="creating-event-handlers-in-windows-forms"></a><span data-ttu-id="88c70-103">Creazione di gestori eventi in Windows Form</span><span class="sxs-lookup"><span data-stu-id="88c70-103">Creating Event Handlers in Windows Forms</span></span>

<span data-ttu-id="88c70-104">Un gestore eventi è una procedura nel codice che determina le azioni da eseguire quando si verifica un evento, ad esempio quando l'utente fa clic su un pulsante o una coda di messaggi riceve un messaggio.</span><span class="sxs-lookup"><span data-stu-id="88c70-104">An event handler is a procedure in your code that determines what actions are performed when an event occurs, such as when the user clicks a button or a message queue receives a message.</span></span> <span data-ttu-id="88c70-105">Al momento della generazione di un evento, vengono eseguiti i gestori eventi che ricevono l'evento.</span><span class="sxs-lookup"><span data-stu-id="88c70-105">When an event is raised, the event handler or handlers that receive the event are executed.</span></span> <span data-ttu-id="88c70-106">Gli eventi possono essere assegnati a più gestori e i metodi che gestiscono determinati eventi possono essere modificati in modo dinamico.</span><span class="sxs-lookup"><span data-stu-id="88c70-106">Events can be assigned to multiple handlers, and the methods that handle particular events can be changed dynamically.</span></span> <span data-ttu-id="88c70-107">È anche possibile usare la Progettazione Windows Form in Visual Studio per creare i gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="88c70-107">You can also use the Windows Forms Designer in Visual Studio to create event handlers.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="88c70-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="88c70-108">In This Section</span></span>

 <span data-ttu-id="88c70-109">[Cenni preliminari sugli eventi](events-overview-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="88c70-109">[Events Overview](events-overview-windows-forms.md)</span></span>\
 <span data-ttu-id="88c70-110">Illustra il modello di eventi e il ruolo dei delegati.</span><span class="sxs-lookup"><span data-stu-id="88c70-110">Explains the event model and the role of delegates.</span></span>

 <span data-ttu-id="88c70-111">[Panoramica sui gestori eventi](event-handlers-overview-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="88c70-111">[Event Handlers Overview](event-handlers-overview-windows-forms.md)</span></span>\
 <span data-ttu-id="88c70-112">Descrive come gestire gli eventi.</span><span class="sxs-lookup"><span data-stu-id="88c70-112">Describes how to handle events.</span></span>

 <span data-ttu-id="88c70-113">[Procedura: creare gestori eventi in fase di esecuzione per Windows Forms](how-to-create-event-handlers-at-run-time-for-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="88c70-113">[How to: Create Event Handlers at Run Time for Windows Forms](how-to-create-event-handlers-at-run-time-for-windows-forms.md)</span></span>\
 <span data-ttu-id="88c70-114">Fornisce le istruzioni per rispondere dinamicamente agli eventi generati dall'utente o dal sistema.</span><span class="sxs-lookup"><span data-stu-id="88c70-114">Gives directions for responding to system or user events dynamically.</span></span>

 <span data-ttu-id="88c70-115">[Procedura: connettere più eventi a un singolo gestore eventi in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="88c70-115">[How to: Connect Multiple Events to a Single Event Handler in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)</span></span>\
 <span data-ttu-id="88c70-116">Fornisce le istruzioni per assegnare la stessa funzionalità a più controlli tramite gli eventi.</span><span class="sxs-lookup"><span data-stu-id="88c70-116">Gives directions for assigning the same functionality to multiple controls through events.</span></span>

 <span data-ttu-id="88c70-117">[Ordine degli eventi nel Windows Forms](order-of-events-in-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="88c70-117">[Order of Events in Windows Forms](order-of-events-in-windows-forms.md)</span></span>\
 <span data-ttu-id="88c70-118">Descrive l'ordine in cui gli eventi vengono generati nei controlli Windows Form.</span><span class="sxs-lookup"><span data-stu-id="88c70-118">Describes the order in which events are raised in Windows Forms controls.</span></span>

 <span data-ttu-id="88c70-119">[Procedura: creare gestori eventi utilizzando la finestra di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)) Viene descritto come utilizzare il Progettazione Windows Form per creare i gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="88c70-119">[How to: Create Event Handlers Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)) Describes how to use the Windows Forms Designer to create event handlers.</span></span>

## <a name="related-sections"></a><span data-ttu-id="88c70-120">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="88c70-120">Related Sections</span></span>

 <span data-ttu-id="88c70-121">[Eventi](../../standard/events/index.md)</span><span class="sxs-lookup"><span data-stu-id="88c70-121">[Events](../../standard/events/index.md)</span></span>\
 <span data-ttu-id="88c70-122">Vengono forniti collegamenti ad argomenti relativi alla gestione e alla generazione di eventi tramite il .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="88c70-122">Provides links to topics on handling and raising events using the .NET Framework.</span></span>

 <span data-ttu-id="88c70-123">[Risoluzione dei problemi relativi ai gestori eventi ereditati in Visual Basic](../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)</span><span class="sxs-lookup"><span data-stu-id="88c70-123">[Troubleshooting Inherited Event Handlers in Visual Basic](../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)</span></span>\
 <span data-ttu-id="88c70-124">Elenca i problemi comuni che si verificano con i gestori eventi nei componenti ereditati.</span><span class="sxs-lookup"><span data-stu-id="88c70-124">Lists common issues that occur with event handlers in inherited components.</span></span>
