---
title: Uso dei domini dell'applicazione
description: Usare i domini applicazione, che forniscono un'unità di isolamento per il Common Language Runtime (CLR). I domini applicazione vengono creati ed eseguiti all'interno di un processo.
ms.date: 03/30/2017
helpviewer_keywords:
- application domains, about
- common language runtime, application domains
- runtime, application domains
ms.assetid: c6d99815-e022-4d2c-9420-1d7ab5b9d504
ms.openlocfilehash: df2a63716904ebfc6ee163121a1f07e53aa07514
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "85105186"
---
# <a name="using-application-domains"></a><span data-ttu-id="0f04e-104">Uso dei domini dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="0f04e-104">Using Application Domains</span></span>

<span data-ttu-id="0f04e-105">I domini dell'applicazione offrono un'unità di isolamento per Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="0f04e-105">Application domains provide a unit of isolation for the common language runtime.</span></span> <span data-ttu-id="0f04e-106">Vengono creati ed eseguiti all'interno di un processo.</span><span class="sxs-lookup"><span data-stu-id="0f04e-106">They are created and run inside a process.</span></span> <span data-ttu-id="0f04e-107">I domini dell'applicazione vengono solitamente creati da un host di runtime, che è un'applicazione responsabile del caricamento del runtime in un processo e dell'esecuzione di codice utente all'interno di un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0f04e-107">Application domains are usually created by a runtime host, which is an application responsible for loading the runtime into a process and executing user code within an application domain.</span></span> <span data-ttu-id="0f04e-108">L'host di runtime crea un processo e un dominio dell'applicazione predefinito ed esegue codice gestito all'interno di esso.</span><span class="sxs-lookup"><span data-stu-id="0f04e-108">The runtime host creates a process and a default application domain, and runs managed code inside it.</span></span> <span data-ttu-id="0f04e-109">Gli host di runtime includono ASP.NET, Microsoft Internet Explorer e la shell di Windows.</span><span class="sxs-lookup"><span data-stu-id="0f04e-109">Runtime hosts include ASP.NET, Microsoft Internet Explorer, and the Windows shell.</span></span>  
  
<span data-ttu-id="0f04e-110">Per la maggior parte delle applicazioni, non è necessario creare il proprio dominio dell'applicazione. L'host di runtime crea tutti i domini dell'applicazione necessari.</span><span class="sxs-lookup"><span data-stu-id="0f04e-110">For most applications, you do not need to create your own application domain; the runtime host creates any necessary application domains for you.</span></span> <span data-ttu-id="0f04e-111">È tuttavia possibile creare e configurare domini dell'applicazione aggiuntivi se l'applicazione necessita di isolare il codice o di usare e scaricare DLL.</span><span class="sxs-lookup"><span data-stu-id="0f04e-111">However, you can create and configure additional application domains if your application needs to isolate code or to use and unload DLLs.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0f04e-112">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="0f04e-112">In This Section</span></span>  

[<span data-ttu-id="0f04e-113">Procedura: Creare un dominio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="0f04e-113">How to: Create an Application Domain</span></span>](how-to-create-an-application-domain.md)  
<span data-ttu-id="0f04e-114">Viene descritto come creare a livello di codice un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0f04e-114">Describes how to programmatically create an application domain.</span></span>  
  
[<span data-ttu-id="0f04e-115">Procedura: Scaricare un dominio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="0f04e-115">How to: Unload an Application Domain</span></span>](how-to-unload-an-application-domain.md)  
<span data-ttu-id="0f04e-116">Viene descritto come scaricare a livello di codice un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0f04e-116">Describes how to programmatically unload an application domain.</span></span>  
  
[<span data-ttu-id="0f04e-117">Procedura: Configurare un dominio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="0f04e-117">How to: Configure an Application Domain</span></span>](how-to-configure-an-application-domain.md)  
<span data-ttu-id="0f04e-118">Viene presentata un'introduzione alla configurazione di un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0f04e-118">Provides an introduction to configuring an application domain.</span></span>  
  
[<span data-ttu-id="0f04e-119">Recupero di informazioni di installazione da un dominio applicazione</span><span class="sxs-lookup"><span data-stu-id="0f04e-119">Retrieving Setup Information from an Application Domain</span></span>](retrieve-setup-information.md)  
<span data-ttu-id="0f04e-120">Viene descritto come recuperare informazioni di installazione da un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0f04e-120">Describes how to retrieve setup information from an application domain.</span></span>  
  
[<span data-ttu-id="0f04e-121">Procedura: Caricare assembly in un dominio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="0f04e-121">How to: Load Assemblies into an Application Domain</span></span>](how-to-load-assemblies-into-an-application-domain.md)  
<span data-ttu-id="0f04e-122">Viene descritto come caricare un assembly in un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0f04e-122">Describes how to load an assembly into an application domain.</span></span>  
  
