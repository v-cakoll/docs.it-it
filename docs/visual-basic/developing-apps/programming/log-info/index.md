---
title: Registrazione di informazioni relative all'applicazione
ms.date: 07/20/2015
helpviewer_keywords:
- Log object
- My.Log object
- applications [Visual Basic], logging information from
- logging
- My.Application.Log object
- examples [Visual Basic], logging application information
ms.assetid: 8bf4f047-22d6-48d6-aec5-93b98ad5b8e8
ms.openlocfilehash: 43738b2d654435532a98654cbc40af134d43f02c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410023"
---
# <a name="logging-information-from-the-application-visual-basic"></a><span data-ttu-id="b43c1-102">Registrazione di informazioni relative all'applicazione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b43c1-102">Logging Information from the Application (Visual Basic)</span></span>

<span data-ttu-id="b43c1-103">Questa sezione contiene argomenti che descrivono come registrare le informazioni provenienti dall'applicazione usando l'oggetto `My.Application.Log` o `My.Log`. Viene anche spiegato come estendere le funzionalità di registrazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b43c1-103">This section contains topics that cover how to log information from your application using the `My.Application.Log` or `My.Log` object, and how to extend the application's logging capabilities.</span></span>  
  
 <span data-ttu-id="b43c1-104">L'oggetto `Log` fornisce i metodi per scrivere le informazioni sui listener di log dell'applicazione, mentre la proprietà avanzata `TraceSource` dell'oggetto `Log` fornisce informazioni di configurazione dettagliate.</span><span class="sxs-lookup"><span data-stu-id="b43c1-104">The `Log` object provides methods for writing information to the application's log listeners, and the `Log` object's advanced `TraceSource` property provides detailed configuration information.</span></span> <span data-ttu-id="b43c1-105">L'oggetto `Log` può essere configurato dal file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b43c1-105">The `Log` object is configured by the application's configuration file.</span></span>  
  
 <span data-ttu-id="b43c1-106">L'oggetto `My.Log` è disponibile solo per le applicazioni ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="b43c1-106">The `My.Log` object is available only for ASP.NET applications.</span></span> <span data-ttu-id="b43c1-107">Per le applicazioni client, usare `My.Application.Log`.</span><span class="sxs-lookup"><span data-stu-id="b43c1-107">For client applications, use `My.Application.Log`.</span></span> <span data-ttu-id="b43c1-108">Per altre informazioni, vedere <xref:Microsoft.VisualBasic.Logging.Log>.</span><span class="sxs-lookup"><span data-stu-id="b43c1-108">For more information, see <xref:Microsoft.VisualBasic.Logging.Log>.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="b43c1-109">Attività</span><span class="sxs-lookup"><span data-stu-id="b43c1-109">Tasks</span></span>  
  
