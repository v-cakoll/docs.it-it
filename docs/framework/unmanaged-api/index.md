---
title: Riferimenti alle API non gestite
ms.date: 11/06/2017
helpviewer_keywords:
- runtime, unmanaged APIs
- common language runtime, unmanaged APIs
- native API reference [.NET Framework]
- unmanaged API reference [.NET Framework]
ms.assetid: 9aa000ee-c04c-492c-ae4f-83ecdf4fdbbe
ms.openlocfilehash: f7dd78b889129998dee31a22f5dd23325613b8ea
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73092023"
---
# <a name="unmanaged-api-reference"></a><span data-ttu-id="011a7-102">Riferimenti alle API non gestite</span><span class="sxs-lookup"><span data-stu-id="011a7-102">Unmanaged API Reference</span></span>
<span data-ttu-id="011a7-103">Questa sezione include informazioni sulle API non gestite che possono essere usate da applicazioni correlate a codice gestito, ad esempio host di runtime, compilatori, disassembler, soluzioni di offuscamento, debugger e profiler.</span><span class="sxs-lookup"><span data-stu-id="011a7-103">This section includes information on unmanaged APIs that can be used by managed-code-related applications, such as runtime hosts, compilers, disassemblers, obfuscators, debuggers, and profilers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="011a7-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="011a7-104">In This Section</span></span>  
 [<span data-ttu-id="011a7-105">Tipi di dati comuni</span><span class="sxs-lookup"><span data-stu-id="011a7-105">Common Data Types</span></span>](common-data-types-unmanaged-api-reference.md)  
 <span data-ttu-id="011a7-106">Vengono elencati i tipi di dati comuni usati, in particolare nelle API non gestite di profilatura e debug.</span><span class="sxs-lookup"><span data-stu-id="011a7-106">Lists the common data types that are used, particularly in the unmanaged profiling and debugging APIs.</span></span>  
  
 [<span data-ttu-id="011a7-107">ALink</span><span class="sxs-lookup"><span data-stu-id="011a7-107">ALink</span></span>](./alink/index.md)  
 <span data-ttu-id="011a7-108">Viene descritta l'API ALink che supporta la creazione di moduli non associati e assembly .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="011a7-108">Describes the ALink API, which supports the creation of .NET Framework assemblies and unbound modules.</span></span>  
  
 [<span data-ttu-id="011a7-109">Authenticode</span><span class="sxs-lookup"><span data-stu-id="011a7-109">Authenticode</span></span>](./authenticode/index.md)  
 <span data-ttu-id="011a7-110">Supporta il modulo di creazione e verifica delle licenze Authenticode XrML.</span><span class="sxs-lookup"><span data-stu-id="011a7-110">Supports the Authenticode XrML license creation and verification module.</span></span>  
  
 [<span data-ttu-id="011a7-111">Costanti</span><span class="sxs-lookup"><span data-stu-id="011a7-111">Constants</span></span>](constants-unmanaged-api-reference.md)  
 <span data-ttu-id="011a7-112">Vengono descritte le costanti definite in CorSym.idl.</span><span class="sxs-lookup"><span data-stu-id="011a7-112">Describes the constants that are defined in CorSym.idl.</span></span>  
  
 <span data-ttu-id="011a7-113">[Attributi di interfaccia personalizzati](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms231946(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="011a7-113">[Custom Interface Attributes](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms231946(v=vs.100))</span></span>  
 <span data-ttu-id="011a7-114">Vengono descritti gli attributi di interfaccia personalizzati COM (Component Object Model).</span><span class="sxs-lookup"><span data-stu-id="011a7-114">Describes component object model (COM) custom interface attributes.</span></span>  
  
 [<span data-ttu-id="011a7-115">Debug</span><span class="sxs-lookup"><span data-stu-id="011a7-115">Debugging</span></span>](./debugging/index.md)  
 <span data-ttu-id="011a7-116">Viene descritta l'API di debug, che consente a un debugger di effettuare il debug del codice in esecuzione nell'ambiente di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="011a7-116">Describes the debugging API, which enables a debugger to debug code that runs in the common language runtime (CLR) environment.</span></span>  
  
 [<span data-ttu-id="011a7-117">Archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="011a7-117">Diagnostics Symbol Store</span></span>](./diagnostics/index.md)  
 <span data-ttu-id="011a7-118">Viene descritta l'API dell'archivio dei simboli di diagnostica, che consente a un compilatore di generare informazioni relative ai simboli che possono essere usate da un debugger.</span><span class="sxs-lookup"><span data-stu-id="011a7-118">Describes the diagnostics symbol store API, which enables a compiler to generate symbol information for use by a debugger.</span></span>  
  
 [<span data-ttu-id="011a7-119">Fusione</span><span class="sxs-lookup"><span data-stu-id="011a7-119">Fusion</span></span>](./fusion/index.md)  
 <span data-ttu-id="011a7-120">Viene descritta l'API Fusion, che consente a un host di runtime di accedere alle proprietà delle risorse di un'applicazione per individuare le versioni corrette di tali risorse per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="011a7-120">Describes the fusion API, which enables a runtime host to access the properties of an application's resources in order to locate the correct versions of those resources for the application.</span></span>  
  
 [<span data-ttu-id="011a7-121">Hosting</span><span class="sxs-lookup"><span data-stu-id="011a7-121">Hosting</span></span>](./hosting/index.md)  
 <span data-ttu-id="011a7-122">Viene descritta l'API di hosting, che consente agli host non gestiti di integrare CLR nelle relative applicazioni.</span><span class="sxs-lookup"><span data-stu-id="011a7-122">Describes the hosting API, which enables unmanaged hosts to integrate the CLR into their applications.</span></span>  
  
 [<span data-ttu-id="011a7-123">Metadati</span><span class="sxs-lookup"><span data-stu-id="011a7-123">Metadata</span></span>](./metadata/index.md)  
 <span data-ttu-id="011a7-124">Viene descritta l'API dei metadati, che consente a un client, ad esempio un compilatore, di generare o accedere ai metadati di un componente senza che i tipi vengano caricati da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="011a7-124">Describes the metadata API, which enables a client such as a compiler to generate or access a component's metadata without the types being loaded by the CLR.</span></span>  
  
 [<span data-ttu-id="011a7-125">Profilatura</span><span class="sxs-lookup"><span data-stu-id="011a7-125">Profiling</span></span>](./profiling/index.md)  
 <span data-ttu-id="011a7-126">Viene descritta l'API di profilatura, che consente a un profiler di monitorare l'esecuzione di un programma da parte di CLR.</span><span class="sxs-lookup"><span data-stu-id="011a7-126">Describes the profiling API, which enables a profiler to monitor a program's execution by the CLR.</span></span>  
  
 [<span data-ttu-id="011a7-127">Denominazione forte</span><span class="sxs-lookup"><span data-stu-id="011a7-127">Strong Naming</span></span>](./strong-naming/index.md)  
 <span data-ttu-id="011a7-128">Viene descritta l'API di denominazione sicura, che consente a un client di amministrare la firma con nome sicuro per gli assembly.</span><span class="sxs-lookup"><span data-stu-id="011a7-128">Describes the strong naming API, which enables a client to administer strong name signing for assemblies.</span></span>  

 [<span data-ttu-id="011a7-129">Contatori delle prestazioni e WMI</span><span class="sxs-lookup"><span data-stu-id="011a7-129">WMI and Performance Counters</span></span>](wmi/index.md)  
 <span data-ttu-id="011a7-130">Descrive le API che eseguono il wrapping di chiamate in librerie di Strumentazione gestione Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="011a7-130">Describes the APIs that wrap calls to Windows Management Instrumentation (WMI) libraries.</span></span>
  
 [<span data-ttu-id="011a7-131">Funzioni helper Tlbexp</span><span class="sxs-lookup"><span data-stu-id="011a7-131">Tlbexp Helper Functions</span></span>](./tlbexp/index.md)  
 <span data-ttu-id="011a7-132">Vengono descritte le due funzioni di supporto e un'interfaccia usata dall'utilità di esportazione della libreria dei tipi (Tlbexp.exe) durante il processo di conversione da assembly a libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="011a7-132">Describes the two helper functions and interface used by the Type Library Exporter (Tlbexp.exe) during the assembly-to-type-library conversion process.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="011a7-133">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="011a7-133">Related Sections</span></span>  
 [<span data-ttu-id="011a7-134">Guida di sviluppo</span><span class="sxs-lookup"><span data-stu-id="011a7-134">Development Guide</span></span>](../../../docs/framework/development-guide.md)  
