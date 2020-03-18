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
# <a name="dependency-loading-in-net-core"></a>Caricamento delle dipendenze in .NET CoreDependency loading in .NET Core

Ogni applicazione .NET Core ha dipendenze. Anche l'app semplice `hello world` ha dipendenze da parti delle librerie di classi .NET Core.

La comprensione della logica di caricamento di assembly predefiniti .NET Core consente di comprendere e eseguire il debug dei problemi di distribuzione tipici.

In alcune applicazioni, le dipendenze vengono determinate dinamicamente in fase di esecuzione. In queste situazioni, è fondamentale comprendere come vengono caricati gli assembly gestiti e le dipendenze non gestite.

## <a name="understanding-assemblyloadcontext"></a>Informazioni su AssemblyLoadContext

L'API <xref:System.Runtime.Loader.AssemblyLoadContext> è fondamentale per la progettazione del caricamento di .NET Core.The API is central to the .NET Core loading design. L'articolo [Informazioni su AssemblyLoadContext](understanding-assemblyloadcontext.md) fornisce una panoramica concettuale della progettazione.

## <a name="loading-details"></a>Dettagli del caricamento

I dettagli dell'algoritmo di caricamento sono descritti brevemente in diversi articoli:The loading algorithm details are covered briefly in several articles:

- [Algoritmo di caricamento dell'assembly gestito](loading-managed.md)
- [Algoritmo di caricamento dell'assembly satellitare](loading-resources.md)
- [Algoritmo di caricamento della libreria non gestita (nativa) Unmanaged (native) library loading algorithm](loading-unmanaged.md)
- [Sondaggio predefinito](default-probing.md)

## <a name="create-a-net-core-application-with-plugins"></a>Creare un'applicazione .NET Core con i plug-in

L'esercitazione [Creare un'applicazione .NET Core con i plug-in](../tutorials/creating-app-with-plugin-support.md) viene descritto come creare un AssemblyLoadContext personalizzato. Esso utilizza <xref:System.Runtime.Loader.AssemblyDependencyResolver> un per risolvere le dipendenze del plugin. L'esercitazione isola correttamente le dipendenze del plug-in dall'applicazione host.

## <a name="how-to-use-and-debug-assembly-unloadability-in-net-core"></a>Come usare ed eseguire il debug di assembly non caricabili in .NET Core

L'articolo Come usare ed eseguire il debug di [unloadability di assembly in .NET Core](../../standard/assembly/unloadability.md) è un'esercitazione dettagliata. Viene illustrato come caricare un'applicazione .NET Core, execute e quindi scaricarla. L'articolo fornisce anche suggerimenti per il debug.