[<span data-ttu-id="0f04e-123">Procedura: reperire informazioni su tipo e membro da un assembly</span><span class="sxs-lookup"><span data-stu-id="0f04e-123">How to: Obtain Type and Member Information from an Assembly</span></span>](../reflection-and-codedom/get-type-member-information.md)  
<span data-ttu-id="0f04e-124">Viene descritto come recuperare informazioni su un assembly.</span><span class="sxs-lookup"><span data-stu-id="0f04e-124">Describes how to retrieve information about an assembly.</span></span>  
  
[<span data-ttu-id="0f04e-125">Creazione di copie replicate di assembly</span><span class="sxs-lookup"><span data-stu-id="0f04e-125">Shadow Copying Assemblies</span></span>](shadow-copy-assemblies.md)  
<span data-ttu-id="0f04e-126">Viene descritto come la copia shadow consente gli aggiornamenti agli assembly mentre sono in uso e come configurare la copia shadow.</span><span class="sxs-lookup"><span data-stu-id="0f04e-126">Describes how shadow copying allows updates to assemblies while they are in use, and how to configure shadow copying.</span></span>  
  
[<span data-ttu-id="0f04e-127">Procedura: Ricevere notifiche di eccezioni first-chance</span><span class="sxs-lookup"><span data-stu-id="0f04e-127">How to: Receive First-Chance Exception Notifications</span></span>](how-to-receive-first-chance-exception-notifications.md)  
<span data-ttu-id="0f04e-128">Viene spiegato come è possibile ricevere una notifica della generazione di un'eccezione, prima che Common Language Runtime abbia iniziato la ricerca di gestori di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="0f04e-128">Explains how you can receive a notification that an exception has been thrown, before the common language runtime has begun searching for exception handlers.</span></span>  
  
[<span data-ttu-id="0f04e-129">Risoluzione caricamenti assembly</span><span class="sxs-lookup"><span data-stu-id="0f04e-129">Resolving Assembly Loads</span></span>](../../standard/assembly/resolve-loads.md)  
<span data-ttu-id="0f04e-130">Vengono offerte indicazioni sull'uso dell'evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> per risolvere gli errori di caricamento di assembly.</span><span class="sxs-lookup"><span data-stu-id="0f04e-130">Provides guidance on using the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event to resolve assembly load failures.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="0f04e-131">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="0f04e-131">Reference</span></span>  

<xref:System.AppDomain>  
<span data-ttu-id="0f04e-132">Rappresenta un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0f04e-132">Represents an application domain.</span></span> <span data-ttu-id="0f04e-133">Offre metodi per creare e controllare i domini dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0f04e-133">Provides methods for creating and controlling application domains.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0f04e-134">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="0f04e-134">Related Sections</span></span>  
[<span data-ttu-id="0f04e-135">Assembly in .NET</span><span class="sxs-lookup"><span data-stu-id="0f04e-135">Assemblies in .NET</span></span>](../../standard/assembly/index.md)  
<span data-ttu-id="0f04e-136">Viene offerta una panoramica delle funzioni svolte dagli assembly.</span><span class="sxs-lookup"><span data-stu-id="0f04e-136">Provides an overview of the functions performed by assemblies.</span></span>  
  
[<span data-ttu-id="0f04e-137">Programmazione con gli assembly</span><span class="sxs-lookup"><span data-stu-id="0f04e-137">Programming with Assemblies</span></span>](../../standard/assembly/index.md)  
<span data-ttu-id="0f04e-138">Descrive come creare, firmare e impostare attributi sugli assembly.</span><span class="sxs-lookup"><span data-stu-id="0f04e-138">Describes how to create, sign, and set attributes on assemblies.</span></span>  
  
[<span data-ttu-id="0f04e-139">Creazione di assembly e metodi dinamici</span><span class="sxs-lookup"><span data-stu-id="0f04e-139">Emitting Dynamic Methods and Assemblies</span></span>](../reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
<span data-ttu-id="0f04e-140">Descrive come creare gli assembly dinamici.</span><span class="sxs-lookup"><span data-stu-id="0f04e-140">Describes how to create dynamic assemblies.</span></span>  
  
[<span data-ttu-id="0f04e-141">Domini applicazione</span><span class="sxs-lookup"><span data-stu-id="0f04e-141">Application Domains</span></span>](application-domains.md)  
<span data-ttu-id="0f04e-142">Viene fornita una panoramica sui concetti di base relativi ai domini applicazione.</span><span class="sxs-lookup"><span data-stu-id="0f04e-142">Provides a conceptual overview of application domains.</span></span>  
  
[<span data-ttu-id="0f04e-143">Panoramica della reflection</span><span class="sxs-lookup"><span data-stu-id="0f04e-143">Reflection Overview</span></span>](../reflection-and-codedom/reflection.md)  
<span data-ttu-id="0f04e-144">Descrive come usare la classe **Reflection** per ottenere informazioni su un assembly.</span><span class="sxs-lookup"><span data-stu-id="0f04e-144">Describes how to use the **Reflection** class to obtain information about an assembly.</span></span>
