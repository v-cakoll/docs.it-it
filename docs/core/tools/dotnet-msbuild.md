---
title: Comando dotnet-msbuild - Interfaccia della riga di comando di .NET Core | Microsoft Docs
description: Il comando dotnet-msbuild consente di accedere alla riga di comando di MSBuild.
keywords: dotnet-msmsbuild, interfaccia della riga di comando, comando dell&quot;interfaccia della riga di comando, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 05/24/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: ffdc40ba-ef33-463e-aa35-b0af1fe615a2
ms.translationtype: Human Translation
ms.sourcegitcommit: df4b2ddd322e4bd2ebaf444439107e88a983f988
ms.openlocfilehash: 2267ef0b5785959456ea443405b6708a423d00ba
ms.contentlocale: it-it
ms.lasthandoff: 05/30/2017

---

<a id="dotnet-msbuild" class="xliff"></a>

# dotnet-msbuild

<a id="name" class="xliff"></a>

## Nome

`dotnet-msbuild`: consente di compilare un progetto e tutte le relative dipendenze.

<a id="synopsis" class="xliff"></a>

## Riepilogo

`dotnet msbuild <msbuild_arguments> [-h]`

<a id="description" class="xliff"></a>

## Descrizione

Il comando `dotnet msbuild` consente di accedere a un'istanza completamente funzionante di MSBuild.

Il comando ha le stesse funzionalità del client della riga di comando di MSBuild esistente. Le opzioni sono uguali. Usare [Riferimenti alla riga di comando di MSBuild](https://docs.microsoft.com/visualstudio/msbuild/msbuild-command-line-reference) per ottenere informazioni sulle opzioni disponibili. 

<a id="examples" class="xliff"></a>

## Esempi

Compilare un progetto e le relative dipendenze:

`dotnet msbuild`

Compilare un progetto e le relative dipendenze usando la configurazione per il rilascio:

`dotnet msbuild /p:Configuration=Release`

Eseguire la destinazione di pubblicazione e pubblicare per il RID `osx.10.11-x64`:

`dotnet msbuild /t:Publish /p:RuntimeIdentifiers=osx.10.11-x64`

Vedere l'intero progetto con tutte le destinazioni incluse dall'SDK:

`dotnet msbuild /pp`
