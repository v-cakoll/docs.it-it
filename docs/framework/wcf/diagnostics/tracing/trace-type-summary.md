---
title: Riepilogo dei tipi di traccia
ms.date: 03/30/2017
ms.assetid: e639410b-d1d1-479c-b78e-a4701d4e4085
ms.openlocfilehash: e3bc66753dd44e1dc4c7417caf593820300f69a5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33486042"
---
# <a name="trace-type-summary"></a><span data-ttu-id="2852c-102">Riepilogo dei tipi di traccia</span><span class="sxs-lookup"><span data-stu-id="2852c-102">Trace Type Summary</span></span>
<span data-ttu-id="2852c-103">[SourceLevels](http://go.microsoft.com/fwlink/?LinkID=94943) definisce vari livelli di traccia: critico, errore, avviso, informazioni e dettagliato, nonché come fornisce la descrizione del `ActivityTracing` flag che attiva o disattiva l'output della traccia gli eventi di trasferimento di limite e attività.</span><span class="sxs-lookup"><span data-stu-id="2852c-103">[Source Levels](http://go.microsoft.com/fwlink/?LinkID=94943) defines various trace levels: Critical, Error, Warning, Information, and Verbose, as well as provides description of the `ActivityTracing` flag, which toggles the output of trace boundary and activity transfer events.</span></span>  
  
 <span data-ttu-id="2852c-104">È inoltre possibile rivedere [TraceEventType](http://go.microsoft.com/fwlink/?LinkId=95169) per i tipi di traccia che può essere emessi da <xref:System.Diagnostics>.</span><span class="sxs-lookup"><span data-stu-id="2852c-104">You can also review [TraceEventType](http://go.microsoft.com/fwlink/?LinkId=95169) for the types of traces which can be emitted from <xref:System.Diagnostics>.</span></span>  
  
 <span data-ttu-id="2852c-105">Nella tabella seguente sono elencati quelli più importanti.</span><span class="sxs-lookup"><span data-stu-id="2852c-105">The following table lists the most important ones.</span></span>  
  
|<span data-ttu-id="2852c-106">Tipo di traccia</span><span class="sxs-lookup"><span data-stu-id="2852c-106">Trace Type</span></span>|<span data-ttu-id="2852c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2852c-107">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="2852c-108">Critical</span><span class="sxs-lookup"><span data-stu-id="2852c-108">Critical</span></span>|<span data-ttu-id="2852c-109">Errore irreversibile o arresto anomalo dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2852c-109">Fatal error or application crash.</span></span>|  
|<span data-ttu-id="2852c-110">Errore</span><span class="sxs-lookup"><span data-stu-id="2852c-110">Error</span></span>|<span data-ttu-id="2852c-111">Errore risolvibile.</span><span class="sxs-lookup"><span data-stu-id="2852c-111">Recoverable error.</span></span>|  
|<span data-ttu-id="2852c-112">Avviso</span><span class="sxs-lookup"><span data-stu-id="2852c-112">Warning</span></span>|<span data-ttu-id="2852c-113">Messaggio informativo.</span><span class="sxs-lookup"><span data-stu-id="2852c-113">Informational message.</span></span>|  
|<span data-ttu-id="2852c-114">Informazioni</span><span class="sxs-lookup"><span data-stu-id="2852c-114">Information</span></span>|<span data-ttu-id="2852c-115">Problema non critico.</span><span class="sxs-lookup"><span data-stu-id="2852c-115">Non-critical problem.</span></span>|  
|<span data-ttu-id="2852c-116">Dettagliato</span><span class="sxs-lookup"><span data-stu-id="2852c-116">Verbose</span></span>|<span data-ttu-id="2852c-117">Traccia di debug.</span><span class="sxs-lookup"><span data-stu-id="2852c-117">Debugging trace.</span></span>|  
|<span data-ttu-id="2852c-118">Inizia</span><span class="sxs-lookup"><span data-stu-id="2852c-118">Start</span></span>|<span data-ttu-id="2852c-119">Avvio di un'unità logica di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="2852c-119">Starting of a logical unit of processing.</span></span>|  
|<span data-ttu-id="2852c-120">Sospendi</span><span class="sxs-lookup"><span data-stu-id="2852c-120">Suspend</span></span>|<span data-ttu-id="2852c-121">Sospensione di un'unità logica di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="2852c-121">Suspension of a logical unit of processing.</span></span>|  
|<span data-ttu-id="2852c-122">Riprendi</span><span class="sxs-lookup"><span data-stu-id="2852c-122">Resume</span></span>|<span data-ttu-id="2852c-123">Ripresa di un'unità logica di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="2852c-123">Resumption of a logical unit of processing.</span></span>|  
|<span data-ttu-id="2852c-124">Arresta</span><span class="sxs-lookup"><span data-stu-id="2852c-124">Stop</span></span>|<span data-ttu-id="2852c-125">Interruzione di un'unità logica di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="2852c-125">Stopping of a logical unit of processing.</span></span>|  
|<span data-ttu-id="2852c-126">Trasferimento</span><span class="sxs-lookup"><span data-stu-id="2852c-126">Transfer</span></span>|<span data-ttu-id="2852c-127">Modifica dell'identità di correlazione.</span><span class="sxs-lookup"><span data-stu-id="2852c-127">Changing of correlation identity.</span></span>|  
  
 <span data-ttu-id="2852c-128">Un'attività è definita come una combinazione dei tipi di traccia riportati sopra.</span><span class="sxs-lookup"><span data-stu-id="2852c-128">An activity is defined as a combination of the trace types above.</span></span>  
  
 <span data-ttu-id="2852c-129">Quella che segue è un'espressione regolare che definisce un'attività ideale in un ambito locale (origine di traccia),</span><span class="sxs-lookup"><span data-stu-id="2852c-129">The following is a regular expression that defines an ideal activity in a local (trace source) scope,</span></span>  
  
 `R = Start (Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop`  
  
 <span data-ttu-id="2852c-130">Ciò significa che un'attività deve soddisfare le condizioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="2852c-130">This means that an activity must satisfy the following conditions.</span></span>  
  
-   <span data-ttu-id="2852c-131">Deve avviarsi e arrestarsi rispettivamente con tracce Start e Stop.</span><span class="sxs-lookup"><span data-stu-id="2852c-131">It must start and stop respectively by a Start and Stop traces</span></span>  
  
-   <span data-ttu-id="2852c-132">Deve avere una traccia Transfer subito prima di una traccia Suspend o Resume</span><span class="sxs-lookup"><span data-stu-id="2852c-132">It must have a Transfer trace immediately preceding a Suspend or Resume trace</span></span>  
  
-   <span data-ttu-id="2852c-133">Non deve avere nessuna traccia tra le tracce Suspend e Resume, se esistono</span><span class="sxs-lookup"><span data-stu-id="2852c-133">It must not have any traces between the Suspend and Resume traces if such traces exist</span></span>  
  
-   <span data-ttu-id="2852c-134">Può avere un numero qualsiasi di tracce Critical/Error/Warning/Information/Verbose/Transfer, a condizione che vengano rispettate le condizioni precedenti</span><span class="sxs-lookup"><span data-stu-id="2852c-134">It can have any and as many of critical/Error/Warning/Information/Verbose/Transfer traces as long as the previous conditions are observed</span></span>  
  
 <span data-ttu-id="2852c-135">Quella che segue è un'espressione regolare che definisce un'attività ideale in ambito globale,</span><span class="sxs-lookup"><span data-stu-id="2852c-135">The following is a regular expression that defines an ideal activity in the global scope,</span></span>  
  
```  
R+   
```  
  
 <span data-ttu-id="2852c-136">con R che è l'espressione regolare per un'attività nell'ambito locale.</span><span class="sxs-lookup"><span data-stu-id="2852c-136">with R being the regular expression for an activity in the local scope.</span></span> <span data-ttu-id="2852c-137">Ciò si traduce in,</span><span class="sxs-lookup"><span data-stu-id="2852c-137">This translates to,</span></span>  
  
```  
[R+ = Start ( Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop]+  
```
