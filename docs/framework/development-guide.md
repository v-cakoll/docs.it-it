---
title: Guida di sviluppo per .NET Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET Framework, development guide
ms.assetid: 26e3d285-24c3-435c-a797-9fe5affb8525
caps.latest.revision: 13
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 7233827b9c331529cb70daf13aeb1308a053b1c1
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="net-framework-development-guide"></a><span data-ttu-id="a33ea-102">Guida di sviluppo per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a33ea-102">.NET Framework Development Guide</span></span>
<span data-ttu-id="a33ea-103">Questa sezione descrive come creare, configurare, sottoporre a debug, proteggere e distribuire app .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a33ea-103">This section explains how to create, configure, debug, secure, and deploy your .NET Framework apps.</span></span> <span data-ttu-id="a33ea-104">In questa sezione vengono fornite informazioni sulle aree tecnologiche, ad esempio programmazione dinamica, interoperabilità, estendibilità, gestione della memoria e threading.</span><span class="sxs-lookup"><span data-stu-id="a33ea-104">The section also provides information about technology areas such as dynamic programming, interoperability, extensibility, memory management, and threading.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a33ea-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="a33ea-105">In This Section</span></span>  
 [<span data-ttu-id="a33ea-106">Concetti di base sulle applicazioni</span><span class="sxs-lookup"><span data-stu-id="a33ea-106">Application Essentials</span></span>](../../docs/standard/application-essentials.md)  
 <span data-ttu-id="a33ea-107">Vengono fornite informazioni sulle attività per lo sviluppo di app di base, quali programmazione con assembly e domini applicazione, uso di attributi, formattazione e tipi di base di analisi, uso di raccolte, gestione di eventi ed eccezioni, uso di file, flussi di dati e generics.</span><span class="sxs-lookup"><span data-stu-id="a33ea-107">Provides information about basic app development tasks, such as programming with app domains and assemblies, using attributes, formatting and parsing base types, using collections, handling events and exceptions, using files and data streams, and using generics.</span></span>  
  
 [<span data-ttu-id="a33ea-108">Dati e modellazione</span><span class="sxs-lookup"><span data-stu-id="a33ea-108">Data and Modeling</span></span>](../../docs/framework/data/index.md)  
 <span data-ttu-id="a33ea-109">Vengono fornite informazioni su come accedere ai dati mediante ADO.NET, LINQ (Language Integrated Query), WCF Data Services e XML.</span><span class="sxs-lookup"><span data-stu-id="a33ea-109">Provides information about how to access data using ADO.NET, Language Integrated Query (LINQ), WCF Data Services, and XML.</span></span>  
  
 [<span data-ttu-id="a33ea-110">Applicazioni client</span><span class="sxs-lookup"><span data-stu-id="a33ea-110">Client Applications</span></span>](../../docs/framework/develop-client-apps.md)  
 <span data-ttu-id="a33ea-111">Viene illustrato come creare app basate su Windows usando Windows Presentation Foundation (WPF) o Windows Form.</span><span class="sxs-lookup"><span data-stu-id="a33ea-111">Explains how to create Windows-based apps by using Windows Presentation Foundation (WPF) or Windows Forms.</span></span>  
  
 [<span data-ttu-id="a33ea-112">Applicazioni Web con ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a33ea-112">Web Applications with ASP.NET</span></span>](../../docs/framework/develop-web-apps-with-aspnet.md)  
 <span data-ttu-id="a33ea-113">Vengono forniti collegamenti alle informazioni sull'utilizzo di ASP.NET per compilare applicazioni Web di livello aziendale con una codifica minima.</span><span class="sxs-lookup"><span data-stu-id="a33ea-113">Provides links to information about using ASP.NET to build enterprise-class web apps with a minimum of coding.</span></span>  
  
 [<span data-ttu-id="a33ea-114">Applicazioni orientate ai servizi con WCF</span><span class="sxs-lookup"><span data-stu-id="a33ea-114">Service-Oriented Applications with WCF</span></span>](../../docs/framework/wcf/index.md)  
 <span data-ttu-id="a33ea-115">Viene descritto come usare Windows Communication Foundation (WCF) per compilare app orientate ai servizi sicure e affidabili.</span><span class="sxs-lookup"><span data-stu-id="a33ea-115">Describes how to use Windows Communication Foundation (WCF) to build service-oriented apps that are secure and reliable.</span></span>  
  
 <span data-ttu-id="a33ea-116">[Flussi di lavoro di compilazione con Windows Workflow Foundation](windows-workflow-foundation/index.md)   </span><span class="sxs-lookup"><span data-stu-id="a33ea-116">[Building workflows with Windows Workflow Foundation](windows-workflow-foundation/index.md)   </span></span>  
 <span data-ttu-id="a33ea-117">Vengono fornite informazioni sul modello di programmazione, sugli esempi e sugli strumenti per Windows Workflow Foundation (WF).</span><span class="sxs-lookup"><span data-stu-id="a33ea-117">Provides information about the programming model, samples, and tools for using Windows Workflow Foundation (WF).</span></span>   

 [<span data-ttu-id="a33ea-118">Applicazioni dei servizi di Windows</span><span class="sxs-lookup"><span data-stu-id="a33ea-118">Windows Service Applications</span></span>](../../docs/framework/windows-services/index.md)  
 <span data-ttu-id="a33ea-119">Viene illustrato come usare Visual Studio e .NET Framework per creare un'app che viene installata come servizio e che avvia, arresta e diversamente controlla il proprio comportamento.</span><span class="sxs-lookup"><span data-stu-id="a33ea-119">Explains how you can use Visual Studio and the .NET Framework to create an app that is installed as a service, and start, stop, and otherwise control its behavior.</span></span>  
  
 [<span data-ttu-id="a33ea-120">Elaborazione parallela e concorrenza</span><span class="sxs-lookup"><span data-stu-id="a33ea-120">Parallel Processing and Concurrency</span></span>](../../docs/standard/parallel-processing-and-concurrency.md)  
 <span data-ttu-id="a33ea-121">Vengono fornite informazioni sul threading gestito, sulla programmazione parallela e sui modelli di progettazione della programmazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="a33ea-121">Provides information about managed threading, parallel programming, and asynchronous programming design patterns.</span></span>  
  
 [<span data-ttu-id="a33ea-122">Programmazione di rete in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a33ea-122">Network Programming in the .NET Framework</span></span>](../../docs/framework/network-programming/index.md)  
 <span data-ttu-id="a33ea-123">Viene descritta l'implementazione gestita, estendibile e a più livelli dei servizi Internet che è possibile integrare nelle app in modo rapido e semplice.</span><span class="sxs-lookup"><span data-stu-id="a33ea-123">Describes the layered, extensible, and managed implementation of Internet services that you can quickly and easily integrate into your apps.</span></span>  
  
 <span data-ttu-id="a33ea-124">[Configurazione di app .NET Framework](configure-apps/index.md)  </span><span class="sxs-lookup"><span data-stu-id="a33ea-124">[Configuring .NET Framework Apps](configure-apps/index.md)  </span></span>  
 <span data-ttu-id="a33ea-125">Viene illustrato come usare i file di configurazione per modificare le impostazioni senza dover ricompilare le app .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a33ea-125">Explains how you can use configuration files to change settings without having to recompile your .NET Framework apps.</span></span>  
  
 [<span data-ttu-id="a33ea-126">Compilazione di app con .NET Native</span><span class="sxs-lookup"><span data-stu-id="a33ea-126">Compiling Apps with .NET Native</span></span>](../../docs/framework/net-native/index.md)  
 <span data-ttu-id="a33ea-127">Viene illustrato come usare la tecnologia di precompilazione di [!INCLUDE[net_native](../../includes/net-native-md.md)] per compilare e implementare app di Windows Store.</span><span class="sxs-lookup"><span data-stu-id="a33ea-127">Explains how you can use the [!INCLUDE[net_native](../../includes/net-native-md.md)] precompilation technology to build and deploy Windows Store apps.</span></span> [!INCLUDE[net_native](../../includes/net-native-md.md)]<span data-ttu-id="a33ea-128"> compila le app scritte in codice gestito (C#) e destinate a .NET Framework in codice nativo.</span><span class="sxs-lookup"><span data-stu-id="a33ea-128"> compiles apps that are written in managed code (C#) and that target the .NET Framework to native code.</span></span>  
  
 [<span data-ttu-id="a33ea-129">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="a33ea-129">Security</span></span>](../../docs/standard/security/index.md)  
 <span data-ttu-id="a33ea-130">Vengono fornite informazioni sulle classi e sui servizi in .NET Framework che semplificano lo sviluppo di app sicure.</span><span class="sxs-lookup"><span data-stu-id="a33ea-130">Provides information about the classes and services in the .NET Framework that facilitate secure app development.</span></span>  
  
 [<span data-ttu-id="a33ea-131">Debug, analisi e profilatura</span><span class="sxs-lookup"><span data-stu-id="a33ea-131">Debugging, Tracing, and Profiling</span></span>](../../docs/framework/debug-trace-profile/index.md)  
 <span data-ttu-id="a33ea-132">Viene illustrato come eseguire test, ottimizzare e profilare le app .NET Framework e l'ambiente dell'app.</span><span class="sxs-lookup"><span data-stu-id="a33ea-132">Explains how to test, optimize, and profile .NET Framework apps and the app environment.</span></span> <span data-ttu-id="a33ea-133">Questa sezione include informazioni per amministratori e sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="a33ea-133">This section includes information for administrators as well as developers.</span></span>  
  
 [<span data-ttu-id="a33ea-134">Sviluppo per piattaforme multiple</span><span class="sxs-lookup"><span data-stu-id="a33ea-134">Developing for Multiple Platforms</span></span>](../../docs/standard/cross-platform/index.md)  
 <span data-ttu-id="a33ea-135">Viene illustrato come usare NET Framework per compilare assembly che possono essere condivisi tra più piattaforme e dispositivi, ad esempio telefoni, computer desktop e dispositivi Web.</span><span class="sxs-lookup"><span data-stu-id="a33ea-135">Provides information about how you can use the .NET Framework to build assemblies that can be shared across multiple platforms and multiple devices such as phones, desktop, and web.</span></span>  
  
 [<span data-ttu-id="a33ea-136">Distribuzione</span><span class="sxs-lookup"><span data-stu-id="a33ea-136">Deployment</span></span>](../../docs/framework/deployment/index.md)  
 <span data-ttu-id="a33ea-137">Viene illustrato come assemblare e distribuire l'app .NET Framework e sono incluse guide di distribuzione sia per sviluppatori che per amministratori.</span><span class="sxs-lookup"><span data-stu-id="a33ea-137">Explains how to package and distribute your .NET Framework app, and includes deployment guides for both developers and administrators.</span></span>  
  
 [<span data-ttu-id="a33ea-138">Prestazioni</span><span class="sxs-lookup"><span data-stu-id="a33ea-138">Performance</span></span>](../../docs/framework/performance/index.md)  
 <span data-ttu-id="a33ea-139">Vengono fornite informazioni sulla memorizzazione nella cache, l'inizializzazione differita, l'affidabilità e gli eventi ETW.</span><span class="sxs-lookup"><span data-stu-id="a33ea-139">Provides information about caching, lazy initialization, reliability, and ETW events.</span></span>  
  
 <!--zz [Advanced Reading for the .NET Framework](http://msdn.microsoft.com/en-us/faae8083-fecb-4514-b133-b0a5a32a7c3c)  
 Provides information about advanced development tasks and techniques in the .NET Framework, including extensibility, interoperability, and reflection. Also includes the reference topics for unmanaged APIs that can be used by managed apps, such as runtime hosts, compilers, disassemblers, debuggers, and profilers.  --> 
  
## <a name="reference"></a><span data-ttu-id="a33ea-140">Riferimento</span><span class="sxs-lookup"><span data-stu-id="a33ea-140">Reference</span></span>  
 [<span data-ttu-id="a33ea-141">Libreria di classi .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a33ea-141">.NET Framework Class Library</span></span>](/dotnet/api/?view=netframework-4.7)  
 <span data-ttu-id="a33ea-142">Vengono forniti sintassi, esempi di codice e informazioni sull'utilizzo per ogni classe contenuta negli spazi dei nomi di [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a33ea-142">Supplies syntax, code examples, and usage information for each class that is contained in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] namespaces.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a33ea-143">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="a33ea-143">Related Sections</span></span>  
 [<span data-ttu-id="a33ea-144">Introduzione</span><span class="sxs-lookup"><span data-stu-id="a33ea-144">Getting Started</span></span>](../../docs/framework/get-started/index.md)  
 <span data-ttu-id="a33ea-145">Offre una panoramica completa di .NET Framework, oltre ai collegamenti a risorse aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="a33ea-145">Provides a comprehensive overview of the .NET Framework and links to additional resources.</span></span>  
  
 [<span data-ttu-id="a33ea-146">Novità</span><span class="sxs-lookup"><span data-stu-id="a33ea-146">What's New</span></span>](../../docs/framework/whats-new/index.md)  
 <span data-ttu-id="a33ea-147">Vengono descritte le nuove funzionalità e le modifiche principali incluse nella versione più recente di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a33ea-147">Describes key new features and changes in the latest version of the .NET Framework.</span></span> <span data-ttu-id="a33ea-148">Sono inclusi gli elenchi di tipi e membri nuovi e obsoleti e viene fornita una guida per eseguire la migrazione delle app dalla versione precedente di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a33ea-148">Includes lists of new and obsolete types and members, and provides a guide for migrating your apps from the previous version of the .NET Framework.</span></span>  
  
 [<span data-ttu-id="a33ea-149">Strumenti</span><span class="sxs-lookup"><span data-stu-id="a33ea-149">Tools</span></span>](../../docs/framework/tools/index.md)  
 <span data-ttu-id="a33ea-150">Vengono descritti gli strumenti che consentono di sviluppare, configurare e distribuire app tramite le tecnologie .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a33ea-150">Describes the tools that help you develop, configure, and deploy apps by using .NET Framework technologies.</span></span>  
  
 [<span data-ttu-id="a33ea-151">Esempi di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a33ea-151">.NET Framework Samples</span></span>](http://msdn.microsoft.com/en-us/177055f8-4a1f-43e7-aee6-995c196079b1)  
 <span data-ttu-id="a33ea-152">Vengono forniti collegamenti alla raccolta di esempi di codice di MSDN per app di esempio che illustrano le tecnologie .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a33ea-152">Provides links to the MSDN Code Samples Gallery for sample apps that demonstrate .NET Framework technologies.</span></span>

