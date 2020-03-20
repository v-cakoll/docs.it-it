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
ms.openlocfilehash: d94d97cd1b519025ff360dc903558ea3656818d5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79181528"
---
# <a name="net-framework-guide"></a><span data-ttu-id="cf685-102">Guida a .NET Framework</span><span class="sxs-lookup"><span data-stu-id="cf685-102">.NET Framework guide</span></span>

> [!NOTE]
> <span data-ttu-id="cf685-103">Questo set di contenuti .NET Framework include informazioni per le versioni di .NET Framework da 4.5 a 4.8.</span><span class="sxs-lookup"><span data-stu-id="cf685-103">This .NET Framework content set includes information for .NET Framework versions 4.5 through 4.8.</span></span> <span data-ttu-id="cf685-104">Per scaricare .NET Framework, vedere [Installare .NET Framework.](./install/guide-for-developers.md)</span><span class="sxs-lookup"><span data-stu-id="cf685-104">To download .NET Framework, see [Install .NET Framework](./install/guide-for-developers.md).</span></span> <span data-ttu-id="cf685-105">Per un elenco delle nuove funzionalità e modifiche in .NET Framework, vedere Novità di [.NET Framework](./whats-new/index.md).</span><span class="sxs-lookup"><span data-stu-id="cf685-105">For a list of new features and changes in .NET Framework, see [What's New in .NET Framework](./whats-new/index.md).</span></span> <span data-ttu-id="cf685-106">Per un elenco delle piattaforme supportate, vedere [Requisiti di sistema di .NET Framework](./get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf685-106">For a list of supported platforms, see [.NET Framework System Requirements](./get-started/system-requirements.md).</span></span> <span data-ttu-id="cf685-107">Per la documentazione relativa alle versioni precedenti di .NET Framework, vedere la documentazione relativa alle versioni precedenti di [.NET.](https://docs.microsoft.com/previous-versions/dotnet/)</span><span class="sxs-lookup"><span data-stu-id="cf685-107">For documentation about older versions of .NET Framework, see [.NET previous versions documentation](https://docs.microsoft.com/previous-versions/dotnet/).</span></span>

<span data-ttu-id="cf685-108">.NET Framework è una piattaforma di sviluppo per la creazione di app per Web, Windows, Windows Server e Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="cf685-108">.NET Framework is a development platform for building apps for web, Windows, Windows Server, and Microsoft Azure.</span></span> <span data-ttu-id="cf685-109">Consiste del Common Language Runtime (CLR) e della libreria di classi .NET Framework, che include un'ampia gamma di funzionalità e supporto per numerosi standard di settore.</span><span class="sxs-lookup"><span data-stu-id="cf685-109">It consists of the common language runtime (CLR) and the .NET Framework class library, which includes a broad range of functionality and support for many industry standards.</span></span>

<span data-ttu-id="cf685-110">.NET Framework fornisce molti servizi, tra cui la gestione della memoria, la sicurezza dei tipi e della memoria, la sicurezza, la rete e la distribuzione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="cf685-110">.NET Framework provides many services, including memory management, type and memory safety, security, networking, and application deployment.</span></span> <span data-ttu-id="cf685-111">Offre anche strutture dati e API semplici che non usano il sistema operativo Windows ai livelli inferiori.</span><span class="sxs-lookup"><span data-stu-id="cf685-111">It provides easy-to-use data structures and APIs that abstract the lower-level Windows operating system.</span></span> <span data-ttu-id="cf685-112">Con .NET Framework è possibile utilizzare linguaggi di programmazione diversi, tra cui C, F e Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="cf685-112">You can use different programming languages with .NET Framework, including C#, F#, and Visual Basic.</span></span>

<span data-ttu-id="cf685-113">Per un'introduzione generale a .NET Framework sia per gli utenti che per gli sviluppatori, vedere [Guida introduttiva.](./get-started/index.md)</span><span class="sxs-lookup"><span data-stu-id="cf685-113">For a general introduction to .NET Framework for both users and developers, see [Getting Started](./get-started/index.md).</span></span> <span data-ttu-id="cf685-114">Per un'introduzione all'architettura e alle funzionalità principali di .NET Framework, vedere i [cenni preliminari](./get-started/overview.md).</span><span class="sxs-lookup"><span data-stu-id="cf685-114">For an introduction to the architecture and key features of .NET Framework, see the [overview](./get-started/overview.md).</span></span>

<span data-ttu-id="cf685-115">.NET Framework può essere utilizzato con Docker e con [i contenitori](/virtualization/windowscontainers/about/)di Windows .</span><span class="sxs-lookup"><span data-stu-id="cf685-115">.NET Framework can be used with Docker and with [Windows Containers](/virtualization/windowscontainers/about/).</span></span>

## <a name="installation"></a><span data-ttu-id="cf685-116">Installazione</span><span class="sxs-lookup"><span data-stu-id="cf685-116">Installation</span></span>

<span data-ttu-id="cf685-117">.NET Framework viene fornito con Windows, che consente di eseguire applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cf685-117">.NET Framework comes with Windows, which enables you to run .NET Framework applications.</span></span> <span data-ttu-id="cf685-118">Potrebbe essere necessaria una versione successiva di .NET Framework rispetto a quella fornita con la versione di Windows.</span><span class="sxs-lookup"><span data-stu-id="cf685-118">You may need a later version of .NET Framework than the one that comes with your Windows version.</span></span> <span data-ttu-id="cf685-119">Per ulteriori informazioni, vedere [Installare .NET Framework in Windows.](./install/index.md)</span><span class="sxs-lookup"><span data-stu-id="cf685-119">For more information, see [Install .NET Framework on Windows](./install/index.md).</span></span>

<span data-ttu-id="cf685-120">Per informazioni su come ripristinare l'installazione di .NET Framework se si verificano errori durante l'installazione, vedere [Ripristinare .NET Framework](./install/repair.md).</span><span class="sxs-lookup"><span data-stu-id="cf685-120">To learn how to repair your .NET Framework installation if you're experiencing errors during installation, see [Repair .NET Framework](./install/repair.md).</span></span>

<span data-ttu-id="cf685-121">Per informazioni più dettagliate sul download di .NET Framework, vedere [Installare .NET Framework per gli sviluppatori.](./install/guide-for-developers.md)</span><span class="sxs-lookup"><span data-stu-id="cf685-121">For more detailed information on downloading .NET Framework, see [Install the .NET Framework for developers](./install/guide-for-developers.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="cf685-122">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="cf685-122">In this section</span></span>

* [<span data-ttu-id="cf685-123">Novità</span><span class="sxs-lookup"><span data-stu-id="cf685-123">What's New</span></span>](./whats-new/index.md)  
<span data-ttu-id="cf685-124">Vengono descritte le nuove funzionalità e le modifiche principali incluse nelle versioni più recenti di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cf685-124">Describes key new features and changes in the latest versions of the .NET Framework.</span></span> <span data-ttu-id="cf685-125">Sono inclusi elenchi di tipi e membri obsoleti e viene fornita una guida per eseguire la migrazione delle applicazioni dalla versione precedente di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cf685-125">Includes lists of obsolete types and members, and provides a guide for migrating your applications from the previous version of the .NET Framework.</span></span>

* [<span data-ttu-id="cf685-126">Guida introduttiva</span><span class="sxs-lookup"><span data-stu-id="cf685-126">Get Started</span></span>](./get-started/index.md)  
<span data-ttu-id="cf685-127">Offre una panoramica completa di .NET Framework, oltre ai collegamenti a risorse aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="cf685-127">Provides a comprehensive overview of the .NET Framework and links to additional resources.</span></span>

* [<span data-ttu-id="cf685-128">Guida all'installazione</span><span class="sxs-lookup"><span data-stu-id="cf685-128">Installation Guide</span></span>](./install/index.md)  
<span data-ttu-id="cf685-129">Fornisce risorse e indicazioni sull'installazione di .NET Framework e la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="cf685-129">Provides resources and guidance about .NET Framework installation and troubleshooting.</span></span>

* [<span data-ttu-id="cf685-130">Guida alla migrazione</span><span class="sxs-lookup"><span data-stu-id="cf685-130">Migration Guide</span></span>](./migration-guide/index.md)  
<span data-ttu-id="cf685-131">Fornisce risorse e un elenco di modifiche che è necessario considerare se si sta migrando l'applicazione a una nuova versione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cf685-131">Provides resources and a list of changes you need to consider if you're migrating your application to a new version of the .NET Framework.</span></span>

* [<span data-ttu-id="cf685-132">Guida di sviluppo</span><span class="sxs-lookup"><span data-stu-id="cf685-132">Development Guide</span></span>](./development-guide.md)  
<span data-ttu-id="cf685-133">Viene fornita una guida per tutte le aree e attività principali per lo sviluppo di applicazioni, quali la creazione, la configurazione, il debug, la sicurezza e la distribuzione dell'applicazione e informazioni su programmazione dinamica, interoperabilità, estendibilità, gestione della memoria e threading.</span><span class="sxs-lookup"><span data-stu-id="cf685-133">Provides a guide to all key technology areas and tasks for application development, including creating, configuring, debugging, securing, and deploying your application, and information about dynamic programming, interoperability, extensibility, memory management, and threading.</span></span>

* [<span data-ttu-id="cf685-134">Strumenti</span><span class="sxs-lookup"><span data-stu-id="cf685-134">Tools</span></span>](./tools/index.md)  
<span data-ttu-id="cf685-135">Vengono descritti gli strumenti che consentono di sviluppare, configurare e distribuire applicazioni tramite le tecnologie .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cf685-135">Describes the tools that help you develop, configure, and deploy applications by using .NET Framework technologies.</span></span>

* [<span data-ttu-id="cf685-136">Librerie di classi e API aggiuntive</span><span class="sxs-lookup"><span data-stu-id="cf685-136">Additional class libraries and APIs</span></span>](./additional-apis/index.md)  
<span data-ttu-id="cf685-137">Fornisce la documentazione per le API di .NET Framework private usate dagli strumenti di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cf685-137">Provides documentation for private .NET Framework APIs used by Microsoft tools.</span></span>

## <a name="see-also"></a><span data-ttu-id="cf685-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf685-138">See also</span></span>

* [<span data-ttu-id="cf685-139">Libreria di classi .NET Framework</span><span class="sxs-lookup"><span data-stu-id="cf685-139">.NET Framework Class Library</span></span>](/dotnet/api/?view=netframework-4.8)
