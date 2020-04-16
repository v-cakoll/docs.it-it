---
title: comando dotnet nuget list source command
description: Il comando dotnet nuget list source elenca tutte le origini esistenti dai file di configurazione NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: 8b14413949bd60ddeed977d19eec9bb99982da70
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463546"
---
# <a name="dotnet-nuget-list-source"></a>dotnet nuget list source

**Questo articolo si applica a:** ✔️ .NET Core 3.1.200 SDK e versioni successive

## <a name="name"></a>Nome

`dotnet nuget list source`- Elenca tutte le origini NuGet configurate.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet nuget list source [--format [Detailed|Short]] [--configfile <FILE>]

dotnet nuget list source -h|--help
```

## <a name="description"></a>Descrizione

Il `dotnet nuget list source` comando elenca tutte le origini esistenti dai file di configurazione NuGet.The command lists all existing sources from your NuGet configuration files.

## <a name="options"></a>Opzioni

- **`--configfile <FILE>`**

  Il file di configurazione NuGet. Se specificato, verranno utilizzate solo le impostazioni di questo file. Se non specificato, verrà utilizzata la gerarchia dei file di configurazione dalla directory corrente. Per ulteriori informazioni, vedere [Configurazioni comuni NuGet](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).

- **`--format [Detailed|Short]`**

  Il formato dell'output `Detailed` del comando elenco: (impostazione predefinita) e `Short`.

## <a name="examples"></a>Esempi

- Elencare le origini configurate dalla directory corrente:

  ```dotnetcli
  dotnet nuget list source
  ```

## <a name="see-also"></a>Vedere anche

- [Sezioni di origine del pacchetto nei file NuGet.configPackage source sections in NuGet.config files](/nuget/reference/nuget-config-file#package-source-sections)

- [comando sources (nuget.exe)](/nuget/reference/cli-reference/cli-ref-sources)
