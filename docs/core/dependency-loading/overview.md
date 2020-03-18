---
title: Caricamento delle dipendenze - .NET CoreDependency loading - .NET Core
description: Panoramica del caricamento delle dipendenze gestito e non gestito in .NET CoreOverview of managed and unmanaged dependency loading in .NET Core
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.topic: overview
ms.openlocfilehash: f6b5fc1f92171b61dcab162b782ca7212c602d76
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "73416675"
---
# <a name="dependency-loading-in-net-core"></a><span data-ttu-id="22e23-103">Caricamento delle dipendenze in .NET CoreDependency loading in .NET Core</span><span class="sxs-lookup"><span data-stu-id="22e23-103">Dependency loading in .NET Core</span></span>

<span data-ttu-id="22e23-104">Ogni applicazione .NET Core ha dipendenze.</span><span class="sxs-lookup"><span data-stu-id="22e23-104">Every .NET Core application has dependencies.</span></span> <span data-ttu-id="22e23-105">Anche l'app semplice `hello world` ha dipendenze da parti delle librerie di classi .NET Core.</span><span class="sxs-lookup"><span data-stu-id="22e23-105">Even the simple `hello world` app has dependencies on portions of the .NET Core class libraries.</span></span>

<span data-ttu-id="22e23-106">La comprensione della logica di caricamento di assembly predefiniti .NET Core consente di comprendere e eseguire il debug dei problemi di distribuzione tipici.</span><span class="sxs-lookup"><span data-stu-id="22e23-106">Understanding .NET Core default assembly loading logic can help understanding and debugging typical deployment issues.</span></span>

<span data-ttu-id="22e23-107">In alcune applicazioni, le dipendenze vengono determinate dinamicamente in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="22e23-107">In some applications, dependencies are dynamically determined at runtime.</span></span> <span data-ttu-id="22e23-108">In queste situazioni, è fondamentale comprendere come vengono caricati gli assembly gestiti e le dipendenze non gestite.</span><span class="sxs-lookup"><span data-stu-id="22e23-108">In these situations, it's critical to understand how managed assemblies and unmanaged dependencies are loaded.</span></span>

## <a name="understanding-assemblyloadcontext"></a><span data-ttu-id="22e23-109">Informazioni su AssemblyLoadContext</span><span class="sxs-lookup"><span data-stu-id="22e23-109">Understanding AssemblyLoadContext</span></span>

<span data-ttu-id="22e23-110">L'API <xref:System.Runtime.Loader.AssemblyLoadContext> è fondamentale per la progettazione del caricamento di .NET Core.The API is central to the .NET Core loading design.</span><span class="sxs-lookup"><span data-stu-id="22e23-110">The <xref:System.Runtime.Loader.AssemblyLoadContext> API is central to the .NET Core loading design.</span></span> <span data-ttu-id="22e23-111">L'articolo [Informazioni su AssemblyLoadContext](understanding-assemblyloadcontext.md) fornisce una panoramica concettuale della progettazione.</span><span class="sxs-lookup"><span data-stu-id="22e23-111">The [Understanding AssemblyLoadContext](understanding-assemblyloadcontext.md) article provides a conceptual overview to the design.</span></span>

## <a name="loading-details"></a><span data-ttu-id="22e23-112">Dettagli del caricamento</span><span class="sxs-lookup"><span data-stu-id="22e23-112">Loading details</span></span>

<span data-ttu-id="22e23-113">I dettagli dell'algoritmo di caricamento sono descritti brevemente in diversi articoli:The loading algorithm details are covered briefly in several articles:</span><span class="sxs-lookup"><span data-stu-id="22e23-113">The loading algorithm details are covered briefly in several articles:</span></span>

- [<span data-ttu-id="22e23-114">Algoritmo di caricamento dell'assembly gestito</span><span class="sxs-lookup"><span data-stu-id="22e23-114">Managed assembly loading algorithm</span></span>](loading-managed.md)
- [<span data-ttu-id="22e23-115">Algoritmo di caricamento dell'assembly satellitare</span><span class="sxs-lookup"><span data-stu-id="22e23-115">Satellite assembly loading algorithm</span></span>](loading-resources.md)
- [<span data-ttu-id="22e23-116">Algoritmo di caricamento della libreria non gestita (nativa) Unmanaged (native) library loading algorithm</span><span class="sxs-lookup"><span data-stu-id="22e23-116">Unmanaged (native) library loading algorithm</span></span>](loading-unmanaged.md)
- [<span data-ttu-id="22e23-117">Sondaggio predefinito</span><span class="sxs-lookup"><span data-stu-id="22e23-117">Default probing</span></span>](default-probing.md)

## <a name="create-a-net-core-application-with-plugins"></a><span data-ttu-id="22e23-118">Creare un'applicazione .NET Core con i plug-in</span><span class="sxs-lookup"><span data-stu-id="22e23-118">Create a .NET Core application with plugins</span></span>

<span data-ttu-id="22e23-119">L'esercitazione [Creare un'applicazione .NET Core con i plug-in](../tutorials/creating-app-with-plugin-support.md) viene descritto come creare un AssemblyLoadContext personalizzato.</span><span class="sxs-lookup"><span data-stu-id="22e23-119">The tutorial [Create a .NET Core application with plugins](../tutorials/creating-app-with-plugin-support.md) describes how to create a custom AssemblyLoadContext.</span></span> <span data-ttu-id="22e23-120">Esso utilizza <xref:System.Runtime.Loader.AssemblyDependencyResolver> un per risolvere le dipendenze del plugin.</span><span class="sxs-lookup"><span data-stu-id="22e23-120">It uses an <xref:System.Runtime.Loader.AssemblyDependencyResolver> to resolve the dependencies of the plugin.</span></span> <span data-ttu-id="22e23-121">L'esercitazione isola correttamente le dipendenze del plug-in dall'applicazione host.</span><span class="sxs-lookup"><span data-stu-id="22e23-121">The tutorial correctly isolates the plugin's dependencies from the hosting application.</span></span>

## <a name="how-to-use-and-debug-assembly-unloadability-in-net-core"></a><span data-ttu-id="22e23-122">Come usare ed eseguire il debug di assembly non caricabili in .NET Core</span><span class="sxs-lookup"><span data-stu-id="22e23-122">How to use and debug assembly unloadability in .NET Core</span></span>

<span data-ttu-id="22e23-123">L'articolo Come usare ed eseguire il debug di [unloadability di assembly in .NET Core](../../standard/assembly/unloadability.md) è un'esercitazione dettagliata.</span><span class="sxs-lookup"><span data-stu-id="22e23-123">The [How to use and debug assembly unloadability in .NET Core](../../standard/assembly/unloadability.md) article is a step-by-step tutorial.</span></span> <span data-ttu-id="22e23-124">Viene illustrato come caricare un'applicazione .NET Core, execute e quindi scaricarla.</span><span class="sxs-lookup"><span data-stu-id="22e23-124">It shows how to load a .NET Core application, execute, and then unload it.</span></span> <span data-ttu-id="22e23-125">L'articolo fornisce anche suggerimenti per il debug.</span><span class="sxs-lookup"><span data-stu-id="22e23-125">The article also provides debugging tips.</span></span>