|<span data-ttu-id="b43c1-110">A</span><span class="sxs-lookup"><span data-stu-id="b43c1-110">To</span></span>|<span data-ttu-id="b43c1-111">Vedere</span><span class="sxs-lookup"><span data-stu-id="b43c1-111">See</span></span>|  
|--------|---------|  
|<span data-ttu-id="b43c1-112">Scrivere le informazioni sugli eventi nei log dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b43c1-112">Write event information to the application's logs.</span></span>|[<span data-ttu-id="b43c1-113">Procedura: Scrivere messaggi di log</span><span class="sxs-lookup"><span data-stu-id="b43c1-113">How to: Write Log Messages</span></span>](how-to-write-log-messages.md)|  
|<span data-ttu-id="b43c1-114">Scrivere le informazioni sulle eccezioni nei log dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b43c1-114">Write exception information to the application's logs.</span></span>|[<span data-ttu-id="b43c1-115">Procedura: Registrare eccezioni</span><span class="sxs-lookup"><span data-stu-id="b43c1-115">How to: Log Exceptions</span></span>](how-to-log-exceptions.md)|  
|<span data-ttu-id="b43c1-116">Scrivere le informazioni di traccia nei log dell'applicazione all'avvio e alla chiusura dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b43c1-116">Write trace information to the application's logs when the application starts and shuts down.</span></span>|[<span data-ttu-id="b43c1-117">Procedura: Registrare messaggi all'avvio o all'arresto dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="b43c1-117">How to: Log Messages When the Application Starts or Shuts Down</span></span>](how-to-log-messages-when-the-application-starts-or-shuts-down.md)|  
|<span data-ttu-id="b43c1-118">Configurare `My.Application.Log` per scrivere le informazioni in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="b43c1-118">Configure `My.Application.Log` to write information to a text file.</span></span>|[<span data-ttu-id="b43c1-119">Procedura: Scrivere informazioni sugli eventi in un file di testo</span><span class="sxs-lookup"><span data-stu-id="b43c1-119">How to: Write Event Information to a Text File</span></span>](how-to-write-event-information-to-a-text-file.md)|  
|<span data-ttu-id="b43c1-120">Configurare `My.Application.Log` per scrivere le informazioni in un log eventi.</span><span class="sxs-lookup"><span data-stu-id="b43c1-120">Configure `My.Application.Log` to write information to an event log.</span></span>|[<span data-ttu-id="b43c1-121">Procedura: Scrivere nel log eventi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="b43c1-121">How to: Write to an Application Event Log</span></span>](how-to-write-to-an-application-event-log.md)|  
|<span data-ttu-id="b43c1-122">Modificare la posizione in cui `My.Application.Log` scrive le informazioni.</span><span class="sxs-lookup"><span data-stu-id="b43c1-122">Change where `My.Application.Log` writes information.</span></span>|[<span data-ttu-id="b43c1-123">Procedura dettagliata: Modifica della posizione di inserimento delle informazioni con My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="b43c1-123">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](walkthrough-changing-where-my-application-log-writes-information.md)|  
|<span data-ttu-id="b43c1-124">Determinare la posizione in cui `My.Application.Log` scrive le informazioni.</span><span class="sxs-lookup"><span data-stu-id="b43c1-124">Determine where `My.Application.Log` writes information.</span></span>|[<span data-ttu-id="b43c1-125">Procedura dettagliata: Individuazione della posizione di inserimento delle informazioni con My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="b43c1-125">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](walkthrough-determining-where-my-application-log-writes-information.md)|  
|<span data-ttu-id="b43c1-126">Creare un listener di log personalizzato per `My.Application.Log`.</span><span class="sxs-lookup"><span data-stu-id="b43c1-126">Create a custom log listener for `My.Application.Log`.</span></span>|[<span data-ttu-id="b43c1-127">Procedura dettagliata: Creazione di listener di log personalizzati</span><span class="sxs-lookup"><span data-stu-id="b43c1-127">Walkthrough: Creating Custom Log Listeners</span></span>](walkthrough-creating-custom-log-listeners.md)|  
|<span data-ttu-id="b43c1-128">Filtrare l'output dei log `My.Application.Log`.</span><span class="sxs-lookup"><span data-stu-id="b43c1-128">Filter the output of the `My.Application.Log` logs.</span></span>|[<span data-ttu-id="b43c1-129">Procedura dettagliata: Filtro dell'output di My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="b43c1-129">Walkthrough: Filtering My.Application.Log Output</span></span>](walkthrough-filtering-my-application-log-output.md)|  
  
## <a name="see-also"></a><span data-ttu-id="b43c1-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b43c1-130">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- [<span data-ttu-id="b43c1-131">Utilizzo dei log applicazione</span><span class="sxs-lookup"><span data-stu-id="b43c1-131">Working with Application Logs</span></span>](working-with-application-logs.md)
- [<span data-ttu-id="b43c1-132">Risoluzione dei problemi: Listener di log</span><span class="sxs-lookup"><span data-stu-id="b43c1-132">Troubleshooting: Log Listeners</span></span>](troubleshooting-log-listeners.md)
