---
title: dotnet nuget disable source comando
description: Il comando dotnet nuget disable source disabilita un'origine esistente nei file di configurazione NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: 54acb40b1944eaff347107e8f3439578ec8e0f3c
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463577"
---
# <a name="dotnet-nuget-disable-source"></a>dotnet nuget disable source

**Questo articolo si applica a:** ✔️ .NET Core 3.1.200 SDK e versioni successive

## <a name="name"></a>Nome

`dotnet nuget disable source`- Disabilitare un'origine NuGet.- Disable a NuGet source.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet nuget disable source <NAME> [--configfile <FILE>]

dotnet nuget disable source -h|--help
```

## <a name="description"></a>Descrizione

Il `dotnet nuget disable source` comando disabilita un'origine esistente nei file di configurazione NuGet.The command disables an existing source in your NuGet configuration files.

## <a name="arguments"></a>Argomenti

- **`NAME`**

  Nome dell'origine.

## <a name="options"></a>Opzioni

- **`--configfile <FILE>`**

  Il file di configurazione NuGet. Se specificato, verranno utilizzate solo le impostazioni di questo file. Se non specificato, verrà utilizzata la gerarchia dei file di configurazione dalla directory corrente. Per ulteriori informazioni, vedere [Configurazioni comuni NuGet](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).

## <a name="examples"></a>Esempi

- Disabilitare un'origine `mySource`con il nome di :

  ```dotnetcli
  dotnet nuget disable source mySource
  ```

## <a name="see-also"></a>Vedere anche

- [Sezioni di origine del pacchetto nei file NuGet.configPackage source sections in NuGet.config files](/nuget/reference/nuget-config-file#package-source-sections)

- [comando sources (nuget.exe)](/nuget/reference/cli-reference/cli-ref-sources)
