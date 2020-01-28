---
title: Comando dotnet msbuild
description: Il comando dotnet msbuild consente di accedere alla riga di comando di MSBuild.
ms.date: 12/03/2018
ms.openlocfilehash: dae1e9f0ca355166d41c11fbafb80c7c9fb29748
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733192"
---
# <a name="dotnet-msbuild"></a>dotnet msbuild

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>Name

`dotnet msbuild`: consente di compilare un progetto e tutte le relative dipendenze.

## <a name="synopsis"></a>Riepilogo

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a>Descrizione

Il comando `dotnet msbuild` consente di accedere a un'istanza completamente funzionante di MSBuild.

Il comando ha esattamente le stesse funzionalità del client della riga di comando MSBuild esistente solo per i progetti in stile SDK. Le opzioni sono uguali. Per ulteriori informazioni sulle opzioni disponibili, vedere la Guida di [riferimento alla riga di comando di MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).

Il comando [dotnet build](dotnet-build.md) equivale a `dotnet msbuild -restore -target:Build`. la [compilazione DotNet](dotnet-build.md) è più comunemente utilizzata per la compilazione di progetti, ma poiché viene sempre eseguita la destinazione di compilazione, è possibile utilizzare `dotnet msbuild` quando non si desidera compilare il progetto. Se, ad esempio, si dispone di una destinazione specifica che si desidera eseguire senza compilare il progetto, utilizzare `dotnet msbuild` e specificare la destinazione.

## <a name="examples"></a>Esempi

* Compilare un progetto e le relative dipendenze:

  ```dotnetcli
  dotnet msbuild
  ```

* Compilare un progetto e le relative dipendenze usando la configurazione per il rilascio:

  ```dotnetcli
  dotnet msbuild -property:Configuration=Release
  ```

* Eseguire la destinazione di pubblicazione e pubblicare per il RID `osx.10.11-x64`:

  ```dotnetcli
  dotnet msbuild -target:Publish -property:RuntimeIdentifiers=osx.10.11-x64
  ```

* Vedere l'intero progetto con tutte le destinazioni incluse dall'SDK:

  ```dotnetcli
  dotnet msbuild -preprocess
  ```
