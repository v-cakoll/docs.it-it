---
title: comando dotnet nuget aggiungere il comando source
description: Il comando dotnet nuget add source aggiunge una nuova origine del pacchetto ai file di configurazione NuGet.The dotnet nuget add source command adds a new package source to your NuGet configuration files.
ms.date: 03/20/2020
ms.openlocfilehash: c1e398699c7482a69b750cde718e6f9178b5c4bd
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2020
ms.locfileid: "80148568"
---
# <a name="dotnet-nuget-add-source"></a>dotnet nuget add source

**Questo articolo si applica a:** ✔️ .NET Core 3.1.200 SDK e versioni successive

## <a name="name"></a>Nome

`dotnet nuget add source`- Aggiungere un'origine NuGet.- Add a NuGet source.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet nuget add source <PACKAGE_SOURCE_PATH> [--name] [--username]
    [--password] [--store-password-in-clear-text] [--valid-authentication-types]
    [--configfile]
dotnet nuget add source [-h|--help]
```

## <a name="description"></a>Descrizione

Il `dotnet nuget add source` comando aggiunge una nuova origine del pacchetto ai file di configurazione NuGet.The command adds a new package source to your NuGet configuration files.

## <a name="arguments"></a>Argomenti

- **`PACKAGE_SOURCE_PATH`**

  Percorso dell'origine del pacchetto.

## <a name="options"></a>Opzioni

- **`--configfile`**

  Il file di configurazione NuGet. Se specificato, verranno utilizzate solo le impostazioni di questo file. Se non specificato, verrà utilizzata la gerarchia dei file di configurazione dalla directory corrente. Per ulteriori informazioni, vedere [Configurazioni comuni NuGet](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).

- **`-n|--name`**

  Nome dell'origine.

- **`-p|--password`**

  Password da utilizzare per la connessione a un'origine autenticata.

- **`--store-password-in-clear-text`**

  Consente di archiviare le credenziali di origine del pacchetto portabile disabilitando la crittografia della password.

- **`-u|--username`**

  Nome utente da utilizzare per la connessione a un'origine autenticata.

- **`--valid-authentication-types`**

  Elenco delimitato da virgole di tipi di autenticazione validi per questa origine. Impostare `basic` questa opzione su se il server annuncia NTLM o Negotiate e le credenziali devono essere inviate usando il meccanismo di base, ad esempio quando si usa un PAT con il server DevOps di Azure locale. Altri valori `negotiate`validi `kerberos` `ntlm`includono `digest`, , e , ma è improbabile che questi valori siano utili.

## <a name="examples"></a>Esempi

- Aggiungi `nuget.org` come origine:

  ```dotnetcli
  dotnet nuget add source https://api.nuget.org/v3/index.json -n nuget.org
  ```

- Aggiungi `c:\packages` come origine locale:

  ```dotnetcli
  dotnet nuget add source c:\packages
  ```

- Aggiungere un'origine che richiede l'autenticazione:Add a source that needs authentication:

  ```dotnetcli
  dotnet nuget add source https://someServer/myTeam -n myTeam -u myUsername -p myPassword --store-password-in-clear-text
  ```

- Aggiungere un'origine che richiede l'autenticazione (quindi installare il provider di credenziali:Add a source that needs authentication (then go install credential provider):

  ```dotnetcli
  dotnet nuget add source https://azureartifacts.microsoft.com/myTeam -n myTeam
  ```

## <a name="see-also"></a>Vedere anche

- [Sezioni di origine del pacchetto nei file NuGet.configPackage source sections in NuGet.config files](/nuget/reference/nuget-config-file#package-source-sections)

- [comando sources (nuget.exe)](/nuget/reference/cli-reference/cli-ref-sources)
