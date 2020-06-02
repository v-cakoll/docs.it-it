---
title: Caricamento delle dipendenze-.NET Core
description: Panoramica del caricamento di dipendenze gestite e non gestite in .NET Core
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.topic: overview
ms.openlocfilehash: 34deb802183f20cc92449c21eb7e149cc002850f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84284222"
---
# <a name="dependency-loading-in-net-core"></a><span data-ttu-id="0ebeb-103">Caricamento delle dipendenze in .NET Core</span><span class="sxs-lookup"><span data-stu-id="0ebeb-103">Dependency loading in .NET Core</span></span>

<span data-ttu-id="0ebeb-104">Tutte le applicazioni .NET Core hanno dipendenze.</span><span class="sxs-lookup"><span data-stu-id="0ebeb-104">Every .NET Core application has dependencies.</span></span> <span data-ttu-id="0ebeb-105">Anche l' `hello world` app semplice presenta dipendenze da parti delle librerie di classi .NET Core.</span><span class="sxs-lookup"><span data-stu-id="0ebeb-105">Even the simple `hello world` app has dependencies on portions of the .NET Core class libraries.</span></span>

<span data-ttu-id="0ebeb-106">Comprendere la logica di caricamento degli assembly predefiniti di .NET Core consente di comprendere e debugging i tipici problemi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="0ebeb-106">Understanding .NET Core default assembly loading logic can help understanding and debugging typical deployment issues.</span></span>

<span data-ttu-id="0ebeb-107">In alcune applicazioni, le dipendenze vengono determinate in modo dinamico in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0ebeb-107">In some applications, dependencies are dynamically determined at run time.</span></span> <span data-ttu-id="0ebeb-108">In queste situazioni è fondamentale comprendere come vengono caricati gli assembly gestiti e le dipendenze non gestite.</span><span class="sxs-lookup"><span data-stu-id="0ebeb-108">In these situations, it's critical to understand how managed assemblies and unmanaged dependencies are loaded.</span></span>

## <a name="understanding-assemblyloadcontext"></a><span data-ttu-id="0ebeb-109">Informazioni su AssemblyLoadContext</span><span class="sxs-lookup"><span data-stu-id="0ebeb-109">Understanding AssemblyLoadContext</span></span>

<span data-ttu-id="0ebeb-110">L' <xref:System.Runtime.Loader.AssemblyLoadContext> API è fondamentale per la progettazione di caricamento di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="0ebeb-110">The <xref:System.Runtime.Loader.AssemblyLoadContext> API is central to the .NET Core loading design.</span></span> <span data-ttu-id="0ebeb-111">L'articolo [informazioni su AssemblyLoadContext](understanding-assemblyloadcontext.md) fornisce una panoramica concettuale della progettazione.</span><span class="sxs-lookup"><span data-stu-id="0ebeb-111">The [Understanding AssemblyLoadContext](understanding-assemblyloadcontext.md) article provides a conceptual overview to the design.</span></span>

## <a name="loading-details"></a><span data-ttu-id="0ebeb-112">Dettagli del caricamento</span><span class="sxs-lookup"><span data-stu-id="0ebeb-112">Loading details</span></span>

<span data-ttu-id="0ebeb-113">I dettagli dell'algoritmo di caricamento sono trattati brevemente in diversi articoli:</span><span class="sxs-lookup"><span data-stu-id="0ebeb-113">The loading algorithm details are covered briefly in several articles:</span></span>

- [<span data-ttu-id="0ebeb-114">Algoritmo di caricamento assembly gestito</span><span class="sxs-lookup"><span data-stu-id="0ebeb-114">Managed assembly loading algorithm</span></span>](loading-managed.md)
- [<span data-ttu-id="0ebeb-115">Algoritmo di caricamento degli assembly satellite</span><span class="sxs-lookup"><span data-stu-id="0ebeb-115">Satellite assembly loading algorithm</span></span>](loading-resources.md)
- [<span data-ttu-id="0ebeb-116">Algoritmo di caricamento libreria non gestito (nativo)</span><span class="sxs-lookup"><span data-stu-id="0ebeb-116">Unmanaged (native) library loading algorithm</span></span>](loading-unmanaged.md)
- [<span data-ttu-id="0ebeb-117">Sondaggio predefinito</span><span class="sxs-lookup"><span data-stu-id="0ebeb-117">Default probing</span></span>](default-probing.md)

## <a name="create-a-net-core-application-with-plugins"></a><span data-ttu-id="0ebeb-118">Creare un'applicazione .NET Core con i plug-in</span><span class="sxs-lookup"><span data-stu-id="0ebeb-118">Create a .NET Core application with plugins</span></span>

<span data-ttu-id="0ebeb-119">L'esercitazione [creare un'applicazione .NET Core con i plug](../tutorials/creating-app-with-plugin-support.md) -in descrive come creare un AssemblyLoadContext personalizzato.</span><span class="sxs-lookup"><span data-stu-id="0ebeb-119">The tutorial [Create a .NET Core application with plugins](../tutorials/creating-app-with-plugin-support.md) describes how to create a custom AssemblyLoadContext.</span></span> <span data-ttu-id="0ebeb-120">Usa un <xref:System.Runtime.Loader.AssemblyDependencyResolver> per risolvere le dipendenze del plug-in.</span><span class="sxs-lookup"><span data-stu-id="0ebeb-120">It uses an <xref:System.Runtime.Loader.AssemblyDependencyResolver> to resolve the dependencies of the plugin.</span></span> <span data-ttu-id="0ebeb-121">L'esercitazione isola correttamente le dipendenze del plug-in dall'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="0ebeb-121">The tutorial correctly isolates the plugin's dependencies from the hosting application.</span></span>

## <a name="how-to-use-and-debug-assembly-unloadability-in-net-core"></a><span data-ttu-id="0ebeb-122">Come usare ed eseguire il debug di assembly non caricabili in .NET Core</span><span class="sxs-lookup"><span data-stu-id="0ebeb-122">How to use and debug assembly unloadability in .NET Core</span></span>

<span data-ttu-id="0ebeb-123">L'articolo [How to use and Debug assembly unloadable in .NET Core](../../standard/assembly/unloadability.md) è un'esercitazione dettagliata.</span><span class="sxs-lookup"><span data-stu-id="0ebeb-123">The [How to use and debug assembly unloadability in .NET Core](../../standard/assembly/unloadability.md) article is a step-by-step tutorial.</span></span> <span data-ttu-id="0ebeb-124">Viene illustrato come caricare un'applicazione .NET Core, eseguirla e scaricarla.</span><span class="sxs-lookup"><span data-stu-id="0ebeb-124">It shows how to load a .NET Core application, execute, and then unload it.</span></span> <span data-ttu-id="0ebeb-125">Questo articolo fornisce anche suggerimenti sul debug.</span><span class="sxs-lookup"><span data-stu-id="0ebeb-125">The article also provides debugging tips.</span></span>
