---
title: comando dotnet nuget list source command
description: Il comando dotnet nuget list source elenca tutte le origini esistenti dai file di configurazione NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: 4d7bc3dbd3ab5eb14c1ebf592044b685d28355cd
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2020
ms.locfileid: "80148575"
---
# <a name="dotnet-nuget-list-source"></a>dotnet nuget list source

**Questo articolo si applica a:** ✔️ .NET Core 3.1.200 SDK e versioni successive

## <a name="name"></a>Nome

`dotnet nuget list source`- Elenca tutte le origini NuGet configurate.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet nuget list source [--format] [--configfile]
dotnet nuget list source [-h|--help]
```

## <a name="description"></a>Descrizione

Il `dotnet nuget list source` comando elenca tutte le origini esistenti dai file di configurazione NuGet.The command lists all existing sources from your NuGet configuration files.

## <a name="options"></a>Opzioni

- **`--configfile`**

  Il file di configurazione NuGet. Se specificato, verranno utilizzate solo le impostazioni di questo file. Se non specificato, verrà utilizzata la gerarchia dei file di configurazione dalla directory corrente. Per ulteriori informazioni, vedere [Configurazioni comuni NuGet](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).

- **`--format`**

  Il formato dell'output `Detailed` del comando elenco: (impostazione predefinita) e `Short`.

## <a name="examples"></a>Esempi

- Elencare le origini configurate dalla directory corrente:

  ```dotnetcli
  dotnet nuget list source
  ```

## <a name="see-also"></a>Vedere anche

- [Sezioni di origine del pacchetto nei file NuGet.configPackage source sections in NuGet.config files](/nuget/reference/nuget-config-file#package-source-sections)

- [comando sources (nuget.exe)](/nuget/reference/cli-reference/cli-ref-sources)
