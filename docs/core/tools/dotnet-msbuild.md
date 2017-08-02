---
title: Comando dotnet-msbuild - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet-msbuild consente di accedere alla riga di comando di MSBuild.
keywords: dotnet-msmsbuild, interfaccia della riga di comando, comando dell'interfaccia della riga di comando, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 05/24/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: ffdc40ba-ef33-463e-aa35-b0af1fe615a2
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1f02dcd779b9ed249ebd2fedb973383b1dcd8963
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-msbuild"></a>dotnet-msbuild

## <a name="name"></a>Nome

`dotnet-msbuild`: consente di compilare un progetto e tutte le relative dipendenze.

## <a name="synopsis"></a>Riepilogo

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a>Descrizione

Il comando `dotnet msbuild` consente di accedere a un'istanza completamente funzionante di MSBuild.

Il comando ha le stesse funzionalità del client della riga di comando di MSBuild esistente. Le opzioni sono uguali. Usare [Riferimenti alla riga di comando di MSBuild](/visualstudio/msbuild/msbuild-command-line-reference) per ottenere informazioni sulle opzioni disponibili. 

## <a name="examples"></a>Esempi

Compilare un progetto e le relative dipendenze:

`dotnet msbuild`

Compilare un progetto e le relative dipendenze usando la configurazione per il rilascio:

`dotnet msbuild /p:Configuration=Release`

Eseguire la destinazione di pubblicazione e pubblicare per il RID `osx.10.11-x64`:

`dotnet msbuild /t:Publish /p:RuntimeIdentifiers=osx.10.11-x64`

Vedere l'intero progetto con tutte le destinazioni incluse dall'SDK:

`dotnet msbuild /pp`

