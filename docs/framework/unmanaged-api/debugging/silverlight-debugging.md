---
title: Debug Silverlight
ms.date: 03/30/2017
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 5e903e04-17d0-4014-ac9a-a43330ec8b1c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 80cee666a05432099a380a5ac547a5ca28698c31
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436033"
---
# <a name="silverlight-debugging"></a><span data-ttu-id="cd79f-102">Debug Silverlight</span><span class="sxs-lookup"><span data-stu-id="cd79f-102">Silverlight Debugging</span></span>
<span data-ttu-id="cd79f-103">Gli argomenti in questa sezione descrivono l'ambiente e le interfacce forniti da Common Language Runtime (CLR) per supportare il debug delle applicazioni basate su Silverlight in esecuzione nel sistema operativo Windows o sulla piattaforma Macintosh.</span><span class="sxs-lookup"><span data-stu-id="cd79f-103">The topics in this section describe the environment and interfaces that the common language runtime (CLR) provides to support debugging Silverlight-based applications that are running on the Windows operating system, or on the Macintosh platform.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cd79f-104">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="cd79f-104">In This Section</span></span>  
 [<span data-ttu-id="cd79f-105">Funzione EnumerateCLRs</span><span class="sxs-lookup"><span data-stu-id="cd79f-105">EnumerateCLRs Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md)  
 <span data-ttu-id="cd79f-106">Fornisce un meccanismo per l'enumerazione di CLR in un processo.</span><span class="sxs-lookup"><span data-stu-id="cd79f-106">Provides a mechanism for enumerating the CLRs in a process.</span></span>  
  
 [<span data-ttu-id="cd79f-107">Funzione CloseCLREnumeration</span><span class="sxs-lookup"><span data-stu-id="cd79f-107">CloseCLREnumeration Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/closeclrenumeration-function.md)  
 <span data-ttu-id="cd79f-108">Chiude tutti gli eventi continuano l'avvio CLR validi posizionati in una matrice di handle restituita dal [funzione EnumerateCLRs](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md)e libera la memoria per le matrici del percorso stringa e di handle.</span><span class="sxs-lookup"><span data-stu-id="cd79f-108">Closes any valid CLR continue-startup events located in an array of handles returned by the [EnumerateCLRs Function](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md), and frees the memory for the handle and string path arrays.</span></span>  
  
 [<span data-ttu-id="cd79f-109">Funzione CreateCoreClrDebugTarget</span><span class="sxs-lookup"><span data-stu-id="cd79f-109">CreateCoreClrDebugTarget Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/createcoreclrdebugtarget-function.md)  
 <span data-ttu-id="cd79f-110">Crea una connessione a una destinazione remota per l'enumerazione del runtime e dei processi.</span><span class="sxs-lookup"><span data-stu-id="cd79f-110">Creates a connection to a remote target for process and runtime enumeration.</span></span>  
  
 [<span data-ttu-id="cd79f-111">Funzione CreateCordbObject</span><span class="sxs-lookup"><span data-stu-id="cd79f-111">CreateCordbObject Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/createcordbobject-function.md)  
 <span data-ttu-id="cd79f-112">Crea un'interfaccia del debugger che fornisce la funzionalità per creare un'istanza di una sessione di debug gestita in un processo remoto.</span><span class="sxs-lookup"><span data-stu-id="cd79f-112">Creates a debugger interface that provides functionality for instantiating a managed debugging session on a remote process.</span></span>  
  
 [<span data-ttu-id="cd79f-113">Funzione CreateVersionStringFromModule</span><span class="sxs-lookup"><span data-stu-id="cd79f-113">CreateVersionStringFromModule Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md)  
 <span data-ttu-id="cd79f-114">Crea una stringa di versione da un percorso CLR in un processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="cd79f-114">Creates a version string from a CLR path in a target process.</span></span>  
  
 [<span data-ttu-id="cd79f-115">Funzione CreateDebuggingInterfaceFromVersion</span><span class="sxs-lookup"><span data-stu-id="cd79f-115">CreateDebuggingInterfaceFromVersion Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/createdebugginginterfacefromversion-function-for-silverlight.md)  
 <span data-ttu-id="cd79f-116">Accetta una stringa di versione CLR restituiti da [funzione CreateVersionStringFromModule](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md)funzione e restituisce un'interfaccia del debugger corrispondente.</span><span class="sxs-lookup"><span data-stu-id="cd79f-116">Accepts a CLR version string returned from [CreateVersionStringFromModule Function](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md)function, and returns a corresponding debugger interface.</span></span>  
  
 [<span data-ttu-id="cd79f-117">Struttura CoreClrDebugProcInfo</span><span class="sxs-lookup"><span data-stu-id="cd79f-117">CoreClrDebugProcInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md)  
 <span data-ttu-id="cd79f-118">Rappresenta un processo in esecuzione in un computer remoto.</span><span class="sxs-lookup"><span data-stu-id="cd79f-118">Represents a process that is running on a remote machine.</span></span>  
  
 [<span data-ttu-id="cd79f-119">Struttura CoreClrDebugRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="cd79f-119">CoreClrDebugRuntimeInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugruntimeinfo-structure.md)  
 <span data-ttu-id="cd79f-120">Rappresenta un'istanza di Common Language Runtime (CLR) che viene caricata in un processo in un computer remoto.</span><span class="sxs-lookup"><span data-stu-id="cd79f-120">Represents a CLR instance that is loaded in a process on a remote machine.</span></span>  
  
 [<span data-ttu-id="cd79f-121">Funzione GetStartupNotificationEvent</span><span class="sxs-lookup"><span data-stu-id="cd79f-121">GetStartupNotificationEvent Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/getstartupnotificationevent-function.md)  
 <span data-ttu-id="cd79f-122">Crea o apre un handle dell'evento che verrà segnalato da qualsiasi CLR (Common Language Runtime) caricato nel processo di destinazione specificato.</span><span class="sxs-lookup"><span data-stu-id="cd79f-122">Creates or opens an event handle that will be signaled upon by any common language runtime (CLR) that is loading in the specified target process.</span></span>  
  
 [<span data-ttu-id="cd79f-123">Interfaccia ICoreClrDebugTarget</span><span class="sxs-lookup"><span data-stu-id="cd79f-123">ICoreClrDebugTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)  
 <span data-ttu-id="cd79f-124">Crea una connessione a una destinazione remota per l'enumerazione del runtime e dei processi.</span><span class="sxs-lookup"><span data-stu-id="cd79f-124">Creates a connection to a remote target for process and runtime enumeration.</span></span>  
  
 [<span data-ttu-id="cd79f-125">Funzione InitDbgTransportManager</span><span class="sxs-lookup"><span data-stu-id="cd79f-125">InitDbgTransportManager Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/initdbgtransportmanager-function.md)  
 <span data-ttu-id="cd79f-126">Inizializza il gestore trasporto per connettersi a una destinazione remota per l'enumerazione del runtime e dei processi.</span><span class="sxs-lookup"><span data-stu-id="cd79f-126">Initializes the transport manager to connect to a remote target for process and runtime enumeration.</span></span>  
  
 [<span data-ttu-id="cd79f-127">Funzione ShutdownDbgTransportManager</span><span class="sxs-lookup"><span data-stu-id="cd79f-127">ShutdownDbgTransportManager Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/shutdowndbgtransportmanager-function.md)  
 <span data-ttu-id="cd79f-128">Arresta il gestore trasporto per una connessione a un computer di destinazione remoto.</span><span class="sxs-lookup"><span data-stu-id="cd79f-128">Shuts down the transport manager for a connection to a remote target machine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd79f-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd79f-129">See Also</span></span>  
 [<span data-ttu-id="cd79f-130">Coclassi di debug</span><span class="sxs-lookup"><span data-stu-id="cd79f-130">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
 [<span data-ttu-id="cd79f-131">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="cd79f-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="cd79f-132">Funzioni statiche globali di debug</span><span class="sxs-lookup"><span data-stu-id="cd79f-132">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
 [<span data-ttu-id="cd79f-133">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="cd79f-133">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="cd79f-134">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="cd79f-134">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
