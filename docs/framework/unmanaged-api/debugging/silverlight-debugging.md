---
title: Debug Silverlight
ms.date: 03/30/2017
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 5e903e04-17d0-4014-ac9a-a43330ec8b1c
ms.openlocfilehash: 91f311818b615ea8f166bb3362ec52d39fcd0297
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790318"
---
# <a name="silverlight-debugging"></a><span data-ttu-id="6e622-102">Debug Silverlight</span><span class="sxs-lookup"><span data-stu-id="6e622-102">Silverlight Debugging</span></span>
<span data-ttu-id="6e622-103">Gli argomenti in questa sezione descrivono l'ambiente e le interfacce forniti da Common Language Runtime (CLR) per supportare il debug delle applicazioni basate su Silverlight in esecuzione nel sistema operativo Windows o sulla piattaforma Macintosh.</span><span class="sxs-lookup"><span data-stu-id="6e622-103">The topics in this section describe the environment and interfaces that the common language runtime (CLR) provides to support debugging Silverlight-based applications that are running on the Windows operating system, or on the Macintosh platform.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6e622-104">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="6e622-104">In This Section</span></span>  
 [<span data-ttu-id="6e622-105">Funzione EnumerateCLRs</span><span class="sxs-lookup"><span data-stu-id="6e622-105">EnumerateCLRs Function</span></span>](enumerateclrs-function.md)  
 <span data-ttu-id="6e622-106">Fornisce un meccanismo per l'enumerazione di CLR in un processo.</span><span class="sxs-lookup"><span data-stu-id="6e622-106">Provides a mechanism for enumerating the CLRs in a process.</span></span>  
  
 [<span data-ttu-id="6e622-107">Funzione CloseCLREnumeration</span><span class="sxs-lookup"><span data-stu-id="6e622-107">CloseCLREnumeration Function</span></span>](closeclrenumeration-function.md)  
 <span data-ttu-id="6e622-108">Chiude tutti gli eventi di avvio continuo di CLR validi presenti in una matrice di handle restituiti dalla [funzione EnumerateCLRs](enumerateclrs-function.md)e libera la memoria per le matrici del percorso di stringa e di handle.</span><span class="sxs-lookup"><span data-stu-id="6e622-108">Closes any valid CLR continue-startup events located in an array of handles returned by the [EnumerateCLRs Function](enumerateclrs-function.md), and frees the memory for the handle and string path arrays.</span></span>  
  
 [<span data-ttu-id="6e622-109">Funzione CreateCoreClrDebugTarget</span><span class="sxs-lookup"><span data-stu-id="6e622-109">CreateCoreClrDebugTarget Function</span></span>](createcoreclrdebugtarget-function.md)  
 <span data-ttu-id="6e622-110">Crea una connessione a una destinazione remota per l'enumerazione del runtime e dei processi.</span><span class="sxs-lookup"><span data-stu-id="6e622-110">Creates a connection to a remote target for process and runtime enumeration.</span></span>  
  
 [<span data-ttu-id="6e622-111">Funzione CreateCordbObject</span><span class="sxs-lookup"><span data-stu-id="6e622-111">CreateCordbObject Function</span></span>](createcordbobject-function.md)  
 <span data-ttu-id="6e622-112">Crea un'interfaccia del debugger che fornisce la funzionalità per creare un'istanza di una sessione di debug gestita in un processo remoto.</span><span class="sxs-lookup"><span data-stu-id="6e622-112">Creates a debugger interface that provides functionality for instantiating a managed debugging session on a remote process.</span></span>  
  
 [<span data-ttu-id="6e622-113">Funzione CreateVersionStringFromModule</span><span class="sxs-lookup"><span data-stu-id="6e622-113">CreateVersionStringFromModule Function</span></span>](createversionstringfrommodule-function.md)  
 <span data-ttu-id="6e622-114">Crea una stringa di versione da un percorso CLR in un processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="6e622-114">Creates a version string from a CLR path in a target process.</span></span>  
  
 [<span data-ttu-id="6e622-115">Funzione CreateDebuggingInterfaceFromVersion</span><span class="sxs-lookup"><span data-stu-id="6e622-115">CreateDebuggingInterfaceFromVersion Function</span></span>](createdebugginginterfacefromversion-function-for-silverlight.md)  
 <span data-ttu-id="6e622-116">Accetta una stringa di versione CLR restituita dalla funzione [CreateVersionStringFromModule Function](createversionstringfrommodule-function.md)e restituisce un'interfaccia del debugger corrispondente.</span><span class="sxs-lookup"><span data-stu-id="6e622-116">Accepts a CLR version string returned from [CreateVersionStringFromModule Function](createversionstringfrommodule-function.md)function, and returns a corresponding debugger interface.</span></span>  
  
 [<span data-ttu-id="6e622-117">Struttura CoreClrDebugProcInfo</span><span class="sxs-lookup"><span data-stu-id="6e622-117">CoreClrDebugProcInfo Structure</span></span>](coreclrdebugprocinfo-structure.md)  
 <span data-ttu-id="6e622-118">Rappresenta un processo in esecuzione in un computer remoto.</span><span class="sxs-lookup"><span data-stu-id="6e622-118">Represents a process that is running on a remote machine.</span></span>  
  
 [<span data-ttu-id="6e622-119">Struttura CoreClrDebugRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="6e622-119">CoreClrDebugRuntimeInfo Structure</span></span>](coreclrdebugruntimeinfo-structure.md)  
 <span data-ttu-id="6e622-120">Rappresenta un'istanza di Common Language Runtime (CLR) che viene caricata in un processo in un computer remoto.</span><span class="sxs-lookup"><span data-stu-id="6e622-120">Represents a CLR instance that is loaded in a process on a remote machine.</span></span>  
  
 [<span data-ttu-id="6e622-121">Funzione GetStartupNotificationEvent</span><span class="sxs-lookup"><span data-stu-id="6e622-121">GetStartupNotificationEvent Function</span></span>](getstartupnotificationevent-function.md)  
 <span data-ttu-id="6e622-122">Crea o apre un handle dell'evento che verrà segnalato da qualsiasi CLR (Common Language Runtime) caricato nel processo di destinazione specificato.</span><span class="sxs-lookup"><span data-stu-id="6e622-122">Creates or opens an event handle that will be signaled upon by any common language runtime (CLR) that is loading in the specified target process.</span></span>  
  
 [<span data-ttu-id="6e622-123">Interfaccia ICoreClrDebugTarget</span><span class="sxs-lookup"><span data-stu-id="6e622-123">ICoreClrDebugTarget Interface</span></span>](icoreclrdebugtarget-interface.md)  
 <span data-ttu-id="6e622-124">Crea una connessione a una destinazione remota per l'enumerazione del runtime e dei processi.</span><span class="sxs-lookup"><span data-stu-id="6e622-124">Creates a connection to a remote target for process and runtime enumeration.</span></span>  
  
 [<span data-ttu-id="6e622-125">Funzione InitDbgTransportManager</span><span class="sxs-lookup"><span data-stu-id="6e622-125">InitDbgTransportManager Function</span></span>](initdbgtransportmanager-function.md)  
 <span data-ttu-id="6e622-126">Inizializza il gestore trasporto per connettersi a una destinazione remota per l'enumerazione del runtime e dei processi.</span><span class="sxs-lookup"><span data-stu-id="6e622-126">Initializes the transport manager to connect to a remote target for process and runtime enumeration.</span></span>  
  
 [<span data-ttu-id="6e622-127">Funzione ShutdownDbgTransportManager</span><span class="sxs-lookup"><span data-stu-id="6e622-127">ShutdownDbgTransportManager Function</span></span>](shutdowndbgtransportmanager-function.md)  
 <span data-ttu-id="6e622-128">Arresta il gestore trasporto per una connessione a un computer di destinazione remoto.</span><span class="sxs-lookup"><span data-stu-id="6e622-128">Shuts down the transport manager for a connection to a remote target machine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e622-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e622-129">See also</span></span>

- [<span data-ttu-id="6e622-130">Coclassi di debug</span><span class="sxs-lookup"><span data-stu-id="6e622-130">Debugging Coclasses</span></span>](debugging-coclasses.md)
- [<span data-ttu-id="6e622-131">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="6e622-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="6e622-132">Funzioni statiche globali di debug</span><span class="sxs-lookup"><span data-stu-id="6e622-132">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
- [<span data-ttu-id="6e622-133">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="6e622-133">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="6e622-134">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="6e622-134">Debugging Structures</span></span>](debugging-structures.md)
