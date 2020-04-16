---
title: Comando dotnet msbuild
description: Il comando dotnet msbuild consente di accedere alla riga di comando di MSBuild.
ms.date: 02/14/2020
ms.openlocfilehash: 88e85868e2d7de564b2e4c90ce6e78bde4cb350e
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463618"
---
# <a name="dotnet-msbuild"></a>dotnet msbuild

**Questo articolo si applica a:** ✔️ .NET Core 2.x SDK e versioni successive

## <a name="name"></a>Nome

`dotnet msbuild`: consente di compilare un progetto e tutte le relative dipendenze.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet msbuild <MSBUILD_ARGUMENTS>

dotnet msbuild -h
```

## <a name="description"></a>Descrizione

Il comando `dotnet msbuild` consente di accedere a un'istanza completamente funzionante di MSBuild.

Il comando ha esattamente le stesse funzionalità del client della riga di comando MSBuild esistente solo per i progetti in stile SDK. Le opzioni sono uguali. Per ulteriori informazioni sulle opzioni disponibili, vedere le informazioni di [riferimento sulla riga di comando MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).

Il comando [dotnet build](dotnet-build.md) equivale a `dotnet msbuild -restore -target:Build`. [dotnet build](dotnet-build.md) è più comunemente usato per la compilazione di `dotnet msbuild` progetti, ma poiché esegue sempre la destinazione di compilazione, è possibile utilizzare quando non si desidera compilare il progetto. Ad esempio, se si dispone di una destinazione specifica `dotnet msbuild` che si desidera eseguire senza compilare il progetto, utilizzare e specificare la destinazione.

## <a name="examples"></a>Esempi

- Compilare un progetto e le relative dipendenze:

  ```dotnetcli
  dotnet msbuild
  ```

- Compilare un progetto e le relative dipendenze usando la configurazione per il rilascio:

  ```dotnetcli
  dotnet msbuild -property:Configuration=Release
  ```

- Eseguire la destinazione di pubblicazione e pubblicare per il RID `osx.10.11-x64`:

  ```dotnetcli
  dotnet msbuild -target:Publish -property:RuntimeIdentifiers=osx.10.11-x64
  ```

- Vedere l'intero progetto con tutte le destinazioni incluse dall'SDK:

  ```dotnetcli
  dotnet msbuild -preprocess
  ```
