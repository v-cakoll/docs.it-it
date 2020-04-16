---
title: dotnet nuget abilita il comando source
description: Il comando dotnet nuget enable source abilita un'origine esistente nei file di configurazione NuGet.The dotnet nuget enable source command enables an existing source in your NuGet configuration files.
ms.date: 03/20/2020
ms.openlocfilehash: 38fb5917361bd7952fef9c31ed897fb81f005155
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463552"
---
# <a name="dotnet-nuget-enable-source"></a>dotnet nuget enable source

**Questo articolo si applica a:** ✔️ .NET Core 3.1.200 SDK e versioni successive

## <a name="name"></a>Nome

`dotnet nuget enable source`- Abilitare un'origine NuGet.- Enable a NuGet source.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet nuget enable source <NAME> [--configfile <FILE>]

dotnet nuget enable source -h|--help
```

## <a name="description"></a>Descrizione

Il `dotnet nuget enable source` comando abilita un'origine esistente nei file di configurazione NuGet.The command enables an existing source in your NuGet configuration files.

## <a name="arguments"></a>Argomenti

- **`NAME`**

  Nome dell'origine.

## <a name="options"></a>Opzioni

- **`--configfile <FILE>`**

  Il file di configurazione NuGet. Se specificato, verranno utilizzate solo le impostazioni di questo file. Se non specificato, verrà utilizzata la gerarchia dei file di configurazione dalla directory corrente. Per ulteriori informazioni, vedere [Configurazioni comuni NuGet](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).

## <a name="examples"></a>Esempi

- Abilitare un'origine `mySource`con nome di :

  ```dotnetcli
  dotnet nuget enable source mySource
  ```

## <a name="see-also"></a>Vedere anche

- [Sezioni di origine del pacchetto nei file NuGet.configPackage source sections in NuGet.config files](/nuget/reference/nuget-config-file#package-source-sections)

- [comando sources (nuget.exe)](/nuget/reference/cli-reference/cli-ref-sources)
