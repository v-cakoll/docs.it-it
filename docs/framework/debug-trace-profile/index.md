---
title: Debug, traccia e profilatura
ms.date: 03/30/2017
helpviewer_keywords:
- debugging [.NET Framework]
- .NET Framework application configuration, debugging
- debugging [.NET Framework], .NET Framework application debugging
- troubleshooting applications [.NET Framework], profiling
- application development [.NET Framework], debugging
- .NET Framework application configuration, profiling
- profiling applications
- troubleshooting applications [.NET Framework], debugging
- troubleshooting applications [.NET Framework]
- application development [.NET Framework], profiling
ms.assetid: 4a04863e-2475-46f4-bc3f-3c11510c2a4b
ms.openlocfilehash: 1a43c7fbcb810b22ff9bc409c233d2b1da67370e
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217397"
---
# <a name="debugging-tracing-and-profiling"></a><span data-ttu-id="6b5df-102">Debug, traccia e profilatura</span><span class="sxs-lookup"><span data-stu-id="6b5df-102">Debugging, Tracing, and Profiling</span></span>
<span data-ttu-id="6b5df-103">Per eseguire il debug di un'applicazione .NET Framework, l'ambiente del compilatore e di runtime deve essere configurato per consentire a un debugger di connettersi all'applicazione e di produrre simboli e mappe di linee, se possibile, per l'applicazione e il corrispondente Microsoft Intermediate Language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="6b5df-103">To debug a .NET Framework application, the compiler and runtime environment must be configured to enable a debugger to attach to the application and to produce both symbols and line maps, if possible, for the application and its corresponding Microsoft intermediate language (MSIL).</span></span> <span data-ttu-id="6b5df-104">Dopo il debug di un'applicazione gestita, è possibile eseguire la profilatura per migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="6b5df-104">After a managed application has been debugged, it can be profiled to boost performance.</span></span> <span data-ttu-id="6b5df-105">La profilatura valuta e descrive le righe del codice sorgente che generano il codice eseguito con maggiore frequenza e il tempo richiesto per eseguirle.</span><span class="sxs-lookup"><span data-stu-id="6b5df-105">Profiling evaluates and describes the lines of source code that generate the most frequently executed code, and how much time it takes to execute them.</span></span>  
  
 <span data-ttu-id="6b5df-106">Il debug delle applicazioni .NET framework viene eseguito facilmente tramite Visual Studio, che gestisce molti dettagli della configurazione.</span><span class="sxs-lookup"><span data-stu-id="6b5df-106">.NET Framework applications are easily debugged by using Visual Studio, which handles many of the configuration details.</span></span> <span data-ttu-id="6b5df-107">Se Visual Studio non è installato, è possibile esaminare e migliorare le prestazioni delle applicazioni .NET Framework usando le classi di debug nello spazio dei nomi <xref:System.Diagnostics> di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6b5df-107">If Visual Studio is not installed, you can examine and improve the performance of .NET Framework applications by using the debugging classes in the .NET Framework <xref:System.Diagnostics> namespace.</span></span> <span data-ttu-id="6b5df-108">Questo spazio dei nomi include le classi <xref:System.Diagnostics.Trace>, <xref:System.Diagnostics.Debug> e <xref:System.Diagnostics.TraceSource> per la traccia del flusso di esecuzione e le classi <xref:System.Diagnostics.Process>, <xref:System.Diagnostics.EventLog> e <xref:System.Diagnostics.PerformanceCounter> per il codice di profilatura.</span><span class="sxs-lookup"><span data-stu-id="6b5df-108">This namespace includes the <xref:System.Diagnostics.Trace>, <xref:System.Diagnostics.Debug>, and <xref:System.Diagnostics.TraceSource> classes for tracing execution flow, and the <xref:System.Diagnostics.Process>, <xref:System.Diagnostics.EventLog>, and <xref:System.Diagnostics.PerformanceCounter> classes for profiling code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6b5df-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="6b5df-109">In This Section</span></span>  
 [<span data-ttu-id="6b5df-110">Abilitazione del debug ad associazione JIT</span><span class="sxs-lookup"><span data-stu-id="6b5df-110">Enabling JIT-Attach Debugging</span></span>](enabling-jit-attach-debugging.md)  
 <span data-ttu-id="6b5df-111">Mostra come configurare il Registro di sistema per eseguire l'associazione JIT di un motore di debug in un'applicazione .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6b5df-111">Shows how to configure the registry to JIT-attach a debug engine to a .NET Framework application.</span></span>  
  
 [<span data-ttu-id="6b5df-112">Semplificazione del debug di un'immagine</span><span class="sxs-lookup"><span data-stu-id="6b5df-112">Making an Image Easier to Debug</span></span>](making-an-image-easier-to-debug.md)  
 <span data-ttu-id="6b5df-113">Mostra come attivare il rilevamento JIT e disattivare l'ottimizzazione per rendere più semplice l'esecuzione del debug di un assembly.</span><span class="sxs-lookup"><span data-stu-id="6b5df-113">Shows how to turn JIT tracking on and optimization off to make an assembly easier to debug.</span></span>  
  
 [<span data-ttu-id="6b5df-114">Traccia e strumentazione di applicazioni</span><span class="sxs-lookup"><span data-stu-id="6b5df-114">Tracing and Instrumenting Applications</span></span>](tracing-and-instrumenting-applications.md)  
 <span data-ttu-id="6b5df-115">Descrive come monitorare l'esecuzione dell'applicazione mentre è in esecuzione e come instrumentarla per visualizzare lo stato o gli errori durante l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6b5df-115">Describes how to monitor the execution of your application while it is running, and how to instrument it to display how well it is performing or whether something has gone wrong.</span></span>  
  
 [<span data-ttu-id="6b5df-116">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="6b5df-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)  
 <span data-ttu-id="6b5df-117">Descrive gli assistenti al debug gestito, strumenti di supporto al debug che funzionano in combinazione con Common Language Runtime (CLR) per fornire informazioni sullo stato di runtime.</span><span class="sxs-lookup"><span data-stu-id="6b5df-117">Describes managed debugging assistants (MDAs), which are debugging aids that work in conjunction with the common language runtime (CLR) to provide information on runtime state.</span></span>  
  
 [<span data-ttu-id="6b5df-118">Miglioramento del debug tramite gli attributi di visualizzazione del debugger</span><span class="sxs-lookup"><span data-stu-id="6b5df-118">Enhancing Debugging with the Debugger Display Attributes</span></span>](enhancing-debugging-with-the-debugger-display-attributes.md)  
 <span data-ttu-id="6b5df-119">Descrive in che modo lo sviluppatore di un tipo può specificarne l'aspetto quando viene visualizzato in un debugger.</span><span class="sxs-lookup"><span data-stu-id="6b5df-119">Describes how the developer of a type can specify what that type will look like when it is displayed in a debugger.</span></span>  
  
 [<span data-ttu-id="6b5df-120">Contatori delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="6b5df-120">Performance Counters</span></span>](performance-counters.md)  
 <span data-ttu-id="6b5df-121">Descrive i contatori che è possibile usare per registrare le prestazioni di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6b5df-121">Describes the counters that you can use to track the performance of an application.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6b5df-122">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="6b5df-122">Related Sections</span></span>  
 [<span data-ttu-id="6b5df-123">Eseguire il debug di app ASP.NET o ASP.NET Core in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6b5df-123">Debug ASP.NET or ASP.NET Core apps in Visual Studio</span></span>](/visualstudio/debugger/how-to-enable-debugging-for-aspnet-applications)  
 <span data-ttu-id="6b5df-124">Fornisce i prerequisiti e le istruzioni su come eseguire il debug di un'applicazione ASP.NET durante lo sviluppo o dopo la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="6b5df-124">Provides prerequisites and instructions for how to debug an ASP.NET application during development or after deployment.</span></span>  
  
 [<span data-ttu-id="6b5df-125">Guida di sviluppo</span><span class="sxs-lookup"><span data-stu-id="6b5df-125">Development Guide</span></span>](../development-guide.md)  
 <span data-ttu-id="6b5df-126">Viene fornita una guida per tutte le aree e attività principali per lo sviluppo di applicazioni, quali la creazione, la configurazione, il debug, la sicurezza e la distribuzione dell'applicazione e informazioni su programmazione dinamica, interoperabilità, estendibilità, gestione della memoria e threading.</span><span class="sxs-lookup"><span data-stu-id="6b5df-126">Provides a guide to all key technology areas and tasks for application development, including creating, configuring, debugging, securing, and deploying your application, and information about dynamic programming, interoperability, extensibility, memory management, and threading.</span></span>
