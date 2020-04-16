---
title: comando dotnet nuget aggiungere il comando source
description: Il comando dotnet nuget add source aggiunge una nuova origine del pacchetto ai file di configurazione NuGet.The dotnet nuget add source command adds a new package source to your NuGet configuration files.
ms.date: 03/20/2020
ms.openlocfilehash: 319501e026f1c3102006b0be5357f127b8e366a7
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463598"
---
# <a name="dotnet-nuget-add-source"></a>dotnet nuget add source

**Questo articolo si applica a:** ✔️ .NET Core 3.1.200 SDK e versioni successive

## <a name="name"></a>Nome

`dotnet nuget add source`- Aggiungere un'origine NuGet.- Add a NuGet source.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet nuget add source <PACKAGE_SOURCE_PATH> [--name <SOURCE_NAME>] [--username <USER>]
    [--password <PASSWORD>] [--store-password-in-clear-text]
    [--valid-authentication-types <TYPES>] [--configfile <FILE>]

dotnet nuget add source -h|--help
```

## <a name="description"></a>Descrizione

Il `dotnet nuget add source` comando aggiunge una nuova origine del pacchetto ai file di configurazione NuGet.The command adds a new package source to your NuGet configuration files.

## <a name="arguments"></a>Argomenti

- **`PACKAGE_SOURCE_PATH`**

  Percorso dell'origine del pacchetto.

## <a name="options"></a>Opzioni

- **`--configfile <FILE>`**

  Il file di configurazione NuGet. Se specificato, verranno utilizzate solo le impostazioni di questo file. Se non specificato, verrà utilizzata la gerarchia dei file di configurazione dalla directory corrente. Per ulteriori informazioni, vedere [Configurazioni comuni NuGet](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).

- **`-n|--name <SOURCE_NAME>`**

  Nome dell'origine.

- **`-p|--password <PASSWORD>`**

  Password da utilizzare per la connessione a un'origine autenticata.

- **`--store-password-in-clear-text`**

  Consente di archiviare le credenziali di origine del pacchetto portabile disabilitando la crittografia della password.

- **`-u|--username <USER>`**

  Nome utente da utilizzare per la connessione a un'origine autenticata.

- **`--valid-authentication-types <TYPES>`**

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
