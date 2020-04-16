---
title: comando dotnet nuget update source (comando)
description: Il comando dotnet nuget update source aggiorna un'origine esistente nei file di configurazione NuGet.The dotnet nuget update source command updates an existing source in your NuGet configuration files.
ms.date: 03/20/2020
ms.openlocfilehash: 42b1aec95cdd57e53f966400f6692a3d0150c16c
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463482"
---
# <a name="dotnet-nuget-update-source"></a>dotnet nuget update source

**Questo articolo si applica a:** ✔️ .NET Core 3.1.200 SDK e versioni successive

## <a name="name"></a>Nome

`dotnet nuget update source`- Aggiornare un'origine NuGet.- Update a NuGet source.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet nuget update source <NAME> [--source <SOURCE>] [--username <USER>]
    [--password <PASSWORD>] [--store-password-in-clear-text]
    [--valid-authentication-types <TYPES>] [--configfile <FILE>]

dotnet nuget update source -h|--help
```

## <a name="description"></a>Descrizione

Il `dotnet nuget update source` comando aggiorna un'origine esistente nei file di configurazione Di NuGet.The command updates an existing source in your NuGet configuration files.

## <a name="arguments"></a>Argomenti

- **`NAME`**

  Nome dell'origine.

## <a name="options"></a>Opzioni

- **`--configfile <FILE>`**

  Il file di configurazione NuGet. Se specificato, verranno utilizzate solo le impostazioni di questo file. Se non specificato, verrà utilizzata la gerarchia dei file di configurazione dalla directory corrente. Per ulteriori informazioni, vedere [Configurazioni comuni NuGet](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).

- **`-p|--password <PASSWORD>`**

  Password da utilizzare per la connessione a un'origine autenticata.

- **`-s|--source <SOURCE>`**

  Percorso dell'origine del pacchetto.

- **`--store-password-in-clear-text`**

  Consente di archiviare le credenziali di origine del pacchetto portabile disabilitando la crittografia della password.

- **`-u|--username <USER>`**

  Nome utente da utilizzare per la connessione a un'origine autenticata.

- **`--valid-authentication-types <TYPES>`**

  Elenco delimitato da virgole di tipi di autenticazione validi per questa origine. Impostare `basic` questa opzione su se il server annuncia NTLM o Negotiate e le credenziali devono essere inviate usando il meccanismo di base, ad esempio quando si usa un PAT con il server DevOps di Azure locale. Altri valori `negotiate`validi `kerberos` `ntlm`includono `digest`, , e , ma è improbabile che questi valori siano utili.

## <a name="examples"></a>Esempi

- Aggiornare un'origine `mySource`con il nome di :

  ```dotnetcli
  dotnet nuget update source mySource --source c:\packages
  ```

## <a name="see-also"></a>Vedere anche

- [Sezioni di origine del pacchetto nei file NuGet.configPackage source sections in NuGet.config files](/nuget/reference/nuget-config-file#package-source-sections)

- [comando sources (nuget.exe)](/nuget/reference/cli-reference/cli-ref-sources)
