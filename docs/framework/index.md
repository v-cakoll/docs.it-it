---
title: Documentazione su .NET Framework
ms.date: 04/02/2019
ms.custom: updateeachrelease
f1_keywords:
- f61f02f2-2f20-483d-8f56-a9c8f3a54986
helpviewer_keywords:
- .NET Framework, documentation
- documentation, .NET Framework
ms.assetid: f61f02f2-2f20-483d-8f56-a9c8f3a54986
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e5a86b3abf821a37944a0e478d0bc8f1bea31ccb
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699049"
---
# <a name="net-framework-guide"></a><span data-ttu-id="63b15-102">Guida a .NET Framework</span><span class="sxs-lookup"><span data-stu-id="63b15-102">.NET Framework Guide</span></span>

> [!NOTE]
> <span data-ttu-id="63b15-103">Questo set di contenuti .NET Framework include informazioni per le versioni di .NET Framework da 4.5 a 4.8.</span><span class="sxs-lookup"><span data-stu-id="63b15-103">This .NET Framework content set includes information for .NET Framework versions 4.5 through 4.8.</span></span> <span data-ttu-id="63b15-104">Per scaricare .NET Framework, vedere [Installazione di .NET Framework](./install/guide-for-developers.md).</span><span class="sxs-lookup"><span data-stu-id="63b15-104">To download the .NET Framework, see [Installing the .NET Framework](./install/guide-for-developers.md).</span></span> <span data-ttu-id="63b15-105">Per un elenco delle nuove funzionalità e delle modifiche in .NET Framework, vedere [Novità di .NET Framework](./whats-new/index.md).</span><span class="sxs-lookup"><span data-stu-id="63b15-105">For a list of new features and changes in the NET Framework, see [What's New in the .NET Framework](./whats-new/index.md).</span></span> <span data-ttu-id="63b15-106">Per un elenco delle piattaforme supportate, vedere [Requisiti di sistema di .NET Framework](./get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63b15-106">For a list of supported platforms, see [.NET Framework System Requirements](./get-started/system-requirements.md).</span></span> <span data-ttu-id="63b15-107">Per la documentazione sulle versioni precedenti di .NET Framework, vedere [Documentazione sulle versioni precedenti di .NET](https://docs.microsoft.com/previous-versions/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="63b15-107">For documentation about older versions of the .NET Framework, see [.NET previous versions documentation](https://docs.microsoft.com/previous-versions/dotnet/).</span></span>

<span data-ttu-id="63b15-108">.NET Framework è una piattaforma di sviluppo per compilare app Web e app per Windows, Windows Phone, Windows Server e Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="63b15-108">The .NET Framework is a development platform for building apps for web, Windows, Windows Phone, Windows Server, and Microsoft Azure.</span></span> <span data-ttu-id="63b15-109">Consiste del Common Language Runtime (CLR) e della libreria di classi .NET Framework, che include un'ampia gamma di funzionalità e supporto per numerosi standard di settore.</span><span class="sxs-lookup"><span data-stu-id="63b15-109">It consists of the common language runtime (CLR) and the .NET Framework class library, which includes a broad range of functionality and support for many industry standards.</span></span>

<span data-ttu-id="63b15-110">.NET Framework offre numerosi servizi, ad esempio gestione della memoria, sicurezza della memoria e del tipo, sicurezza, connessioni di reti e distribuzione di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="63b15-110">The .NET Framework provides many services, including memory management, type and memory safety, security, networking, and application deployment.</span></span> <span data-ttu-id="63b15-111">Offre anche strutture dati e API semplici che non usano il sistema operativo Windows ai livelli inferiori.</span><span class="sxs-lookup"><span data-stu-id="63b15-111">It provides easy-to-use data structures and APIs that abstract the lower-level Windows operating system.</span></span> <span data-ttu-id="63b15-112">È possibile usare vari linguaggi di programmazione con .NET Framework, ad esempio C#, F# e Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="63b15-112">You can use different programming languages with the .NET Framework, including C#, F#, and Visual Basic.</span></span>

<span data-ttu-id="63b15-113">Per un'introduzione generale a .NET Framework per utenti e sviluppatori, vedere [Introduzione](./get-started/index.md).</span><span class="sxs-lookup"><span data-stu-id="63b15-113">For a general introduction to the .NET Framework for both users and developers, see [Getting Started](./get-started/index.md).</span></span> <span data-ttu-id="63b15-114">Per un'introduzione all'architettura e alle principali funzionalità di .NET Framework, vedere la [panoramica](./get-started/overview.md).</span><span class="sxs-lookup"><span data-stu-id="63b15-114">For an introduction to the architecture and key features of the .NET Framework, see the [overview](./get-started/overview.md).</span></span>

<span data-ttu-id="63b15-115">.NET Framework può essere usato con Docker e con i [contenitori Windows](/virtualization/windowscontainers/about/).</span><span class="sxs-lookup"><span data-stu-id="63b15-115">The .NET Framework can be used with Docker and with [Windows Containers](/virtualization/windowscontainers/about/).</span></span>

## <a name="installation"></a><span data-ttu-id="63b15-116">Installazione</span><span class="sxs-lookup"><span data-stu-id="63b15-116">Installation</span></span>

<span data-ttu-id="63b15-117">.NET Framework è incluso in Windows e consente di eseguire applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="63b15-117">The .NET Framework comes with Windows, enabling you to run .NET Framework applications.</span></span> <span data-ttu-id="63b15-118">Potrebbe essere necessario usare una versione di .NET Framework successiva a quella inclusa nella versione di Windows installata.</span><span class="sxs-lookup"><span data-stu-id="63b15-118">You may need a later version of the .NET Framework than the one that comes with your Windows version.</span></span> <span data-ttu-id="63b15-119">Per altre informazioni, vedere [Installazione di .NET Framework in Windows](./install/index.md).</span><span class="sxs-lookup"><span data-stu-id="63b15-119">For more information, see [Install the .NET Framework on Windows](./install/index.md).</span></span>

<span data-ttu-id="63b15-120">Vedere [Ripristinare .NET Framework](./install/repair.md) per informazioni su come ripristinare l'installazione se si verificano errori durante l'installazione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="63b15-120">See [Repair the .NET Framework](./install/repair.md) to learn how to repair your .NET Framework installation if you're experiencing errors when installing the .NET Framework.</span></span>

<span data-ttu-id="63b15-121">Per informazioni più dettagliate sul download di .NET Framework, vedere [Install the .NET Framework for developers](./install/guide-for-developers.md) (Installare .NET Framework per sviluppatori).</span><span class="sxs-lookup"><span data-stu-id="63b15-121">For more detailed information on downloading the .NET Framework, see [Install the .NET Framework for developers](./install/guide-for-developers.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="63b15-122">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="63b15-122">In this section</span></span>

* [<span data-ttu-id="63b15-123">Novità</span><span class="sxs-lookup"><span data-stu-id="63b15-123">What's New</span></span>](./whats-new/index.md)  
<span data-ttu-id="63b15-124">Vengono descritte le nuove funzionalità e le modifiche principali incluse nelle versioni più recenti di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="63b15-124">Describes key new features and changes in the latest versions of the .NET Framework.</span></span> <span data-ttu-id="63b15-125">Sono inclusi elenchi di tipi e membri obsoleti e viene fornita una guida per eseguire la migrazione delle applicazioni dalla versione precedente di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="63b15-125">Includes lists of obsolete types and members, and provides a guide for migrating your applications from the previous version of the .NET Framework.</span></span>

* [<span data-ttu-id="63b15-126">Introduzione</span><span class="sxs-lookup"><span data-stu-id="63b15-126">Get Started</span></span>](./get-started/index.md)  
<span data-ttu-id="63b15-127">Offre una panoramica completa di .NET Framework, oltre ai collegamenti a risorse aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="63b15-127">Provides a comprehensive overview of the .NET Framework and links to additional resources.</span></span>

* [<span data-ttu-id="63b15-128">Guida all'installazione</span><span class="sxs-lookup"><span data-stu-id="63b15-128">Installation Guide</span></span>](./install/index.md)  
<span data-ttu-id="63b15-129">Fornisce risorse e indicazioni sull'installazione di .NET Framework e la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="63b15-129">Provides resources and guidance about .NET Framework installation and troubleshooting.</span></span>

* [<span data-ttu-id="63b15-130">Guida alla migrazione</span><span class="sxs-lookup"><span data-stu-id="63b15-130">Migration Guide</span></span>](./migration-guide/index.md)  
<span data-ttu-id="63b15-131">Fornisce risorse e un elenco di modifiche che è necessario considerare se si sta migrando l'applicazione a una nuova versione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="63b15-131">Provides resources and a list of changes you need to consider if you're migrating your application to a new version of the .NET Framework.</span></span>

* [<span data-ttu-id="63b15-132">Guida di sviluppo</span><span class="sxs-lookup"><span data-stu-id="63b15-132">Development Guide</span></span>](./development-guide.md)  
<span data-ttu-id="63b15-133">Viene fornita una guida per tutte le aree e attività principali per lo sviluppo di applicazioni, quali la creazione, la configurazione, il debug, la sicurezza e la distribuzione dell'applicazione e informazioni su programmazione dinamica, interoperabilità, estendibilità, gestione della memoria e threading.</span><span class="sxs-lookup"><span data-stu-id="63b15-133">Provides a guide to all key technology areas and tasks for application development, including creating, configuring, debugging, securing, and deploying your application, and information about dynamic programming, interoperability, extensibility, memory management, and threading.</span></span>

* [<span data-ttu-id="63b15-134">Strumenti</span><span class="sxs-lookup"><span data-stu-id="63b15-134">Tools</span></span>](./tools/index.md)  
<span data-ttu-id="63b15-135">Vengono descritti gli strumenti che consentono di sviluppare, configurare e distribuire applicazioni tramite le tecnologie .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="63b15-135">Describes the tools that help you develop, configure, and deploy applications by using .NET Framework technologies.</span></span>

* [<span data-ttu-id="63b15-136">Librerie di classi e API aggiuntive</span><span class="sxs-lookup"><span data-stu-id="63b15-136">Additional class libraries and APIs</span></span>](./additional-apis/index.md)  
<span data-ttu-id="63b15-137">Fornisce la documentazione per le API di .NET Framework private usate dagli strumenti di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="63b15-137">Provides documentation for private .NET Framework APIs used by Microsoft tools.</span></span>

## <a name="see-also"></a><span data-ttu-id="63b15-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63b15-138">See also</span></span>

- [<span data-ttu-id="63b15-139">Libreria di classi .NET Framework</span><span class="sxs-lookup"><span data-stu-id="63b15-139">.NET Framework Class Library</span></span>](/dotnet/api/?view=netframework-4.8)
