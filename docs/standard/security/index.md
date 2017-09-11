---
title: Sicurezza in .NET Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- .NET Framework, security
- security [.NET Framework], about security
- application development [.NET Framework], security
- security [.NET Framework]
ms.assetid: 9a9621d7-8883-4a4f-a874-65e8e09e20a6
caps.latest.revision: 37
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b2c487c76a6a0b42370b7b70099d5baba58f42db
ms.contentlocale: it-it
ms.lasthandoff: 09/05/2017

---
# <a name="security-in-the-net-framework"></a><span data-ttu-id="c9c10-102">Sicurezza in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c9c10-102">Security in the .NET Framework</span></span>
<span data-ttu-id="c9c10-103">Common Language Runtime e .NET Framework forniscono numerosi servizi e classi utili che consentono agli sviluppatori di scrivere in modo semplice codice sicuro e consentono agli amministratori di sistema di personalizzare le autorizzazioni concesse al codice per l'accesso alle risorse protette.</span><span class="sxs-lookup"><span data-stu-id="c9c10-103">The common language runtime and the .NET Framework provide many useful classes and services that enable developers to easily write secure code and enable system administrators to customize the permissions granted to code so that it can access protected resources.</span></span> <span data-ttu-id="c9c10-104">In Common Language Runtime e .NET Framework sono inoltre disponibili servizi e classi che semplificano l'uso della crittografia e della protezione basata sui ruoli.</span><span class="sxs-lookup"><span data-stu-id="c9c10-104">In addition, the runtime and the .NET Framework provide useful classes and services that facilitate the use of cryptography and role-based security.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c9c10-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="c9c10-105">In This Section</span></span>  
 [<span data-ttu-id="c9c10-106">Modifiche della sicurezza</span><span class="sxs-lookup"><span data-stu-id="c9c10-106">Security Changes</span></span>](../../../docs/framework/security/security-changes.md)  
 <span data-ttu-id="c9c10-107">Descrive importanti modifiche al sistema di sicurezza di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c9c10-107">Describes important changes to the .NET Framework security system.</span></span>  
  
 [<span data-ttu-id="c9c10-108">Concetti chiave sulla sicurezza</span><span class="sxs-lookup"><span data-stu-id="c9c10-108">Key Security Concepts</span></span>](../../../docs/standard/security/key-security-concepts.md)  
 <span data-ttu-id="c9c10-109">Fornisce una panoramica sulle funzionalità di protezione di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="c9c10-109">Provides an overview of common language runtime security features.</span></span> <span data-ttu-id="c9c10-110">Questa sezione è di particolare interesse per gli sviluppatori e gli amministratori di sistema.</span><span class="sxs-lookup"><span data-stu-id="c9c10-110">This section is of interest to developers and system administrators.</span></span>  
  
 [<span data-ttu-id="c9c10-111">Sicurezza basata sui ruoli</span><span class="sxs-lookup"><span data-stu-id="c9c10-111">Role-Based Security</span></span>](../../../docs/standard/security/role-based-security.md)  
 <span data-ttu-id="c9c10-112">Illustra come scrivere codice tenendo conto della protezione basata sui ruoli.</span><span class="sxs-lookup"><span data-stu-id="c9c10-112">Describes how to interact with role-based security in your code.</span></span> <span data-ttu-id="c9c10-113">Questa sezione è di particolare interesse per gli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="c9c10-113">This section is of interest to developers.</span></span>  
  
 [<span data-ttu-id="c9c10-114">Modello di crittografia</span><span class="sxs-lookup"><span data-stu-id="c9c10-114">Cryptography Model</span></span>](../../../docs/standard/security/cryptography-model.md)  
 <span data-ttu-id="c9c10-115">Fornisce una panoramica sui servizi di crittografia forniti da .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c9c10-115">Provides an overview of cryptographic services provided by the .NET Framework.</span></span> <span data-ttu-id="c9c10-116">Questa sezione è di particolare interesse per gli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="c9c10-116">This section is of interest to developers.</span></span>  
  
 [<span data-ttu-id="c9c10-117">Linee guida per la generazione di codice sicuro</span><span class="sxs-lookup"><span data-stu-id="c9c10-117">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)  
 <span data-ttu-id="c9c10-118">Descrive alcune delle procedure consigliate per la creazione di applicazioni .NET Framework affidabili.</span><span class="sxs-lookup"><span data-stu-id="c9c10-118">Describes some of the best practices for creating reliable .NET Framework applications.</span></span> <span data-ttu-id="c9c10-119">Questa sezione è di particolare interesse per gli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="c9c10-119">This section is of interest to developers.</span></span>  
  
 [<span data-ttu-id="c9c10-120">Linee guida per la creazione di codice sicuro applicabili al codice non gestito</span><span class="sxs-lookup"><span data-stu-id="c9c10-120">Secure Coding Guidelines for Unmanaged Code</span></span>](../../../docs/framework/security/secure-coding-guidelines-for-unmanaged-code.md)  
 <span data-ttu-id="c9c10-121">Descrive alcune procedure consigliate e alcuni problemi di sicurezza in relazione alle chiamate di codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="c9c10-121">Describes some of the best practices and security concerns when calling unmanaged code.</span></span>  
  
 [<span data-ttu-id="c9c10-122">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="c9c10-122">Windows Identity Foundation</span></span>](../../../docs/framework/security/index.md)  
 <span data-ttu-id="c9c10-123">Descrive come è possibile implementare l'identità basata sulle richieste nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="c9c10-123">Describes how you can implement claims-based identity in your applications.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c9c10-124">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="c9c10-124">Related Sections</span></span>  
 [<span data-ttu-id="c9c10-125">Guida di sviluppo</span><span class="sxs-lookup"><span data-stu-id="c9c10-125">Development Guide</span></span>](../../../docs/framework/development-guide.md)  
 <span data-ttu-id="c9c10-126">Viene fornita una guida per tutte le aree e attività principali per lo sviluppo di applicazioni, quali la creazione, la configurazione, il debug, la sicurezza e la distribuzione dell'applicazione e informazioni su programmazione dinamica, interoperabilità, estendibilità, gestione della memoria e threading.</span><span class="sxs-lookup"><span data-stu-id="c9c10-126">Provides a guide to all key technology areas and tasks for application development, including creating, configuring, debugging, securing, and deploying your application, and information about dynamic programming, interoperability, extensibility, memory management, and threading.</span></span>

