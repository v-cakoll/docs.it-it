---
title: Programmazione con i domini applicazione e gli assembly
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], programming
- programming assemblies
- application domains, programming
- programming application domains
ms.assetid: 96d3b8e3-bef8-4da0-9a81-9841e23a94e9
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 216766a8d8f120594c7d6dd1fd192f90b775c1d7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="programming-with-application-domains-and-assemblies"></a><span data-ttu-id="fd1b2-102">Programmazione con i domini applicazione e gli assembly</span><span class="sxs-lookup"><span data-stu-id="fd1b2-102">Programming with Application Domains and Assemblies</span></span>
<span data-ttu-id="fd1b2-103">Gli host come Microsoft Internet Explorer, ASP.NET e la shell di Windows caricano Common Language Runtime in un processo, creano un [dominio dell'applicazione](../../../docs/framework/app-domains/application-domains.md) in tale processo e quindi caricano ed eseguono codice dell'utente in tale dominio dell'applicazione quando eseguono un'applicazione .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fd1b2-103">Hosts such as Microsoft Internet Explorer, ASP.NET, and the Windows shell load the common language runtime into a process, create an [application domain](../../../docs/framework/app-domains/application-domains.md) in that process, and then load and execute user code in that application domain when running a .NET Framework application.</span></span> <span data-ttu-id="fd1b2-104">Nella maggior parte dei casi, non è necessario occuparsi della creazione dei domini dell'applicazione e del caricamento di assembly all'interno degli stessi, perché è l'host di runtime a eseguire tali attività.</span><span class="sxs-lookup"><span data-stu-id="fd1b2-104">In most cases, you do not have to worry about creating application domains and loading assemblies into them because the runtime host performs those tasks.</span></span>  
  
 <span data-ttu-id="fd1b2-105">Tuttavia, se si sta creando un'applicazione che ospita Common Language Runtime, strumenti o codice che si vogliono scaricare a livello di codice o componenti modulari che possono essere scaricati e ricaricati in tempo reale, si creano anche domini dell'applicazione personalizzati.</span><span class="sxs-lookup"><span data-stu-id="fd1b2-105">However, if you are creating an application that will host the common language runtime, creating tools or code you want to unload programmatically, or creating pluggable components that can be unloaded and reloaded on the fly, you will be creating your own application domains.</span></span> <span data-ttu-id="fd1b2-106">Anche se non si sta creando un host di runtime, questa sezione fornisce importanti informazioni su come utilizzare i domini dell'applicazione e gli assembly caricati al loro interno.</span><span class="sxs-lookup"><span data-stu-id="fd1b2-106">Even if you are not creating a runtime host, this section provides important information on how to work with application domains and assemblies loaded in these application domains.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fd1b2-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="fd1b2-107">In This Section</span></span>  
 [<span data-ttu-id="fd1b2-108">Argomenti relativi alle procedure per domini applicazione e assembly</span><span class="sxs-lookup"><span data-stu-id="fd1b2-108">Application Domains and Assemblies How-to Topics</span></span>](../../../docs/framework/app-domains/application-domains-and-assemblies-how-to-topics.md)  
 <span data-ttu-id="fd1b2-109">Fornisce i collegamenti a tutte le procedure contenute nella documentazione sui concetti relativi alla programmazione con domini dell'applicazione e assembly.</span><span class="sxs-lookup"><span data-stu-id="fd1b2-109">Provides links to all How-to topics found in the conceptual documentation for programming with application domains and assemblies.</span></span>  
  
 [<span data-ttu-id="fd1b2-110">Uso dei domini dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="fd1b2-110">Using Application Domains</span></span>](../../../docs/framework/app-domains/use.md)  
 <span data-ttu-id="fd1b2-111">Fornisce esempi di creazione, configurazione e uso dei domini dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fd1b2-111">Provides examples of creating, configuring, and using application domains.</span></span>  
  
 [<span data-ttu-id="fd1b2-112">Programmazione con gli assembly</span><span class="sxs-lookup"><span data-stu-id="fd1b2-112">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 <span data-ttu-id="fd1b2-113">Descrive come creare, firmare e impostare attributi sugli assembly.</span><span class="sxs-lookup"><span data-stu-id="fd1b2-113">Describes how to create, sign, and set attributes on assemblies.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="fd1b2-114">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="fd1b2-114">Related Sections</span></span>  
 [<span data-ttu-id="fd1b2-115">Creazione di assembly e metodi dinamici</span><span class="sxs-lookup"><span data-stu-id="fd1b2-115">Emitting Dynamic Methods and Assemblies</span></span>](../../../docs/framework/reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
 <span data-ttu-id="fd1b2-116">Descrive come creare gli assembly dinamici.</span><span class="sxs-lookup"><span data-stu-id="fd1b2-116">Describes how to create dynamic assemblies.</span></span>  
  
 [<span data-ttu-id="fd1b2-117">Assembly in Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="fd1b2-117">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 <span data-ttu-id="fd1b2-118">Viene fornita una panoramica sui concetti di base relativi agli assembly.</span><span class="sxs-lookup"><span data-stu-id="fd1b2-118">Provides a conceptual overview of assemblies.</span></span>  
  
 [<span data-ttu-id="fd1b2-119">Domini dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="fd1b2-119">Application Domains</span></span>](../../../docs/framework/app-domains/application-domains.md)  
 <span data-ttu-id="fd1b2-120">Viene fornita una panoramica sui concetti di base relativi ai domini applicazione.</span><span class="sxs-lookup"><span data-stu-id="fd1b2-120">Provides a conceptual overview of application domains.</span></span>  
  
 [<span data-ttu-id="fd1b2-121">Panoramica della reflection</span><span class="sxs-lookup"><span data-stu-id="fd1b2-121">Reflection Overview</span></span>](../../../docs/framework/reflection-and-codedom/reflection.md)  
 <span data-ttu-id="fd1b2-122">Descrive come usare la classe **Reflection** per ottenere informazioni su un assembly.</span><span class="sxs-lookup"><span data-stu-id="fd1b2-122">Describes how to use the **Reflection** class to obtain information about an assembly.</span></span>
