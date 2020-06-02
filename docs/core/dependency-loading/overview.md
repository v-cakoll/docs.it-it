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
# <a name="dependency-loading-in-net-core"></a>Caricamento delle dipendenze in .NET Core

Tutte le applicazioni .NET Core hanno dipendenze. Anche l' `hello world` app semplice presenta dipendenze da parti delle librerie di classi .NET Core.

Comprendere la logica di caricamento degli assembly predefiniti di .NET Core consente di comprendere e debugging i tipici problemi di distribuzione.

In alcune applicazioni, le dipendenze vengono determinate in modo dinamico in fase di esecuzione. In queste situazioni è fondamentale comprendere come vengono caricati gli assembly gestiti e le dipendenze non gestite.

## <a name="understanding-assemblyloadcontext"></a>Informazioni su AssemblyLoadContext

L' <xref:System.Runtime.Loader.AssemblyLoadContext> API è fondamentale per la progettazione di caricamento di .NET Core. L'articolo [informazioni su AssemblyLoadContext](understanding-assemblyloadcontext.md) fornisce una panoramica concettuale della progettazione.

## <a name="loading-details"></a>Dettagli del caricamento

I dettagli dell'algoritmo di caricamento sono trattati brevemente in diversi articoli:

- [Algoritmo di caricamento assembly gestito](loading-managed.md)
- [Algoritmo di caricamento degli assembly satellite](loading-resources.md)
- [Algoritmo di caricamento libreria non gestito (nativo)](loading-unmanaged.md)
- [Sondaggio predefinito](default-probing.md)

## <a name="create-a-net-core-application-with-plugins"></a>Creare un'applicazione .NET Core con i plug-in

L'esercitazione [creare un'applicazione .NET Core con i plug](../tutorials/creating-app-with-plugin-support.md) -in descrive come creare un AssemblyLoadContext personalizzato. Usa un <xref:System.Runtime.Loader.AssemblyDependencyResolver> per risolvere le dipendenze del plug-in. L'esercitazione isola correttamente le dipendenze del plug-in dall'applicazione host.

## <a name="how-to-use-and-debug-assembly-unloadability-in-net-core"></a>Come usare ed eseguire il debug di assembly non caricabili in .NET Core

L'articolo [How to use and Debug assembly unloadable in .NET Core](../../standard/assembly/unloadability.md) è un'esercitazione dettagliata. Viene illustrato come caricare un'applicazione .NET Core, eseguirla e scaricarla. Questo articolo fornisce anche suggerimenti sul debug.
