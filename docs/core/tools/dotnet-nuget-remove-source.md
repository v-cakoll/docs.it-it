---
title: dotnet nuget rimuovere il comando di origine
description: Il comando dotnet nuget remove source rimuove un'origine esistente dai file di configurazione NuGet.The dotnet nuget remove source command removes an existing source from your NuGet configuration files.
ms.date: 03/20/2020
ms.openlocfilehash: b259873e1885644b272136fa31414410bdfd9f27
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463496"
---
# <a name="dotnet-nuget-remove-source"></a>dotnet nuget remove source

**Questo articolo si applica a:** ✔️ .NET Core 3.1.200 SDK e versioni successive

## <a name="name"></a>Nome

`dotnet nuget remove source`- Rimuovere un'origine NuGet.- Remove a NuGet source.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet nuget remove source <NAME> [--configfile <FILE>]

dotnet nuget remove source -h|--help
```

## <a name="description"></a>Descrizione

Il `dotnet nuget remove source` comando rimuove un'origine esistente dai file di configurazione NuGet.The command removes an existing source from your NuGet configuration files.

## <a name="arguments"></a>Argomenti

- **`NAME`**

  Nome dell'origine.

## <a name="options"></a>Opzioni

- **`--configfile`**

  Il file di configurazione NuGet. Se specificato, verranno utilizzate solo le impostazioni di questo file. Se non specificato, verrà utilizzata la gerarchia dei file di configurazione dalla directory corrente. Per ulteriori informazioni, vedere [Configurazioni comuni NuGet](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).

## <a name="examples"></a>Esempi

- Rimuovere un'origine `mySource`con il nome di :

  ```dotnetcli
  dotnet nuget remove source mySource
  ```

## <a name="see-also"></a>Vedere anche

- [Sezioni di origine del pacchetto nei file NuGet.configPackage source sections in NuGet.config files](/nuget/reference/nuget-config-file#package-source-sections)

- [comando sources (nuget.exe)](/nuget/reference/cli-reference/cli-ref-sources)
