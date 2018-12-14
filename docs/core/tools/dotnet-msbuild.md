---
title: Comando dotnet msbuild - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet msbuild consente di accedere alla riga di comando di MSBuild.
ms.date: 12/03/2018
ms.openlocfilehash: 93471ded9614502ab89d5afb19dd9992f068ef80
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53128047"
---
# <a name="dotnet-msbuild"></a>dotnet msbuild

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>nome

`dotnet msbuild`: consente di compilare un progetto e tutte le relative dipendenze.

## <a name="synopsis"></a>Riepilogo

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a>Description

Il comando `dotnet msbuild` consente di accedere a un'istanza completamente funzionante di MSBuild.

Il comando ha le stesse funzionalità del client della riga di comando di MSBuild esistente solo per il progetto di tipo SDK. Le opzioni sono uguali. Per altre informazioni sulle opzioni disponibili, vedere [Riferimenti alla riga di comando di MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).

Il comando [dotnet build](dotnet-build.md) equivale a `dotnet msbuild -restore -target:Build`. `dotnet build` è più usato per compilare i progetti, ma `dotnet msbuild` consente maggiore controllo. Se ad esempio si vuole eseguire una destinazione specifica (senza eseguire la destinazione di compilazione), probabilmente è preferibile usare `dotnet msbuild`.

## <a name="examples"></a>Esempi

* Compilare un progetto e le relative dipendenze:

  ```console
  dotnet msbuild
  ```

* Compilare un progetto e le relative dipendenze usando la configurazione per il rilascio:

  ```console
  dotnet msbuild -p:Configuration=Release
  ```

* Eseguire la destinazione di pubblicazione e pubblicare per il RID `osx.10.11-x64`:

  ```console
  dotnet msbuild -t:Publish -p:RuntimeIdentifiers=osx.10.11-x64
  ```

* Vedere l'intero progetto con tutte le destinazioni incluse dall'SDK:

  ```console
  dotnet msbuild -pp
  ```